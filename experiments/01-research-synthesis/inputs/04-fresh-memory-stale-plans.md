# Source Packet 04 — Fresh Memory, Stale Plans: when updated facts do not update derived actions

## Source

Evan Chen, Shiqiang Wang, and Christopher G. Brinton,  
**“Fresh Memory, Stale Plans: Dependency-Scoped Validation for Distributed LLM-Agent Memory”**  
arXiv:2609.03340  
https://arxiv.org/abs/2609.03340  
Submitted September 3, 2026.

## Research focus

This preprint studies a failure mode in distributed LLM-agent systems where an agent can receive the newest shared fact while still acting from a plan that was derived from an older version of that fact.

The authors call this **stale-plan execution**.

Their example pattern is:

1. a planner creates an action based on an earlier requirement;
2. another agent later updates that requirement;
3. an executor can see the new requirement;
4. the previously derived plan is not automatically invalidated;
5. the executor may therefore act using a plan whose assumptions are no longer current.

The paper’s central point is that **fresh state does not guarantee fresh derived behavior**.

The authors introduce a protocol called PlanFence. Plans record which public records they depended on. Before an external action is executed, the relevant dependencies are validated. If a dependency changed, the system can replan or block the action rather than blindly executing the old plan.

In 30 controlled live workflows containing a revision after planning, the paper reports that a freshness-only executor acted on the obsolete plan in all 30 tasks. Under the PlanFence setup, all 30 tasks completed without an invalid action.

The authors explicitly characterize these as controlled safety and systems-cost results rather than broad claims about overall task accuracy.

## What this source establishes

- Updating stored/shared information may be insufficient when other system state was derived from the old information.
- A plan can become stale even while the underlying memory or shared record is fresh.
- Tracking dependencies between facts and derived plans can provide a way to detect when replanning is necessary.
- “The system knows the new fact” and “the system is behaving according to the new fact” are separate questions.

## What this source does NOT establish

This is a September 2026 preprint, not a universally established design standard.

The experiment concerns distributed LLM-agent workflows, not ordinary consumer-chat preference memory.

The 30/30 results apply to the authors’ controlled experimental setup and should not be generalized to all agents or tasks.

The paper does not show that every memory update must invalidate every downstream plan; its proposed validation is dependency-scoped specifically to avoid unnecessary revalidation.
