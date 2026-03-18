# Release 2024.03

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Docker CE  | 24.0.6         | -              |
| Kubernetes | 1.25           | -              |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 13.8           | -              |
| Redis         | v6.2.10        | -              |
| MongoDB Cloud | 5.0.24         | Yes            |
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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>v2.12.0</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.3.0</td><td>Yes</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.1.0</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.70</td><td>Yes</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.5.1</td><td>-</td></tr><tr><td><code>engine</code></td><td>v3.9.2</td><td>-</td></tr><tr><td><code>gateway</code></td><td>3.4.17</td><td>-</td></tr><tr><td><code>ipm-server</code></td><td>v3.20.0</td><td>-</td></tr><tr><td><code>ipm-service</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>4.4.1</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.2.0</td><td>-</td></tr><tr><td><code>overseer</code></td><td>4.3.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v2.2.1</td><td>-</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v2.10.3</td><td>-</td></tr><tr><td><code>trackman</code></td><td>v2.6.0</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.2.0</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>v4.29.0</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.4.2</td><td>-</td></tr><tr><td><code>web-zone</code></td><td>v4.45.4</td><td>Yes</td></tr></tbody></table>

## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* Using templates to create scenarios is now much easier and more flexible.
  * We added an X icon that allows you to easily close the module settings. This means you can now open and set up modules in any order you prefer.
* We introduced badges for each module to make sure you don't miss any important information:
  * A green badge indicates that all required fields are filled in.
  * An orange badge signals that you need to provide some additional information.
  * A gray badge reminds you that you still need to get started with setting up the module.
* Filters also now have setup status badges:
  * Checkmark means that your filter is set up and ready.
  * Asterisk means that your filter has unsaved changes.
* Once you complete the setup and all your badges turn green, you will see a side panel that gives you the option to run, edit, or schedule your scenario.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* In some cases, it was not possible to remove users from a deleted organization. You can now remove users from any organization as expected.
* If a scenario contained an iterator followed by an aggregator, sometimes it would get stuck when processing a large number of bundles. The scenario then failed to create scenario logs. Now scenarios run smoothly and create scenario logs.
* Switching from one team to another sometimes resulted in an error message. Navigating to a different team now works normally.
* Custom functions sometimes took too long to finish, which caused an error and disabled your scenario. We reviewed the timeout settings on custom functions. Before using custom functions, try to measure or evaluate how long they run before using them in production.
