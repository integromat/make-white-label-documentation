# Release 2026.06

This release note lists the current software and service versions for White Label instances of Make, plus app updates and deprecations since the previous release.

## Current software version numbers

The following is a list of current software versions running in Make's release environment.

**Containerization**

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.35           | -              |

**Databases**

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.19          | Yes            |
| Redis         | v6.2.20        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 8.19.13        | -              |

**Message Queues**

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7.1       | -              |
| Erlang   | 26.2.5.19      | -              |

**Filesystem**

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

## Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to Administration > Monitoring.

| Service                | Version                                  | Version update |
| ---------------------- | ---------------------------------------- | -------------- |
| accman                 | 0c4fb875dfecf32ef507b4f67b89e172d61996f7 | Yes            |
| agency                 | 23f3d441567d0ab32070654f33daa7d28edc66e6 | -              |
| broker                 | cd1ca94-20261104                         | Yes            |
| broker-gw-logger       | cd1ca94-20261104                         | Yes            |
| cron                   | v1.1.10                                  | Yes            |
| datadog-agent          | 7.84.2                                   | Yes            |
| datadog-cluster-agent  | 7.84.2                                   | Yes            |
| db-updater             | 9a70df13552eafdb73eb4fe4177ecfa0ecafd82c | Yes            |
| emails-processor       | b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3 | -              |
| engine                 | cd1ca94-20261104                         | Yes            |
| execution-controller   | 61aa682-20261105                         | Yes            |
| gateway                | c80e252e06a718f287c336f668820937fe425e32 | Yes            |
| imt-auditman           | f4104335fce8f8725b5d457f95576cd69b28cd4a | Yes            |
| ipm-server             | 3.74.1                                   | Yes            |
| ipm-service            | d464aea474c597bde885ab7c3f32d7e5204a7adf | Yes            |
| kibana                 | 8.19.13                                  | -              |
| lickman                | cab5525021496ff5b2c7d18c3533cfc66ea40730 | Yes            |
| make-apps-processor    | 1.11.1                                   | Yes            |
| nginx                  | v1.28.0                                  | -              |
| notification-processor | 4cd0ef8514a8511d8660d983af45ac992e4d74a7 | Yes            |
| overseer               | a6ad20da68a2d9a39b8928f85a74e7d2c57089c2 | Yes            |
| renderer-processor     | 1f7e97d6321fbfa4dfb36196b3bba382fdd2ea22 | Yes            |
| roleman                | 4c4121bc24f3c308231d752fd4a7e5410b28d2e5 | Yes            |
| scheduler              | cd1ca94-20261104                         | Yes            |
| trackman               | 2.28.1                                   | Yes            |
| trigger                | 209bca7b7560deb42c402dd81af2a88b4a0157f3 | Yes            |
| web-api                | 27cd1dfdacc649b5128f3d527dd415cf8ad6a6c6 | Yes            |
| web-streamer           | 4a2b37f533462a7a3d43fd807e3365df3a156744 | Yes            |
| web-zone               | 2026.06                                  | Yes            |
| zone-assets-server     | 2026.06                                  | Yes            |

## Public-facing changes

This section includes updates, fixes, and deprecations since the previous release.

### OpenAI: video modules deprecation

Due to OpenAI's decision to deprecate its entire Videos API and Sora models, all video-related modules in the OpenAI app are deprecated.

{% hint style="warning" %}
Action required by September 24, 2026. After this date, scenarios using the deprecated video modules stop running. You can no longer create new scenarios using these modules.
{% endhint %}

#### What's changing?

* OpenAI is removing its entire Videos API, including all Sora models, on September 24, 2026. OpenAI has not announced a replacement.
* All video-related modules in the OpenAI app on Make are deprecated.
* Existing scenarios using the deprecated modules continue to run until September 24, 2026.
* You can no longer add these deprecated modules to new scenarios.

#### What do you need to do?

To avoid disruption, you must update your scenarios before September 24, 2026. Migrate to an alternative third-party video generation service and remove the deprecated OpenAI video modules from your scenarios.

#### Deprecated modules

| **Deprecated module** | **Module to use**     |
| --------------------- | --------------------- |
| Generate a Video      | No direct replacement |
| Remix a Video         | No direct replacement |
| Get a Video           | No direct replacement |
| Delete a Video        | No direct replacement |
| List Videos           | No direct replacement |
| Watch Video Jobs      | No direct replacement |

#### Resources

* [OpenAI documentation — Help Center](https://apps.make.com/openai-gpt-3)
* [OpenAI API Deprecations](https://developers.openai.com/api/docs/deprecations)

***

### OpenAI: legacy model deprecation

In line with OpenAI's plan to improve reliability and simplify model selection, Make is retiring several legacy models. These models are now hidden from the selection menus in the OpenAI app to prevent their use in new scenarios.

{% hint style="warning" %}
Action required by September 28, 2026. After this date, scenarios using the deprecated models stop running. You can no longer create new scenarios or update existing modules to use these models.
{% endhint %}

#### What's changing?

* A set of legacy OpenAI models are no longer available for selection in new modules.
* Existing scenarios that use these deprecated models continue to run until September 28, 2026.
* After this date, any scenarios still using the deprecated models fail.

#### What you need to do

To ensure your scenarios continue to run after the deadline, you must update any OpenAI modules using a deprecated model to a recommended replacement before September 28, 2026.

#### Deprecated models and recommended replacements

| Deprecated model            | Recommended replacement    |
| --------------------------- | -------------------------- |
| gpt-3.5-turbo-instruct      | gpt-5-mini or gpt-4.1-mini |
| gpt-3.5-turbo-1106          | gpt-5-mini or gpt-4.1-mini |
| babbage-002                 | gpt-5-mini or gpt-4.1-mini |
| davinci-002                 | gpt-5-mini or gpt-4.1-mini |
| gpt-3.5-turbo-instruct-0914 | gpt-5-mini or gpt-4.1-mini |

#### Resources

* [OpenAI documentation — Help Center](https://apps.make.com/openai-gpt-3)
* [OpenAI Deprecations Notice](https://platform.openai.com/docs/deprecations#2025-09-26-legacy-gpt-model-snapshots)

***

### Microsoft Dynamics 365 Business Central

Due to Microsoft removing API v1.0 in its Business Central 2026 release wave 1 (version 28.0 and newer), Make updated the app's connection settings to help guide users to the correct API version. Scenarios with connections manually configured to use the retired /api/v1.0/ endpoint fail.

#### What's changing?

Microsoft removed API v1.0 for Business Central. The Make app's default connection configuration already uses the current API v2.0, but any connections manually set to use the /api/v1.0/ endpoint no longer work. To prevent errors, the connection settings now include help text that clarifies which API version to use.

#### What do you need to do?

To ensure your scenarios continue to run, check your Microsoft Dynamics 365 Business Central connections and update them if necessary:<br>

1. In your scenarios, locate your Microsoft Dynamics 365 Business Central modules and click to edit the connection.
2. In the connection settings, check the Endpoint field.
3. If the field is set to `/api/v1.0/`, you must update it to `/api/v2.0/`.

#### Resources

* [Microsoft Dynamics 365 Business Central documentation — Help Center](https://apps.make.com/microsoft-dynamics-365-business-central)
* [Microsoft's API v2.0 transition guide](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/api-reference/v2.0/transition-to-api-v2.0)

***

### Google Ads

Google deprecated the v22 version of the Google Ads API on October 7, 2026. Make removed v22 as an option in all Google Ads modules to prevent its use in new configurations. Scenarios with modules that still use API v22 fail.

To fix an affected scenario, update its modules to a supported API version:

1. Review your scenarios to find the ones that use Google Ads modules.
2. Open each Google Ads module and check the API Version field. If it's set to v22, select a newer version.

***

### Wealthbox

The Wealthbox API Token connection type is deprecated and replaced by a new Wealthbox OAuth connection type.\
Wealthbox is deprecating personal API token authentication. Existing scenarios that use the deprecated connection continue to run until October 21, 2026. After that date, they stop running. You can no longer create new connections with the deprecated type.

To keep your scenarios running, replace the deprecated connection before October 21, 2026:

1. In a Wealthbox module, click Add next to the connection field, and select Wealthbox OAuth to authenticate your account.
2. In every scenario that uses the Wealthbox app, replace the deprecated connection with the new one.

***

### Google Gemini AI

#### Generate a video module update required by September 30, 2026

Google deprecated the gemini-omni-flash-preview model, so the Generate a video module now uses the new gemini-omni-1.1-flash model, adding control over video output resolution and generation task type. Scenarios using the previous model stopped working after September 30, 2026.

#### What's changing?

* The Generate a video module now uses the new gemini-omni-1.1-flash model, replacing the deprecated gemini-omni-flash-preview model.
* New features include:
* Output resolution: Select 360p, 720p, 1080p, or 4K for your video output.
* Generation task: Specify edit or extend for more precise control.
* Existing scenarios using the deprecated model continued to run until September 30, 2026.
* You can no longer select the deprecated gemini-omni-flash-preview model in new modules.
* The module is out of preview, with an updated name and description.
* The module no longer returns an incorrect prompt violation error when you use a video as a reference.
* Gemini Omni 1.1 Flash doesn't support media resolution for reference images or videos.

#### What do you need to do?

To keep your scenarios running, update your existing Generate a video modules:<br>

1. Open any scenario that uses the Google Gemini AI Generate a video module.
2. The module automatically defaults to the new gemini-omni-1.1-flash model. Save the scenario to apply the update.

#### Upcoming deprecation of the gemini-2.5-flash-image model

Google is retiring the gemini-2.5-flash-image model, also known as "Nano Banana." Update any modules using this model before October 2, 2026.

After that date, scenarios using gemini-2.5-flash-image fail, and you can't select it when configuring new or existing modules. The change affects modules that use a model list, including the Generate an image, Generate a response, and Extract structured data modules.

To update a module, select a supported alternative, such as Nano Banana 2, from the model dropdown.

#### Gemini 4 Argon model support

The Gemini 4 Argon model is now available in the Simple text prompt, Generate a response, and Extract structured data modules.

Gemini 4 Argon is Google's flagship reasoning model for complex tasks, such as advanced software engineering, scientific problem-solving, and building multi-step autonomous agents. It processes text, image, video, audio, and PDF inputs. The model requires a connection configured with a paid-tier Google API key. A free-tier key results in an error.

#### Resources

* [Google Gemini AI documentation — Help Center](https://apps.make.com/gemini-ai)
* [Google Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog)
* [Google Gemini Omni guide](https://ai.google.dev/gemini-api/docs/omni)

***

### Twilio Autopilot

The Twilio Autopilot app is retired in Make. Twilio shut down its Autopilot API in August 2023, so the app no longer works. This change is effective immediately and requires action.

#### What's changing?

The Twilio Autopilot app and its modules are now hidden and unavailable in new scenarios.<br>

* Existing scenarios that use Twilio Autopilot modules return an error when they run.
* You can't create new scenarios or connections with this app.
* The twilio-autopilot connection type is also retired.

#### What do you need to do?

If you have scenarios that use Twilio Autopilot modules, you must remove them. Twilio has not provided a direct replacement for the Autopilot service. Explore alternative solutions depending on your specific use case.

#### Retired modules

The following modules are retired and have no direct replacement:

| **Deprecated module** | **Replacement**       |
| --------------------- | --------------------- |
| Create Assistant      | No direct replacement |
| Read Assistant        | No direct replacement |
| Update Assistant      | No direct replacement |
| Delete Assistant      | No direct replacement |
| List Assistants       | No direct replacement |
| Create Task           | No direct replacement |
| Read Task             | No direct replacement |
| Update Task           | No direct replacement |
| Delete Task           | No direct replacement |
| List Tasks            | No direct replacement |
| Create Field          | No direct replacement |
| Read Field            | No direct replacement |
| Delete Field          | No direct replacement |
| List Fields           | No direct replacement |
| Create Sample         | No direct replacement |
| Read Sample           | No direct replacement |
| Update Sample         | No direct replacement |
| Delete Sample         | No direct replacement |
| List Samples          | No direct replacement |
| Make an API Call      | No direct replacement |

***

### Metricool

Starting October 22, 2026, the Get network metrics module no longer returns data for about 30 metric codes that Metricool removed or replaced. Meta and other platforms discontinued the underlying data, so Metricool stopped providing it.

#### What changed

Scenarios that use the removed metrics don't fail. They return 0 or an empty result instead, the same as they already do for data that Meta no longer provides.

Some metrics have a direct replacement:

| **Removed metric**                                                                                  | **Replacement**                                                                                      |
| --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| FBEV01 Page Likes                                                                                   | FBEV17 Page Followers                                                                                |
| FBEV02 Page Impressions                                                                             | FBEV49 Page Media View (Views)                                                                       |
| FBEV05 Page Likes Acquired                                                                          | FBEV47 Page Followers Acquired                                                                       |
| FBEV06 Page Likes Lost                                                                              | FBEV48 Page Followers Lost                                                                           |
| FBDP01 / FBDP02 Country Name / Country Followers (Likes)                                            | FBDP03 / FBDP04 Country Name / Country Followers                                                     |
| FBDC01 / FBDC02 City Name / City Followers (Likes)                                                  | FBDC03 / FBDC04 City Name / City Followers                                                           |
| FACA16 / FACA17 Meta Ads Campaigns Conversions / Conversions Value, FADE12 Meta Ads Ads Conversions | A specific conversion metric, for example Purchase or Lead, or FACA23 / FADE73 All conversions value |
| LIEV03 LinkedIn Impressions                                                                         | LIEV22 Account Posts Impressions                                                                     |

Other metrics have no replacement, because the platform discontinued them: FBEV07 Page Website Clicks, FBEV09 Page CTA Clicks, FBEV32 Page Posts Clicks, GMRE05 GBP Reviews Reply Comment, TWCO08 Twitch Competitors Views, and IGHT02 Instagram Hashtags Impressions.

Make also removed several calculated metrics that always returned an empty result, so this has no functional impact: FBEV08, IGEV08, IGEV24, LIEV09, LIPO11, TTEV15, PIEV03, TKEV10, TKPO12, and THEV04 (Engagement / Engagement timeline).

#### What you need to do

To avoid interruptions in your scenarios:

1. Open each scenario that uses the Get network metrics module.
2. Remove the deprecated metrics from your selection.
3. Pick a replacement metric where one is available.

***

### Alegra

Alegra is migrating resource IDs from numeric values to text-based UUIDs (Universally Unique Identifiers). Seller IDs moved to the new format first, and item IDs moved to UUIDs on September 21, 2026.

The change affects most Alegra resources, including items, sellers, estimates, invoices, and contacts. Existing records keep their numeric IDs, but new records created after each resource type's migration date use UUIDs.

If your scenarios use filters, formulas, or functions that treat these IDs as numbers, update that logic. For example, a filter condition like Item ID > 1000 no longer works and must be removed or changed.

***

### Anthropic Claude

* Claude Opus 5.5 is now supported in the Create a Prompt and Simple Text Prompt modules.
* Claude Sonnet 5.5 is now supported for users on paid plans in the Make AI Toolkit and Anthropic Claude apps. It supports a context window of up to 1,000,000 tokens and text output of up to 128,000 tokens. In Simple Text Prompt (via Amazon Bedrock) and Create a Prompt, select it from the Model dropdown. The Create a Prompt module also has a new diagnostics output parameter, a new Turn Off Up-Front Thinking option, and no longer fails when you use the Computer Use Tool with this model. Tool choice is limited to the Auto setting for Sonnet 5.5.
* Claude Haiku 5.5 is now available in the Create a Prompt module and in the Make AI Toolkit and Anthropic Claude apps. It's the cheapest Claude model, built for high-volume tasks such as classification, routing, extraction, and subagent tasks. On the Free plan, scenarios using a premium model, such as Opus, now run with Claude Haiku 5.5 as the fallback.
* The claude-sonnet-4-5-20250929 model is now marked as (deprecated) in the Create a Prompt module. Anthropic retires this model on November 30, 2026. Existing scenarios continue to run until then. For new scenarios, use a newer model, such as Claude Sonnet 5.5.

For more information, see [Anthropic Claude documentation](https://apps.make.com/anthropic-claude).

***

### OpenAI

* GPT-6 Sol and Luna are now available in the Make AI Toolkit and OpenAI (ChatGPT, Whisper) apps. GPT-6 Sol is for complex, multi-step work. GPT-6 Luna is for high-volume intake, such as categorizing and routing support requests.
* GPT Image 2.5 Sunburst and Flare are now available in the Generate Images and Edit Images modules of the OpenAI (ChatGPT, Whisper) app. Flare is for fast, routine edits. Sunburst is for precise, detailed edits when quality matters more than speed.
* The Create a Prompt module now includes the GPT-6.1 Sol model in the model dropdown. GPT-6.1 Sol is designed for complex tasks and is available only on paid Make plans. It's available in the Make AI Toolkit and OpenAI (ChatGPT, Whisper) apps, and supports Functions, Web search, File search, and Computer use. Multi-agent support is in beta.

For more information, see [OpenAI](https://apps.make.com/openai-modules) documentation.

***

### xAI

Grok 4.7 is now available in the xAI app. Send text and images, including long source materials, to Grok 4.7 to generate text briefs for review workflows. The model has a 500,000-token context window.

Grok 4.7 is available to users with an xAI API key that has access to Grok 4.7 and the required endpoints. xAI account token usage and billing apply.

For more information, see [xAI](https://apps.make.com/xai).

***

### WordPress

Make now strictly validates SSL certificates for all connections to your WordPress sites. This change helps ensure your data transfers securely and prevents man-in-the-middle attacks.

* Strict validation: Connections to WordPress sites with an invalid or expired SSL certificate now fail with an error. Previously, Make might have ignored these issues silently. If your scenarios are affected, make sure your server's SSL certificate is valid.
* Self-signed certificates: If your WordPress site uses a self-signed certificate, such as in development or internal environments, you can now upload your custom certificate in the connection settings.

***

### Workday Human Capital Management

The Workday HCM app has a new, more secure connection type. Authorize your connection as a specific Workday user so scenarios run with user-specific permissions instead of a generic integration system user.<br>

* Workday HCM (Authorization code): Authenticate in your browser using the standard OAuth 2.0 authorization flow. Scenarios run with the permissions of the authorizing user.
* Workday HCM (Refresh token): The existing OAuth connection that requires a pasted refresh token is renamed for clarity. Its functionality is unchanged, and existing connections continue to work without action.

For more information, see [Workday Human Capital Management](https://apps.make.com/workday-human-capital-management) documentation.

***

### Workday Financial Management

The Workday app has a new connection type that uses the OAuth 2.0 authorization code flow. Individual users authorize Make through their browser, so scenarios run with the permissions of that Workday user and respect your data access policies.

* Workday Financial Management (Authorization code): Authorize Make through your browser. Scenarios only access the data that the user can view in Workday.
* Workday Financial Management (Refresh token): The existing OAuth 2.0 connection that uses a manually entered refresh token is renamed for clarity. Its functionality is unchanged.

For more information, see [Workday](https://apps.make.com/workday) documentation.

***

### Notion

Make updated the Notion app to support Notion's latest API version (2026-03-11). This update ensures continued compatibility and aligns the app with Notion's new data structures for managing items in the trash.

#### Updated modules

* General: Modules that handle pages, databases, blocks, and data source items now return a new In Trash boolean field in their output. To ensure your existing scenarios continue to work without changes, the previous Archived field is also returned and contains the same value.
* Update a Page and Update a Page Content: The Archived input parameter now correctly moves items to or from Notion's trash, reflecting the new in\_trash status in the Notion API.

For more information, see [Notion documentation — Help Center](https://apps.make.com/notion).

***

### Facebook Conversions API

The Facebook Conversions API and Facebook Conversions API for CRM apps now support conversion value tracking.

#### Updated modules

* Send Event(s) (Facebook Conversions API): New optional Conversion Value and Conversion Currency fields enhance event tracking.
* Create a Lead Event (Facebook Conversions API for CRM): New optional Conversion Value and Conversion Currency fields enhance event tracking. If you already configured a Purchase event, these fields moved to the main module settings, and your existing mappings continue to work.

For Purchase events, you must provide both a value and a currency to comply with Meta's API.

***

### WhatsApp Business Cloud

Make updated the WhatsApp Business Cloud app to align with Meta's new pricing model for service messages, which takes effect on October 1, 2026. These changes help you monitor your usage and prevent messages from failing to send.

#### Updated modules

* Watch Events: A new Type field is added to the Pricing collection in the webhook's output. This field indicates whether a message was part of your free monthly tier (free\_customer\_service) or paid (regular), so you can monitor when you've used your free message allowance.
* Send a Message: The information banner now clarifies that after you use your 1,000 free monthly service messages, subsequent messages aren't delivered unless a valid payment method is configured in your Meta Billing Hub.

For more information, see [WhatsApp Business Cloud documentation — Help Center](https://apps.make.com/whatsapp-business-cloud).

***

### TypeSafe AI (Jev)

TypeSafe is now available on Make. It's a decision-making API that evaluates content and provides structured answers with confidence scores. Connect it to your scenarios to automatically classify, route, score, and gate your workflows.

The app was renamed from TypeSafe to TypeSafe AI (Jev). Your existing scenarios and connections aren't affected. You can also find the app by searching for "Jev" in the app gallery or Scenario Builder.

#### Available modules

* Evaluate a state: Evaluates state against typed questions and gets back structured answers.
* Make an API Call: Sends a custom API call to TypeSafe. Use it to call endpoints that existing modules don't cover.

#### Who it's for

This integration is useful for support and operations teams who want to automate the routing of incoming requests, or for product teams who want to systematically score customer feedback.

#### Resources

* [TypeSafe documentation — Help Center](https://apps.make.com/typesafe)
* [TypeSafe API documentation](https://docs.typesafe.ai/api)

***

### monday.com

#### Build AI agents from your scenarios

The monday.com app has a new Agents capability. Build scenarios that act as team members in your monday.com workspace and respond to chats, mentions, and assignments automatically.

#### New modules

* Watch Agent Events (Beta): An instant trigger that starts your scenario when your Make agent is activated in monday.com. It supports direct chats, @mentions in item updates, and task assignments.
* Send Agent Response (Beta): Posts a text response to the monday.com chat session where the agent was triggered.

#### Updated modules

* Create an Update: Now supports replying in threads and mentioning agents, users, or teams.

To set up an agent:

1. In monday.com, create a new Make.com Scenario Agent to get an Agent API key.
2. In a Make scenario, add the Watch Agent Events trigger and create a new monday.com Agent (beta) connection using your API key.
3. Build your scenario logic. For example, connect to an AI model like OpenAI, look up customer data in a CRM, or triage tasks.
4. Use Send Agent Response or Create an Update to send the result back to monday.com.

#### App name and labels updated

The app, its connections, and webhooks now consistently use the monday.com name. Connection labels changed from Monday v2 to monday.com and from Monday Agent (beta) to monday.com Agent (beta). All webhooks that previously started with "Monday" now start with "monday.com". No action is required. Existing connections and scenarios continue to work as before.

#### Connection validation improved

The app now validates connections and shows an error if you use a monday.com agent API key. These agent-level keys have limited permissions and caused scenario runs to fail in certain modules.

#### Resources

* [monday.com documentation](https://apps.make.com/monday)

***

### Google Drive

The Google Drive app has two new modules. Get file and folder metadata without downloading content, and manage access permissions dynamically in your scenarios.

#### New modules

* Get a File/Folder Metadata: Retrieve details about a file or folder, including its name, parent folders, size, description, custom properties, and web links, without downloading the content. Use it to check or route large files efficiently.
* List Permissions: Get a list of users and their access levels for a file or folder. Map the Permission ID to the Update a File/Folder Access or Revoke a File/Folder Access modules to automate access management.

#### Resources

* [Google Drive documentation](https://apps.make.com/google-drive)

***

### Slack

The Create a Channel and Invite Users modules now support bot connections in addition to user connections. You can invite users to channels using either a bot or a user account.

For more information, see [Slack documentation](https://apps.make.com/slack).

***

### Linear

* The new Update an Issue module changes an existing issue's title, description, priority, due date, or status. It also reassigns issues, adds them to different projects or cycles, and manages labels and subscribers.
* The help text for the Trashed field in Update an Issue now states that an issue must be archived before you can move it to the trash.
* Several modules, including Update an Issue, List Issues, and List Comments, previously failed to load data correctly. This issue is resolved, and dropdown menus and data lists populate as expected.
* Make refactored how the app communicates with the Linear API, so scenarios now run more consistently.
* The app shows Linear's new logo.

For more information, see [Linear documentation](https://apps.make.com/linear).

***

### SAP SuccessFactors

The Get a Record and Search for Records/Objects modules no longer show record types related to SAP's Legacy People Profile Configuration API. SAP deletes this API on November 13, 2026.

This change affects only new scenarios. Existing scenarios that use the Make an API Call module to access these endpoints aren't affected by this update, but the SAP deadline may still affect them. The following entities are removed:<br>

* EmployeeProfilePageConfig
* EmployeeProfileHeaderConfig
* EmployeeProfileSectionConfig
* EmployeeProfileSubSectionConfig
* EmployeeProfileBlockContent
* EmployeeProfileBlockLink
* EmployeeProfileFieldConfig
* MDFBlockConfig

***

### Kimi

The Kimi app is deprecated and no longer available in new scenarios. New connections to Kimi kept failing with an authentication error, so Make deprecated the app.

***

### Airtable

The Search Records module now shows the search, filter, formula, and sort options when you map the Base ID and Table ID. Previously, these options disappeared when you mapped the IDs dynamically.

***

### AppsFlyer

All modules in the AppsFlyer app now have a five-minute processing time limit. The limit prevents scenarios from failing when you run reports or other long, complex operations.

***

### Basecamp 3

The app has an updated logo that reflects its current branding.

***

### Bigin by Zoho CRM

An issue where dropdown fields, including single- and multi-select picklists, saved incorrect values in the create and update modules is resolved. Previously, these modules sent the field's internal ID instead of its text value, which could create an unwanted new option in your Zoho Bigin account.

***

### Box

Setting Text Signatures Enabled or Reminders Enabled to No in the Create a Sign Request module didn't work as expected. This issue is resolved, and Make now applies these settings when you create a sign request.

***

### Calendly

The app now uses Calendly's latest logo. This visual change doesn't affect the app's functionality.

***

### ClickUp

Filtering tasks by custom fields now works with advanced operators in the List Filtered Tasks and List All Tasks modules. Previously, filtering by a custom field with multiple values returned incorrect results, and the value field didn't accept the correct format for some operators. Use an array of values with the RANGE, ANY, ALL, NOT ANY, and NOT ALL operators.

***

### Detrack

The Notify Email field in the Create a Job module previously accepted only a single email address. You can now enter multiple email addresses as a text string to send job notifications to several recipients at once.

***

### EspoCRM

Two issues are resolved. The Watch Changes webhook trigger no longer fails silently for some updates, so webhooks from all supported EspoCRM versions, including older self-hosted instances, process correctly. The Lead ID dropdown in the Delete a Lead module now loads its options.

***

### Facebook Pages

The Publish a Reel module now loads your list of Pages. When you create a new connection with this module, Make now requests the necessary permissions, so you can select your Page. If you were affected, reauthorize your existing Facebook Pages connection for the fix to take effect.

***

### Google Vertex AI

The Make an API Call module no longer fails when you select Global, European Union (multi-region), or United States (multi-region) as the Service Endpoint Location. The module now builds the URL correctly for these locations.

***

### Microsoft 365 Excel

* The Add a Table Row module now works with a mapped Workbook ID. It accepts empty cell values and uses the specified Row ID to insert or update rows at the correct position.
* The Table Row ID output in the Add a Table Row, List Table Rows, and Watch Table Rows modules is now a number instead of text, so it works better with other modules.

***

### Nextcloud

An issue that corrupted files, such as .docx documents, in the Download a file module is resolved. The module now handles binary data correctly, so later modules in your scenarios can process the files reliably.

***

### PrestaShop

The Update a Product module no longer changes a product's creation date to the current date. It now preserves the original creation date when you update a product.

***

### Revolut Business

The Create a Draft Payment module now requires only the payment details needed for the recipient's country. Previously, both the Account Number and IBAN fields were required. You can now create payments to non-IBAN regions, such as New Zealand, Japan, and Singapore.

***

### Salesforce

The Create a Record module no longer fails when loading fields for certain object types, such as Case. The module now loads all associated fields, so you can configure it without errors.

***

### Salesforce Pardot

The Create a Record and Update a Record modules now show all custom fields for the Prospects record type. Previously, some custom fields didn't appear.

***

### ShipStation

The Intl Options Customs Items field in the Create an order module is now mappable. You can dynamically map customs information when creating international orders.

***

### Shopify

When you create a Shopify connection for the first time, the error message now gives clear instructions to complete the connection. Previously, the connection returned a vague "No access token specified" error.

***

### Tadabase

* Update a Record: Fixed an issue where scenarios failed if a File field contained more than one file. You can now correctly update records with multiple files in a single field.
* Create a Record: Fixed an issue that caused scenarios to fail with an error when uploading files. The module now correctly creates records with mapped files, and you can upload multiple files to fields of the Files type.

***

### TimeCamp

An issue with the Make an API Call module that prevented new tasks from being created is resolved. The module was communicating with an outdated API endpoint, which caused it to fail silently. It now connects to the correct endpoint.

***

### Xero

* Xero modules previously failed unexpectedly when you selected an Organization in the module configuration. This issue is resolved, and Xero (Webhook) connections show a clear error message if you enter an invalid organization name.
* The Search for Invoices module now returns a clear error message when you enter an invoice ID in an invalid format.

***

### YouCanBook.me

Creating a new connection no longer fails with an authentication error. The connection setup fields now have clearer labels and instructions, and they specify that an API key is required.

***

### Zoho CRM

An issue that caused the Description (multiline) and custom Details (rich text) fields to go missing in the Upsert a Lead module is resolved. These fields are now available for mapping.

***

### Zoho Recruit

The Search Records module previously failed to retrieve more than 200 records. The module now correctly fetches all records that match your search criteria, up to the limit you define in the module settings.
