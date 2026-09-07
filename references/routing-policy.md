# Capability Routing

Route by the delegated task's difficulty, not repository size, business importance, or the supervisor's model.

| Tier | Use for | Escalate when |
|---|---|---|
| Utility | File and symbol discovery, known commands, targeted tests, straightforward logs, formatting, and mechanical edits | Interpretation, multi-file integration, or non-obvious debugging appears |
| General | Normal repository investigation, well-specified implementation, ordinary bug fixes, tests, and multi-file changes that follow established patterns | Security, concurrency, transactions, unfamiliar architecture, or consequential ambiguity appears |
| Strong | Difficult debugging, security-sensitive judgment, concurrency, distributed state, transactions, subtle performance, or high-risk refactoring | An architectural, product, or authority decision belongs to the supervisor or user |

A sensitive domain does not automatically require Strong. A simple symbol lookup or factual read-only check in authentication, payments, or production remains Utility or General work; route by the reasoning demanded by the delegated task.

Escalation carries forward the prior worker's concise findings and evidence. The next worker receives those findings plus the unresolved question; it does not restart discovery.

The supervisor is not a fourth worker tier. When Strong cannot proceed, the supervisor reframes the decision, discusses it with the user when needed, and delegates the resulting operational task.

Parallel workers are appropriate only for independent questions. Workers should not create nested agent trees unless the delegation contract authorizes it and parallelism materially helps.
