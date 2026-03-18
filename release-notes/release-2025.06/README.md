# Release 2025.06

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.33           | Yes            |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.12          | -              |
| Redis         | v6.2.16        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7.1       | Yes            |
| Erlang   | 26.2.5.11      | Yes            |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

<details>

<summary><strong>Current service version numbers</strong></summary>

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>f54c9fba8d9856b5d6304517b3871fe4ff294b75</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>Yes</td></tr><tr><td><code>broker</code></td><td>2acbedef60afa6be8a3bab0139bdb4e1c651f7e7</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>2acbedef60afa6be8a3bab0139bdb4e1c651f7e7</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.0</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>1346627ccc53a5a06070d93d0a4493ebdffdfbcf</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>14147969a6259d0969168433927553803fc9cf01</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>9c0da38-20250708</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>7ca2bbd95a216a4adb17844d3add1113edd47ad6</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.7.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.46.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>1.9.1</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>lickman</code></td><td>3de28dd5893d647a28260e51c058a79f95623a79</td><td>-</td></tr><tr><td><code>make-apps-processor</code></td><td>1.4.0</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.27.4</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>d53c36e858f2d9fdb5be7d64b610d26405a80d62</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>b677aa22c364c453d590c057a526c03598e8c16f</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>b4b9a3b8c861532a1342f041c6d2edf7e0643d00</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>6f52b202697237178ec66a211ded5db2e25d6d36</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>9c0da38-20250708</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.17.1</td><td>-</td></tr><tr><td><code>trigger</code></td><td>06d5ee367beec935c40c6c10c31ec1400b00c08e</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>hot-fix-3-2025-6</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>b84110f1a5ba7b0d5faee2a837ca0a682271049b</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>2025.06-1</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>2025.06</td><td>Yes</td></tr></tbody></table>

</details>

## New service: Lickman <a href="#new-service-roleman" id="new-service-roleman"></a>

We're introducing a new service designed to manage lifecycle of licenses and provides the system with the ability to respond to changes in organization licenses and license parameters.

**What it does:** Lickman manages the available license parameters recognized by the system.

**What's coming:** In an upcoming release, we'll deploy the Lickman service to your environments. Here are the key aspects:

* The Lickman service will be installed and ready for use.
* Changes to the licenses will continue operate normally.
* Service-to-service communication for Lickman will be activated in this release.
* There will not be any data migration other than automatic bootstrap.

**Why this matters:** This update is **required**. Deploying Lickman is requisite for keeping the licenses in healthy state.

#### **Resource allocation**

The Lickman has the following memory configuration:

*   Requested memory: `128Mi`

    This is the minimum amount of memory the service needs to start and run.
*   Memory limit: `256Mi`

    This is the maximum amount of memory the service is allowed to use.

## Public-facing changes

#### New apps

* [Pictory](https://apps.make.com/pictory) - This AI-powered platform enables you to create and edit engaging videos quickly and easily. You can manage transcriptions, summaries, and video generation in your Pictory account using this new app.
* [Postiz](https://apps.make.com/postiz) - This open-source social media tool lets you create, update, and delete posts, upload files, and retrieve post data from your Postiz account—directly within your scenarios.

#### Updated apps

* [OpenAI](https://apps.make.com/openai-gpt-3) - We’ve added new parameters to our Create a Model Response module and Create a Completion module.
* [Shopify](https://apps.make.com/shopify) – We’ve released an updated version of the Shopify app using the GraphQL API, offering better performance and improved data handling. To learn more, see [Shopify tips and examples](https://apps.make.com/shopify-tips-and-examples).
* [Webhooks](https://apps.make.com/gateway) - You can now attach multiple API keys to your custom webhook. This feature provides an extra layer of security to control access management.
* [Make](https://apps.make.com/make) - Connections to the Make app can now be established using OAuth2 or an API key.
* [Salesforce Pardot](https://apps.make.com/salesforce-pardot) - It’s now possible to connect using OAuth client credentials, streamlining the authentication process.
* [Calendly](https://apps.make.com/calendly) - We've added a new module: **Cancel an Event**.
* [LiveChat](https://apps.make.com/livechat) - A new connection procedure has been imlpemented for LiveChat, requiring your client credentials.
* [Printful](https://apps.make.com/printful) - The API key connection type has been deprecated. You can now create a connection using client credentials.
