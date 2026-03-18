# Release 2024.07

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
| MongoDB Cloud | 5.0.26         | -              |
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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.15.2</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.0</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.3.1</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.76</td><td>-</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.8.2</td><td>-</td></tr><tr><td><code>engine</code></td><td>v4.6.0</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.8.2</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>v3.23.0</td><td>-</td></tr><tr><td><code>ipm-service</code></td><td>v1.2.1</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>5.0</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>v1.0.0</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.4.0</td><td>-</td></tr><tr><td><code>overseer</code></td><td>4.4.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v4.6.0</td><td>Yes</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v4.6.0</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.9.0-hotfix-1</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.3.0</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>v5.5.0-hotfix-3</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.6.0</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>v4.53.3</td><td>Yes</td></tr></tbody></table>



## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* We added a new read-only **Audience URI** field to the SSO settings, where you can find the path to the `metadata.xml`. This can be useful for setting up SSO on the provider’s side. Also, we included a link to the documentation in the SSO settings so that users can access the information more easily.
* We created new Make API endpoints to help you monitor the usage of operations in your scenarios.
  * **Get scenario usage**: Returns the daily operation usage for a specific scenario over the past 30 days.
  * **Get team usage**: Returns the daily operation usage for all scenarios within a team over the past 30 days.
  * **Get organization usage**: Returns the daily operation usage for all scenarios across all teams within the organization over the past 30 days.

Learn more about them in the [Make API documentation](https://www.make.com/en/api-documentation).

* We updated the timezones for operations and data transfer in your organization and team dashboards. Instead of showing usage in GMT+0, the dashboards will now display data based on each user’s account timezone.
* The organization and team dashboards now include data from incomplete executions, covering both operations and data transfer usage.

{% hint style="warning" %}
If your Make scenarios frequently have incomplete executions, you may notice an increase in usage metrics on the dashboards.
{% endhint %}

* Previously, it was not possible to open a scenario in a new tab from the Table view of the **Scenarios** tab. Now, you can right-click on a scenario from the list and select the option to open it in a new tab. Note that the Table view is only available for the **Enterprise** accounts.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* We resolved an issue where, in rare cases, scenarios were running indefinitely and blocking the processing of webhook queue items. With this fix, scenarios will no longer get stuck, allowing the webhook queue items to be processed smoothly.

### Apps updates <a href="#apps-updates" id="apps-updates"></a>

#### New apps: <a href="#new-apps" id="new-apps"></a>

* [Crossbeam](https://www.make.com/en/help/apps/marketing/crossbeam) - This app helps you find potential partnerships among your customers and identify account overlap to uncover new leads and boost your sales.
* [watsonx.ai](https://www.make.com/en/help/apps/ai/watsonx-ai) - This AI app lets you generate responses to a prompt using a variety of large language models (LLMs).
* [Sage Intacct](https://www.make.com/en/help/apps/business-operations-and-erps/sage-intacct) - This app allows you to keep accounting, staff management tools, and reports in one place. Within Make, you can handle records in your Sage Intacct account.
* [Google Ads Reports](https://www.make.com/en/help/apps/marketing/google-ads-reports) - This app is an integral part of Google Ads that is responsible for marketing reports based on data in your Google Ads account.

#### Updated apps: <a href="#updated-apps" id="updated-apps"></a>

* [Firebase Cloud Messaging](https://www.make.com/en/help/apps/marketing/fcm) - It was required to enter additional credentials to create a connection before. Now you can just sign in to your Google account to work with Firebase Cloud Messaging and enjoy!
* [Stripe](https://www.make.com/en/help/apps/commerce/stripe) - In the beginning of June, Stripe will deprecate all API keys that you used to create a connection in Make. To prepare for this, we created a new connection type: Restricted API key. Don’t forget to switch to the new connection type to continue working with Stripe!
* [Google Chrome (v2)](https://www.make.com/en/help/apps/communication/chrome) - We’ve released version 2 of our Chrome app to align with the new API, so you can continue to send notifications through your browser.
* [Celoxis](https://www.make.com/en/help/apps/productivity/celoxis) - The API URL for Celoxis has been updated, ensuring all app parts and documentation reflect this mandatory change.
* [Custify](https://www.make.com/en/help/apps/business-intelligence/custify) - The app documentation has been updated with revised module names and improved structure.
