# Anthropic Claude model deprecations on June 15, 2026

Anthropic is deprecating two Claude models on **June 15, 2026**. After that date, scenarios using these models will fail.

#### What's changing? <a href="#uexix" id="uexix"></a>

The following models will no longer be available on the Anthropic Claude API starting June 15, 2026:

* Claude Sonnet 4
* Claude Opus 4

After June 15, 2026, all requests using these models will return an error. Existing modules in your scenario that use these models will fail when they run.

#### What do you need to do? <a href="#potai" id="potai"></a>

Review your Anthropic Claude modules and replace any deprecated models with a supported model.

| Deprecated model | Replacement model |
| ---------------- | ----------------- |
| Claude Sonnet 4  | Claude Sonnet 4.6 |
| Claude Opus 4    | Claude Opus 4.6   |

Review Anthropic's model pricing documentation for these replacement models, as your costs may change depending on your usage.

#### Resources <a href="#id-0ifwu" id="id-0ifwu"></a>

* [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations#2026-04-14-claude-sonnet-4-and-claude-opus-4-models)
* [Make Help Center — Anthropic Claude documentation](https://apps.make.com/anthropic-claude)

