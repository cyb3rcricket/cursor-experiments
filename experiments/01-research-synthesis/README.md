# Experiment 1: research synthesis

Can a model compare four source packets without treating them as one architecture or turning inference into a research finding?

[Read the prompt](prompt.md) → [Inspect the inputs](inputs/) → [Read the first answer](raw-output.md) → [Read the saved evaluation](evaluation.md)

## Inputs

- [OpenAI: memory controls and freshness](inputs/01-openai-memory-controls.md)
- [Mem0: current and superseded facts](inputs/02-mem0-current-vs-history.md)
- [LongMemEval: temporal reasoning and knowledge updates](inputs/03-longmemeval-knowledge-updates.md)
- [Fresh Memory, Stale Plans: derived actions](inputs/04-fresh-memory-stale-plans.md)

These are curated summaries of the linked sources. The model was instructed to use those summaries only.

## What the answer shows

The answer distinguishes relevance, supersession, time, and the currency of derived plans. It separates retrieval from correct use and labels findings, synthesis, and unresolved questions. The saved evaluation totals **48.5/50**; its main criticism is repetitive prose.

The complete memo contains 999 whitespace-delimited tokens, including headings and Markdown, within the requested approximate 700–1,000 words. “First answer” is the delivered answer after the agent's own drafting within one run.

The original evaluation is a saved text export, so its tab-separated scoring rows and conversational ending are preserved. See the [review notes](../../REVIEW_NOTES.md) for source-version details and the limits of the preference-change claim.

Article 2 mapping: **“Test 1: Can it actually synthesize research?”**

[Back to the evidence packet](../../README.md)
