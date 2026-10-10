# Grok 4.7 + Cursor: three controlled workspace experiments

This is the evidence packet behind Article 2, **“I Put Grok 4.7 to Work in Cursor. Research Was the Easy Part.”**

I wanted to know whether a model working inside a real file-based workspace could do three different jobs:

1. synthesize several sources without flattening their differences;
2. turn that research into writing that sounded like me; and
3. reconstruct the current state of a project when the files disagreed.

The answer was not one clean yes or no. Grok handled evidence much better than it handled voice.

## What is here

| Experiment | Question | Result | Article 2 section |
|---|---|---|---|
| [01 — Research synthesis](experiments/01-research-synthesis/) | Can it synthesize four source packets while preserving differences, uncertainty, and source boundaries? | **48.5/50.** Strong synthesis and uncertainty handling; repetitive, memo-shaped prose. | “Test 1: Can it actually synthesize research?” |
| [02 — Style transfer](experiments/02-style-transfer/) | Can it use one controlled factual source and two style samples to write in the Cyb3rCricket voice? | **29.5/40.** Strong factual discipline; weak voice and structure match; one source-attribution error. | “Test 2: Okay, but can it sound like me?” |
| [03 — Conflicting state](experiments/03-conflicting-project-state/) | Can it distinguish approved, superseded, speculative, and unresolved project information? | **49.5/50.** Correct current-state reconstruction and strong resistance to a false premise. | “Test 3: What happens when the workspace itself is messy?” |

Each experiment includes:

- the exact prompt used for the first run;
- the exact input files available to the model;
- the raw first-run output, preserved without rewriting; and
- the saved post-run evaluation.

## Method

All three experiments were run on October 10, 2026, with Grok 4.7 inside Cursor.

The workspaces were deliberately small and controlled. Each prompt limited the model to the supplied files and prohibited web search, outside knowledge, prior conversations, and unstated assumptions. I saved the prompt before running it and evaluated the first answer without revising it or repeatedly prompting toward a preferred result.

Experiment 1 used four curated source packets about AI memory, knowledge updates, and stale downstream behavior. Experiment 2 used Experiment 1’s raw memo as its only factual source and two published Cyb3rCricket articles as style references. Experiment 3 used five fictional Lantern project files designed to make recency and authority point in different directions.

## What this does not prove

Three controlled tests are still three controlled tests.

- This is not a benchmark of Grok 4.7 against other Cursor models.
- The inputs were small and hand-selected. A large, messy, long-lived workspace could behave differently.
- The evaluations are qualitative post-run reviews supplied with the experiments. Their scores are not blinded, independently replicated, or calibrated against other models; evaluator authorship is not recorded in the saved files.
- The tests cover first-run behavior, not what several rounds of prompt refinement might produce.
- Vendor documentation in Experiment 1 is treated as documentation of a product’s stated behavior, not independent proof that the design works universally.
- The Lantern project in Experiment 3 is fictional. Its dates, tools, and decisions are test fixtures, not claims about a real project.

## Reading the artifacts

Start with a prompt, inspect its `inputs/` folder, read `raw-output.md`, and then compare it with `evaluation.md`. That order keeps the evidence separate from my interpretation of it.

[PROVENANCE.md](PROVENANCE.md) explains how the files were recovered and what was intentionally left out of the public packet.

## Source links used in Experiment 1

- [OpenAI — Memory in ChatGPT](https://help.openai.com/en/articles/8590148-memory-in-chatgpt)
- [OpenAI — Dreaming: Better memory for a more helpful ChatGPT](https://openai.com/index/chatgpt-memory-dreaming/)
- [Mem0 — Dream: Background memory consolidation for AI agents](https://mem0.ai/blog/dream-background-memory-consolidation-for-ai-agents)
- [LongMemEval](https://arxiv.org/abs/2410.10813)
- [Fresh Memory, Stale Plans](https://arxiv.org/abs/2609.03340)

The files in `inputs/` are the actual bounded test fixtures used for the runs. Follow the original links above when you need the authoritative source.
