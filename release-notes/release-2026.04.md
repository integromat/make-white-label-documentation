# Release 2026.04

This release note lists the current software and service versions for White Label instances of Make, plus app updates and deprecations since the previous release.

### Current software version numbers

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

### Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to **Administration** > **Monitoring**.&#x20;

| Service                | Version                                  | Version update |
| ---------------------- | ---------------------------------------- | -------------- |
| accman                 | 7b20c1bd59567ff2235f2c3e93297f40f4c23513 | Yes            |
| agency                 | 4.0-beta                                 | -              |
| aws-rds-log-reader     | v1.1.1                                   | -              |
| broker                 | c8d549a7031e806d71aa92cdf355867e63b2c0db | Yes            |
| broker-gw-logger       | c8d549a7031e806d71aa92cdf355867e63b2c0db | Yes            |
| cron                   | v1.1.6                                   | Yes            |
| datadog-agent          | 7.75.0                                   | -              |
| datadog-cluster-agent  | 7.75.0                                   | -              |
| db-updater             | 4d4b9a5b8cbbdfb1d8cb2839b8b326db66b29ace | Yes            |
| emails-processor       | b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3 | -              |
| engine                 | f528c3a-20260710                         | Yes            |
| execution-controller   | 1c8c7b95d5e4db64bd83058fe00c26f0ff978ee0 | Yes            |
| gateway                | 7190c63df2030f4c4be56577f2e4a7666c225b07 | Yes            |
| imt-auditman           | 76f6d5091d96734bef016bc499b7e880c1f2cbc7 | Yes            |
| ipm-server             | 3.64.2                                   | Yes            |
| ipm-service            | 5ebc24ca9d8b0963ee896121bf65ee139c4acc54 | Yes            |
| kibana                 | 8.19.13                                  | -              |
| lickman                | 0bd3fd6d0c92bdf18fcad5b60a6ed89c504d74ab | Yes            |
| make-apps-processor    | 1.9.0                                    | Yes            |
| mongo-auto-indexer     | master                                   | -              |
| nginx                  | v1.28.0                                  | -              |
| notification-processor | ba23dcc670c5cad78dddea9e4df629f74de11e46 | Yes            |
| overseer               | 2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e | -              |
| renderer-processor     | 1f7e97d6321fbfa4dfb36196b3bba382fdd2ea22 | Yes            |
| roleman                | dc610974199623bb68a4d42bd5f9044b005c8397 | Yes            |
| s3proxy                | 3.1.0                                    | -              |
| scheduler              | f528c3a-20260710                         | Yes            |
| trackman               | 2.27.0                                   | Yes            |
| trigger                | 77debb45349e64732ce3680bf4304bc0d247ea33 | Yes            |
| web-api                | e4074328349b802ccff4090c116be91f0c44d280 | Yes            |
| web-streamer           | 70aba298eef467c67549ad7b9313ce7d231de5e7 | Yes            |
| web-zone               | 4b5fb44a3f34bbbee94c7c5de93d92845471d219 | Yes            |
| zone-assets-server     | 4b5fb44a3f34bbbee94c7c5de93d92845471d219 | Yes            |

### Public-facing changes

This section includes app updates and deprecations since the previous release.

#### Google Chrome app and browser extension deprecation on August 31, 2026

Make is retiring the native **Google Chrome** app and the Chrome browser extension on August 31, 2026.

**What changed**

Before August 31, 2026, the **Google Chrome** app is hidden from the app catalog, so you can't add it to new scenarios. Existing scenarios that use the app continue to run without changes until the end of support date.

On August 31, 2026, the **Google Chrome** app will be removed from all organizations and the Chrome browser extension from the Chrome Web Store. After this date, scenarios that use the **Google Chrome** app will stop working, and Make doesn't offer a replacement module for this functionality.

**What you need to do**

If you use the **Google Chrome** app in a scenario, remove it before August 31, 2026 to avoid disruption.

#### Dynamic labels for HTTP and Sleep modules

HTTP and [**Sleep**](https://help.make.com/util#sleep) modules now have labels that update automatically based on the module settings. **HTTP** modules show the request method and endpoint path, and **Sleep** modules show the delay time.

#### Make AI Agents (New): MCP tools are now available

You can now add MCP tools in the **Make AI Agent (New)** app. Use the new **Add MCP** button to connect to tools beyond the standard Make apps and expand what your agent can do.

#### Anthropic Claude model deprecations from June 15, 2026

Anthropic deprecated two Claude models on **June 15, 2026**. After that date, scenarios using these models will fail.

**What changed?**

Starting June 15, 2026, the following models are no longer available on the Anthropic Claude API :

* Claude Sonnet 4
* Claude Opus 4

After this date, all requests using these models will return an error. Existing modules in your scenario that use these models will fail when they run.

**What do you need to do?**

Review your Anthropic Claude modules and replace any deprecated models with a supported model.

| **Deprecated model** | **Replacement model** |
| -------------------- | --------------------- |
| Claude Sonnet 4      | Claude Sonnet 4.6     |
| Claude Opus 4        | Claude Opus 4.6       |

Review [Anthropic's model pricing](https://platform.claude.com/docs/en/about-claude/pricing) documentation for these replacement models, as your costs may change depending on your usage.

#### Databricks app is now available (Enterprise plans)

The **Databricks** app is now available in Make for Enterprise plans. Data and IT teams can run SQL queries and manage Databricks jobs, pipelines, and Unity Catalog volumes in their scenarios.&#x20;

To learn how to use the **Databricks** app in Make, see [Databricks](https://apps.make.com/databricks).

#### App updates

**Amazon Seller Central** — The **Create a Report** module now flags two settlement report options for deprecation on November 11, 2026. A replacement report type is already available, so no immediate action is needed.

***

**Bitbucket** — Due to Atlassian's API changes, most Bitbucket modules are now deprecated; only the **Watch a Repository**, **Watch a Workspace**, and **Make an API Call** modules remain. If your scenarios use the **Watch a Repository** trigger, re-select the repository to keep it working, and note that the **Events** field is now required in both watch modules.

***

**Anthropic (Claude)** — Two updates to the app:

* The **Create a Message** module now supports the latest versions of the **Code Execution**, **Web Search**, and **Web Fetch** tools. A new **Response Inclusion** option excludes result blocks to reduce token usage, and the tool selector is now grouped for faster selection.
* The **Simple Text Prompt** module now includes the new **Claude Fable 5** model and new **stop\_reason** and **stop\_details** outputs that show why a generation stopped.

***

**Amazon Bedrock** — Select the new **Claude Sonnet 5** model in the **Simple Text Prompt** module's **Model** dropdown for coding, complex reasoning, and professional-grade tasks.

***

**OpenAI (ChatGPT, Sora, Whisper)** — Three updates to the app:

* The **Create a Prompt Completion** and **Generate a Response** modules now support the new **GPT-5.6 Sol**, **Terra**, and **Luna** models.
* A new **Max** reasoning effort option is now available in the **Generate a Response** module, with updated help text noting that Temperature and Top P aren't supported by GPT-5.6 models.
* The **Generate a Completion** module now has clearer guidance for reasoning effort and other parameters.

***

**monday.com** — Two updates to the app:

* The item picker for a **Connect Boards** column now shows items from all connected boards, not just the first, in the **Create an Item (advanced)** and **Update Column Values of a Specific Item** modules.
* Two new AI-powered modules let you automate conversational tasks:
  * **Run Platform Agent (Beta)** sends prompts to monday.com's Sidekick agent and supports conversational memory through a **Context ID**.
  * **Generate a Chat Completion (Beta)** connects to the Platform AI Gateway to generate text or structured JSON for tasks like summarizing reports or classifying data.

***

**Sage Intacct** — New modules and updates to the app:

* The **Create a Purchasing Document** module creates new purchase orders, requisitions, or other document types.
* The **Get a Purchasing Document** module retrieves the details of a specific purchasing document by its ID.
* The **Update a Purchasing Document** module modifies an existing purchasing document.
* The **Search Purchasing Documents** module finds purchasing documents based on filter criteria, and no longer errors when you use a single filter.
* The **List Purchasing Documents** module gets a list of all purchasing documents of a specific type.
* Invoice modules now use the date data type for **createdDateTime** and **modifiedDateTime**, and connections no longer disconnect frequently during scenario runs.

***

**QuickBooks** — Two updates to the app:

* The **Update a Time Activity** module now preserves the original date of a time activity unless you map a new one, instead of resetting it to the current date.
* The **Create/Update Invoice**, **Credit Memo**, **Estimate**, and **Sales Receipt** modules now have an **Email status** field — set it to **Do not send** to create a transaction without emailing the customer.

***

**Axonaut** — The **Create a Company** module now has an **Is B2C** field for creating B2C companies with employee details, and new **Language**, **IBAN**, and **BIC** fields; **Name** and **Business Manager** are no longer required. The **Update a Company** module now has fields to update **Currency**, **Language**, **IBAN**, and **BIC**.

***

**Getform** — **Getform** is now **Forminit**, with an updated logo across Make. This is a visual change only — existing scenarios and connections aren't affected.

***

**Microsoft 365 Email (Outlook)** — Two updates to the app:

* The **List Attachments** module no longer fails when processing attachments in S/MIME signed emails. It also handles a wider range of filename formats and character encodings, preventing scenario errors.
* A new **Trigger by** field in the **Watch Emails** and **Watch Emails in a Shared Folder** modules lets you trigger scenarios on emails moved into a folder, not just newly created ones. The default stays **Created Date**, so existing scenarios aren't affected.

***

**WordPress** — The **Create a Post** module no longer requires the **Content** field, so you can create posts with only a title.

***

**Formidable Forms** — The **List Form Entries** module no longer fails on forms with non-input fields like HTML blocks, dividers, or captchas, and the **Form ID** dropdown now loads correctly.

***

**Fatture in Cloud** — The **Create an Issued Document** module now sends the **paid\_date** field in the correct format, so scenarios no longer error on payment dates.

***

**Google Docs** — The **Create a Document from a Template** module no longer skips placeholders that appear after an empty (null) value, so all placeholders update correctly.

***

**Jotform** — Accounts with more than 50 forms can now see and select all available forms (up to 500) in modules like **Watch Submissions** and **Get Form Submissions**.

***

**MCP Client** — The **Execute an action with AI** module now lets you choose your AI provider:

* Use Make AI Provider to access OpenAI and Claude AI models through Make credits, with no external account or API key required
* Connect your own OpenAI API key to use models you already pay for with full control over spend. Either way, you can run AI steps directly within your MCP flow.

***

**HubSpot CRM** — We've moved authentication to HubSpot's more secure **OAuth v3 API**, improving connection security, preparing your scenarios for the eventual retirement of the v1 API, and standardizing error messages for easier troubleshooting. No action is required; existing connections continue to work.

***

**Manago AI** — Salesmanago has been renamed to Manago AI across Make, with an updated logo. Existing scenarios and connections aren't affected.

***

**Google Sheets** — We've fixed an issue where the **Add a Row** and **Update a Row** modules failed to write data when "Table contains headers" was enabled and columns had empty headers, so data is now reliably added or updated as expected.

***

**Reddit** — The new **List Comments in a Post** module retrieves all comments and replies from a post, so you can monitor discussions and analyze sentiment more effectively, even on posts with many comments.

We've also improved the **List Subreddit Posts** module to return a clear error message instead of raw HTML when a subreddit doesn't exist.

***

**Discord** — The new **Get an Invite** and **Delete an Invite** modules let you retrieve and remove channel invites. We've also updated **Create a Channel Invite** to support assigning multiple roles at once, with the roles list filtered to show only assignable roles.

***

**GitHub** — The new **Make an API Call** module sends a custom REST API call to any GitHub endpoint, so you can access API features not available in other modules and build highly customized scenarios.

***

**xAI** — The new **Create a response** module lets you generate AI responses using web search, code interpretation, and custom functions directly within scenarios.

***

**Pipedrive** — You can now assign up to ten users to a single task. The **Create a Task** and **Update a Task** modules include a new **Assignee IDs** field, and **Search Tasks** and **Get a Task** now return it too.

***

**Trustpilot** — We've added a server-to-server connection type, so you can connect to Trustpilot using OAuth 2.0 with your API key and secret, ideal for automated scenarios that run without user interaction.

***

**Amazon Bedrock** — The **Create a conversation** module now supports models that require an inference profile, so you can select the required profile directly when configuring the module.
