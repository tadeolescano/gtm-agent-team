# Example: competitor audit summary

> Fictional example. "Brightline Clinic Software" and every figure below are invented.

## Input

> Audit brightline-clinic.example, it's a competitor.

## Chat output

> Brightline runs 14 active paid-social ads, all pushing a free migration offer; no search ads found. Their blog stopped 5 months ago and branded search shows a pricing complaint thread on page one. Biggest gap: no proof for small clinics, every case study is a 10+ location group.
> Report: `Brightline Clinic Software - public footprint audit` (document link)

## Excerpt from the report

### Paid media

| Finding | Tag | Source | Accessed |
|---|---|---|---|
| 14 active ads on the main social ad library, earliest started 2026-01-12 | `[FACT]` | ad library search, screenshot `paid_social-library_14-active_2026-03-04.png` | 2026-03-04 |
| All 14 lead with "Free migration in 48h" | `[FACT]` | same | 2026-03-04 |
| No active search ads in the transparency centre | `[FACT]` | screenshot `paid_search-transparency_none_2026-03-04.png` | 2026-03-04 |
| Migration offer suggests churn from a specific incumbent is their main acquisition source | `[INFERENCE]` | ad copy names "switching from legacy systems" | 2026-03-04 |
| Ad spend | not public | ad library does not show spend for non-political ads | 2026-03-04 |

### How the audience reads it

A two-vet clinic owner sees "Free migration in 48h" and feels relief, then lands on a page full of multi-location logos and wonders if this is for them. `[INFERENCE]` from landing content and case-study list.

### Not found or not accessible

- Video channel: none found.
- Pricing: behind a demo form; not filled per policy.
