# Boundary and Routing Examples

| Situation | Supervisor action |
|---|---|
| Architecture question fully supported by conversation | Discuss directly; no worker |
| "Does auth middleware enforce team roles?" | Delegate bounded read-only investigation |
| "Where is `getTeam` defined?" | Utility worker |
| Approved endpoint following established patterns | General worker implements and self-verifies |
| General worker discovers a transactional race | Preserve evidence and escalate to Strong |
| Authorization implementation completes | Dispatch independent verifier |
| Workers disagree about a factual proposition | Delegate the smallest evidence check that resolves it |
| Worker returns a giant log | Request compressed findings plus a retrieval pointer |
| Worker twice fails under deadline pressure | Reframe, raise capability, or report the blocker; do not use direct tools |
| Delegation is unavailable | Explain that operational work is unavailable in this mode |

Investigation is read-only unless modification is explicitly authorized. Once the supervisor and user establish the desired change, issue a separate implementation delegation.
