# Demo data

Fictional inputs for running the scenario in `scenario.md`. Use them in vendor demos and to test a build. No real company, person or product is described. Any resemblance is coincidental.

## The fictional company

**Lumen Outdoor AB**, a Swedish online retailer of outdoor gear, about 85 employees, EU customers.

It uses a CRM, a payroll system, a recruitment platform and an AI customer-support assistant. It also runs a returns portal for partner shops, where it acts as processor.

| Role | Name (fictional) |
|---|---|
| Sales lead | Maja Lindqvist |
| HR lead | Erik Holm |
| Support lead | Sofia Nyberg |
| Operations lead | not named in the register (a gap) |
| External DPO | Anna Berg |

## Files

| File | What it is |
|---|---|
| `excel-register.xlsx` | The existing "Excel register", ready to upload. Messy on purpose |
| `excel-register.csv` | Same data as plain text, easy to read on GitHub |
| `contracts-pdf/` | The three contract summaries as PDFs, ready to upload |
| `contracts/crm-vendor.md` | Summary of the CRM supplier's data protection terms (editable source) |
| `contracts/payroll-provider.md` | Same, payroll provider |
| `contracts/ai-support-vendor.md` | Same, AI support assistant |
| `retention-policy.md` | Lumen's retention policy. Covers some activities, not all |
| `answer-key.md` | What a good tool should find. Don't show vendors this file |

There is no contract for the recruitment platform or the newsletter tool. That is deliberate.

## How to use

1. Give the vendor `excel-register.xlsx`, the three PDFs in `contracts-pdf/` and `retention-policy.md` (convert it to PDF or Word if the tool needs that).
2. Run `evaluation/demo-script.md`.
3. Compare what the tool shows against `answer-key.md`. Note what it found, missed, or invented.

The contracts are short summaries, not full agreements. Edit the markdown files in `contracts/` and regenerate the PDFs if you change them. If you change the data, update `answer-key.md` so the findings still match.
