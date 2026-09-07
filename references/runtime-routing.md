# Provider-Aware Runtime Routing

Provider adapters translate portable capability tiers into models exposed by the active runtime. The supervisor performs this detection from its system identity and agent-tool metadata; provider detection is not an operational filesystem or web task.

## Detection

1. Read the supervisor model/provider identity supplied by the runtime.
2. Read the available subagent models and their capability descriptions from the dispatch interface.
3. Use a matching adapter below.
4. If no adapter matches, classify only the exposed models: fastest economical model for Utility, balanced coding model for General, strongest non-supervisor worker for Strong. If metadata cannot distinguish them, ask the user for a mapping before the first operational delegation.

Never invent a model name, assume that a provider model is installed, or silently inherit the supervisor model.

## OpenAI Codex adapter

Use when the supervisor is `gpt-6-astra` or the runtime exposes the matching Codex worker catalog.

| Capability | Model | Default reasoning |
|---|---|---|
| Utility | `gpt-5.6-luna` | `low` or `medium` |
| General | `gpt-5.6-terra` | `medium` or `high` |
| Strong | `gpt-5.6-sol` | `high` or `xhigh` |
| Supervisor | `gpt-6-astra` | Chosen by the user/session |

In Codex, specify `model`, `reasoning_effort`, and `fork_turns` when spawning. Default `fork_turns` to `"none"` and supply a self-contained delegation contract. Use a small positive turn count only when quoting those turns would be less precise or more expensive.

Raise capability when the worker reports a concrete reasoning limitation. Do not raise capability merely because a repository is large. Do not route routine verification to Astra; use a worker capable of independently judging the relevant risk.

## Additional providers

Add a provider section only after its runtime exposes a verified worker catalog. Keep the same Utility, General, Strong, and Supervisor meanings. Provider adapters may differ in names and reasoning controls; they must preserve explicit selection, minimal inherited context, and escalation without falling back to the supervisor as an execution worker.
