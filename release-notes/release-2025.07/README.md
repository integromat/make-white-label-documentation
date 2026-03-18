# Release 2025.07

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
| Redis         | v6.2.16        | -              |
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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>8b35353b81375e3d846e5adf568004d8408f942f</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>856514b68772203933f937e6aeab92262281a9d5</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>856514b68772203933f937e6aeab92262281a9d5</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.1</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.67.0</td><td>Yes</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.67.0</td><td>Yes</td></tr><tr><td><code>db-updater</code></td><td>41885cd3171a96db31834089d3f21be054da7108</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>7b0d096673ab2fccd6c066d89272630bbbfb0f7d</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>989dd81-20250828</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>pi-gateway-patch-1</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.9.1</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.51.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>1.11.0</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>lickman</code></td><td>190e70701155d6ed8aeb367c55c84e81ef70e289</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.5.0</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.27.4</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>c9dc63d306e074ed7a13a127bfa8d4c51ea27de9</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>pi-overseer-patch-1</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>5c217f801370cb2a1025a47f1e8656f025c58b19</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>6f2527b8e824538aa17e90790845f4fc3507e199</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>989dd81-20250828</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.18.1</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>245fc6c5c1b199ac060b00c047004c2fd83a4206</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>3e5c0cbee674a2cab93c64433993a8cf1d6ef127</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>035161fbc722691c7561757076386f221cd66f6e</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>2025.07-3</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>2025.07</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

#### Coming soon: credits as new billing unit in Make

**We're replacing operations with credits as our billing unit**, allowing for more flexible pricing that better reflects your actual usage of Make.

**The change**: You will be billed in credits instead of operations. Operations will refer to individual module runs that process or check for data, and credits will be what you buy and consume for those operations and other usage-based factors.

**Why it's happening**: The transition to credits enables a more flexible pricing model based on your actual usage of the platform, taking into account factors such as processing complexity or if Make's AI provider is used.

{% hint style="info" %}
To find out more about credits and what to expect, head to our [Credits](https://help.make.com/credits) documentation.
{% endhint %}

***

#### **Scheduling update for required scenario inputs**

Previously, it was unclear in the product that scenarios with required [scenario inputs](https://help.make.com/scenario-inputs-and-outputs) must have on-demand scheduling. Now, when you try to save a scenario with required scenario inputs, you will be prompted to update the scenario scheduling to on demand and save the scenario again.

***

#### **Updated apps**

* [OpenAI](https://apps.make.com/openai-gpt-3) — We now support **GPT-5** for more accurate responses, richer context understanding, and improved reliability in the OpenAI modules. This new model also handles longer inputs and produces higher-quality results for your scenarios.
* [Whatsapp Business Cloud](https://apps.make.com/whatsapp-business-cloud) — We’ve renewed the connection process for the WhatsApp Business Cloud app. Creating a connection is now simpler, as it does not require a Facebook Developer account. Additionally, **Watch Events** webhooks are now set up automatically.
*   [Slack](https://apps.make.com/slack) — Following Slack’s update to conversation rate limits, we’ve added a new optional field **Enable pagination** to the following modules:

    * Watch Public Channel Messages
    * Watch Private Channel Messages
    * Watch Direct Messages
    * Watch Multiparty Direct Messages
    * List Replies

    For more details, see the [Conversation rate limits in Slack](https://apps.make.com/slack#JB4tZ) section.
* [Runway](https://apps.make.com/runway-ml-api) — The Runway app has a new **Generate an image** module. Use it to create images directly in your Runway account from Make. Additionally, this module now supports **Gen-4 Image** model.
* [Zoho CRM](https://apps.make.com/zohocrm) — The Zoho CRM app in Make now supports all zones, so you can connect your account regardless of region.
* [Zoho Invoice](https://apps.make.com/zoho-invoice) — We’ve added full zone support to the Zoho Invoice app in Make. You can now connect your account from any region without restrictions.
