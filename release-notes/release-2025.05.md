# Release 2025.05

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.30           | -              |

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
| RabbitMQ | 3.13.7         | -              |
| Erlang   | 26.2.5.3       | -              |

### Filesystem

| Software | Version number | Version update |
| -------- | -------------- | -------------- |
| NFS      | 4.1            | -              |

<details>

<summary><strong>Current service version numbers</strong></summary>

The following are the current version numbers for services. You can verify them in your instance by going to **Administration > Monitoring**.

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.21.0</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>broker</code></td><td>0b2a6125277ff25e5d11675cf14cc6993083f207</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>0b2a6125277ff25e5d11675cf14cc6993083f207</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.17</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>1052b9568afa6f7e877fd05b26b7ab879efd1fea</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>4605b5792979582d4de8b159da769bd5e3c57d7a</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>d192e67-20250529</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>92d64e31446482686dceb6711f0b9192c9a30217</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.6.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.43.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>1.8.5</td><td>-</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>make-apps-processor</code></td><td>1.3.3</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.27.4</td><td>Yes</td></tr><tr><td><code>notifications-processor</code></td><td>v2.6.1</td><td>-</td></tr><tr><td><code>overseer</code></td><td>0255226f99c3262eedcf537fadf397159e10bde9</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>3.3.1</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>81f5f7b33f957d5b28ab85d627c0f97de41eba5a</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>d192e67-20250529</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.17.1</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.24.2</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>2e3c98995e680bb6efba30ba76930becf4ab155f</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>6.3.1</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>69f3a56462ffb4fd38c193cc1d9ed673e811938e</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>4.66.2</td><td>-</td></tr></tbody></table>

</details>

## New service: Roleman

We're introducing a new, dedicated service: **Roleman**. This service is designed to improve how we manage user permissions and roles across our platform.

**What it does:** Roleman serves as the central source for all authorization data within our platform. Release of this service allows us to deliver more powerful, adaptable, and advanced permission-based functionalities.

**What's coming:** In an upcoming release, we'll deploy the Roleman service to your environments. Here are the key aspects:

* The Roleman service will be installed and ready for use
* Existing permissions and roles will continue to function exactly as they do.
* Service-to-service communication for Roleman will not be activated in this release.
* There will not be any data migration (e.g., of existing roles and permissions) to Roleman in this release.

**Why this matters:** This update is **required**. Deploying Roleman is a mandatory prerequisite for an upcoming release, which will automatically migrate existing roles and permissions to Roleman. Skipping this update is not an option.

A future release will automatically migrate all existing roles and permissions to the new Roleman service. This upcoming deployment is required to enable that process. Setting up Roleman now ensures a smooth transition later.

**Resource allocation**

The Roleman has the following memory configuration:

*   Requested memory: `128Mi`

    This is the minimum amount of memory the service needs to start and run.
*   Memory limit: `512Mi`

    This is the maximum amount of memory the service is allowed to use.

## Public-facing changes

#### Make AI Tools now available in Open Beta

We're excited to launch Make AI Tools for all paid plan customers. This pre-built app includes 9 AI modules that handle common tasks like sentiment analysis, text categorization, and language translation — all without needing to write prompts or set up third-party AI accounts.

{% hint style="info" %}
For more details, refer to the [Make Help Center](https://help.make.com/make-ai-tools-now-available-in-open-beta).
{% endhint %}

#### UI updates to module rename panel

We've enhanced the module renaming experience with an updated panel design that's more intuitive and user-friendly.

<figure><img src="../.gitbook/assets/image (7).png" alt="" width="375"><figcaption></figcaption></figure>

### Apps updates

* [OpenAI](https://apps.make.com/openai-gpt-3) - You now have access to OpenAI's most advanced models:
  * **GPT-4.1** - Enhanced reasoning and problem-solving capabilities
  * **o4** - Optimized for complex tasks with improved accuracy
* [Google Vertex AI (Gemini)](https://apps.make.com/google-vertex-ai) - New Gemini models are now available in the app:
  * **Gemini 2.5 Flash** - Faster responses for everyday tasks
  * **Gemini 2.5 Pro** - Advanced capabilities for complex scenarios
* [YouTube](https://apps.make.com/youtube) - We have two new modules available in the app:
  * **Delete a Video** - Remove videos directly from your channel
  * **Make an API Call** - Access any YouTube endpoint for custom integrations
