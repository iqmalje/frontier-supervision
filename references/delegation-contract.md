# Delegation Contract

Use the shortest form that preserves these decision-relevant fields.

```text
OBJECTIVE
Concrete result the worker must produce.

PURPOSE
Decision or next step this result supports.

REQUIRED INFORMATION
Questions that must be answered.

KNOWN CONTEXT
Established facts the worker should not rediscover without cause.

SCOPE / OUT OF SCOPE
Initial boundary and prohibited expansion.

PERMITTED ACTIONS
Read-only investigation, modification, targeted execution, web access, or another explicit set.

AUTONOMY
Strict | Local expansion | Goal-directed

EVIDENCE AND VERIFICATION
Files, symbols, commands, tests, or other proof required before returning.

RETURN
Required report sections and approximate return budget.

ESCALATE WHEN
Facts conflict, confidence is low, risk or scope expands materially, or a consequential decision is required.
```

Use **Strict** when the supplied boundary must not move. Use **Local expansion** by default; it permits direct callers, imports, and definitions needed for the objective. Use **Goal-directed** for a well-defined result where broader investigation is expected, while excluding unrelated cleanup.

On escalation, preserve findings, identify the unresolved decision, and state the next capability or user decision required.
