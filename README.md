# Eval for Eval

An English-language skill for auditing how agents are evaluated. It helps test whether an evaluation measures what it claims, find false accepts and false rejects, and verify fixes with independent evidence. It covers documentation audits, offline scoring, and end-to-end experiments.

## Use with your agent

- **Agent Skills-compatible clients.** Install the [`eval-for-eval`](skills/eval-for-eval/) directory using your client's skill installation or discovery mechanism. Ask the agent to use `eval-for-eval` by name. [Agent Skills specification](https://agentskills.io/specification)
- **Any agent that accepts text instructions.** Paste the Markdown body of [`SKILL.md`](skills/eval-for-eval/SKILL.md) into a chat, project instruction field, or system prompt. Then provide your audit request and available evidence. Everything needed to follow the workflow is in that one file.

```text
Use eval-for-eval to audit this agent evaluation. Check whether the grader
can pass a failed task based on the final answer alone. Give a minimal case
family and an independent way to verify each outcome.
```

The skill has no bundled scripts, runtime dependencies, or provider-specific tool requirements. A text-only agent can reconstruct the method and design tests. Running an offline or end-to-end experiment requires access to the relevant grader, evidence, and, for end-to-end tests, an executable agent and environment.
