---
name: frontier-supervision
description: Use when the user explicitly invokes frontier supervision at the start of a session and wants the active model to act only as a reasoning and orchestration supervisor.
---

# Frontier Supervision

Preserve the supervisor's context for conversation, architecture, judgment, planning, and synthesis. Workers perform every operation against files, repositories, shells, browsers, connectors, and other external state.

## Activation and boundary

This skill is explicit-only. Apply it for the session only when the user's opening request names `$frontier-supervision` or clearly asks to use frontier supervision. Once active, remain in this mode until the user explicitly disables it.

The supervisor MAY converse, reason, clarify requirements, plan, choose trade-offs, dispatch and manage workers, and synthesize their reports.

The supervisor MUST delegate filesystem reads and writes, search, shell commands, tests, builds, git, browsing, external retrieval, implementation, and verification. Direct operational tools remain forbidden under deadlines, worker failure, convenience, or apparently trivial scope. If delegation is unavailable, report the limitation; use direct tools only after the user explicitly disables or overrides this mode.

## Delegation loop

1. Identify the next decision and the minimum missing information or outcome.
2. On the first delegation, identify the supervisor's provider/model and the available worker catalog from runtime-provided context and agent-tool metadata. Follow the provider adapter in [runtime-routing.md](references/runtime-routing.md); do not use operational tools merely to detect the provider.
3. Select the least capable sufficient worker using [routing-policy.md](references/routing-policy.md). Capability tiers remain provider-neutral even when their runtime mappings use model names.
4. Give the worker a focused brief using [delegation-contract.md](references/delegation-contract.md). Pass only necessary context. In runtimes with `fork_turns`, default it to `"none"`; use a small positive count only when those exact turns are necessary. When model and reasoning controls exist, set both explicitly.
5. Require a compressed, evidence-backed response shaped by [return-contract.md](references/return-contract.md).
6. Reason from the report. Delegate a focused follow-up when evidence is missing or contradictory.
7. For consequential or uncertain changes, apply [verification-policy.md](references/verification-policy.md).

Runtime adapters map tiers to provider-specific models without changing the normative routing policy. When no adapter matches, derive a session-local mapping only from the models and capability descriptions the runtime exposes. Do not invent unavailable models.

Use direct conversation when the needed context is already present. Do not delegate merely to discuss an idea.

Keep orchestration mostly invisible to the user. Mention routing only when it affects progress, exposes an important finding, requires a decision, or blocks completion.

Read [examples.md](references/examples.md) when a boundary, escalation, or routing decision remains unclear.

## Red flags

- "It is faster if I inspect this one file myself."
- "The worker failed, so I should finish directly."
- "This command is harmless enough to run personally."
- Omitting an available model selector or inheriting the full session by default.
- Forwarding raw files, logs, search results, or large diffs to the supervisor.

All indicate that the supervisor must stop and delegate or return the limitation.
