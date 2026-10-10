# Research Memo: What Stays Current When a Saved Preference Changes

**Question.** When a user changes a previously saved preference, how should an assistant decide what is current, what should remain historical, and what can go wrong if retrieval does not account for the change?

**Evidence limit.** Four packets describe different systems. `01-openai-memory-controls.md` (OpenAI help; “Dreaming,” June 4, 2026) and `02-mem0-current-vs-history.md` (Mem0, August 4, 2026, updated September 28, 2026) are vendor accounts, not independent proof. `03-longmemeval-knowledge-updates.md` is LongMemEval (submitted October 14, 2024; revised March 4, 2025). `04-fresh-memory-stale-plans.md` is Chen, Wang, and Brinton (submitted September 3, 2026) on distributed agents.

## 1. What does it mean for information to be “current”?

**Directly supported finding.** In `01`, remembered information changes with context, and the system selects what is relevant. “Dreaming” gives a trip memory that should later reflect that the trip already happened, inside an updated summary rather than only a static saved-memory list. In `02`, only a clear replacement of the same fact is superseded: the old memory is marked superseded and pointed at the replacement; ambiguity should block that step, and `latest_only=true` returns non-superseded items. In `03`, knowledge updates mean recognizing a later revision, and temporal reasoning uses when a statement was true. In `04`, stale-plan execution means a new shared fact can leave a plan from the old fact still running. Fresh state does not guarantee fresh derived behavior.

**Synthesis.** “Current” can mean response-relevant (`01`), non-superseded after a clear same-fact replacement (`02`), true at the required time (`03`), or governing action (`04`). No packet equates it with the newest stored item.

**Unresolved question.** No packet shows that the newest preference is current, or that conflict handling in `01` or `02` is reliable.

## 2. Why might an older fact still be worth retaining?

**Directly supported finding.** `02` keeps superseded memories because history can still be useful, returns them in search by default, and separates that history from a current-only view.

`01` separates lifecycles without that usefulness claim. Saved memories can survive deletion of the source chat. “Don’t mention this again” changes personalization and leaves the source in place. Disabling chat-history reference schedules derived information for deletion while the chats remain. `03` shows that an answer can depend on when a statement was true, and it states no retention policy. `04` treats an old record as a plan dependency to validate, which is separate from presenting it as the current preference.

**Synthesis.** Retention can serve search (`02`), an independent source lifecycle (`01`), a time-specific question (`03`), or dependency checking (`04`).

**Unresolved question.** The packets do not show that every old preference should be kept, or that keeping it authorizes continued use.

## 3. What can go wrong when current and historical information coexist?

**Directly supported finding.** Returned superseded items in `02` can show the model both versions, with no evidence of correct selection. `03` separates indexing, retrieval, and reading, so retrieved text can still be misread; its drop of roughly 30 percent is an aggregate on sustained interaction, not a knowledge-update score. In `01`, correct conflict choice is not shown, and the memory summary may omit details or sources. In `04`, the executor can see a new requirement while the old plan remains. Across 30 controlled workflows with a post-plan revision, a freshness-only executor used the obsolete plan every time; PlanFence finished all 30 with no invalid action.

**Synthesis.** The failures above are distinct, and retrieval does not establish correct use.

**Unresolved question.** `03` does not test the preference-change scenario it names. The 30-task result stays inside the distributed-agent setup in `04`.

## 4. What do the supplied sources suggest a memory system should do when information changes?

**Directly supported finding.** `01` lets users flag a memory as incorrect or outdated and, where supported, edit it; chat-history derivatives can be revised; controls vary by plan, region, platform, and workspace. `02` keeps the old memory as superseded, with a pointer and a current-only view, and should skip supersede when the link is unclear. `03` varies indexing and retrieval, including time-aware query expansion. `04` validates recorded plan dependencies before an external action and can replan or block. The check stays dependency-scoped.

**Synthesis.** Joining conservative replacement (`02`), update-and-time tests (`03`), user correction (`01`), and a dependency check (`04`) into one pipeline is an inference.

**Unresolved question.** No packet measures when a new preference replaces an old one rather than adding another current fact, beyond the ambiguity rule in `02`.

## 5. What do the supplied sources not establish?

**Directly supported finding.** `01` withholds its full retrieval algorithm and any claim of identical controls on every account. `02` does not prove its classifier, correct downstream use, or that its design is the only valid one. `03` does not turn the headline drop into a knowledge-update score or a universal fix. `04`’s 30 workflows are controlled safety and cost results on distributed agents, not a consumer-chat finding.

**Unresolved question.** A general rule for a changed preference remains open, as does whether the newest item, a rewritten summary, current-only search, or a dependency check is sufficient alone.

## Practical Design Principles

1. **Separate “still stored” from “treated as current.”** Strongly supported by superseded status and `latest_only` in `02`, and by a different lifecycle split in `01`. Neither vendor account is general proof.

2. **Supersede only for a clear replacement of the same fact.** Strongly supported as the rule in `02`, including no action when the link is ambiguous. Correct application is not established.

3. **Treat retrieval and correct use as separate problems.** Strongly supported in different forms: reading can fail after retrieval (`03`); both versions may be returned (`02`); a fresh fact need not refresh an earlier plan (`04`).

4. **Validate recorded dependencies before an external action.** Strongly supported inside the controlled setup in `04`. Extending that check to ordinary chat personalization is a reasonable design inference, not a finding of that paper.

5. **Carry time and update structure into retrieval and reading.** A reasonable design inference from the temporal and knowledge-update abilities in `03`.