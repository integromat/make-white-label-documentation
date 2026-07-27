---
hidden: true
---

# Release 2026.04

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.35           | Yes            |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.17          | Yes            |
| Redis         | v6.2.20        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 8.19.13        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7.1       | -              |
| Erlang   | 26.2.5.11      | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

<details>

<summary><strong>Current service version numbers</strong></summary>

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>c7574116b1803a674727a1776e91643f9d95b057</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>02e3643398291ece611cac519419c1f1f8a72958</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>6e9a6541951b7627a96327b878322e25ae534e6a</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.1.4</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>7a872ca5e928cea6875296350e06a9e8737d518c</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3</td><td>-</td></tr><tr><td><code>engine</code></td><td>55e3b27-20260529</td><td>Yes</td></tr><tr><td><code>execution-controller</code></td><td>59ec8aed7f867e409badc4a160b026af41ef2e1f</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>84bed5ea52d5feab52657423a4882c3d724c898a</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.25.1</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.61.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>2.4.2</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>8.19.13</td><td>Yes</td></tr><tr><td><code>lickman</code></td><td>ae63665271818a32d892623714966df13da7bf0d</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.7.0</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>7975c23b4675d437c8ffb90c2bb30ffb7ae27bae</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>59f44e25e7a394247000bcb1c76be89a2feaf15a</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>f3f259d8e036bd0d05f37e68699572c932032bd3</td><td>Yes</td></tr><tr><td><code>s3proxy</code></td><td>3.1.0</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>55e3b27-20260529</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.26.1</td><td>-</td></tr><tr><td><code>trigger</code></td><td>fc351241929dd1774a7cba09bbdd953bc1e30180</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>de3fda3f1ba64eb2c14f96205a5febdb929917ef</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>709887c160a7c9326fd9846b788c33e674935d0e</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>12d22018d4d7193f33f21a915c4337b1378592a0</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>12d22018d4d7193f33f21a915c4337b1378592a0</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

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
