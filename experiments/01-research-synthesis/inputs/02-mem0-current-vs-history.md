# Source Packet 02 — Mem0: current facts, superseded facts, and retrieval

## Source

Mem0, **“Dream: Background memory consolidation for AI agents”**  
https://mem0.ai/blog/dream-background-memory-consolidation-for-ai-agents  
Published August 4, 2026; page updated September 28, 2026.

## Documented behavior

Mem0 describes a memory-consolidation system called Dream for long-running AI agents. The stated problem is that memory stores accumulate duplicates, contradictions, and facts that were once true but are no longer current.

Dream uses several lifecycle operations. The most relevant one for this experiment is **supersede**.

When Mem0 determines that a newer memory clearly replaces an older fact, the older memory is not deleted. Instead, it is marked as `superseded` and points to the replacement memory.

Mem0 says superseded memories remain available because historical information can still be useful.

By default, superseded memories can still appear in search. Mem0 exposes a `latest_only=true` option when an application wants retrieval limited to current, non-superseded memories.

This creates a deliberate distinction between:

- keeping a complete historical record, and
- retrieving only the memories treated as current.

Mem0 says its supersede decision is intended to be conservative. A supersede should occur only when the new information is a clear replacement for the same fact. If the relationship is ambiguous, the system is supposed to take no supersede action.

The system records lifecycle changes rather than destructively deleting the old memory. Mem0 also describes storing a pointer from the older memory to the replacement.

Dream includes other consolidation operations, such as merging duplicates and creating synthesized higher-level memories from multiple supporting observations. Those behaviors are separate from superseding an outdated fact.

## What this source establishes

- A memory system can preserve an old fact while marking it as no longer current.
- “Current truth” and “full history” can be exposed as different retrieval views.
- Keeping history does not require treating every historical item as simultaneously active.
- Retrieval policy matters: if superseded items are returned, a downstream model may receive both old and new information.
- Mem0 treats ambiguous replacement as a reason not to supersede automatically.

## What this source does NOT establish

This is Mem0’s own product documentation/blog material, not an independent evaluation.

It does not prove that the supersede classifier always identifies conflicts correctly.

It does not prove that a downstream language model will always use the current fact correctly after retrieval.

It does not establish that Mem0’s approach is the only correct architecture for handling changing information.

The source describes a specific Mem0 feature and should not be generalized to all AI memory systems.
