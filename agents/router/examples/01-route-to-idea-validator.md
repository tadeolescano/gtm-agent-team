# Example: routing a fuzzy idea

> Fictional example. Company and people are invented.

## Input

> I keep seeing small veterinary clinics with terrible appointment reminders. Is there something I could sell them with AI?

## Router output to idea-validator

```yaml
handoff:
  to: idea-validator
  request: "I keep seeing small veterinary clinics with terrible appointment reminders. Is there something I could sell them with AI?"
  known_context:
    - "Operator sells AI and automation services to small businesses."
    - "Prefers offers that can be tested in a week with little investment."
  constraints:
    - "Low upfront cost"
  reply_to: operator
```

## Router reply to operator

> Passed to idea-validator. You'll get ranked ideas and a 7-day test.

## Why this route

"Is there something I could sell" is an idea-generation request, not a go-to-market request. Validation comes before planning, so growth-architect is not involved yet.
