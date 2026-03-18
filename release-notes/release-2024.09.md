# Release 2024.09

{% hint style="warning" %}
This release includes a crucial security fix for the sandbox across the entire platform. Please ensure that all your software and services are updated to the latest version as soon as possible.
{% endhint %}

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

<table><thead><tr><th>Service</th><th width="249">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.16.5</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.2</td><td>Yes</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.0.2</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>broker</code></td><td>6.3.2</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.14</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.40.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>v1.5.76</td><td>-</td></tr><tr><td><code>elasticsearch</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>emails-processor</code></td><td>v2.8.4</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>v4.8.1</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3.8.3</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>v3.25.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>v1.2.2</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo</code></td><td>5.0</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>v1.0.0</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.4.3</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>4.4.0</td><td>-</td></tr><tr><td><code>recycler</code></td><td>v4.8.1</td><td>Yes</td></tr><tr><td><code>redis</code></td><td>v6.2.10.1</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>v3.2.0</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>v4.8.1</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.10.0</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.5.1</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>v5.9.0-hotfix-1</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>5.6.3</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>v4.57.1</td><td>Yes</td></tr></tbody></table>

## Public-facing changes <a href="#public-facing-changes" id="public-facing-changes"></a>

### Improvements and changes <a href="#improvements-and-changes" id="improvements-and-changes"></a>

* Previously, the route order numbers were hidden by default when using a router in your Make scenario. We have now enabled the Show route order option as the default setting, making it easier to view and manage route orders.
* To help avoid accidental deletion of organizations or teams, we've added an additional step. Users now need to type the name of the organization or team to confirm the deletion.
* You can now update your keys in the Keys tab. To do so, navigate to the Keys tab, locate the key you want to update, and click the Edit button. Note that you can only overwrite the existing value with a new one. Both the previous and updated key values will not be visible when editing.
* We've added a Remember this device option for two-factor authentication (2FA). When enabled, this feature allows users to skip 2FA on the same device for 30 days. This option makes accessing your account faster and easier on trusted devices.
* Previously, the cloned Make scenarios were saved in the Uncategorized folder. Now, they stay in the same folder as the original scenario.
* Non-admin users can now decide to leave an organization, with the option to either keep or delete their connections. A confirmation window will appear to help them decide how to manage their connections.
* We’ve added helpful tooltips to the app search. Now, when you hover over the app type badge (Verified, Built-in, Community, etc.), a tooltip will appear, providing a clear explanation of what each badge represents.

### Fixed issues <a href="#fixed-issues" id="fixed-issues"></a>

* When using the Search or Get modules, if the processed data exceeded 3.5 MB and there were many output bundles, only the last set of bundles would be shown in the module's output. This issue has been resolved. Now, regardless of the amount of processed data or the number of output bundles, all bundles are displayed correctly in the module output.
* Sometimes, module outputs failed to load properly. We've fixed this bug and now you can see module outputs without any issues.

### Apps updates <a href="#apps-updates" id="apps-updates"></a>

#### New apps: <a href="#new-apps" id="new-apps"></a>

* [Canva](https://www.make.com/en/help/apps/marketing/canva) - This app provides an intuitive design platform that allows users to create professional-quality graphics and documents with ease, regardless of their design experience. Within Make, you can manage your design assets, folders, and other items to automate working with your projects.
* [Zoom](https://www.make.com/en/help/apps/communication/zoom-user) - Experience seamless virtual communication with high-quality video conferencing and easy screen sharing. Before Make had only Zoom for administrators, but now you can enjoy Zoom as a user: handle your webinars, meetings, chats, and cloud recordings from the user prospective.
* [Motion](https://www.make.com/en/help/apps/ai/motion) - Motion is a powerful productivity app designed to streamline task and project management with automated scheduling and time-blocking features. With Make modules, you can manage your tasks, projects, and comments.

#### Updated apps: <a href="#updated-apps" id="updated-apps"></a>

* [Zoom Administration](https://www.make.com/en/help/apps/communication/zoom) - The already existing Zoom app is now called Zoom Administration. You can use it if you have the administrator role in the Zoom account.
* [Active Campaign](https://www.make.com/en/help/apps/marketing/activecampaign) - We added several new modules such as **Watch Tasks**, **Watch Deals**, **Create a Deal** and others to let you leverage your data in a more flexible way.
* [Bird](https://www.make.com/en/help/apps/communication/bird) - This app, formerly known as MessageBird, has been rebranded. We’ve updated our documentation to reflect this change.
* [TikTok Campaign Management](https://www.make.com/en/help/apps/marketing/tiktok) - The existing TikTok app has been renamed to TikTok Campaign Management. This app allows you to manage your campaigns and ads in your TikTok Business account efficiently.
* [BambooHR](https://www.make.com/en/help/apps/hr-management/bamboohr) - The API key connection method has been deprecated. Now, only the OAuth connection is available for connecting the app.
* [OpenAI](https://www.make.com/en/help/ai-in-make/openai--dall-e---chatgpt-) - In the **Message an Assistant** module, you can now select a tool that a model will call.
* [Shortcut](https://www.make.com/en/help/apps/marketing/shortcut) - Previously called Clubhouse, this app is now named Shortcut. Our documentation has been updated to align with the new name.
* [Ortto](https://www.make.com/en/help/apps/marketing/ortto) - The app formerly known as Autopilot has been rebranded to Ortto. We’ve made updates to our documentation to reflect this rebranding
