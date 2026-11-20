# Fleet health

A team of agents drifts like any team. A short monthly review keeps it sharp.

## Monthly checklist

| Check | Question | Action if failing |
|---|---|---|
| One job | Does each agent's last month of work match its one-sentence job? | Tighten the job or split the agent |
| Anti-jobs | Did any agent do work its spec says it refuses? | Add the case to the anti-jobs list with an owner |
| Leftover tools | Is any granted tool unused for 30 days? | Remove it |
| Dead agents | Has any agent not been triggered in 60 days? | Archive it, or merge its job into another |
| Tag discipline | Sample 5 outputs: any untagged numbers? | Add a failing example to the agent's `examples/` |
| Human gates | Any send, spend or publish without explicit approval? | Treat as an incident; fix the tool permissions, not the prompt |
| Quiet-day rule | Did a watcher send "nothing today" messages? | Fix the bar or the trigger |
| Cost | Which agents or schedules consumed the most runs? | Lower frequency, narrow sources, or batch |
| Overlap | Did two agents answer the same kind of request? | Update the router's table; one owner per intent |

## Signals worth logging per run

- Agent, trigger (request or schedule), duration.
- Tools called.
- Whether the output was used, edited or ignored by the operator.
- Any hand-off and its target.

"Ignored" is the most useful signal: an agent whose output is regularly ignored has a wrong job, a wrong bar or a wrong voice.

## When to create a new agent

Only when the router hits the same unowned request three times and the work is large enough to need its own process. Start from the checklist in [docs/design-principles.md](../docs/design-principles.md#checklist-for-a-new-agent).
