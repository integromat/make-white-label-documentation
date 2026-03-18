# Release 2024.02

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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>v2.12.0</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.2.11</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.1.0</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.68</td><td>Yes</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.5.1</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>v3.9.2</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.4.17</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>v3.20.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>4.4.1</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.2.0</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>4.3.0</td><td>Yes</td></tr><tr><td><code>recycler</code></td><td>v2.2.1</td><td>-</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v2.10.3</td><td>-</td></tr><tr><td><code>trackman</code></td><td>v2.5.2</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.1.5</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>v4.26.0-hotfix-1</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.4.2</td><td>-</td></tr><tr><td><code>web-zone</code></td><td>v4.42.4</td><td>Yes</td></tr></tbody></table>

## Public-facing changes <a href="#public-facing-changes-custom-scenario-properties" id="public-facing-changes-custom-scenario-properties"></a>

### Custom scenario properties <a href="#public-facing-changes-custom-scenario-properties" id="public-facing-changes-custom-scenario-properties"></a>

Custom scenario properties let your users add customized metadata to organize their scenarios. For example, they can use this feature to add client emails, URLs, or any other information to a scenario and use it to filter and sort scenarios. You can find more details in our [public documentation of this feature](https://www.make.com/en/help/scenarios/custom-scenario-properties).

You can enable custom scenario properties by following the general procedure in the [Customize user access to features article](https://app.theneo.io/make/white-label-dev/customize-your-instance/customize-user-access-to-features#Feature-access). Use the license parameter `customProperties`. For users to access this feature, the parameter value must be higher than 0.

### Dynamic connections <a href="#dynamic-connections" id="dynamic-connections"></a>

Dynamic connections allow users to use their connections as [scenario inputs](https://www.make.com/en/help/scenarios/scenario-inputs). For example, a user creates a scenario with a dynamic connection. Other users with access to the scenario can input their connections instead of the original connections to run the scenario. To learn more about dynamic connections, check out the [article in our public Help Center](https://www.make.com/en/help/connections/dynamic-connections).

You can enable dynamic connections by following the general procedure in the [Customize user access to features ](https://developers.make.com/white-label-documentation/customize-your-instance/customize-user-access-to-features)article. Use the following license parameters: `dynamicDependencies` and `dynamicConnections`.

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* You can now get shared webhook URLs for apps directly in the native apps administration. Check the [dedicated section](https://app.theneo.io/make/white-label-dev/install-and-configure-apps/shared-webhooks) in the apps management.
* A link to [Make Community](https://community.make.com/) now appears in the sidebar Help submenu.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* The list of users for both organizations and teams only displayed 10 users. User lists now include all members.
* It wasn't possible to delete records in a webhook queue: the **Delete** button wasn't clickable.
* The infinite scroll in the scenario history wasn't infinite: it got stuck and didn't show all records. Now you have access to the full history.
* The hints for creating names of custom functions and scenario inputs were incorrect. The hints now show the correct requirements for custom function and scenario inputs names.
* Doubled and unaligned texts appeared when you clicked the **Create a connection** button. We solved it, so you have beautifully aligned and correct texts.
* When you tried to resolve incomplete executions, the **Run once** button wasn't clickable. Also, a module that caused an error lost its mapping. We fixed both issues.
* Mapping pills showed their raw name. Pills now have descriptive names.
* When you ran the **Explain flow** option and then deleted one or more modules, the dot showing the flow was stuck. We unfroze the dot, and now it shows the full flow (and takes into account the deleted modules).
* On **Administration** > **Roles**, the toggle buttons did not load properly. These buttons now appear and behave normally. Only users with the `SA` role can edit instance-level permissions.
