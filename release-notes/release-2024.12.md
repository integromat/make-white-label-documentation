# Release 2024.12

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.28           | -              |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.5           | -              |
| Redis         | v6.2.10        | -              |
| MongoDB Cloud | 7.0            | Yes            |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7         | -              |
| Erlang   | 26.2           | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

### Current service version numbers

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

| Service                   | Version          | Version update |
| ------------------------- | ---------------- | -------------- |
| `accman`                  | 2.16.10          | Yes            |
| `apps-processor`          | v2.4.2           | -              |
| `aws-rds-log-reader`      | v1.0.2           | -              |
| `agency`                  | 4.0-beta         | -              |
| `broker`                  | 6.3.9            | Yes            |
| `cron`                    | v1.0.15          | -              |
| `datadog-agent`           | 7.40.1           | -              |
| `datadog-cluster-agent`   | 7.40.1           | -              |
| `db-updater`              | v1.5.79          | Yes            |
| `elasticsearch`           | 7.17.15          | -              |
| `emails-processor`        | v2.9.0           | -              |
| `engine`                  | v4.10.1          | Yes            |
| `gateway`                 | 3.11.0           | Yes            |
| `imt-auditman`            | 1.0.3            | -              |
| `ipm-server`              | v3.28.0          | -              |
| `ipm-service`             | v1.3.0           | -              |
| `kibana`                  | 7.17.15          | -              |
| `mongo`                   | 7.0              | Yes            |
| `mongo-auto-indexer`      | master           | -              |
| `nginx`                   | v1.22.1          | -              |
| `notifications-processor` | v2.5.0           | -              |
| `overseer`                | 4.5.0            | Yes            |
| `redis`                   | v6.2.10          | -              |
| `renderer-processor`      | v3.2.2           | -              |
| `scheduler`               | v4.10.1          | Yes            |
| `trackman`                | v2.11.0          | -              |
| `trigger`                 | 2.5.5            | Yes            |
| `web-api`                 | v5.15.0-hotfix.3 | Yes            |
| `web-streamer`            | 5.8.5            | Yes            |
| `web-zone`                | v4.62.0          | Yes            |

## Public-facing changes

### Improvements and changes

* We revamped the toolbar in our scenario editor! We have made numerous visual and functionality improvements, like moving the Run once button into the toolbar or making the toolbar expandable. Read more about the new toolbar [here](https://www.make.com/en/help/scenarios/scenario-editor).

<figure><img src="../.gitbook/assets/new toolbar.png" alt=""><figcaption></figcaption></figure>

* The [subscenarios](https://www.make.com/en/help/scenarios/subscenarios) are have left the closed beta and are now available to users in organizations with the **Teams** or **Enterprise** plan.
* The custom IML function for developing custom apps has been re-enabled! It was disabled because of security reasons, and is now available again.
* We are migrating the existing custom apps to the new technology in batches, so it might take time until you can edit a custom IML function in an already existing custom app. You can read more about the re-enablement here.

### Fixed issues

* We fixed a bug that was causing an error when multiple scenarios were called in an array using the scenario ID. Now, multiple scenario ID values are passed in the scenario URL.

### Documentation updates

* [Types of modules](https://www.make.com/en/help/modules/types-of-modules) - We've updated the article to include complete information on each module type, along with their features and ways of usage. The advanced tips section offers expert users new tricks and examples for working with modules.
* **Make Public API Documentation** - We published the documentation for the keys API. You can check it out on our [Developer Portal](https://developers.make.com/api-documentation/api-reference/keys-1).

### Apps updates

New apps:

* [Schogini Image Wizard](https://www.make.com/en/help/apps/file-and-document-management/schogini-image-wizard) - Easily edit images with the new Schogini Image Wizard app, allowing you to blur, resize, rotate, and more, all within Make.
* [Poper](https://www.make.com/en/help/apps/website-building/poper) - Watch new leads in your Poper account using the new app in Make.

Updated apps:

* [SAP ECC Agent](https://www.make.com/en/help/apps/business-operations-and-erps/sap-agent) - We’ve created a custom function that lets you apply padding to any values across all SAP ECC Agent modules.
* [MailerSend](https://www.make.com/en/help/apps/marketing/mailersend) - Starting November 1, MailerSend has made changes that affect all modules. Check out the article and take the necessary steps to ensure smooth work with MailerSend.
* [Anthropic Claude](https://www.make.com/en/help/apps/it-and-development/anthropic-claude#anthropic-claude-2014867) - There is a new **Make an API Call** module for Anthropic Claude.
