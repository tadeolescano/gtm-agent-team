# Design principles

These rules came from running a team of narrow AI agents against real GTM work: idea validation, launch plans, competitive audits and brand monitoring. Each rule exists because breaking it produced a specific, repeatable failure.

## 1. One job, one sentence

Every spec opens with `One job:` followed by a single sentence. The test is simple: if the sentence needs two "and"s, split the agent.

**Why.** A model optimises for the whole prompt. An agent asked to "generate ideas, plan distribution and write the ads" produces mediocre ideas because it is already thinking about ads. Narrow agents produce sharper output and failures are attributable: when a plan is weak, you know which spec to fix.

**Smell.** The spec has a section called "Other things you can help with."

## 2. Anti-jobs are explicit and point somewhere

Each spec has an `Anti-jobs` list: what the agent refuses even when the operator asks directly. Every anti-job names who owns that work instead.

```
- Does not choose or generate business ideas. Owner: idea-validator.
- Does not launch campaigns or spend budget. Owner: the operator.
```

**Why.** Without anti-jobs, helpful models drift into adjacent work and do it badly. Pointing to the owner turns a refusal into a hand-off, so the operator never hits a dead end.

## 3. No leftover tools

An agent gets exactly the tools its one job requires. Remove a tool the moment a spec change makes it unnecessary.

**Why.** Unused tools are both a distraction (the model tries to use them) and a risk surface (an analysis agent with email access can email). Capability should follow responsibility, not convenience.

| Agent | Needs | Does not get |
|---|---|---|
| router | agent hand-off, read-only calendar/inbox for summaries | send, spend, publish |
| idea-validator | web search, append-only idea log | email, browser automation, payments |
| growth-architect | web search, page fetch, document write | email, ad accounts, payments |
| market-intel | web search, page fetch, headless browser for screenshots, document write | forms, logins, social actions |
| brand-listener | search over public forums/news/social, digest delivery to the operator | posting, replying, liking |

## 4. Evidence tags on every claim

Four tags, used consistently across the team:

| Tag | Meaning | Required companion |
|---|---|---|
| `[FACT]` | Observed directly | Source link and access date; screenshot when visual |
| `[INFERENCE]` | Deduced from facts | The reasoning in one line |
| `[ESTIMATE]` | Approximate number | A range and the method |
| `[ASSUMPTION]` | Stated to keep moving when input is missing | What would confirm or kill it |

Two hard rules follow:

- **No point values without a source.** "CPC is $2.40" is forbidden. "CPC `[ESTIMATE]` $1.50 to $3.50, based on keyword planner ranges for 3 head terms" is fine.
- **Missing is a section, not a gap to fill.** If a channel does not exist or cannot be opened, it goes under "Not found or not accessible." It is never padded.

## 5. Humans own irreversible actions

Sending, spending, publishing, deleting and contacting third parties are human actions. Agents draft; the operator executes.

When an agent is explicitly asked to send something, the approval covers **that message, to those recipients, once**. A later "send the follow-up too" is a new approval.

**Why.** In GTM the irreversible actions are also the expensive ones: domain reputation, ad budget, a prospect's first impression.

## 6. Intake is bounded

When critical input is missing, an agent asks **at most five questions in one message**, then proceeds. If the operator says "assume" or does not answer, the agent continues with `[ASSUMPTION]` tags.

**Why.** Unbounded clarification loops kill momentum. A tagged assumption is reviewable; a blocked agent is not.

Agents ask **upstream before asking the human**: the growth architect asks the idea validator for context on an idea it produced before bothering the operator.

## 7. Short chat, long artifact

Long deliverables (a launch plan, an audit) go into a document with headings and tables. The chat gets two or three lines: the verdict, what to do first, and the link.

**Why.** Chat is for decisions. A 4,000-word plan in a chat window is unreadable and gets lost.

## 8. Self-critique before delivery

Before output leaves the agent:

- The idea validator kills its own weakest ideas and says why, attacking each like a sceptical investor and a frugal business owner.
- Market intel re-checks every claim against its source and deletes what it cannot prove.
- The growth architect names the top risks plainly, including "this market is too small" when true.

## 9. Silence is a valid output

Watchers and reporters stay quiet when nothing clears the bar. A daily digest that says "nothing today" trains the operator to ignore it.

## 10. Agents learn from feedback, in writing

When the operator corrects an agent, the lesson is saved as a short rule in the agent's persistent notes and applied from that message on. The agent states what it learned in one line ("learned: nothing that needs more than two weeks of setup").

## 11. One voice per agent

Each spec defines a voice: direct, senior, no motivational filler, no AI jargon, no empty adjectives. The answer comes first. Reports use plain analyst English.

## Checklist for a new agent

- [ ] `One job:` fits in one sentence
- [ ] Anti-jobs listed, each with an owner
- [ ] Tool list matches the job; nothing left over
- [ ] Output contract defined (shape, location, chat summary length)
- [ ] Evidence tags required where numbers or claims appear
- [ ] Human gate on every send/spend/publish/delete
- [ ] Trigger defined: on request only, or on a schedule with a quiet-day rule
- [ ] At least two fictional I/O examples
