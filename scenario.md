# Scenario

Use this for every vendor demo and every build test. Fill the framing block first.

## Framing (Step 0)

> Example values (synthetic), matching the fictional company in `demo-data/`. Replace them when you use this for a real client.

- Client / project: Lumen Outdoor AB (fictional). Choose a RoPA tool and set up a register that stays current.
- Who decides: Lumen's managing director, on the recommendation of Anna Berg (external DPO).
- Primary user (SME owner / privacy lead / external DPO): External DPO (Anna Berg). Business owners (Maja Lindqvist, Erik Holm, Sofia Nyberg) confirm their own activities.
- Replacing what today: A single Excel register, last updated between 2022 and 2025, with unclear owners and no approval trail.
- Decision deadline: 15 December 2026.
- Lane (Evaluate / Build / Both): Both. Evaluate 2 or 3 tools first. Build only if none passes the P0 checks.

## Test scenario

> We are an EU company using a CRM, payroll system, recruitment platform, and AI customer-support assistant. We already have an Excel register, supplier contracts, and a retention policy. Show us how you import these, identify missing information, validate it with owners, and produce separate controller and processor records.

## Inputs for the demo

Ready-made fictional inputs are in [`demo-data/`](demo-data/) (a made-up Swedish retailer, Lumen Outdoor AB). Use them as they are, or swap in your own with the same shape.

| Input | In `demo-data/` | Notes |
|---|---|---|
| Excel register | `excel-register.xlsx` (and `.csv`) | Messy on purpose: missing retention, a conflict with the policy, a duplicate row, a wrong role |
| Supplier contracts | `contracts-pdf/` (and `contracts/` as markdown) | CRM vendor, payroll provider, AI support assistant. No contract for recruitment or the newsletter tool, deliberately |
| Retention policy | `retention-policy.md` | Covers some activities, not all |
| Named owners | listed in `demo-data/README.md` | Sales lead, HR lead, support lead, external DPO. One owner is missing on purpose |
| Answer key | `answer-key.md` | 12 planted findings. Keep it away from vendors until after the demo |

Use fictional data, not real client data, in vendor demos.

## Systems in scope

1. CRM
2. Payroll
3. Recruitment platform
4. AI customer-support assistant

## Expected outcomes

- Imported activities with sources shown
- Missing information listed as questions with owners
- Owner confirmation and DPO review recorded separately
- A controller record and a processor record, structured differently
- At least one change (new vendor or changed retention) routed for revalidation
- Export of records, evidence references and version history
