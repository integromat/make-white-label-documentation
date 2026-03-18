# Release 2025.04

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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.21.0</td><td>-</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>broker</code></td><td>2dad9efdfaf93442aad26119cb3439b8e0241017</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>2dad9efdfaf93442aad26119cb3439b8e0241017</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.16</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>f5d05cb282bb99d3fe37949cdb2a33bd778ccf0f</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>ef03ad0cf2b1a133549548a7f1ce4dcd7b76a091</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>9afad03-20250509</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3f5049cdd7c4330ab3df456cfb13ec12afde0abd</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.5.0</td><td>-</td></tr><tr><td><code>ipm-server</code></td><td>3.39.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>1.8.5</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>make-apps-processor</code></td><td>1.3.3</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.6.1</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>7722bbaad8d1494897c3bf4365b41be81dddb7d0</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>3.2.6</td><td>-</td></tr><tr><td><code>scheduler</code></td><td>9afad03-20250509</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.14.0</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>2.24.1</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>7d840057e77a6e3cb210def44a6dffeeea7a234f</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>6.2.2</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>v4.67.0</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>4.66.2</td><td>-</td></tr></tbody></table>

</details>

## New On-premise Services

We're introducing two new services to improve how applications are managed in your On-premise environment: **Zone Assets Server** and **Make Apps Processor**. These services streamline operations and enhance reliability for self-hosted deployments. To deploy these new services, follow the steps outlined in [Set up Helm charts](../set-up-helm-charts.md) guide.

### Zone Assets Server

**What it does:** The Zone Assets Server is a dedicated service that delivers essential files and resources (assets) directly within your On-premise infrastructure. Think of it as a local content delivery system that ensures your applications can quickly access everything they need to run smoothly.

**Why this matters:** Previously, each application had to manage its own assets internally, which added complexity. By centralizing asset delivery through a dedicated service, we're simplifying our core applications and making the overall system more maintainable.

**Technical details:** This NestJS-based file server contains all the assets that would normally be stored in cloud-based content delivery networks (CDNs). Since CDNs aren't practical for self-hosted environments, this service provides a local alternative that packages all necessary assets in a separate, containerized service.

#### **Zone Assets Server Deployment**

**Current status:** The Zone Assets Server is already running in your environment but isn't active yet. Your web-zone container still uses its internal asset packages as before.

**What's coming:** In an upcoming release, we'll activate the new system. When this happens:

* The web-zone container will stop bundling its own assets
* Instead, it will retrieve assets from the Zone Assets Server
* This transition will be automatic and require no action from you

**Resource allocation**

The Zone Assets Server has the following memory configuration:

*   Requested memory: `128Mi`

    This is the minimum amount of memory the service needs to start and run.
* Memory limit: `512Mi`\
  This is the maximum amount of memory the service is allowed to use.

### Make Apps Processor

**What it does**: The Make Apps Processor automatically handles application updates by compiling your app changes into native formats and deploying them to your IPM server. This streamlines the entire application deployment process.

**Service transition**: This new service will replace the current Apps Processor (apps-processor) in an upcoming release, providing enhanced functionality and improved reliability.

**Resource allocation**

The Make Apps Processor is optimized for low resource usage and stable performance. Here’s the recommended configuration:

*   Recommended memory: `1024 MB`

    This gives the service enough memory to compile and deploy your applications efficiently.
*   Recommended CPU: `1/3 vCPU`

    The service runs smoothly with low CPU usage. This setting is enough for stable performance.

{% hint style="info" %}
No immediate action is required for either service. Both are being deployed as part of your regular update cycle and will be activated automatically when ready.
{% endhint %}

## Public-facing changes

### Improvements and changes

#### Make﻿ TypeScript SDK now available

We've added a new client library to our API documentation – the [Make TypeScript SDK](https://developers.make.com/api-documentation/client-libraries). This library provides developers with:

* Comprehensive type definitions
* Support for most Make API endpoints
* Built-in error handling
* Response typing

The SDK is fully compatible with pure JavaScript projects, allowing seamless integration regardless of your preferred development approach.

#### Improved collection handling

We've simplified your workflow with automatic collection conversion. When mapping a collection to a text field, Make now automatically converts it to a JSON string for you. This eliminates the manual conversion step previously required, saving you time and reducing potential errors in your scenarios.

### Apps updates

#### New apps

* [SAP SuccessFactors](https://apps.make.com/sap-successfactors) - A cloud-based human capital management software that helps companies manage employee information. You can now retrieve and search for the records in your SAP SuccessFactors account.
* [XLSX](https://apps.make.com/xls) - The XLSX app is our built-in app available on all plans. It allows you to aggregate data in an XLSX file without the need to connect to the Microsoft 365 Excel app.
* [Amazon Bedrock](https://apps.make.com/amazon-bedrock) - We've released the new Amazon app. You can now build AI-powered automations that create text, images, or chat responses using your Bedrock setup.
* [Clay](https://apps.make.com/clay) - The new Clay app lets you create new webhook records in your Clay tables.

#### Updated apps

* [OpenAI](https://apps.make.com/openai-modules#67hWK) - The OpenAI app now includes four new modules that help you manage model responses more effectively:
  * List Input Items
  * Get a Model Response
  * Create a Model Response
  * Delete a Model Response
* [xAI](https://apps.make.com/xai) - A new module called Generate an image is now available. It lets you create images based on a prompt.
* [Monday.com](https://apps.make.com/monday) - We have two new modules that will let you monitor the events and search items in the board by column values:
  * Watch Events
  * Watch Events\
    Search Item sin the Board by Column Values (advanced)
* [Facebook Pages](https://apps.make.com/facebook-pages) - A new module is now available that lets you publish Reels directly to your Facebook Page:
  * Publish a Reel
* [Crowdin](https://apps.make.com/crowdin) - The app now supports both OAuth and API key authentication, giving you two different ways to create a connection.
