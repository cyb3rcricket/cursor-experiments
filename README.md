# Grok 4.7 + Cursor: three controlled workspace experiments

This is the evidence packet behind Article 2, **“I Put Grok 4.7 to Work in Cursor. Research Was the Easy Part.”**

I wanted to know whether a model working inside a real file-based workspace could do three different jobs:

1. synthesize several sources without flattening their differences;
2. turn that research into writing that sounded like me; and
3. reconstruct the current state of a project when the files disagreed.

In these runs, the strongest results came from reasoning over evidence. Matching my writing voice was harder.

## What is here

| Experiment | Question | Saved evaluation | Article 2 section |
|---|---|---|---|
| [01 — Research synthesis](experiments/01-research-synthesis/README.md) | Can it synthesize four source packets while preserving differences and uncertainty? | **48.5/50.** Strong synthesis; repetitive, memo-shaped prose. | “Test 1: Can it actually synthesize research?” |
| [02 — Style transfer](experiments/02-style-transfer/README.md) | Can it use one factual source and two style samples to write in the Cyb3rCricket voice? | **29.5/40.** Strong factual discipline; weak voice match; a date-attribution error. | “Test 2: Okay, but can it sound like me?” |
| [03 — Conflicting state](experiments/03-conflicting-project-state/README.md) | Can it distinguish approved decisions, historical information, proposals, and unresolved questions? | **49.5/50.** All four target values correct; unsupported Firebase premise rejected. | “Test 3: What happens when the workspace itself is messy?” |

These scores come from different qualitative rubrics. They are editorial judgments about the saved answers, not comparable benchmark percentages.

Each experiment includes:

- the exact prompt used for the first run;
- the input files used for the task;
- the first delivered answer, preserved without rewriting; and
- the saved post-run evaluation.

## Method

All three experiments were run on October 10, 2026, in Cursor. The saved evaluations identify the model as Grok 4.7; a provider model identifier, Cursor version, and generation settings were not captured in the public artifacts.

The workspaces were deliberately small and controlled. Each prompt limited the model to the supplied files and prohibited web search, outside knowledge, prior conversations, and unstated assumptions. The prompts and first delivered answers match the recovered Cursor transcripts. Each transcript contains one user prompt; no second user prompt refined the answer.

“First run” means the first delivered answer to that prompt. The agent could draft, count words, and edit its own working files before delivering the answer, as it did in Experiment 1. The published answers were not edited afterward.

Experiment 1 used four curated source packets about AI memory, knowledge updates, and stale downstream behavior. Experiment 2 used Experiment 1’s raw memo as its only factual source and two published Cyb3rCricket articles as style references. Experiment 3 used five fictional Lantern project files designed to make recency and authority point in different directions.

Experiment 3’s Firebase challenge was included in the original prompt. It was not a separate follow-up interaction.

## What this does not prove

Three controlled tests are still three controlled tests.

- This is not a benchmark of Grok 4.7 against other Cursor models.
- The inputs were small and hand-selected. A large, messy, long-lived workspace could behave differently.
- The evaluations are qualitative post-run reviews supplied with the experiments. Their scores are not blinded, independently replicated, or calibrated against other models; evaluator authorship is not recorded in the saved files.
- The tests cover first-run behavior, not what several rounds of prompt refinement might produce.
- The prompts explicitly supplied the reasoning rules, and the fictional project files clearly labeled approval and speculation. These results do not establish how the model handles less explicit evidence or an unprompted false premise.
- Vendor documentation in Experiment 1 is treated as documentation of a product’s stated behavior, not independent proof that the design works universally.
- The Lantern project in Experiment 3 is fictional. Its dates, tools, and decisions are test fixtures, not claims about a real project.

## Reading the artifacts

Start with a prompt, inspect its `inputs/` folder, read `raw-output.md`, and then compare it with `evaluation.md`. That order keeps the evidence separate from my interpretation of it.

[PROVENANCE.md](PROVENANCE.md) explains recovery and file integrity. [REVIEW_NOTES.md](REVIEW_NOTES.md) records the accuracy check, known errors, and source-version details. The original evaluations, inputs, and outputs retain their original formatting and wording.

## Source links used in Experiment 1

- [OpenAI — Memory in ChatGPT](https://help.openai.com/en/articles/8590148-memory-in-chatgpt)
- [OpenAI — Dreaming: Better memory for a more helpful ChatGPT](https://openai.com/index/chatgpt-memory-dreaming/)
- [Mem0 — Dream: Background memory consolidation for AI agents](https://mem0.ai/blog/dream-background-memory-consolidation-for-ai-agents)
- [LongMemEval — v2, March 4, 2025](https://arxiv.org/abs/2410.10813v2)
- [Fresh Memory, Stale Plans — v1, September 3, 2026](https://arxiv.org/abs/2609.03340v1)

The source packets are curated summaries, not full copies of the papers or vendor pages. The versioned links above match the dates and titles in those packets; the original unversioned links remain in the preserved inputs. Vendor pages can change after a run.
