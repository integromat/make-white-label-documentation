# Release 2024.13

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.30           | Yes            |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.5           | -              |
| Redis         | v6.2.16        | Yes            |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7         | -              |
| Erlang   | 26.2.5.3       | Yes            |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

## Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

| Service                   | Version          | Version update |
| ------------------------- | ---------------- | -------------- |
| `accman`                  | 2.16.11          | Yes            |
| `apps-processor`          | v2.4.3           | Yes            |
| `agency`                  | 4.0-beta         | -              |
| `aws-rds-log-reader`      | v1.0.2           | -              |
| `broker`                  | 6.3.11           | Yes            |
| `broker-gw-logger`        | 6.3.11           | -              |
| `cron`                    | v1.0.15          | -              |
| `datadog-agent`           | 7.58.1           | Yes            |
| `datadog-cluster-agent`   | 7.58.1           | Yes            |
| `db-updater`              | v1.5.81          | Yes            |
| `emails-processor`        | v2.10.0          | Yes            |
| `engine`                  | v4.11.2          | Yes            |
| `gateway`                 | 3.13.5           | Yes            |
| `imt-auditman`            | 1.0.3            | -              |
| `ipm-server`              | v3.29.0          | Yes            |
| `ipm-service`             | v1.4.0           | Yes            |
| `kibana`                  | 7.17.15          | -              |
| `mongo-auto-indexer`      | master           | -              |
| `nginx`                   | v1.22.1          | -              |
| `notifications-processor` | v2.5.1           | Yes            |
| `overseer`                | 4.5.0            | -              |
| `renderer-processor`      | v3.2.2           | -              |
| `scheduler`               | v4.11.2          | Yes            |
| `trackman`                | v2.11.2          | Yes            |
| `trigger`                 | 2.5.5            | -              |
| `web-api`                 | v5.18.1-hotfix.3 | Yes            |
| `web-streamer`            | 5.9.0            | Yes            |
| `web-zone`                | v4.63.0          | Yes            |

## Public-facing changes

### Improvements and changes

* Users can now update their existing connections when their credentials change, instead of creating and reconfiguring new connections.

<div align="center"><figure><img src="../.gitbook/assets/Editable connections.png" alt="" width="375"><figcaption></figcaption></figure></div>

* The [scenario inputs](https://www.make.com/en/help/scenarios/scenario-inputs) are now available to all Make users. Previously, scenario inputs were available only to users in organizations with the Pro plan or higher.
* The scenario entity in the Make API now has the `isActive` parameter. This parameter shows whether a scenario [is active](https://developers.make.com/api-documentation/api-reference/scenarios). The `islinked` parameter is now deprecated. Make API still returns the `islinked` parameter for backward compatibility.
* Custom app developers now have the ability to utilize data structures directly within custom apps. Users can create a data structure and integrate it into their app, similar to how data structures function in data stores.
* Previously, when a Team Admin only had an organization member role, they were unable to add new users to the team. Now, a Team Admin with a member role can see all the organization users and add users to the team.
* Custom app developers can now add a banner to the module settings. You can use banners in module settings to highlight new features or announce changes.

### Fixed issues

* When parsing a date with the `parseDate` function in the timestamp format in milliseconds, users had to convert the timestamp to a number first. This is no longer required. The `parseDate` function converts timestamps in seconds or in milliseconds directly.
* Previously, attempting to add a custom property would result in an error stating that the property data already exists if there was an empty value for that property. Now, the function recognizes an empty object as a condition and allows the user to add the new property without receiving an error.

### Documentation updates

* [LinkedIn Conversions API](https://www.make.com/en/help/apps/marketing/linkedin-conversions-api) - We improved our documentation, so now you have new tips and examples for using fields in the app modules.
* [Zenler](https://www.make.com/en/help/apps/education/zenler) - We've updated the Zenler app documentation to ensure all information is clear and accurate for an improved user experience.
* [NocoDB](https://www.make.com/en/help/apps/it-and-development/nocodb) - New documentation for the NocoDB app is now available, detailing how to create the integration in Make.
* [Projectworks](https://www.make.com/en/help/apps/productivity/projectworks) - Updated documentation for Projectworks covers how to create connection and detailed module descriptions in Make.
* [Schogini AI Wizard](https://www.make.com/en/help/apps/ai/schogini-ai-wizard) - This app enables users to analyze sentiments, detect languages, extract contact details, and create YouTube metadata.

### Apps updates

New apps:

* [TikTok Audiences](https://www.make.com/en/help/apps/marketing/tiktok-audiences) - A new app that enables you to manage custom audiences, customer audience contacts, customer file audiences, and saved audiences directly from your TikTok Business account.
* [Lusha](https://www.make.com/en/help/apps/crm-and-sales-tools/lusha) - This new app helps businesses find accurate and verified contact and company information for easy prospecting and research.
* [xAI](https://www.make.com/en/help/apps/ai/xai) - An app enabling users to create text completions from prompts or chats, supporting streamlined automation and enhanced workflows.
* [Snapchat Conversions](https://www.make.com/en/help/apps/marketing/snapchat-conversions) - This new app allows you to directly send conversions event data to Snapchat's servers, improving conversion tracking accuracy and enhancing campaign performance through better measurement.

Updated apps:

* [LinkedIn Conversions API](https://www.make.com/en/help/app/linkedin-conversions-api#linkedin-conversions-api) - The documentation has been updated with additional details, including Salesforce configuration guidance, required LinkedIn account permissions, and steps for setting up conversion events.
* [Snack Prompt](https://www.make.com/en/help/app/snack-prompt) - We've updated the documentation to include more detailed information about the modules in the app.
* [ServiceNow](https://www.make.com/en/help/apps/customer-support/servicenow#servicenow) - We have a new connection type that uses custom app client credentials. Our documentation has been updated to explain both connection types.
* [LinkedIn Conversion API](https://www.make.com/en/help/apps/marketing/linkedin-conversions-api) - Now you can associate multiple campaigns with a conversion rule: just add as many campaigns as you want by their IDs.
* [Klaviyo](https://www.make.com/en/help/apps/marketing/klaviyo) - We removed the following modules due to API deprecation:
  * Watch Events Profiles
  * Watch Event Metrics
  * Watch Profiles on a List
  * Watch Profiles on a Segment
