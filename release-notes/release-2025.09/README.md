# Release 2025.09

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.33           | -              |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.12          | -              |
| Redis         | v6.2.20        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 7.17.15        | -              |

### Message Queues

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| RabbitMQ | 3.13.7.1       | -              |
| Erlang   | 26.2.5.11      | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

<details>

<summary><strong>Current service version numbers</strong></summary>

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2ef07ff040c557917c474bf5c0546cbecd0dd335</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>da019774c6f3256f0fa227e35f1e2b0b6b541b75</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>da019774c6f3256f0fa227e35f1e2b0b6b541b75</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.71.1</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.71.1</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>eecd37967f7defbbde9ba5041b3a2909ed191e11</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>d494caac00faa491fd7a3d4c39692bef16560a69</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>35b2ef7-20251121</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>2e7b7af9bdaa8b3866a324badb30f310285ae3e8</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.11.2</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.52.0</td><td>-</td></tr><tr><td><code>ipm-service</code></td><td>2.1.2</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>lickman</code></td><td>085e06276ca2f17651af840870ac92d3a9323e4b</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.5.1</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>ca37f9e1f7604a90ccefce99c97e9301ef9ec262</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>254d9fcfdf64ca2d94ad87a7b87c1bef2a2d6193</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>dd9549e231da052a3f80034685b6c6ba37cf6542</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>35b2ef7-20251121</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.24.2</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>6d9b27d3a13f73fbe0e61c7673f3f51900e7018d</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>c4acf877e45178dcf8fbbe4e9328bb5fa97fa3b9</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>21451cc0ebb9a2a8d2d4b0412e9c76b84545bf0d</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>d903a9460ed996a4e27184fa74768d5697726e15</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>d903a9460ed996a4e27184fa74768d5697726e15</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

#### New Gmail app

We've released a new [Gmail](https://apps.make.com/google-email) app, that simplifies the setup and offers new module enhancements:

* **Easier setup**: Unlike [Gmail (Legacy)](https://apps.make.com/gmail-legacy), it doesn't require creating a Google Cloud Platform project and OAuth credentials for personal Gmail accounts.
* **New modules and improvements**: Additional parameters in existing modules plus new modules like **Reply to an Email**, **Search Emails**, **Get an Email**, **Send a Draft Email**, **List Email Attachments** a**nd Media** and **Make an API Call**.

{% hint style="info" %}
Learn more in our technical documentation: [Gmail app](https://apps.make.com/google-email)
{% endhint %}

***

#### Make AI Web Search

We've released Make AI Web Search, a built-in app that lets you search and get real-time information directly in your scenarios. You can run all web searches securely within Make, without relying on external integrations.

Use the **Generate a response** module to run a web search based on your prompt. You can select whether you want the AI's text response to be parsed as JSON and apply location-based filters. These options give you more control over the search context and the format of the AI-generated output, making the results easier to use in the rest of your scenario.

{% hint style="info" %}
Learn more in our technical documentation: [Make AI Web Search app](https://apps.make.com/make-ai-web-search)
{% endhint %}

***

#### New HTTP app

The new HTTP app is now available, giving you a simpler way to create powerful, secure, and scalable integrations with any API:

* **Easier setup**: An updated UI simplifies the workflow with HTTP requests.
* **Reusable data structures for request bodies**: A new data structure editor helps to ensure valid JSON requests and enables data reuse across scenarios.
* **New built-in pagination**: A new capability allows you to configure pagination directly within the module and retrieve large data sets in a structured, manageable way.
* **Full compliance with HTTP standards**: A new app is fully compliant with current HTTP standards and allows following redirects with 3xx status codes.
* **Secure keychain storage and management**: A secure keychain stores and encrypts API keys and tokens in one place, allowing simple rotation of keys and credentials management independently of scenarios.
* **Secure connections with Mutual TLS and proxy**: Support for Mutual TLS and configurable proxy settings enables encrypted and high-security connections.

***

#### LinkedIn Events

We've released a new LinkedIn app that allows users and organizations create and manage virtual or in-person events directly in Make.

{% hint style="info" %}
Learn more in our technical documentation: [LinkedIn Events app](https://apps.make.com/linkedin-events)
{% endhint %}

***

#### Updated apps

* [OpenAI (ChatGPT, Sora, DALL-E, Whisper)](https://apps.make.com/openai-gpt-3) — We’ve added new Video modules that let you generate and remix videos with Sora, track new video jobs, list and delete videos, and retrieve detailed video information. Module names were also refined for better clarity.
* [MCP Client](https://apps.make.com/mcp-client) — We've added **Execute an action with AI**, a new MCP Client module that uses AI to complete tasks with MCP tools. Select which tools the AI can access, describe the task, and the module automatically identifies and executes the right tool. Additionally, the list of verified remote MCP servers has been expanded. This update lets you securely connect to more trusted remote servers directly.
* [Notion](https://apps.make.com/notion) — The **Internal connection** type now works in all Notion modules that were missing it. You can now use this connection type in any Notion module.
* [Runway](https://apps.make.com/runway-ml-api) — We've added a new **Generate a Video from a Video** module that allows you to create an AI-generated video using an existing video and a text prompt.
* [Virtuagym](https://apps.make.com/virtuagym) — The Virtuagym connection process is now simpler. You no longer need to provide your username and password when creating a new connection.
* [Parseur](https://apps.make.com/parseur) — We've added a new trigger module, **Watch Process Failed**, that triggers when a process doesn’t complete successfully.
* [Frame.io](https://apps.make.com/frame-io) — A new version of the Frame.io app is now live. This new version ensures seamless integration and up-to-date functionality.
* [Tellent Recruitee](https://apps.make.com/recruitee) — The Recruitee app has been renamed to **Tellent Recruitee** reflect the platform’s rebranding.
