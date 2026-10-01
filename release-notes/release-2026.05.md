# Release 2026.05

This release note lists the current software and service versions for White Label instances of Make, plus app updates and deprecations since the previous release.

## Current software version numbers

The following is a list of current software versions running in Make's release environment.&#x20;

#### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.35           | -              |

#### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.17          | -              |
| Redis         | v6.2.20        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 8.19.13        | -              |

#### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7.1       | -              |
| Erlang   | 26.2.5.19      | Yes            |

#### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

## Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to **Administration** > **Monitoring**.&#x20;

| Service                | Version                                  | Version update |
| ---------------------- | ---------------------------------------- | -------------- |
| accman                 | 3b16ba3787aa67ed5fe43b5e8be80dd41c96313d | Yes            |
| agency                 | 4.0-beta                                 | -              |
| aws-rds-log-reader     | v1.1.1                                   | -              |
| broker                 | 79ac0c1c03dfbc83bf4cdf398de3627ff60f808f | Yes            |
| broker-gw-logger       | 79ac0c1c03dfbc83bf4cdf398de3627ff60f808f | Yes            |
| cron                   | v1.1.6                                   | -              |
| datadog-agent          | 7.75.0                                   | -              |
| datadog-cluster-agent  | 7.75.0                                   | -              |
| db-updater             | 47d15ffb2b1174354ea3106f3d3abdd5c7d2c2cf | Yes            |
| emails-processor       | b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3 | -              |
| engine                 | de61b0a-20260911                         | Yes            |
| execution-controller   | 68226f10fa0a2cbeba6158ff8c0864e668edfd04 | Yes            |
| gateway                | 9551474c991853af6d3669710a2a61d8ee32a4cd | Yes            |
| imt-auditman           | 99be5118c84ada0b7b9dde6e054cfd4b0db9ee54 | Yes            |
| ipm-server             | 3.71.1                                   | Yes            |
| ipm-service            | 7d7dff9d425509b34e6e1f22ccee00729c350442 | Yes            |
| kibana                 | 8.19.13                                  | -              |
| lickman                | a11cbe0e852dae1deed2e9fbd8e2dc47b6a943fd | Yes            |
| make-apps-processor    | 1.9.0                                    | -              |
| mongo-auto-indexer     | master                                   | -              |
| nginx                  | v1.28.0                                  | -              |
| notification-processor | 8eb4dd8ce1ba30f7d7493cd8642f698da02df82a | Yes            |
| overseer               | f56f1361696d120526e27863bf80152035338591 | Yes            |
| renderer-processor     | cf620604b0b9fb0673999fce0e7a6692230a8c1f | Yes            |
| roleman                | b359d7fb7722d528be6b3094108ddb68b8bbd952 | Yes            |
| scheduler              | 823cde9-20260910                         | -              |
| trackman               | 2.27.0                                   | -              |
| trigger                | e016362fe8fc23f221d99b8c044aedd8a37e61d3 | Yes            |
| web-api                | f1db70059a1dcaa33e5d7d4fae926b3948d4edaf | Yes            |
| web-streamer           | 81e5b1e88ea29eecc1e75ca7856dc638c6fc8cd6 | Yes            |
| web-zone               | 9ea09a62c1837cc1021108106060da881a935c14 | Yes            |
| zone-assets-server     | 9ea09a62c1837cc1021108106060da881a935c14 | Yes            |

## Public-facing changes

This section includes updates, fixes, and deprecations since the previous release.

### Engine worker architecture change: one worker per pod

{% hint style="warning" %}
This is a breaking change for on-premises and self-hosted deployments only.&#x20;
{% endhint %}

Each Engine pod now runs one worker. To scale capacity, increase the number of Kubernetes replicas for the Engine deployment. This change is already live on the public cloud. On-premises and self-hosted deployments must update their configuration.

#### **What's changing**

Previously, an Engine pod could run several worker processes (Node.js processes) side by side. The `sizeOfWorkersPool` config parameter (Helm value `SIZE_OF_WORKER_POOL`, default `10`) controlled how many.

Now, every pod runs one worker. The `sizeOfWorkersPool` parameter and `SIZE_OF_WORKER_POOL` value no longer have any effect.

#### **Why it's changing**

Scenarios running in the same pod shared memory. If one scenario ran the pod out of memory (OOM), Kubernetes killed the pod and every other scenario running in it, regardless of tenant.

With one worker per pod, a misbehaving scenario affects only its own pod. Other scenarios keep running.

#### **Impact if you don't act**

Your deployment keeps running, but with less capacity. For example, if you ran 10 workers per pod across N pods, your capacity drops to one-tenth of what it was until you increase your replica count.

#### **What you need to do**

1. Remove `sizeOfWorkersPool` and `SIZE_OF_WORKER_POOL` from your config. If you leave the parameter at its old default, the worker logs a warning at boot until you resize your replica count.
2. Set your replica count. To keep the same total capacity, multiply your previous workers per pod by your pod count. For example, if you ran 10 workers per pod across N pods, set `10 × N` replicas.
3. Set memory requests and limits for a single worker. Each pod no longer shares memory across several workers, so base the values on one worker's footprint.
   * **Request:** We recommend  `400Mi`, which is a stable baseline for most scenario executions. `200Mi` is likely enough as a minimum, but monitor for OOM kills before you rely on it.
   * **Limit:** A limit is optional and depends on your available compute capacity. If you set one, we recommend staying at or below `8Gi` per pod. Large scenario executions (large scenarios or large payloads) can cause memory spikes at or above that size. The headroom you need depends on tenant behavior.

#### **Rollback**

You can't roll back to multi-worker pods. We removed `sizeOfWorkersPool` and `SIZE_OF_WORKER_POOL` from the codebase. To increase throughput, add replicas.

### Aircall

Due to Aircall deprecating its User V1 APIs and events, we've updated the Aircall app on Make to use their latest V2 endpoints. This change affects several modules and requires you to update your scenarios.

#### Action required by September 30, 2026 <a href="#action-required-by-september-30-2026" id="action-required-by-september-30-2026"></a>

After this date, scenarios using the deprecated modules and webhooks will stop working. You can no longer create new scenarios using the deprecated Search Users' Availability module.

#### What's changing? <a href="#whats-changing" id="whats-changing"></a>

* The **Get a User** and **Search Users** modules have been migrated to Aircall’s V2 API.
* The **Watch Users** webhook trigger now uses Aircall's V2 events.
* The availability data field has been removed from the output of the **Get a User** and **Search Users** modules, as it is not supported in Aircall's V2 API.
* The numbers data array is no longer included in the output of the **Watch Users** trigger for V2 events.
* Existing scenarios using the older module versions will continue to run until September 30, 2026, to give you time to migrate.

#### What you need to do <a href="#what-you-need-to-do" id="what-you-need-to-do"></a>

To keep your scenarios running, you must update your Aircall scenarios before September 30, 2026.

1. **Step 1:** Identify all scenarios using the **Get a User**, **Search Users**, or **Watch Users** modules.
2. **Step 2:** For scenarios using the **Watch Users** trigger, open the module settings and re-select the user events you want to watch. This action will automatically update the webhook to use the new V2 events.
3. **Step 3:** Review any downstream modules that map the availability or numbers fields from the affected Aircall modules. You must remove or update these mappings, as these fields will no longer provide data.

#### Deprecated items <a href="#deprecated-items" id="deprecated-items"></a>

| Deprecated Item                   | Module(s) Affected         | Replacement           |
| --------------------------------- | -------------------------- | --------------------- |
| Search Users' Availability module | Search Users' Availability | No direct replacement |
| availability field                | Get a User, Search Users   | No direct replacement |
| numbers array                     | Watch Users                | No direct replacement |

***

### Amazon Seller Central

Due to upcoming changes in the Amazon Seller Central API, we have updated our Amazon Seller Central app with new modules for managing orders. The old modules, based on the Orders v0 API, will be retired on March 27, 2027.

#### What's changing? <a href="#whats-changing" id="whats-changing"></a>

* We have released three new modules to replace the old ones: **Watch orders**, **Search orders**, and **Get an order**.
* The older order-related modules are now marked as **(deprecated)** and have been moved to the "Other" group in the app.
* Existing scenarios using the deprecated modules will continue to run until March 27, 2027.
* You can no longer create new scenarios using the deprecated modules.

#### What do you need to do? <a href="#what-do-you-need-to-do" id="what-do-you-need-to-do"></a>

To keep your scenarios running, you must replace the deprecated modules with their new equivalents in all of your Amazon Seller Central scenarios before **March 27, 2027**.

#### Module migration guide <a href="#module-migration-guide" id="module-migration-guide"></a>

| Deprecated module                     | Module to use         | Required filter/Note                                                                                  |
| ------------------------------------- | --------------------- | ----------------------------------------------------------------------------------------------------- |
| **Get an order (deprecated)**         | Get an order          | -                                                                                                     |
| **Search orders (deprecated)**        | Search orders         | -                                                                                                     |
| **Watch new orders (deprecated)**     | Watch orders          | In the module settings, set the **Trigger on** field to New orders.                                   |
| **Watch orders updates (deprecated)** | Watch orders          | In the module settings, set the **Trigger on** field to Updated orders.                               |
| **List order lines (deprecated)**     | No direct replacement | Order items are now included in the output of the new **Get an order** and **Search orders** modules. |

#### Resources <a href="#resources" id="resources"></a>

* [Amazon Seller Central documentation — Help Center](https://apps.make.com/amazon-seller-central)
* [Amazon SP-API Deprecations Documentation](https://developer-docs.amazon.com/sp-api/docs/sp-api-deprecations)

***

### Anthropic Claude (Claude)

* Claude Fable 5.1 is now available (Make AI Agent (New), Make AI Toolkit, MCP Client, Anthropic Claude apps), with up to a 1M-token context window and up to 128,000 output tokens.
* Opus 5, Opus 4.8, Opus 4.7, Opus 4.6, Opus 4.5, and Fable 5 are temporarily disabled due to a model provider update; affected scenarios fail until restored.

For more information, see [Anthropic (Claude) documentation](https://apps.make.com/anthropic-claude).

***

### AWS Bedrock (Amazon Bedrock)

The Simple Text Prompt and Create a Message modules now support Anthropic's Claude Fable 5.1 model.

***

### Atera

* Fixed a connection failure for newer Atera API tokens.
* Invalid/expired API key errors now show a clear "\[401] Invalid API Key" message instead of a generic error.

***

### Bitrix24

The Create a Lead module no longer creates empty leads; all mapped data (name, email, phone) is now included.

***

### Brevo

Category-type contact attributes (for example, language codes) use a new value format. Re-select affected attribute values in Create/Update a Contact, or Brevo drops the category data (scenarios keep running).

***

### Calendly

We've updated the Calendly app with over a dozen new modules based on Calendly's latest Scheduling and Event Type Management APIs. You can now programmatically book meetings, manage event types and availability schedules, and track no-shows—all within your Make scenarios.

#### New modules

**Scheduling**

* **Create an event invitee**: Programmatically book a meeting on behalf of an invitee without redirects. _Requires a paid Calendly plan._
* **List event type available times**: Find available time slots for a specific event type within a 7-day window.

**Event Types**

* **Create an event type**: Create new one-on-one event types.
* **Update an event type**: Modify the settings of an existing event type.
* **List event type availability schedules**: Get the availability schedules linked to an event type.
* **Update event type availability schedule**: Replace all availability rules for an event type's schedule.

**User Availability**

* **List user availability schedules**: Retrieve all availability schedules for a given user.
* **Get a user availability schedule**: Get the details of a specific availability schedule.
* **List user busy times**: Find all busy time blocks for a user within a 7-day window.
* **List user meeting locations**: Return a list of a user’s configured meeting locations.

**No-Show Management**

* **Create an invitee as no show**: Creates a new invitee no show.
* **Get an invitee no show**: Retrieve the details of a specific no-show record.
* **Delete an invitee no show**: Remove the no-show status from an invitee.

#### Resources <a href="#resources" id="resources"></a>

* [Calendly documentation — Help Center](https://apps.make.com/calendly)

***

### Capsule CRM

Billing and Shipping options added to the Address Type field in Create a Party and Update a Party.

***

### Coda (now Superhuman Docs)

Renamed to Superhuman Docs with an updated logo and theme. Existing scenarios and connections unaffected; select Superhuman Docs for new connections.

***

### Deel

Fixed a Search Records error when filtering timesheets by a single contract type.

***

### Dropbox

* Create a Share Link (formerly Create/Update a Share Link) now only creates new links.
* New Update/Revoke a Share Link module changes or revokes an existing link.
* Scenarios that used the old module to update a link, or that create a link where one exists, now error - use Update/Revoke a Share Link instead.

***

### Etsy

Fixed a **Get a Listing module** failure caused by an Etsy API change.

***

### Eventbrite

Fixed a Watch Attendees in Organization trigger timeout for organizations with large attendee volumes.

***

### Facebook Messenger

Sticker attachments in Watch Messages switch from type "image" to type "sticker" on August 30, 2026. Update filters to check for type "sticker" (or the sticker\_id parameter) before then.

***

### Frame.io

We've updated the Frame.io app to make your file transfer automations more powerful. You can now get a direct download URL for your files, making it simple to save assets from Frame.io to other cloud storage services.

**Updated module**

**Get a File:** This module now includes a new **Include download URL** option. When enabled, the module's output will contain the direct download URL for the original file. You can then map this URL to other modules to create scenarios that automatically back up approved assets to services like Google Drive or Dropbox.

***

### Freshdesk

Attachments in the Create an Outbound Email module are now included in the email sent to the recipient, not just attached to the ticket.

***

### Gemini Enterprise Agent Platform (formerly Google Vertex AI)

**Google Vertex AI (Gemini)** is now **Gemini Enterprise Agent Platform**, matching Google's rebrand. This is a display name change only. Your existing scenarios and connections aren't affected, and you can still find the app by searching "Vertex."

The app also has a new video module and an update to an existing one:

* The new **Generate Videos with Omni (beta)** module generates up to three 720p videos from a text prompt or up to 10 reference images, and supports conversational editing: chain modules together by mapping the **Interaction ID** from one module's output to the next to refine a video with text prompts. It also outputs the video's resolution when available.
* We've updated the **Generate Videos with Veo** module's label for clarity and corrected its description to confirm it supports up to 1080p resolution.

***

### GitHub

We've added new search capabilities to GitHub and resolved several issues to make the app easier to use.

#### New modules <a href="#wuqkc" id="wuqkc"></a>

* **Search Items (Advanced):** Find issues, pull requests, repositories, or users with a single module. Search across all repositories in an organization and filter by author, assignee, review-requested user, and more.
* **Watch Items (Advanced):** Trigger scenarios when items matching your advanced search criteria are created or updated. Monitor your entire organization for specific events, such as new high-priority issues or pull requests needing review.

#### Bug fixes and UI improvements <a href="#xr0yi" id="xr0yi"></a>

The direction parameter labeled Last in several modules now correctly retrieves the last items instead of the first. Repositories owned by a GitHub organization now load correctly in dropdown lists across all relevant modules. Required fields for setting the number and direction of items to retrieve are now marked correctly, and toggle and sort labels across modules are clearer and more consistent.

***

### GoHighLevel

GoHighLevel is deprecating its V1 API, so we've retired API key-based connections in Make. Update your connections to OAuth 2.0 to avoid disruptions:

1. Create a new GoHighLevel connection and authenticate with OAuth 2.0.
2. Replace the API Key connection in your existing GoHighLevel modules with the new one.

You can no longer create API key connections, and GoHighLevel may disable more V1 endpoints at any time, causing affected modules to fail.

***

### GoToWebinar

* Fixed a bug preventing webhook creation for the Webinar Updated event in trigger modules.
* The Client Secret field is now masked by default when creating or editing a connection.

***

### Google Gemini AI

* Gemini 3.8 Flash now available in the Simple Text Prompt module.
* Gemini 3.7 Flash is available in the Google Gemini AI app, with availability expanded to the Make AI Agent (New) and Make AI Toolkit apps as well - multimodal input, function calling, search, computer use, and adjustable thinking levels.

For more information, see [Google Gemini AI documentation](https://apps.make.com/gemini-ai).

***

### Google Sheets

The advanced Value input option field is now required in **Update a Row**, **Update a Cell**, **Add Multiple Rows**, and **Update Multiple Rows**, preventing failures from incomplete configuration.

***

### Gorgias

* New **Watch Events**, **Get a Ticket**, **Search Tickets**, **Get a Customer**, and **Search Customers** modules.
* Existing ticket/customer modules now support custom fields; **Create a Ticket** and **Add a Reply to a Ticket** parameters reordered.
* New options added, including a whatsapp channel and ticket priority levels.

***

### Greenhouse Recruiting

* New Client Credentials (OAuth 2.0) connection type authenticates directly with a Client ID/Secret, for action and search modules (use the original Harvest connection type for Watch Events).
* Fixed a Make an API Call error when creating an advanced connection.
*   New app version now built on Harvest API v3, using OAuth instead of an API key. Greenhouse Recruiting is shutting down the Harvest v1/v2 API on August 31, 2026. Several modules have updated inputs and outputs to match the new data structure. This replaces the deprecated Harvest v1/v2 API and its API key authentication with an OAuth connection.

    Scenarios still using the old app version and API key connection will stop working after that date. Migrate your scenarios to the new app version and an OAuth connection before then to avoid disruption.

    See the full module-by-module migration guide, including field mapping and breaking changes, in the [Greenhouse Recruiting](https://apps.make.com/greenhouse-recruiting) page.

***

### iDoklad

* New v2 app version supports iDoklad API v3; v1 is deprecated and works until September 8, 2026.
* Fixes: Update an Invoice (Issued/Received/Proforma) no longer resets unrelated fields on single-item updates; Country field now required in Create a Contact; clearer field labels.

***

### Jira Cloud

The **Update an Issue** module has a new **Additional fields to update** section for updating any field by Field ID, including Edit Issue screen-only fields.

***

### Lexoffice

Lexoffice changed the ID for the Einnahmen als Kleinunternehmer revenue category, so we've updated the **Category ID** dropdown in the **Create a Voucher** module. The new option is now the default, and the old one is labeled Einnahmen als Kleinunternehmer (deprecated).

Update affected scenarios before **August 31, 2026**, or they'll fail:

1. Find any **Create a Voucher** modules that use the Einnahmen als Kleinunternehmer category.
2. Open the **Category ID** dropdown and reselect Einnahmen als Kleinunternehmer to apply the new ID.

New scenarios use the correct ID by default.

***

### LinkedIn Events

The Create an Event module now supports Live Video events via a new "Online event - Live Video" option, subject to LinkedIn eligibility (follower count, account age).

***

### Microsoft Advertising Conversions

New Make an API Call module for authenticated calls to any endpoint. Client secret field now masked.

***

### Microsoft Advertising Reports

New Make a REST API Call module for custom API calls. Client secret field now masked.

***

### Microsoft Excel

Fixed a 404 error from dynamically mapping a worksheet by ID; the field now clearly expects a worksheet name (use "Enter an ID manually" to map by ID). Applies to Add/Update/Delete/List Worksheet Row and Retrieve Data modules.

***

### NetSuite

The Watch Records module no longer skips records between runs when using a saved search.

***

### OpenAI

* GPT-6 Astra model added to **Simple Text Prompt** (paid plans) and modules with dynamic model selection.
* **Create a Chat Completion**: Tools (functions) field now hidden when Tool Choice is "None"; correctly required when "Auto" or "Required."
* **New Generate an Embedding**, **List Vector Stores**, **Search a Vector Store**, and **Delete a Vector Store** modules; **Create a Vector Store** or **Add Files** can now create an empty store and includes a chunking\_strategy parameter.
* **Upload a File**: Purpose field relabeled "File Search / Vector Store" with new User Data and Evals options; created\_at output now parses as a date instead of a raw timestamp.
* The Message an Assistant module is removed - update affected scenarios to a supported alternative.
* **Create a Completion** module no longer includes the credits formula; gpt-5.2-chat-latest and gpt-5.3-chat-latest no longer selectable in this module.
* gpt-5.2-chat-latest and gpt-5.3-chat-latest models deprecated; migrate to gpt-5.5 before August 10, 2026, or affected scenarios stop running.
* Credit costs reduced in Simple Text Prompt: gpt-5.6-terra now 20% cheaper, gpt-5.6-luna now 80% cheaper (gpt-5.6-sol unchanged). No action needed.

For more information, see [OpenAI](https://apps.make.com/openai-gpt-3) documentation.

***

### Outreach

The `contactHistogram` field is removed from the output of the Get a Prospect, Search Prospects, Create a Prospect, and Update a Prospect modules to align with upcoming Outreach API changes. This is a preventative update and doesn't affect any active scenarios.

***

### Pipedrive

Fixed an authentication token refresh issue that caused unexpected disconnects and "401 Invalid token" errors.

***

### Plytix

[Plytix](https://apps.make.com/plytix), a product information management (PIM) platform, is now available in Make. Use it to automate product data management, from creating and updating products to handling digital assets, and to keep product data in sync across your e-commerce workflows.

***

### REST Countries

Migrated to API v5 (from deprecated v2); now requires an API key. Search by Country Code output fields changed. New Make an API Call module added.

For more information, see [REST Countries: App migration to API v5 requires immediate action](https://help.make.com/rest-countries-api-v5-migration-brevo-contact-attribute-fix-and-more-app-updates#rest-countries-app-migration-to-api-v5-requires-im) page.

***

### Reddit

New connections now require your own custom OAuth app credentials (Reddit-approved); existing connections unaffected.

***

### SAP S/4HANA

The password field is now masked when creating or editing a connection.

***

### Salesforce Pardot

Fixed a connection/reauthorization failure when Salesforce's PKCE security policy was enabled.

***

### Shopify

To prevent your scenarios from failing, you must update any scenario that uses the **Update an inventory level** module with its deprecated parameters. Scenarios using the old configuration will no longer work correctly.

* **Breaking Change in 'Update an Inventory Level'**: The Compare quantity and Ignore compare quantity parameters have been removed. They are replaced by a new Change from quantity parameter to align with Shopify's API.
* **Update to 'Adjust an Inventory Level'**: A new optional Change from quantity parameter has been added. This change is not breaking and existing scenarios using this module will continue to work without modification.

For more information, see [Shopify: Action required for update an Inventory level module](https://help.make.com/shopify-action-required-for-the-update-an-inventory-level-module) page.

***

### Spotify

Fixed an issue preventing connection creation and verification.

***

### Square

Watch Payments and List Payments now correctly filter by Location ID instead of only returning the default location's payments.

***

### Squarespace

Fixed a URL Slug validation error in Create a Product and Update a Product.

***

### Stripe

Stripe now requires a new permission to create hosted invoices and payment links, and we've updated the **Stripe** app to support it. Reauthorize your connection to restore functionality:

1. Go to the **Connections** tab in your organization.
2. Locate your Stripe connection and click **Reauthorize**.
3. Approve the new permissions on the Stripe website.

Scenarios using an unreauthorized connection will continue to fail with a permission error.

***

### Strava

Due to changes in Strava's API access policy, you must now create your own Strava API application and connect to Make using your own credentials. Make's shared Strava application credentials are being deprecated, and the Watch Activities and Athletes trigger module has been replaced with a new version. To keep your scenarios running, create a Strava API application, set up a new connection with your Client ID and Client Secret, and update your scenarios to use the new trigger module.

For more information, see [Strava](https://apps.make.com/strava) documentation.

***

### Typeform

We've updated the Typeform app to align with recent changes to the Typeform Webhooks API. The Create or Update a Webhook module now requires all webhook URLs to use the secure `https://` protocol.

**Updated module**

**Create or Update a Webhook:** This module now validates that the provided **Webhook URL** begins with `https://`. Scenarios attempting to use an `http://` URL will now show a validation error, preventing the scenario from running with an invalid configuration.

***

### Vapi

Create/Update/List/Get/Delete a Workflow modules deprecated, along with the workflowId parameter in Create a Call and Create an Outbound Phone Call, as Vapi replaces Workflows with Squads. Migrate before August 18, 2026.

***

### Vitally.io

New Vitally connection type supports all account types with US/EU data center and subdomain selection, fixing regional \[401] errors. Legacy connections still work.

***

### Vonage

API Secret field now masked on entry; authorization tokens sanitized to prevent exposure.

***

### Webflow

The List Assets module has a new Folder ID field (retrieves assets from a folder and subfolders) and now outputs each asset's Folder ID and Alt Text.

***

### WooCommerce

Fixed the trigger occasionally skipping orders, especially when sorting by Date Completed.

***

### WordPress

The Create a Post module now returns an error with troubleshooting guidance instead of silently completing without creating a post (mainly affected CDN/caching setups).

***

### Workday Human Capital Management

We've fixed an Invalid Request error in the **Get an Employee** module when listing employees.

***

### YNAB

Fixed a `[400] bad_request` error in Create Transaction when using a `YYYY-MM-DD` date; date-only values now process correctly.

***

### Zendesk

Fixed a `BundleValidationError` for scenarios using custom fields with certain regex validation patterns.

***

### Zendesk Guide

An issue that prevented the **Permission Group ID** dropdown from loading in the **Create an Article** module is resolved. You can now correctly select a permission group when creating an article.

***

### Zoho CRM

Fixed intermittent connection failures for newer Zoho CRM connections.

***

### Zoho Notebook

Fixed a connection failure when selecting additional scopes; connections with all scopes now set up reliably.
