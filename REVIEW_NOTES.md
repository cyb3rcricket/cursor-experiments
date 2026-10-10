# Accuracy review — October 10, 2026

This review checks the saved evidence and its presentation. It adds context without changing the original prompts, inputs, answers, evaluations, or scores.

## Run integrity

All 25 files in the initial public packet matched the local package by Git content hash. All 21 preserved artifacts passed the SHA-256 manifest check. Experiment 2's factual input is byte-for-byte identical to Experiment 1's answer.

The recovered Cursor transcripts contain one user prompt per experiment. All three prompts and delivered answers match the saved artifacts after line-ending normalization and removal of a trailing file newline. The recorded start timestamps are October 10, 2026 at 1:17 PM, 1:56 PM, and 2:28 PM, respectively, in UTC−5 (America/Chicago).

Experiment 1 includes internal drafting, word counting, and editing before delivery. Its raw output is the first delivered answer, not the agent's earliest working draft. Experiment 3's Firebase challenge is part of its initial prompt, not a separate follow-up. Article 2 should describe that sequence accordingly.

The recorded tool calls show reads of the intended factual and style inputs, plus the agent's own working drafts in Experiment 1. They do not show a web-search tool call. This checks observable tool use; it cannot prove that a model excluded its pretrained knowledge or capture every hidden runtime instruction.

## Source checks and corrections

The five primary source pages were accessible during this review. Their relevant descriptions support the packets' central distinctions, with the following qualifications:

- **OpenAI:** June 4, 2026 belongs to the [Dreaming article](https://openai.com/index/chatgpt-memory-dreaming/), not the separately maintained [memory help page](https://help.openai.com/en/articles/8590148-memory-in-chatgpt). Experiment 2 conflates them. The raw draft's description of “Dreaming” as a trip memory is also awkward: the trip is an example in the article, not the name of a memory item.
- **Mem0:** The [Dream post](https://mem0.ai/blog/dream-background-memory-consolidation-for-ai-agents) supports retaining superseded memories, the `latest_only=true` filter, and conservative same-fact replacement. These are vendor descriptions rather than independent guarantees of classifier or downstream-model accuracy.
- **LongMemEval:** [Version 2](https://arxiv.org/abs/2410.10813v2) matches the packet's March 4, 2025 revision date. Its headline accuracy drop is an aggregate claim, not a knowledge-update-specific score or a result for these Grok runs. The raw answers' wording about not testing “the preference-change scenario” should be read narrowly: this repository's exact workflow was not evaluated by that paper. LongMemEval does include knowledge updates and preference-related tasks; it should not be described as ignoring changing user information. See the paper's [benchmark definitions](https://arxiv.org/html/2410.10813v2).
- **Fresh Memory, Stale Plans:** The packet's title and September 3, 2026 date match [version 1](https://arxiv.org/abs/2609.03340v1). Its original unversioned link opens [version 2](https://arxiv.org/abs/2609.03340v2), revised September 27 with the subtitle *Derivation Currency for Distributed LLM-Agent Memory*. The README now links to v1 to match the saved packet. The reported 30-workflow result belongs to that controlled study, not to Experiment 3 or general agent performance.

The longer firsthand sources cited in style sample 1 and the Cursor documentation were accessible. The two X citation URLs did not return readable post text through the review tool, so their content was not independently verified here. Style sample 2's wizard comparison is retained as a writing sample; its code and videos are outside this evidence packet and were not re-evaluated in this review.

## Scores and answer checks

The scoring rows sum correctly: **48.5/50**, **29.5/40**, and **49.5/50**. They are the saved evaluators' judgments under different rubrics, not calibrated comparisons. Evaluator identity and a blinded review procedure are not recorded in the saved evaluation files.

Using nonempty whitespace-delimited tokens as an approximate word count, Experiment 1's full memo contains 999, and Experiment 2's draft body contains 748. Experiment 2 also includes the requested claims section, so the entire response is longer than the draft's 600–800-word target. The 14 claims are visible in the output.

Experiment 3's answer agrees with all four established fixture values and stays within the 150-word status-summary limit. It preserves the unresolved observability decision and does not promote Firebase, prototype SQLite, or the November 17 proposal into approved production decisions.

## Interpretation and privacy

These are three small, prompted demonstrations. The prompts explicitly tell the model how to handle uncertainty, evidence, recency, and approval; the project fixtures label those distinctions clearly. The results support inspecting those delivered answers, not a broad claim about reliability on messy real workspaces or a causal finding that Cursor improves Grok's reasoning.

Grok 4.7 is the author-reported model label in the saved evaluations. A provider model identifier, Cursor version, generation settings, and random seed are not captured in the public packet. The files support rerunning the tasks, but do not promise identical outputs.

A renewed scan found no private contact details, local absolute paths, account-holder legal-name references, or credential assignments in the publication files. Public citation names and handles remain. The originals keep their export formatting, including style-sample image descriptions and the first evaluation's conversational ending. Their hashes remain the reference for historical integrity.
