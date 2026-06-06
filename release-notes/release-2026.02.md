# Release 2026.02

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
| ElasticSearch | 8.19.13        | Yes            |

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

<table><thead><tr><th width="195.2716064453125">Service</th><th width="361.3212890625">Version</th><th>Version update</th></tr></thead><tbody><tr><td><code>accman</code></td><td>c7574116b1803a674727a1776e91643f9d95b057</td><td>Yes</td></tr><tr><td><code>agency</code></td><td>4.0-beta</td><td>-</td></tr><tr><td><code>aws-rds-log-reader</code></td><td>v1.1.1</td><td>-</td></tr><tr><td><code>broker</code></td><td>9eab1f10bdaa4ab9701aac9bb6c145eff4c7a5b7</td><td>Yes</td></tr><tr><td><code>broker-gw-logger</code></td><td>6e9a6541951b7627a96327b878322e25ae534e6a</td><td>Yes</td></tr><tr><td><code>cron</code></td><td>v1.1.3</td><td>Yes</td></tr><tr><td><code>datadog-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>datadog-cluster-agent</code></td><td>7.75.0</td><td>-</td></tr><tr><td><code>db-updater</code></td><td>3282397c268be01f38ec62362173729bec121f05</td><td>Yes</td></tr><tr><td><code>emails-processor</code></td><td>b1e8a78dca74de7cf43ba83fdc2ccef3d23ea5d3</td><td>Yes</td></tr><tr><td><code>engine</code></td><td>dc1ffec-20260331</td><td>Yes</td></tr><tr><td><code>execution-controller</code></td><td>2026.05.26-a0c5191</td><td>Yes</td></tr><tr><td><code>gateway</code></td><td>31cc4859c735ba5ca9c900965ad4e0da52adc115</td><td>Yes</td></tr><tr><td><code>imt-auditman</code></td><td>1.21.0</td><td>Yes</td></tr><tr><td><code>ipm-server</code></td><td>3.58.0</td><td>Yes</td></tr><tr><td><code>ipm-service</code></td><td>2.3.3</td><td>Yes</td></tr><tr><td><code>kibana</code></td><td>7.17.28</td><td>Yes</td></tr><tr><td><code>lickman</code></td><td>789319483fc65a675b8cc4300a8302949b0a9c46</td><td>Yes</td></tr><tr><td><code>make-apps-processor</code></td><td>1.6.1</td><td>-</td></tr><tr><td><code>mongo-auto-indexer</code></td><td>master</td><td>-</td></tr><tr><td><code>nginx</code></td><td>v1.28.0</td><td>-</td></tr><tr><td><code>notifications-processor</code></td><td>ca37f9e1f7604a90ccefce99c97e9301ef9ec262</td><td>-</td></tr><tr><td><code>overseer</code></td><td>2f1113b6fe7c44e72b8c8e05a473173e89c3ab9e</td><td>-</td></tr><tr><td><code>renderer-processor</code></td><td>e000e5b913abdfc7ee6551a3db9166d33642ffdb</td><td>Yes</td></tr><tr><td><code>roleman</code></td><td>a597fe9ff5d9c66d2c4f89bd64c8f79d2531bba2</td><td>Yes</td></tr><tr><td><code>s3proxy</code></td><td>3.1.0</td><td>Yes</td></tr><tr><td><code>scheduler</code></td><td>dc1ffec-20260331</td><td>Yes</td></tr><tr><td><code>trackman</code></td><td>2.26.1</td><td>Yes</td></tr><tr><td><code>trigger</code></td><td>4a2f1db7a4761f08d56b873cad08aa58b559fec7</td><td>Yes</td></tr><tr><td><code>web-api</code></td><td>5d0b268f3784c62b19b26593d06c3ece21d47348-hotfix-1</td><td>Yes</td></tr><tr><td><code>web-streamer</code></td><td>2fb26adf4a142aa77b163f93837f862943796ec4</td><td>Yes</td></tr><tr><td><code>web-zone</code></td><td>36d0f822915aa60639fba319172e944d022346f1</td><td>Yes</td></tr><tr><td><code>zone-assets-server</code></td><td>36d0f822915aa60639fba319172e944d022346f1</td><td>Yes</td></tr></tbody></table>

</details>

## Public-facing changes

### Gemini 3.1 Pro Preview model now available in Make

Gemini 3.1 Pro Preview is Google's latest model, built for complex reasoning and high-volume tasks. It's now available in Make across both keyless and bring-your-own-key options.

* **Efficient**: Optimized to process instructions more efficiently, leading to quicker responses and better overall reliability.
* **Cost-effective**: the Gemini 3.1 Pro Preview model will process your instructions more concisely, generate faster responses, and lower credit usage for the same results.
* **Agent-ready**: It is designed for agentic workflows that require tool usage and follow multi-step instructions with precision.

### OpenAI GPT-5.4 and GPT-5.3 models now available in Make

OpenAI's GPT-5.4 and GPT-5.3 models are now available in Make, bringing faster, more cost-efficient AI with expanded context and smarter tool handling to your automations.

### New encryption and data security guide

All encryption and data security documentation has been consolidated into a [new, comprehensive guide](https://help.make.com/securing-data-with-make). It includes updated [Encryptor app documentation](https://apps.make.com/crypto), a breakdown of data-securing methods, and step-by-step examples for using AES, PGP, digital signatures, and hash functions in your scenarios.

### OpenAI GPT-5.4 nano and mini now available in Make

OpenAI's GPT-5.4 nanoi and mini are now available in Make. These models are built for speed and efficiency, giving you more options when choosing models for multi-step and agentic workflows.

**What's new**

* `GPT-5.4` mini offers a good balance of strong reasoning, speed, and affordability, and is ideal for coding and multimodal tasks.
* `GPT-5.4` nano is a cost-efficient choice for simpler, repetitive tasks, such as data extraction, classification, and routing.

**Key benefits**

* **Shorter run times:** Mini and nano handle high-volume work that needs to move fast.
* **More model variety:** Use larger models for orchestration, and mini or nano for subtasks at any scale.
* **Cheaper multi-step workflows:** Build complex scenarios for classification, intent detection, ranking, triage, and heavy text processing at a lower cost.

### Deprecated OpenAI model automatically replaced

We've removed the deprecated `chatgpt-4o-latest` model from the OpenAI app and automatically migrated existing scenarios to `gpt-4o-2024-08-06`. No action is required on your part.

**What changed**

The `chatgpt-4o-latest` model is no longer available for selection. Any scenarios that previously used this model now automatically send requests to `gpt-4o-2024-08-06`. We made this change to make sure your scenarios continue running without interruption after OpenAI discontinued the original model.

**What this mean for you**

Your scenarios are unaffected and will continue to run as expected. The OpenAI modules in those scenarios will now display `gpt-4o-2024-08-06` as the selected model. Keep in mind that outputs may vary slightly due to differences in model behavior.

### App updates

* [Google Sheets](https://apps.make.com/google-sheets) — We've added the option to use column headers as column IDs in the Add a Row and Update a Row modules. In this case, column header names are used as stable IDs, and as long as you don't rename your columns in the sheet, existing mappings will continue to work even if other columns are added, removed, or reordered in the table.
* [OpenAI](https://apps.make.com/openai-gpt-3) — **Chunking Strategy** options are now available in the **Generate a Transcription** module when using the `gpt-4o-transcribe-diarize` model. For more information, refer to the [OpenAI app documentation](https://apps.make.com/openai-modules#generate-a-transcription).
* [HTTP](https://apps.make.com/http) — We've released a new Resolve URL module that allows you to follow all automatic redirects to identify the final destination address of a link.
* [Google Gemini AI](https://apps.make.com/gemini-ai) — Gemini 3 Pro Preview model has been [deprecated](https://ai.google.dev/gemini-api/docs/deprecations) since March 9, 2026. Any scenarios using this model in the **Simple text prompt** or **Generate a response** modules have been automatically migrated to Gemini 3.1 Pro Preview to avoid interruptions. No action required.
