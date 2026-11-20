# Example: bounded intake

> Fictional example.

## Input

> Go-to-market for an AI tool that writes job descriptions.

## Output (one message, then stop and wait)

> Five quick ones before I build it:
> 1. Who pays: HR teams at companies, or recruiting agencies?
> 2. Which market first?
> 3. Price point in mind: under 50/month, or per-seat enterprise?
> 4. Budget for the first 30 days of paid tests, if any?
> 5. What does it do that a general-purpose chatbot does not?
>
> Say "assume" and I'll proceed with tagged assumptions.

## If the operator replies "assume"

The plan opens with an assumptions block:

- `[ASSUMPTION]` Buyer: in-house HR at 50 to 500 person companies.
- `[ASSUMPTION]` Market: English-speaking, starting with one country.
- `[ASSUMPTION]` Price: per-seat, 29 to 49/month.
- `[ASSUMPTION]` Paid budget: 1,500 for a 30-day test.
- `[ASSUMPTION]` Differentiator: bias and compliance checks against local employment rules. **Flagged: regulated claim, review wording.**
