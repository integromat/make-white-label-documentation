# Release 2024.04

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
| MongoDB Cloud | 5.0.24         | -              |
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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>v2.15.1</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.3.0</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.1.1</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.71</td><td>Yes</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.5.1</td><td>-</td></tr><tr><td><code>engine</code></td><td>v4.3.0</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.6.2</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>v3.21.2</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>4.4.1</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.2.0</td><td>-</td></tr><tr><td><code>overseer</code></td><td>4.3.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v2.2.1</td><td>-</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v4.3.0</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.6.0</td><td>-</td></tr><tr><td><code>trigger</code></td><td>2.2.0</td><td>-</td></tr><tr><td><code>web-api</code></td><td>v4.31.0-hotfix-2</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.4.2</td><td>-</td></tr><tr><td><code>web-zone</code></td><td>v4.47.0</td><td>Yes</td></tr></tbody></table>

## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* [Managing and rotating](https://www.make.com/en/help/access-management/saml-certificate-management) SAML service provider (SP) certificates became easier for the Enterprise customers. Organization owners can now activate, deactivate, copy, and download SP certificates within the SSO settings. They can also see which certificates are active. When it's time to rotate certificates, users will receive a notification from Make, giving them time to schedule the switch and minimize downtime. Additionally, we’ve extended the validity of SP certificates to three years, instead of just one. To learn more, check out our [SAML certificate management](https://www.make.com/en/help/access-management/saml-certificate-management) article.
* We've updated the banners that let you know when you've reached your operations limit. Now, when you see one of these banners, you'll get all the details about your upgrade options right there. If you decide to upgrade or purchase more operations, you can just click the link in the banner.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* Custom functions sometimes took too long to finish, which caused an error and disabled your scenario. We reviewed the timeout settings on custom functions. Before using custom functions, check the [limits](https://www.make.com/en/help/functions/custom-functions#limitations-of-custom-functions).
* Webhooks migrated from the Integromat platform sometimes returned a `ConnectionError`. We fixed the issue so your legacy webhooks remain stable.
* In some cases, domain verification did not work for SSO domain claim. Verification now works as expected.
* Sharable links to templates went to the organization dashboard. These links now go directly to the specific template.
* Switching from one team to another sometimes resulted in an error message. Navigating to a different team now works just fine.
* Clicking the **Details** button in the webhook queue resulted in an error. We fixed it, so you can see all the data that webhooks received.
* Make built-in functions that use timezone information, like the `addDays` function, didn’t work in custom functions. We fixed the custom function’s context, so now you can use the date functions in your custom functions.
