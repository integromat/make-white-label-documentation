# Release 2024.10

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

| Service                   | Version          | Version update |
| ------------------------- | ---------------- | -------------- |
| `accman`                  | 2.16.6           | Yes            |
| `apps-processor`          | v2.4.2           | -              |
| `aws-rds-log-reader`      | v1.0.2           | -              |
| `agency`                  | 4.0-beta         | -              |
| `broker`                  | 6.3.4            | Yes            |
| `cron`                    | v1.0.14          | -              |
| `datadog-agent`           | 7.40.1           | -              |
| `datadog-cluster-agent`   | 7.40.1           | -              |
| `db-updater`              | v1.5.77          | Yes            |
| `elasticsearch`           | 7.17.15          | -              |
| `emails-processor`        | v2.8.4           | -              |
| `engine`                  | v4.9.0           | Yes            |
| `gateway`                 | 3.8.6            | Yes            |
| `ipm-server`              | v3.27.0          | Yes            |
| `ipm-service`             | v1.2.2           | -              |
| `kibana`                  | 7.17.15          | -              |
| `mongo`                   | 5.0              | -              |
| `mongo-auto-indexer`      | master           | Yes            |
| `nginx`                   | v1.22.1          | -              |
| `notifications-processor` | v2.4.4           | Yes            |
| `overseer`                | 4.4.0            | -              |
| `recycler`                | v4.9.0           | Yes            |
| `redis`                   | v6.2.10.1        | -              |
| `renderer-processor`      | v3.2.0           | -              |
| `scheduler`               | v4.9.0           | Yes            |
| `trackman`                | v2.11.0          | Yes            |
| `trigger`                 | 2.5.2            | Yes            |
| `web-api`                 | v5.12.0-hotfix-1 | Yes            |
| `web-streamer`            | v5.7.0           | Yes            |
| `web-zone`                | v4.59.4          | Yes            |

## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Audit Logs release <a href="#audit-logs-release" id="audit-logs-release"></a>

We're excited to introduce [Audit Logs](https://www.make.com/en/help/access-management/audit-logs), a powerful new feature designed to help you monitor activities within your Make account! With Audit Logs, you can:

* **Track Key Events**: Stay informed about significant events in your Organization or Team, such as scenario creation or deletion, connection updates, user removals, and more.
* **Identify User Actions**: Easily see who did what and when, as Audit Logs provide the user’s name and a timestamp for each event.
* **Filter and Sort Easily**: Focus on the information that matters most by selecting a specific timeframe, filtering by event type, or tracking the actions of a particular user.
* **View Detailed Event Information**: Access comprehensive details for each event logged.

Audit Logs are available with the Enterprise plan, giving you enhanced visibility and control over your environment.

* Our DevTool, which helps users debug their scenarios, has been rebranded and is now called Make DevTool in the Chrome Web Store. If you’ve been using it before the name change, there’s no need to worry - it will continue to work as usual, just under a new name.
* Users with API access can now create up to 100 API tokens. The former limit was 5.
* We've added new sorting options to the Scenarios list, allowing you to sort scenarios alphabetically from A to Z or by creation date, either from newest to oldest or oldest to newest. Previously, sorting was only available in the Table view, and scenarios in the List view were sorted by status (active/inactive) and then alphabetically from A to Z.
* We're excited to announce that we've added new functions!
  * [Math functions](https://www.make.com/en/help/functions/math-functions):
    * `abs(number)` - returns the absolute value of an integer.
    * `median([array of values])` - returns the median values in a specified array.
    * `trunc(number)` - truncates a number to an integer.
    * `stdevS([array of values])` - returns the standard deviation of a specified array of sample values.
    * `stdevP([array of values])` - returns the standard deviation of a specified array of population values.
  * [String function](https://www.make.com/en/help/functions/string-functions):
    * `replaceEmojiCharacters(text)` - replaces emoji characters with the new string.
* When creating a new module in your custom app, you now have three options to choose from:
  * Add example code to the new module (default).
  * Create a blank module with no additional code.
  * Copy code from an existing module to clone it.

These options help you speed up the process of writing boilerplate code.

* User search no longer requires accents to find a match. Now, searching for a name like "Tomas" will return results for "Tomáš", "Tomás", and "Tomas", making it easier to find users with different accent marks.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* Previously, some scenarios would reach their run time limit earlier than expected. This issue has now been resolved, ensuring all scenarios run within their specified time limits.
* When a scenario was cloned in the Table view, the **Created By** column was left empty. Now, it shows the name of the user who created the original scenario. Please note that the Table view is available only for Enterprise customers.
* The links to incomplete executions in the notification emails sometimes didn't work. This issue has been fixed, and the links now function correctly.
* When manually resolving an incomplete execution, Make didn’t create a new incomplete execution if another module returned an error. This issue has been fixed, so a new incomplete execution is created if an error occurs during the resolution process.
* Before, when a scenario was cloned, the **Created By** column was empty. Now the name of the user who created the original scenario is shown.

### Documentation Updates <a href="#documentation-updates" id="documentation-updates"></a>

* We're excited to announce that we've updated our [Help Center page on operations](https://www.make.com/en/help/scenarios/counting-the-number-of-operations)! It now offers more detailed information, including how operations are used, how to count them, and what steps to take if you're approaching the operation limit of your Make plan.

### Apps updates <a href="#apps-updates" id="apps-updates"></a>

New apps:

* [Microsoft Advertising Conversions](https://www.make.com/en/help/apps/marketing/ms-advertising-conversions) - A new app allows managing offline and online conversions in your Microsoft Adversiting account.

Updated apps:

* [LinkedIn](https://www.make.com/en/help/apps/marketing/linkedin) - We have a new, secure connection method using **OpenID** that enhances privacy and security for your LinkedIn integrations. This feature is also available in certain LinkedIn apps.
* [Pipedrive CRM](https://www.make.com/en/help/apps/crm-and-sales-tools/pipedrive-crm#build-pipedrive-crm-scenarios) - We added a couple of new modules that allows you to list deals according to different criteria as well as watch emails.
* [Adobe Acrobat Sign](https://www.make.com/en/help/apps/file-and-document-management/adobe-sign) - Now you can define scopes for your connection if you have a custom application in your Adobe Acrobat Sign account.
* [UiPath](https://www.make.com/en/help/apps/business-operations-and-erps/uipath) - The On-prem connection type is no longer available to use.
* [Cin7 Core](https://www.make.com/en/help/apps/business-operations-and-erps/dear-inventory) - Dear Inventory has rebranded to Cin7 Core. We have updated our documentation to ensure it accurately reflects this change.
* [Active Campaign](https://www.make.com/en/help/apps/marketing/activecampaign) - We added new modules for working with custom objects in your Active Campaign account: **Create or Update Custom Object Records** and **List Custom Object Records**.
* [LinkedIn Lead Forms](https://www.make.com/en/help/apps/marketing/linkedin-lead-forms) - Previously we had two LinkedIn Lead Forms apps for working with forms and responses. Now you don’t have to split work - just use a new **LinkedIn Lead Forms** app
