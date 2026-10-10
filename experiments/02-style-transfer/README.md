# Experiment 2: writing from controlled context

Can a model turn a research memo into writing that resembles Cyb3rCricket while keeping the facts and caveats intact?

[Read the prompt](prompt.md) → [Inspect the inputs](inputs/) → [Read the first answer](raw-output.md) → [Read the saved evaluation](evaluation.md)

## Inputs

- [Experiment 1's memo](inputs/experiment-1-raw-output.md), the only permitted factual source
- [Style sample 1: Beyond Coding](inputs/style-sample-1.md)
- [Style sample 2: Same prompt. Three wizards.](inputs/style-sample-2.md)

The style samples concern other topics. Their claims were not permitted as factual sources for this draft.

## What the answer shows

The answer supplies 14 planned claims followed by a draft. The draft body contains 748 whitespace-delimited tokens, within the requested 600–800 words; the claims section is additional requested material.

The saved evaluation totals **29.5/40**. It finds stronger factual discipline than voice resemblance, with a source-by-source structure that would need substantial editing for publication.

The raw draft incorrectly attaches June 4, 2026 to OpenAI's memory help page. That is the publication date of the separate [Dreaming article](https://openai.com/index/chatgpt-memory-dreaming/). The mistake remains visible in the raw output. The [review notes](../../REVIEW_NOTES.md) also clarify its wording about LongMemEval.

Article 2 mapping: **“Test 2: Okay, but can it sound like me?”**

[Back to the evidence packet](../../README.md)
