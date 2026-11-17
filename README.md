# Brent Williams

I find where AI systems mishandle rate limits and retries, and I get the fixes merged.

- **10 fixes merged** into AI frameworks and tools, including LangChain.js, Genkit, VoltAgent and Botpress.
- **LangChain.js adopted my WAIT / CAP / STOP distinction** in its shared retry classifier ([issue](https://github.com/langchain-ai/langchainjs/issues/10566) · [merged PR](https://github.com/langchain-ai/langchainjs/pull/10674)).
- **70 documented failures** in [Pitstop Truth](https://github.com/SirBrenton/pitstop-truth), each with evidence, a validated schema and a public corrections log.

**How I work:** I run long technical projects with AI models as collaborators, check their output against evidence, and publish corrections when I'm wrong.

---

## Recent Execution Reliability Contributions

Real reliability findings and execution fixes merged into production AI systems and developer tooling.

| Repository | Contribution |
|---|---|
| <img src="https://github.com/langchain-ai.png" width="18" /> [langchainjs](https://github.com/langchain-ai/langchainjs) | Identified inconsistent 429 handling across Anthropic, OpenAI, Google, and OpenRouter provider paths — maintainer adopted the WAIT/CAP/STOP classification distinction directly into the shared retry classifier, fix merged across `@langchain/core`, `@langchain/google`, and `@langchain/openrouter` ([Issue #10566](https://github.com/langchain-ai/langchainjs/issues/10566) · [Merged PR #10674](https://github.com/langchain-ai/langchainjs/pull/10674)) |
| <img src="https://github.com/genkit-ai.png" width="18" /> [genkit](https://github.com/genkit-ai/genkit) | Identified missing Retry-After propagation channel across middleware boundary — fix merged across Anthropic, OpenAI, and Gemini integrations ([Issue #5270](https://github.com/genkit-ai/genkit/issues/5270) · [Merged PR #5343](https://github.com/genkit-ai/genkit/pull/5343)) |
| <img src="https://github.com/garrytan.png" width="18" /> [gstack](https://github.com/garrytan/gstack) | Improved provider-aware Retry-After handling ([Merged](https://github.com/garrytan/gstack/issues/1244#event-25339963479)) |
| <img src="https://github.com/earendil-works.png" width="18" /> [pi](https://github.com/earendil-works/pi) | Separated retry semantics for provider failures ([Merged PR](https://github.com/earendil-works/pi/pull/4486)) |
| <img src="https://github.com/VoltAgent.png" width="18" /> [voltagent](https://github.com/VoltAgent/voltagent) | Identified framework-level Retry-After omission causing coordinated retry amplification under shared provider contention — fix merged ([Issue #1276](https://github.com/VoltAgent/voltagent/issues/1276) · [Merged PR #1283](https://github.com/VoltAgent/voltagent/pull/1283)) |
| <img src="https://github.com/jo-inc.png" width="18" /> [camofox-browser](https://github.com/jo-inc/camofox-browser) | Identified false-success acknowledgement path where HTTP 429 relay rejection was silently treated as successful crash-report delivery — fix merged ([Merged PR #3413](https://github.com/jo-inc/camofox-browser/pull/3413) · [Release Sync #4150](https://github.com/jo-inc/camofox-browser/pull/4150)) |
| <img src="https://github.com/cline.png" width="18" /> [Cline](https://github.com/cline/cline) | Surfaced Retry-After propagation behavior ([Issue](https://github.com/cline/cline/issues/10139)) |
| <img src="https://github.com/garrytan.png" width="18" /> [gbrain](https://github.com/garrytan/gbrain) | Added receipt document type to native frontmatter inference ([Open PR](https://github.com/garrytan/gbrain/pull/973)) |
| <img src="https://github.com/gsd-build.png" width="18" /> [gsd-2](https://github.com/gsd-build/gsd-2) | Fixed unwired Codex execution path ([Merged PR](https://github.com/gsd-build/gsd-2/pull/5859)) |
| <img src="https://github.com/botpress.png" width="18" /> [Botpress](https://github.com/botpress/botpress) | Identified SDK vs CLI retry policy divergence ([Merged PR](https://github.com/botpress/botpress/pull/15145)) |
| <img src="https://github.com/superset-sh.png" width="18" /> [Superset](https://github.com/superset-sh/superset) | Surfaced agent-side 429 propagation issue ([Merged PR](https://github.com/superset-sh/superset/pull/4373)) |
| <img src="https://github.com/Yeachan-Heo.png" width="18" /> [oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode) | Improved provider retry behavior handling ([Merged PR](https://github.com/Yeachan-Heo/oh-my-claudecode/pull/2746)) |


---

## The Thesis

Most AI systems fail in the layers *around* the model.

The recurring problems are surprisingly consistent:

* retries without provider semantics
* cooldowns enforced at the wrong scope
* collapsed error classifications
* hidden retry amplification
* budgets treated as suggestions instead of constraints
* orchestration without receipts or verification

I’m interested in making execution:

* predictable
* inspectable
* enforceable
* auditable

The goal is simple:

```text
execute(intent, budget, policy) -> result + receipt
```

---

## Pitstop Truth

A growing corpus of real-world AI/API execution failures, reliability hazards, and remediation patterns.

Current focus areas:

* 429 handling
* Retry-After semantics
* provider cooldown behavior
* routing failures
* CAP vs WAIT classification
* retry amplification
* blast-radius correctness

→ [View the corpus](https://github.com/SirBrenton/pitstop-truth)

---

## Background

Solo founder. Background in systematic trading infrastructure and quantitative strategy development.

Building at the intersection of execution reliability, deterministic orchestration, and AI-native systems.

---

## Writing / Contact

* [Pitstop.dev](https://pitstop.dev)
* [LinkedIn](https://www.linkedin.com/in/brentwilliams/)
* [brent@pitstop.dev](mailto:brent@pitstop.dev)
