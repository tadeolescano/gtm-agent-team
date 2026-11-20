# Example: chat reply for a finished plan

> Fictional example. Company names and figures are invented.

## Input

```yaml
validated_idea:
  name: "Tidybooks onboarding"
  customer: "Two-to-ten person bookkeeping firms"
  pain: "New-client onboarding takes two weeks of chasing documents."
  offer: "Automated document-request portal with reminders, set up in 3 days"
  price_model: "Setup 400 + 89/month"
  first_10_customers_channel: "Regional bookkeeping associations"
  viability_score: 7
  experiment_7d:
    action: "Demo to 12 firms from one association directory"
    success_metric: "3 paid setups"
```

## Chat output

> Verdict: viable, narrow wedge. Lead with "onboard a client in 3 days, not 2 weeks."
> Launch first: association partnership + a comparison page against generic form builders. Paid search waits until the landing converts above 4% organically.
> Plan: `Tidybooks onboarding - GTM prototype` (document link)

The document contains all seven sections. An excerpt of the pricing table:

| Plan | Price | Includes | For | Upgrade trigger |
|---|---|---|---|---|
| Starter | 59/mo `[ASSUMPTION]` | 15 active clients, email reminders | Solo bookkeepers | Client cap |
| Firm | 89/mo | 60 active clients, SMS reminders, branding | 2 to 10 staff | Branding, SMS |
| Practice | 169/mo | Unlimited, multi-office, API | 10+ staff | Multi-office |

Unit economics: max tolerable CAC `[ESTIMATE]` 180 to 260, from 89/mo, 80% gross margin and a 3 to 4 month payback target.
