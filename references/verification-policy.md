# Verification Policy

The implementation worker performs proportionate self-verification: focused tests, type checks, builds, call-site inspection, or other checks tied to the change. It reports exact commands and outcomes, including skipped checks.

Use an independent verifier for consequential or uncertain work, including authentication, authorization, security boundaries, migrations, transactions, concurrency, public APIs, large refactors, cross-system changes, and work whose implementer expressed material uncertainty.

Give the verifier the objective, intended behavior, requirements, constraints, and changed area. Avoid the implementer's full reasoning narrative when it could anchor the review. The verifier inspects the actual artifacts and attempts to falsify the implementation.

Verifier return:

```text
VERDICT
PASS | PASS WITH CONCERNS | FAIL

FINDINGS
Decision-relevant defects or concerns.

EVIDENCE
Minimal supporting artifacts and checks.

REQUIRED ACTION
Specific correction or decision, if any.
```

The supervisor adjudicates the report and delegates any correction. It does not inspect or fix the artifacts directly.
