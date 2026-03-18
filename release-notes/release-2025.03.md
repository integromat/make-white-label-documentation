# Release 2025.03

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

<table><thead><tr><th width="194.58154296875">Service</th><th width="354.9583740234375">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>2.21.0</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.0</td><td>-</td></tr><tr><td><code>broker</code></td><td>7d091a0a7f47fd49a4dcf4ec225776f352c7cf28</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>7d091a0a7f47fd49a4dcf4ec225776f352c7cf28</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.0.16</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.63.3</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>350f0e6992863691c9579e18f0b9903c8c8186b0</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>v2.12.1</td><td>-</td></tr><tr><td><code>engine</code></td><td>7f437f3-20250319</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>aed888cb1f1275c97a1a682502582e444cb3b30c</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.5.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.34.0</td><td>-</td></tr><tr><td><code>ipm-service</code></td><td>1.8.2</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.22.1</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>v2.6.0</td><td>-</td></tr><tr><td><code>overseer</code></td><td>7722bbaad8d1494897c3bf4365b41be81dddb7d0</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>3.2.6</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>7f437f3-20250319</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>v2.12.3</td><td>-</td></tr><tr><td><code>trigger</code></td><td>2.20.0</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>fc8041262fc5fd6a953c06c7275be7f99f35ed31</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>6.1.3</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>v4.65.1</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

#### X (formerly Twitter) app integration discontinued

We are removing the X (formerly Twitter) app integration from our offering due to X's API policy requirements and pricing that prevent us from providing a reasonable integration to our customers. Starting April 3, 2025, you will not be able to create any new scenarios using the X (formerly Twitter) integration. For more details, refer to the [Make Help Center](https://help.make.com/x-formerly-twitter-app-integration-discontinued).

### Improvements and changes

* To ensure faster and more seamless payments, Wise has replaced PayPal as our exclusive payment provider for affiliates. When you register for the [affiliate program](https://help.make.com/affiliate-program#4-zYG), you’ll be asked to provide your Wise email address, account type, and preferred payout currency. If you're already part of the program, you can [update your account information](https://help.make.com/affiliate-program#61YP5) at any time.
* We've improved the way incomplete executions are retried. When retrying a large number of incomplete executions, we now limit how many are processed at the same time. This helps prevent retries from failing due to `RateLimitError` caused by too many simultaneous requests.
*   You can now write `/` in mapping fields to get completion suggestions based on what you write next.

    <figure><img src="../.gitbook/assets/image (10).png" alt="" width="540"><figcaption></figcaption></figure>
*   You can now map the entire output bundle from one module to another.

    <figure><img src="../.gitbook/assets/2025-04-17_10-40-33.png" alt="" width="375"><figcaption></figcaption></figure>

### Fixed issues

* Sometimes, a confirmation prompt to discard changes to scenario notes appeared even when you didn’t make any. This is fixed now.
* The app search wasn’t visible in rare cases when adding the first module to a new scenario. We fixed the issue so this doesn't happen anymore.

### Apps updates

New apps:

* [Adobe Workfront](https://apps.make.com/adobe-workfront) - A work management platform designed to help teams plan, execute, and deliver projects efficiently. This new app lets you connect with Adobe Workfront to manage tasks, projects, issues, and users directly from Make
* [Amazon Rekognition](https://apps.make.com/amazon-rekognition) - This new app lets you connect with Amazon Rekognition to detect objects, scenes, and faces; moderate content; and extract text from images and videos.
* [Kimi](https://apps.make.com/kimi) - AI language model developed by Moonshot AI that allows you to create chat completions and list the available models.

Updated apps:

* [OpenAI](../) - Now we support GPT-4.5 models. You can see the new GPT-4.5 group in the model selection dropdown.
* [Hugging Face](https://apps.make.com/huggingface) - Two new modules are now available:
  * Create a Chat Completion (Prompt)
  * Generate an Image
* [Twilio](https://apps.make.com/twilio) - A new module, Make an API Call for Lookup, is now available. This module lets you send custom API requests to Twilio's Lookup API, helping you retrieve information about phone numbers - such as line type, carrier, or caller name.
*   [ServiceTitan](https://apps.make.com/service-titan) - We've added a new connection type to reflect recent changes in the ServiceTitan app. You can now connect using either your own ServiceTitan application or the default Make

    ServiceTitan application.
* [Azure DevOps](https://apps.make.com/azure-devops) – From now you can choose between Azure DevOps and Azure DevOps (Azure App OAuth) when setting up a connection, giving you more flexibility in how you authenticate.
