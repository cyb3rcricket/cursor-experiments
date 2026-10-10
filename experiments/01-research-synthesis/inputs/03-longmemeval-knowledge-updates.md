# Source Packet 03 — LongMemEval: long-term memory, temporal reasoning, and knowledge updates

## Source

Di Wu, Hongwei Wang, Wenhao Yu, Yuwei Zhang, Kai-Wei Chang, and Dong Yu,  
**“LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory”**  
arXiv:2410.10813  
https://arxiv.org/abs/2410.10813  
Submitted October 14, 2024; revised March 4, 2025.

## Research focus

LongMemEval is a benchmark for evaluating long-term memory in chat assistants across sustained interactions.

The benchmark identifies five core abilities:

1. information extraction
2. multi-session reasoning
3. temporal reasoning
4. knowledge updates
5. abstention

The dataset contains 500 curated questions embedded in scalable user-assistant conversation histories.

The paper reports that commercial chat assistants and long-context language models show roughly a 30% accuracy drop when trying to remember information across sustained interactions.

The authors separate long-term-memory system design into stages involving **indexing, retrieval, and reading**. Their experiments explore changes such as session decomposition, fact-augmented indexing, and time-aware query expansion.

The inclusion of **knowledge updates** as a distinct benchmark ability is important for changing user information. A system may need to recognize that later information updates something stated earlier rather than treating every statement as equally current.

The inclusion of **temporal reasoning** is also relevant. Correct answers can depend not merely on retrieving a matching fact, but on understanding when events or statements were true.

LongMemEval therefore tests more than simple recall. A memory system can retrieve relevant text and still fail the downstream question if the assistant interprets the retrieved material incorrectly.

## What this source establishes

- Long-term conversational memory involves multiple distinct abilities, including temporal reasoning and knowledge updates.
- Memory quality cannot be reduced to whether relevant text exists somewhere in storage.
- Retrieval and downstream answer generation are separate stages in a memory system.
- Sustained interaction histories remain challenging for existing assistants and long-context models.
- Time-aware retrieval and representation are explicit design concerns in long-term memory research.

## What this source does NOT establish

The headline accuracy drop is an aggregate result and should not be treated as a score specifically for knowledge-update questions.

The paper does not prove that one particular memory architecture solves changing preferences universally.

It does not evaluate the exact fictional preference-change scenario used in our Cursor/Grok experiment.

The benchmark predates some 2026 commercial memory architectures, so its results should not be presented as a current score for any product unless that product was directly evaluated under the same conditions.
