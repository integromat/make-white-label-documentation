# Release 2024.06

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
| MongoDB Cloud | 5.0.26         | Yes            |
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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>v2.15.2</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.0</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.3.1</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.73</td><td>-</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.7.0</td><td>-</td></tr><tr><td><code>engine</code></td><td>v4.5.2</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.8.0</td><td>-</td></tr><tr><td><code>ipm-server</code></td><td>v3.23.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.2.1</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>4.4.1</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>v1.0.0</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.4.0</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>4.4.0</td><td>Yes</td></tr><tr><td><code>recycler</code></td><td>v4.5.2</td><td>Yes</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v4.5.2</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.8.0</td><td>-</td></tr><tr><td><code>trigger</code></td><td>2.2.1</td><td>-</td></tr><tr><td><code>web-api</code></td><td>v5.2.0-hotfix-1</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.5.0</td><td>-</td></tr><tr><td><code>web-zone</code></td><td>v4.51.3</td><td>Yes</td></tr></tbody></table>



## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* We’ve added a small but important improvement to the **Users** tab. Now you can filter users by their role at both organization and team levels. Simply click on the filter icon and select the role that you would like to see in the list.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* Recently, when searching for modules in the scenario editor, the **Instant** tag was missing from instant triggers and they were mistakenly labeled as **ACID** (polling) triggers. This issue has been resolved, and it now works as expected.

### Apps updates <a href="#apps-updates" id="apps-updates"></a>

#### New apps: <a href="#new-apps" id="new-apps"></a>

* [Google Search Console](https://www.make.com/en/help/apps/marketing/google-search-console) - This app provides additional online marketing support to monitor and troubleshoot your website’s Google Search results.
* [Flodesk](https://www.make.com/en/help/apps/marketing/flodesk) - This app allows users to create visually engaging emails for designing and managing email marketing campaigns.

For more details, go to our [public release notes](https://www.make.com/en/help/release-notes).
