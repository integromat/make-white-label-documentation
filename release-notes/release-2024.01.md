# Release 2024.01

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
| MongoDB Cloud | 4.4.26         | Yes            |
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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>v2.12.0</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.2.11</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.0.0</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.66</td><td>-</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.5.0</td><td>-</td></tr><tr><td><code>engine</code></td><td>v3.9.1</td><td>-</td></tr><tr><td><code>gateway</code></td><td>3.4.15</td><td>-</td></tr><tr><td><code>ipm-server</code></td><td>v3.19.0</td><td>-</td></tr><tr><td><code>ipm-service</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>4.4.1</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.1.1</td><td>-</td></tr><tr><td><code>overseer</code></td><td>4.2.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v2.2.1</td><td>-</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v2.10.3</td><td>-</td></tr><tr><td><code>trackman</code></td><td>v2.5.1</td><td>-</td></tr><tr><td><code>trigger</code></td><td>2.1.4</td><td>-</td></tr><tr><td><code>web-api</code></td><td>v4.23.0-hotfix-1</td><td>-</td></tr><tr><td><code>web-streamer</code></td><td>5.4.2</td><td>-</td></tr><tr><td><code>web-zone</code></td><td>v4.40.0</td><td>-</td></tr></tbody></table>

## Public facing changes <a href="#public-facing-changes-custom-scenario-properties" id="public-facing-changes-custom-scenario-properties"></a>

* Previously, when users reduced the number of settings in the module settings window, it didn't automatically adjust its size. But now, the window shrinks based on the number of settings you have.
* When users searched for an app to add to the Favorites list, the search didn't show results. We fixed it: users can search for an app and get relevant results.
* After users tried to resolve the Incomplete execution, the diagram didn't load. This UX issue doesn't exist anymore.
* fter users deleted a custom variable, an incorrect warning message popped up when you tried to save the scenario.
* The Auto-align feature refused to align all modules in scenarios. Currently, it aligns all modules in the scenario.
* When signing in with SSO, **Enter** did not always work. It's fixed so you can stay on your keyboard when logging in and not bother with clicking.
* In some cases, the list of organization members did not immediately update after inviting a new member. Invited members now appear as expected.
