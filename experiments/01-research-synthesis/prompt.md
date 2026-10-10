You are working inside a Cursor workspace containing four source files about AI memory, knowledge updates, current versus historical facts, and stale downstream behavior.

Your task is to answer this research question:

**When a user changes a previously saved preference, how should an AI assistant decide what is current, what should remain historical, and what can go wrong if retrieval does not account for the change?**

Use only the four source files in this workspace.

Do not use web search, outside knowledge, prior conversations, or unstated assumptions.

Produce a research memo of approximately 700–1,000 words.

Organize the memo around these five questions:

1. What does it mean for information to be “current”?
2. Why might an older fact still be worth retaining?
3. What can go wrong when current and historical information coexist?
4. What do the supplied sources suggest a memory system should do when information changes?
5. What do the supplied sources **not** establish?

For every important factual claim, identify the source file that supports it.

Clearly distinguish between:

- **Directly supported finding** — explicitly established by one or more supplied sources
- **Synthesis or inference** — a conclusion you are drawing by connecting information across sources
- **Unresolved question** — something the supplied evidence does not establish

Important constraints:

- Do not treat vendor documentation as independent proof that a design works universally.
- Do not treat the four systems or papers as if they describe the same architecture.
- Do not assume that the newest stored item is automatically the current truth unless the evidence supports that conclusion.
- Do not assume that retaining an old fact means the system should continue using it as current.
- Do not assume successful retrieval means the model will use retrieved information correctly.
- Preserve disagreements and differences between the sources rather than smoothing them into one unified mechanism.
- If the evidence is insufficient to support a conclusion, say so explicitly.
- Do not recommend TinyTalk or refer to any implementation that is not present in the supplied files.

End with a short section titled **Practical Design Principles** containing 3–5 principles that follow from the supplied evidence.

For each principle, indicate whether it is:

- strongly supported by the sources, or
- a reasonable design inference based on the sources.

Do not present design inferences as established research findings.