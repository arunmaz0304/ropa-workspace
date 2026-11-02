# Dry run 1: Claude on the Lumen demo data

2 November 2026. Question: can Claude do evidence-backed drafting and gap detection on messy inputs without inventing values?

Output of the run: [claude-intake-output.md](claude-intake-output.md), unedited.

## Method

- A separate Claude agent got only the inputs (register as CSV, three contract summaries, retention policy) and the product rules: every value shows a source or stays open, controller and processor records are separate, every gap gets an owner and a due date.
- It was not told what to look for and never saw the answer key. It reported reading only the five input files. That is self-reported, not logged.
- Scored by Claude against `demo-data/answer-key.md`. Same model family as the agent, so treat the result as a first signal, not a verdict.

## Result

11 found, 1 partly found, 0 missed, 0 invented values.

| # | Finding | Result | What it did |
|---|---|---|---|
| F1 | Recruitment retention blank | Found | Left erasure OPEN, noted the policy excludes applicants, gap G17 to Erik Holm. No period invented |
| F2 | No recruitment contract | Found | Recipients and transfers marked unsupported, gaps G15 and G18 |
| F3 | CRM retention conflict | Found | Left erasure OPEN, listed 7 years, 5 years and 5 years after last purchase, G03 to Maja Lindqvist |
| F4 | Duplicate CRM row | Found | Not drafted as its own record, G05 asks to merge |
| F5 | Payroll US support, SCCs not attached | Found | Transfer suggested with source, marked unconfirmed, G09 asks for the SCCs and any assessment |
| F6 | AI support role wrong | Found | Flagged the conflict, drafted as a controller record, G22 |
| F7 | AI chat retention "TBD" | Found, more cautious than the key | Kept erasure OPEN but showed the 12-month vendor default with its source, G24 to Sofia Nyberg |
| F8 | Model improvement, opt-out off | Found | In purposes and in note 4, G25. Read the clause correctly: use is active unless Lumen opts out |
| F9 | Newsletter tool unnamed | Found | G30 asks for tool, vendor and contract |
| F10 | Returns portal, no controller named | Found | Processor record, controllers OPEN, G37 asks for the partner list |
| F11 | Owners incomplete | Partly | Flagged "Marketing" with no person and the portal with no owner. Did not flag "Maja" as a first name only |
| F12 | US LLM provider | Found | Transfer suggested with source, SCC copy requested, G23 |

## Invented values

None found. Every filled value cites a register line or a contract item. One disclosed assumption: for Recruitment, Newsletter and the Returns portal the agent took "Lumen Outdoor AB" as the entity from the retention policy title, and said so.

## Weak spots

- 40 gaps for 6 activities. Six are "confirm everything" bundles. Too many for a business owner to face at once. A real tool has to prioritise.
- Questions still use terms like SCCs and sub-processors. Not yet written for a non-lawyer.
- 11 gaps went to "unassigned, DPO", including every security-measures gap. Most of those belong with an activity owner or IT.
- Kept AI chat retention OPEN where the key expects a suggested 12 months. Cautious, and arguably right.

## What this does not show

- **Import.** Inputs were clean CSV and markdown, not a messy .xlsx or scanned PDFs.
- **Steps 4 to 7.** Owner validation, approval states, change propagation and export. These are workflow, not extraction. They are where tools differ and where your hypothesis lives.
- **Repeatability.** One run, one model, data and key written by the same person.

## Key changes after this run

Run 1 was scored against the old key. Later runs use the corrected one.

- **F10.** No partner is named anywhere in the data, so "one gap per partner" can't be met. Now asks for a gap for the partner list.
- **F11.** The operations lead isn't mentioned in any input, so no tool could find it. Replaced with the returns portal having no owner.

## Next

1. Repeat with the real files uploaded (.xlsx and PDFs).
2. Test the change step: add a sub-processor, change a retention period, check that the right records return to draft.
3. Run the same inputs through the shortlisted vendors and compare.
