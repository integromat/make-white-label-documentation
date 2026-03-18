# Release 2025.02

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.30           | -              |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.12          | Yes            |
| Redis         | v6.2.16        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7         | -              |
| Erlang   | 26.2.5.3       | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |



<details>

<summary><strong>Current service version numbers</strong></summary>

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th width="194.650146484375">Service</th><th width="354.890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.19.1</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>broker</code></td><td>cfe10e920b852308ed74b566e76d98a2f6e411e6</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>cfe10e920b852308ed74b566e76d98a2f6e411e6</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.16</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.63.3</td><td>Yes</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.63.3</td><td>Yes</td></tr><tr><td><code>db-updater</code></td><td>07d5ca7c165bdf50b48c20b4981c28c82774dd7b</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>v2.12.1</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>v5.2.0</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>37b91ec5580fe188afc9d0faf4a7810bec4b1f3c</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.3.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.34.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.5.5</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.6.0</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>ff79675e8e309e6f9265753d6cf684789ac45b04</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>3.2.5</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>v5.2.0</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.12.3</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.11.1</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>efb07c61d2da29ac934da2daf00a0d5426754cf1</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.11.1</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>0f8edfe1c849ed1c58c1019db27445e6a9869f99</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

### Improvements and changes

* We have improved the notes experience, making it easier and more enjoyable to create and manage notes. In addition to a fresh new look, notes now support rich text formatting. For more information, refer to our new [Scenario notes](https://help.make.com/scenario-notes) documentation.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* Managing operations at the team level is now easier with the new **Enterprise** feature, [Operations per Team Management](https://help.make.com/operations-per-team-management). Benefits include improved control over team consumption, operational continuity, real-time monitoring of operations usage, flexibility in operations allocation, and proactive usage notifications.
* You can now connect third-party apps or clients with Make using the **OAuth 2.0** protocol. Check out the latest updates in our [Make API documentation update](https://developers.make.com/api-documentation/authentication/requesting-an-oauth-2.0-client).
* We’ve added more filter options to our [Analytics dashboard](https://help.make.com/analytics-dashboard), available to **Enterprise** users. Additional filters include **Status**, **Team**, and **Folder** for overall stats, with **Executions Change** and **Folder** now available in the scenario breakdown.
* Scenario execution history can now be exported into a CSV file. This is a useful option for users who want to analyze their scenario execution history in an external system. Before exporting, you can choose to hide check runs or the change log, depending on what data you want to include in the file.
* You can now rename keys without specifying their values. Previously, when renaming keys, you had to provide the current values. If you did not, the values would be replaced with blank entries.

### Apps updates

New apps:

* [Bluesky](https://www.make.com/en/help/apps/marketing/bluesky) - A social media platform designed for open and independent networking. This new app lets you connect with Bluesky to manage users, posts, messages, media, likes, and lists in your account.
* [ClickFunnels 2.0](https://www.make.com/en/help/apps/marketing/click-funnels-2) - We have a new version of ClickFunnels. This version allows you to monitor contacts, orders, and form submissions, as well as manage contacts and orders in your ClickFunnels account.

Updated apps:

* [OpenAI](https://www.make.com/en/help/ai-in-make/openai--dall-e---chatgpt-) - The **GPT-4o** and **GPT-4o-mini** series of models now include a new [Predicted Outputs](https://platform.openai.com/docs/guides/predicted-outputs) parameter in the **Create a Completion** module. Additionally, **o3** models are now supported in this module, and this update has also been reflected in the documentation.
* [Workday Human Capital Management](https://www.make.com/en/help/apps/hr-management/workday-human-capital-management) - A new **Make a REST API Call** module has been released to enable interaction with Workday's API for greater flexibility.
* [Make](https://www.make.com/en/help/apps/process-management/make) - We have released the following **Incomplete Scenario Executions** modules that allow you to manage and monitor incomplete executions effectively:
  * List scenario incomplete executions
  * Get incomplete execution detail
  * Retry incomplete executions in a scenario
  * Delete incomplete executions in a scenario
* [Workday Financial Management](https://www.make.com/en/help/apps/business-operations-and-erps/workday-financial-management) - The **Make a REST API Call** module has been added, allowing users to interact with Workday's API for enhanced flexibility.
* [Salesforce](https://www.make.com/en/help/apps/crm-and-sales-tools/salesforce) - A new module, **Make an API Call (Advanced)**, has been added, allowing for advanced API interactions with Salesforce.
* [Ablefy](https://www.make.com/en/help/apps/commerce/elopage) - Elopage has been rebranded as Ablefy. This change has been reflected in our documentation to ensure consistency and clarity.
* [Google Vertex AI (Gemini)](https://www.make.com/en/help/apps/ai/google-vertex-ai) - We have added new modules that allow you to create and process images:
  * Generate an Image
  * Generate an Image Caption
  * Generate an Answer for an Image
*   [Runway](https://www.make.com/en/help/apps/file-and-document-management/runway-ml-api) - In the **Generate a Video from Image(s)** module, we have added two new fields: **First URL** and **Last URL**, which require an HTTPS URL pointing to an image used to generate the video. The **Ratio** field has also updated values to select.

    Additionally, we have added a new field **API version** into the **Make an API Call** module.
* [Front](https://www.make.com/en/help/apps/productivity/front) – We have updated the Front app logo to match the latest branding.
* [ClickFunnels Classic](https://www.make.com/en/help/apps/marketing/clickfunnels) - The previous version of ClickFunnels has been renamed due to the API deprecation. The new version, [ClickFunnels 2.0](https://www.make.com/en/help/apps/marketing/click-funnels-2), is now available.
* [Base.com](https://www.make.com/en/help/apps/commerce/baselinker) – The BaseLinker app has been updated and renamed to Base.com, along with a new logo.
