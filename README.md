# Agent Harness Playbook

**Do not put every rule, fact, workflow, and tool into one always-loaded file.**

Separate them by load behavior and responsibility. That single decision is what
keeps context cost down, prevents contradictory copies of the same knowledge,
and gives every change a clear verification path.

📖 **[Read the playbook](https://amandachan-ai.github.io/agent-harness-playbook/)**

---

## The core split

| Concern | Best home | Why |
|---|---|---|
| Rules that must never be missed | Global instructions | They are sent on every request, so keep them short |
| Verified facts, decisions, incidents | Indexed memory | Retrieved when relevant, not sent continuously |
| Repeatable multi-step workflows | Skills | They need triggers, ordered steps, guardrails, completion criteria |
| External capabilities | Tool servers | Capability configuration stays separate from policy and knowledge |
| Per-session progress and artifacts | Session state | Conversation-specific state should not become global memory |

## Also covered

- **Memory patterns** — one source of truth per topic, and updating the existing
  entry when new evidence overturns an old conclusion rather than appending
  a second, contradictory one
- **Skills vs subagents** — when a workflow deserves each
- **Session-state ritual** — naming and recording so a session can be found again
- **Tool profiles** — a lean default, opt-in extras, and a recovery rule
- **Verification and recovery** — proving state rather than claiming it
- **Failure patterns** — eight, each with the lesson
- **Public adaptation checklist** — what to remove or generalize before
  publishing a harness document, and what is safe to keep

## One failure worth reading first

**A checker stays green while the system is wrong.** The lesson is to test the
checker against a known failure before trusting it — if it does not go red on a
case you know is broken, a green result means nothing. The same idea appears in
the [Evaluation Playbook](https://github.com/amandachan-ai/evaluation-playbook)
as *a number that a failure can also produce is not a check*; harness
engineering and evaluation share most of their failure modes.

## Scope

Developed against a command-line coding agent, but the pattern does not depend
on any one vendor. Contains no organization-specific services, product
codenames, account details, machine identifiers, private paths, usage telemetry,
credentials, or private knowledge catalogs.

## License

MIT
