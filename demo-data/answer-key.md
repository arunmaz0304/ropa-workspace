# Answer key

What a good tool should find in the demo data. Don't share this with vendors before the demo.

Mark each finding as: **found**, **missed**, or **invented** (the tool filled a value with no support).

## Findings

| # | Finding | Where | A good tool should |
|---|---|---|---|
| F1 | Recruitment retention is blank in the register and not covered by the policy | Register row 3, policy | Leave it empty, create a gap for Erik Holm. Not invent a period |
| F2 | No contract for the recruitment platform | Contracts folder | Show recipients and transfers as unsupported, create gaps |
| F3 | CRM retention conflict: register says 7 years, policy says 5 years after last purchase | Register row 1, policy | Flag the conflict, ask the owner (Maja Lindqvist), not pick one silently |
| F4 | Duplicate CRM row with a different retention and a different owner name | Register row 6 | Flag as a likely duplicate for merge or removal |
| F5 | Payroll "outside EU" is blank, but the contract names a US support sub-processor with SCCs referenced, copy not attached | Register row 2, payroll contract | Suggest the transfer with its source, mark unconfirmed, create a gap for the safeguards document |
| F6 | AI support role is wrong: register says processor, but Lumen decides the purpose, so Lumen is controller and HelpPilot is the processor | Register row 4, AI contract | Flag the role mismatch, place the activity in the controller record |
| F7 | AI chat retention is "TBD". Contract default is 12 months, configurable. Policy is silent | Register row 4, AI contract, policy | Suggest 12 months labelled as the vendor default with its source. Owner must confirm or set Lumen's own period |
| F8 | HelpPilot may use anonymised transcripts to improve models unless opted out. Opt-out is off | AI contract | Raise it for the DPO and the AI-use inventory |
| F9 | Newsletter tool is unnamed and has no contract | Register row 5 | Create a gap for the vendor name and a contract |
| F10 | Returns portal: Lumen is processor, but no controller (partner shop) is named | Register row 7 | Produce a processor record, mark controller names as open, create a gap for the partner list (no partner is named in the data) |
| F11 | Owners are incomplete: first name only on one row, "Marketing" with no person, returns portal with no owner | Register rows 5-7 | Ask for a named owner for each |
| F12 | US LLM provider for the AI assistant: transfer and safeguards are not documented | AI contract | Suggest the transfer with its source, flag the missing safeguards copy |

## Bonus finding

Not planted on purpose, found in dry run 2.

| # | Finding | Where | A good tool should |
|---|---|---|---|
| B1 | The retention policy lists website analytics data and accounting documents, but neither activity is in the register | Policy, register | Ask whether those activities exist, who owns them, and which tools they use |

## Expected outputs

- Controller records: customer management, payroll, recruitment, AI customer support, newsletter.
- Processor record: returns portal for partner shops.
- Open gaps at the end of intake: at least the items in F1, F2, F3, F5, F7, F9, F10 and F11.
- No field filled without a source.

## Version

v1.1, 2 November 2026. F10 and F11 corrected after dry run 1, because the original wording asked for things that can't be found in the inputs. See `evaluation/dry-run/dry-run-1-score.md`.

## Change test (demo step 6)

Do both:

1. Tell the tool that ClientHub is adding a new analytics sub-processor.
2. Change CRM retention to 5 years after last purchase.

A good tool flags the CRM activity, routes it to Maja Lindqvist and Anna Berg, returns the record to draft, and requires revalidation. A weak tool changes the field silently.
