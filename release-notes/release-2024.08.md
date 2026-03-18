# Release 2024.08

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Docker CE  | 24.0.6         | -              |
| Kubernetes | 1.28           | -              |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.5           | -              |
| Redis         | v6.2.10        | -              |
| MongoDB Cloud | 5.0            | -              |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.11.18        | -              |
| Erlang   | 25.3           | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

### Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.16.3</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.0</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.3.1</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.76</td><td>-</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.8.2</td><td>-</td></tr><tr><td><code>engine</code></td><td>v4.7.0</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.8.2</td><td>-</td></tr><tr><td><code>ipm-server</code></td><td>v3.25.1-hotfix-1</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.2.2</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>5.0</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>v1.0.0</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.4.1</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>4.4.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v4.7.0</td><td>Yes</td></tr><tr><td><code>redis</code></td><td>v6.2.10</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v4.7.0</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.9.1</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.5.0</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>v5.7.0-hotfix-3</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.6.1</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>v4.55.1</td><td>Yes</td></tr></tbody></table>

## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* We made an improvement to the scenario property creation process. Now, you can add new scenario properties directly from the table view without needing to go back to the **Organization → Scenario** properties tab. Newly created properties are immediately visible in the table. Note that the Table view is only available for the **Enterprise** accounts.
* Previously, if a folder had a long name, it was not possible to see the full name in the left sidebar. Now, hovering over a folder with a long name displays a tooltip showing the full name.
* The scenario editor has been updated for better usability. Previously, to add a new module, you had to hover over the last module to see the **+Add another module button**. Now, the button is always visible and shows a hint upon hover.
* We have released a new major version of our **Visual Studio Code** extension. The new version brings in the local development for apps, which enables you to use `git` versioning for custom app development.
* Local development for apps is currently in beta. Feel free to share your feedback!

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* We've updated how we track scenario operations. Now, the list includes operations used to resolve incomplete executions. Plus, the Make API endpoint for listing [scenario operations usage](https://developers.make.com/white-label-documentation/) also covers these operations.
* An issue was resolved where scenarios rarely ended with an error when processing items from the webhook queue with sequential processing enabled. The processing of webhook queue items with sequential processing enabled now works as expected.

### Apps updates <a href="#apps-updates" id="apps-updates"></a>

#### New apps: <a href="#new-apps" id="new-apps"></a>

* [SuiteDash](https://www.make.com/en/help/apps/productivity/suitedash) - We're excited to announce a new powerful CRM tool integration with Make! This highly requested app allows you to manage contacts and companies directly within your SuiteDash account. Now, you can automatically create tasks, projects, and update client information in SuiteDash based on triggers from other apps. Additionally, this integration ensures that data for contacts, invoices, and project statuses are synced and up-to-date across all platforms.
* [Chatdata](https://www.make.com/en/help/apps/communication/chatdata) - This new app is a platform that allows you to create AI chatbots using your chosen data or data provided by the service.
* [Iterable](https://www.make.com/en/help/apps/marketing/iterable) - This app allows you to manage user data and engagement efficiently. With Iterable, you can manage user information, track events, and lists, improving your communication with users

#### Updated apps: <a href="#updated-apps" id="updated-apps"></a>

* [Youtube](https://www.make.com/en/help/apps/marketing/youtube) - We’ve added new modules that will let you manage your videos, channels, and playlists.
* [SugarCRM](https://www.make.com/en/help/apps/crm-and-sales-tools/sugarcrm) - In the advanced settings section, we’ve added a new field API Version that will allow you to enter the version you want to work with.
* [OpenAI](https://www.make.com/en/help/ai-in-make/openai--dall-e---chatgpt-) - Introducing Batch Modules! Now you can work in bulk with our app’s functionality. We've added five new Batch modules and an Upload a File module.
* [Smartsheet](https://www.make.com/en/help/apps/productivity/smartsheet) - We’ve added a new Search Rows module.
* [BigQuery](https://www.make.com/en/help/apps/business-intelligence/bigquery) - We’ve added a new Get Query Results by Job ID module.
* [Hubspot CRM](https://www.make.com/en/help/apps/crm-and-sales-tools/hubspot-crm) - There is a new module named **Create or Update a Contact**. It creates a new contact if the specified email address in the properties does not exist; otherwise, updates the existing contact.
* [Google Sheets](https://www.make.com/en/help/apps/productivity/google-sheets) - We’ve added two new modules: **Bulk Add Rows (advanced)** and **Bulk Update Rows (advanced)** that works with multiple rows.
* [Anthropic Claude](https://www.make.com/en/help/ai-in-make/anthropic-claude) - The **Create a Message** module has been renamed to Create a Prompt.
* [Facebook Conversions API for CRM](https://www.make.com/en/help/apps/marketing/facebook-conversion-leads) - Previously named Facebook Conversion Leads, this app has a new video to walk you through the setup process.
* [Airtable](https://www.make.com/en/help/apps/database/airtable) - Four new advanced modules for bulk operations have been added to help you manage multiple records.
* [NetSuite](https://www.make.com/en/help/apps/business-operations-and-erps/netsuite) - There are two new modules added: **Search Records (Saved Search)** and **Watch Records (Saved Search)**.
* [Slack](https://www.make.com/en/help/apps/communication/slack) - We’ve updated the terminology within the app for better clarity. The following changes have been made:
  * **IM channel** → **Direct message**
  * **Multiple IM channel** → **Direct message to multiple people**
* [Mem](https://www.make.com/en/help/ai-in-make/mem) - The **Create a Mem** module has been renamed to **Create a Mem (Prompt)**.
* [Azure OpenAI](https://www.make.com/en/help/apps/ai/azure-openai) - The **Create a Completion** module has been renamed to **Create a Completion (Prompt)**.
