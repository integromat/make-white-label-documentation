# Release 2026.01

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
| ElasticSearch | 7.17.28        | Yes            |

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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>79eefccc53375dab9c12b3c4d03b491fc4e9a643</td><td>Yes</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>a8737391322e8fcc84ba7c661db7ec8f4f0b0615</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>a8737391322e8fcc84ba7c661db7ec8f4f0b0615</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.2</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.75.0</td><td>Yes</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.75.0</td><td>Yes</td></tr><tr><td><code>db-updater</code></td><td>18332ee6f51bef41dc7d866eb7c924270f6da71d</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>8c25058300e6eaba3291ff92f656bc72ee5f8280</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>21bae5b-20260206</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>0220eed7f5178457e51ddea45d38e2cd66171c40</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.18.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.56.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>2.2.0</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>lickman</code></td><td>085e06276ca2f17651af840870ac92d3a9323e4b</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.6.1</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>ca37f9e1f7604a90ccefce99c97e9301ef9ec262</td><td>-</td></tr><tr><td><code>overseer</code></td><td>2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>254d9fcfdf64ca2d94ad87a7b87c1bef2a2d6193</td><td>-</td></tr><tr><td><code>roleman</code></td><td>ada6622432c9d44eebffe5650e404240e9ab2fa4</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>21bae5b-20260206</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.24.2</td><td>-</td></tr><tr><td><code>trigger</code></td><td>ff7484240fe29328e918df4c3edaf7110c052743</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>d56b74bfe88c0d22b33ce6fa6ab89f8ba708753b</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>a070d1f2824b58c8d660700db4f83bea1b35144b</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>4.75.0</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>4.75.0</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

### Pipedrive API v1 to v2 transition

Due to changes in the Pipedrive API, we’ve released updated versions of all Pipedrive modules in Make.

#### **What's changing?**

Some of the Pipedrive API v1 modules are now deprecated. Existing scenarios using these modules will continue to run until **July 31, 2026**. After this date, Pipedrive API v1 endpoints will no longer be available, and the scenarios using them will stop working. You can no longer create new scenarios using the deprecated modules.

#### **What do you need to do**

To keep your scenarios running, replace your Pipedrive API v1 modules with their API v2 equivalents before July 31, 2026.

<figure><img src="../.gitbook/assets/image (12).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="info" %}
For a detailed migration guide, see the [Pipedrive Developer Documentation](https://pipedrive.readme.io/docs/pipedrive-api-v2-migration-guide).
{% endhint %}

#### **Connection type deprecation**

The **Pipedrive API token** connections are deprecated. When creating a new Pipedrive connection, select **Pipedrive OAuth** in the **Connection type** field. This is the supported connection method for Pipedrive modules. If you’re using an existing connection created with an API token, update it to use Pipedrive OAuth to ensure compatibility with the current Pipedrive API.

#### **Modules deprecated without replacement**

The following Pipedrive modules have been deprecated and **do not** have a replacement or supported alternative in API v2:

* Add a Recurring Subscription
* Add an Installment Subscription
* Cancel a Recurring Subscription
* Delete a Subscription
* Find Subscription By Deal
* Get a Subscription
* List Payments of a Subscription
* Update a Recurring Subscription
* Update an Installment Subscription

Some deprecated modules don't have direct replacements, but you can replicate the same functionality using other Pipedrive modules with the required filters.

| Deprecated module             | Module to use   | Required filter        |
| ----------------------------- | --------------- | ---------------------- |
| List Activities in a Deal     | List Activities | ID filter              |
| List Deals for a Person       | List Deals      | Person ID filter       |
| List Deals in a Pipeline      | List Deals      | Pipeline ID filter     |
| List Deals in a Stage         | List Deals      | Stage ID filter        |
| List Deals in an Organization | List Deals      | Organization ID filter |
| List Persons in a Deal        | List Persons    | Deal ID filter         |

Use the modules and filters in the module configuration to achieve the same behavior as the deprecated modules.

#### **Webhook changes**

Some webhook endpoints are no longer available in the Pipedrive API v2.

The following webhook modules are replaced by a single generic module:

* New Activity Event → Watch New Events
* New Deal Event → Watch New Events
* New Note Event → Watch New Events
* New Organization Event → Watch New Events
* New Person Event → Watch New Events
* New Product Event → Watch New Events

***

### monday.com app v1 to v2 transition

We've released a new version of the monday.com app in Make. Here's what's changing and what you need to know.

#### **What's changing?**

Monday.com is updating their API version, and we've released a new version of the monday.com app in Make to support it. While we explored all options to maintain backward compatibility, this change requires an update to how the Make monday.com app works.

{% hint style="warning" %}
**Support timeline:**

* **Now through May 1, 2026:** Both v1 and v2 are available and fully supported.
* **After May 1, 2026:** v1 will no longer be supported. Scenarios still using v1 modules may stop working or return errors.
{% endhint %}

<figure><img src="../.gitbook/assets/image.png" alt="" width="375"><figcaption></figcaption></figure>

#### **Who is affected?**

* **Everyone using monday.com:** You'll need to upgrade all your modules from v1 to v2 by May 1, 2026. If your scenarios use specific modules with mapping changes, you'll need to update your mappings before or during the upgrade. See below to check if this applies to you.
* **Not using monday.com?** No action needed.

#### **Do your modules have mapping changes?**

Before you upgrade, check if you're using any of these affected modules. If not, skip to the upgrade steps.

**Affected Module Type 1: Discontinued fields**

* **Modules:** List Boards, Get a Board
* What changed: These fields no longer exist: `border`, `var_name`, `done_colors`, `color_mapping`, `labels_position_v2`, `hide_footer`
* **What you do:** Remove mappings that reference these fields.

**Affected Module Type 2: Timestamp renamed**

* **Modules:**
  * **Get & List:** Get an Item, Get an Item's Column Value, List Board's Items, List Group's Items
  * **Search:** Search Items in the Board by Column Values, Search Items in the Board by Column Values (advanced)
  * **Watch:** Watch Board's Items (poling trigger), Watch Board's Items by Column Values, Watch Group's Items, Watch Board’s Column Values, Watch Item's Column Value
* **What changed:** `changed_at` timestamp is now `updated_at`
* **What you do:** Remap any mappings using `changed_at` to use `updated_at` instead.

#### How to upgrade

1.  **Replace your v1 modules.**\
    In the Scenario Builder, look for the green upgrade arrow on your monday.com modules. Click it, then select "Show me new modules" to upgrade to v2.

    <figure><img src="../.gitbook/assets/image (1).png" alt="" width="188"><figcaption></figcaption></figure>
2. **Update affected mappings** (if applicable).\
   For any modules listed above, find and remove or remap the discontinued or changed fields.
3. **Test your scenarios.**\
   Run your scenarios to ensure they work correctly.

**Tip: Speed up your migration**

You can use the [Make DevTool](https://help.make.com/make-devtool) to speed up your migration. Use the Swap Variable function to update mappings more efficiently across multiple modules instead of editing each one individually.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

**Where to learn more**

* Technical documentation: [monday.com](https://monday.comhttps/apps.make.com/monday)

***

### Updated scenario filtering and sorting

Managing dozens of scenarios gets messy. We have added the ability to sort scenarios by **Last edited** and redesigned the filtering interface to help you find relevant scenarios faster.

#### **What's new**

* **Last edited sorting:** Scenarios now sort by most recent edits
* **Enhanced interface:** Cleaner dropdown menu with more sorting options (Name A-Z, Created newest/oldest, Credit usage)

<figure><img src="../.gitbook/assets/image (13).png" alt="" width="375"><figcaption></figcaption></figure>

#### Who it's for

* **Teams managing shared scenarios:** See which scenarios have been recently updated
* **Anyone with multiple scenarios:** Sort by last edited to find what you were working on

{% hint style="info" %}
Available on all plans. Start using these features in the Scenario Builder today.
{% endhint %}

***

### Scenario history columns

The Scenario history now supports [showing and hiding columns](https://help.make.com/scenario-history#GiUD1). This gives you more control over what you see in the Scenario history.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

***

### Claude Opus 4.6 now available in Make

Anthropic's newest model, Claude Opus 4.6, is now available in Make for AI-powered automations.

#### What's new

Claude Opus 4.6 is Anthropic's most advanced model, built for:

* Large-scale data processing: 1M token context window lets you process entire codebases or document archives in a single prompt
* Complex reasoning: Enhanced capabilities for multi-step workflows and autonomous decision-making
* Agentic workflows: Built for tool use and course-correction in automated processes

#### How to use Claude Opus 4.6 in Make

Select the option that fits your workflow:

* [Make AI Toolkit](https://apps.make.com/ai-tools): Use the ‘Simple text prompt’ module for quick testing with zero configuration. No API key required – select Claude Opus 4.6 from the model dropdown.
* [Anthropic Claude](https://apps.make.com/anthropic-claude): Connect your Anthropic API key with the ‘Create a prompt’ module for structured prompts.
* [Make AI Agents (New)](https://help.make.com/make-ai-agents-new): Build agentic workflows using your own Anthropic API key.
