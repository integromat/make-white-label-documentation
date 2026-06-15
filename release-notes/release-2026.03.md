# Release 2026.03

## Current software version numbers

The following is a list of current software versions running in Make's release environment. You can also find announcements of planned updates and upcoming end-of-life support for specific versions here.

### Containerization

| Software   | Version number | Version update |
| ---------- | -------------- | -------------- |
| Kubernetes | 1.35           | Yes            |

### Databases

| Software      | Version number | Version update |
| ------------- | -------------- | -------------- |
| PostgreSQL    | 15.17          | Yes            |
| Redis         | v6.2.20        | -              |
| MongoDB Cloud | 7.0            | -              |
| ElasticSearch | 8.19.13        | -              |

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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>c7574116b1803a674727a1776e91643f9d95b057</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>02e3643398291ece611cac519419c1f1f8a72958</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>6e9a6541951b7627a96327b878322e25ae534e6a</td><td>-</td></tr><tr><td><code>cron</code></td><td>v1.1.4</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>7a872ca5e928cea6875296350e06a9e8737d518c</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3</td><td>-</td></tr><tr><td><code>engine</code></td><td>55e3b27-20260529</td><td>Yes</td></tr><tr><td><code>execution-controller</code></td><td>59ec8aed7f867e409badc4a160b026af41ef2e1f</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>84bed5ea52d5feab52657423a4882c3d724c898a</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.25.1</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.61.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>2.4.2</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>8.19.13</td><td>Yes</td></tr><tr><td><code>lickman</code></td><td>ae63665271818a32d892623714966df13da7bf0d</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.7.0</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>7975c23b4675d437c8ffb90c2bb30ffb7ae27bae</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>59f44e25e7a394247000bcb1c76be89a2feaf15a</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>f3f259d8e036bd0d05f37e68699572c932032bd3</td><td>Yes</td></tr><tr><td><code>s3proxy</code></td><td>3.1.0</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>55e3b27-20260529</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.26.1</td><td>-</td></tr><tr><td><code>trigger</code></td><td>fc351241929dd1774a7cba09bbdd953bc1e30180</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>de3fda3f1ba64eb2c14f96205a5febdb929917ef</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>709887c160a7c9326fd9846b788c33e674935d0e</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>12d22018d4d7193f33f21a915c4337b1378592a0</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>12d22018d4d7193f33f21a915c4337b1378592a0</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

#### Introducing new OpenAI Skills and Skill Versions modules

Make now supports **Skills** and **Skill Versions** in the OpenAI app. Use them to create reusable sets of instructions and tools, manage versions, and attach Skills to model responses in your scenarios.

With Skills, you can keep repeated AI instructions in one place instead of recreating them in each module. This helps you build more consistent AI-powered scenarios and update shared instructions more easily.

{% hint style="info" %}
For more information, refer to the [Make OpenAI Skills release note](https://help.make.com/introducing-new-openai-skills-and-skill-versions-modules).
{% endhint %}

#### App updates

[WhatsApp Business Cloud](https://apps.make.com/whatsapp-business-cloud) — You can now choose a setup type when creating a connection, so you can connect an existing WhatsApp Business Account, create a new one, or connect your WhatsApp Business App number.

The legacy connection type is also available as a fallback until **April 2027**, but new scenarios should use the embedded signup connection for better long-term compatibility.

The **Watch Events** trigger now accepts only the supported connection type to help prevent connection-related errors.

***

[NetSuite](https://apps.make.com/netsuite) — You can now clear existing field values in the **Create or Update a Record** module by mapping a field to null and enabling **Erase Null** Fields. This fixes an issue where null values didn’t remove existing data during **Update** or **Upsert** operations. The setting is disabled by default, so existing scenarios keep their current behavior.

***

[Bluesky](https://apps.make.com/bluesky) — The **Create a Post** and **Create a Reply** modules now include an optional **Size** field for images and videos. Map the Size output from the Upload Media module to help prevent \[400] InvalidSize errors when publishing posts with media. If you leave the field empty, Make uses the default maximum size.

***

[xAI](https://apps.make.com/xai) — The new **Create a response** module lets you generate AI responses with tools such as web search, X search, file search, a code interpreter, and custom functions.

***

[Fatture in Cloud](https://apps.make.com/fatture-in-cloud) — The Create an Issued Document and Update an Issued Document modules now include 15 new input fields and five additional output fields, giving you more control when creating or updating e-invoices.

***

[monday.com](https://apps.make.com/monday) — The new **Aggregate Table (beta)** module lets you run calculations such as SUM, AVERAGE, and COUNT on monday.com boards without retrieving every item. You can group results by selected columns, build queries with dropdown fields or raw JSON, and get clearer outputs when grouping by a **Connect to Board** column.

***

[QuickBooks](https://apps.make.com/quickbooks) — Search modules now retrieve all matching results instead of stopping at the previous 100-item limit. Dropdown fields for records such as customers, accounts, classes, and vendors now show up to 1,000 items, making it easier to select the right data when configuring modules.

The **Get an Invoice** module also returns the Invoice link field for invoices that support online payments and have a valid customer email address in QuickBooks. The **Watch Events** trigger now supports the new QuickBooks webhook format, so existing scenarios keep working without any action in Make.

***

[ActiveCampaign](https://apps.make.com/activecampaign) — The **Pipeline** field in the **Watch Deals** and **List Deals** modules is now a dropdown menu. You can select a pipeline directly from your ActiveCampaign account or map its ID, so you no longer need to find and enter the Pipeline ID manually.

***

[Salesmate](https://apps.make.com/salesmate) — The **Create an Activity** and **Update an Activity** modules now include fields for Primary Contact ID, Primary Company ID, and Related Deal ID. You can use these fields to link activities to the right contacts, companies, and deals directly in your scenarios.

***

[GoHighLevel](https://apps.make.com/highlevel) — We’ve released a new **Watch Events** instant trigger for more reliable event delivery. The previous trigger is now available as **Watch Events (legacy)** and is deprecated. To keep receiving new events, update your scenarios to use the new Watch Events trigger with a [GoHighLevel Events OAuth 2.0 connection](https://apps.make.com/highlevel#set-up-a-gohighlevel-webhook).

#### Deprecated OpenAI audio preview models

OpenAI has deprecated the `gpt-4o-audio-preview`  and `gpt-4o-mini-audio-preview` models. You can no longer choose these models when setting up OpenAI modules.

* The `gpt-4o-audio-preview` and `gpt-4o-mini-audio-preview` models are no longer available in OpenAI modules.
* You can’t select these models for new or updated modules.
* Existing modules that use these models may fail when they run.

Review your OpenAI modules and replace any deprecated audio preview models with a supported model.

| Deprecated model            | Replacement model |
| --------------------------- | ----------------- |
| `gpt-4o-audio-preview`      | `gpt-audio-1.5`   |
| `gpt-4o-mini-audio-preview` | `gpt-audio-mini`  |

{% hint style="info" %}
Review OpenAI's pricing information for these new models, as your costs may change depending on your usage.
{% endhint %}

#### Deprecated Anthropic Claude models

The following models are no longer be available on the Anthropic Claude API:

* Claude Sonnet 4
* Claude Opus 4

After June 15, 2026, all requests using these models will return an error. Existing modules in your scenario that use these models will fail when they run.

Review your Anthropic Claude modules and replace any deprecated models with a supported model.

| Deprecated model | Replacement model |
| ---------------- | ----------------- |
| Claude Sonnet 4  | Claude Sonnet 4.6 |
| Claude Opus 4    | Claude Opus 4.6   |

Review [Anthropic's model pricing](https://platform.claude.com/docs/en/about-claude/pricing) documentation for these replacement models, as your costs may change depending on your usage.
