# Release 2025.08

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
| Redis         | v6.2.20        | Yes            |
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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>4c4596ceba0b9ef2ede0217fb26b7cbe636f4405</td><td>Yes</td></tr><tr><td><code>apps-processor</code></td><td>v2.4.3</td><td>-</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>ef0e7cd6f1ae875f795a8cec312b64ed0fc89bde</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>ef0e7cd6f1ae875f795a8cec312b64ed0fc89bde</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>datadog-agent</code></td><td>7.71.1</td><td>Yes</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.71.1</td><td>Yes</td></tr><tr><td><code>db-updater</code></td><td>637f6064168fc71054bc587f3672e3abd17fa940</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>6fca0ee4b468fdcf699dd636f924232e08bf33cf</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>9905603-20251010</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>3f49994b75c2917a4586352210eae5f8774a252a</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.10.2</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.52.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>2.1.2</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.15</td><td>-</td></tr><tr><td><code>lickman</code></td><td>e53496a083cae031e743c54748f00d0753e88f31</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.5.1</td><td>Yes</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>Yes</td></tr><tr><td><code>notifications-processor</code></td><td>7574100ce48c7d2b87d18e11e55a6103fe6c6cc0</td><td>Yes</td></tr><tr><td><code>overseer</code></td><td>a688ee99fe3469bfb8a586a1f189c635f47eb620</td><td>Yes</td></tr><tr><td><code>renderer-processor</code></td><td>dce8eac4cac38070abad7393d7c7797e4dc465b5</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>7f9f433c3b51f20ec871b50e8823fbf8e527d9b8</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>989dd81-20250828</td><td>-</td></tr><tr><td><code>trackman</code></td><td>2.22.0</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>a76cb02797f203309ef2eba6d581c10849f4dd6f</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>a0f099d41f1cb2983ae6513901327287f6730a84</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>6b72216bb9e05f2f08a4a61cfef18023572927f1</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>b9ced895578f42eb0a09d6f28b8483b63cddeb23</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>627f4bbe181f957a65c2e1bab938401bbf40cea5</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

#### Make AI Toolkit

Make AI Toolkit is an app that streamlines common AI tasks using either Make's built-in AI Provider or your own external AI models. The toolkit offers essential capabilities including sentiment analysis, text categorization, language identification, information extraction, text standardization, summarization, translation, and text chunking.

{% hint style="info" %}
For more information, refer to the [Make AI Toolkit documentation](https://apps.make.com/ai-tools).
{% endhint %}

***

#### Make AI Content Extractor

We've released a built-in app that extracts structured text and metadata from files like PDFs, Word documents, images, and audio recordings—directly within your Make scenarios.

{% hint style="info" %}
For more information, refer to the [Make AI Content Extractor documentation](https://apps.make.com/make-ai-extractors).
{% endhint %}

***

#### Fix for Team Restricted Member role permission

We've fixed an issue with the permissions assigned to the **Team Restricted Member** role. The role now does not have any unexpected modification capabilities.

**What we fixed**

We've removed the permission that allowed the Team Restricted Member role to modify team settings.

**What this means for you**

If you have the Team Restricted Member role, you will no longer be able to modify any team settings for the team you are a part of.

The Team Restricted Member role remains supported for existing teams, even though it is considered deprecated. This fix allows the role to function securely and in the way it was originally intended.

