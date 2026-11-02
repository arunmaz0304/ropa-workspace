# Dry run 2: real files and a change test

2 November 2026. Two blind runs, same method as [run 1](dry-run-1-score.md): a separate Claude agent, only the inputs and the product rules, no answer key. Both agents reported reading only their own input files (self-reported). Scored by Claude.

Outputs, unedited: [intake](claude-intake-output-run2.md) and [change test](claude-change-output-run2.md). The change-test key is [dry-run-2-key.md](dry-run-2-key.md), written before the run.

This is not a clean repeat of run 1. Part A used the real .xlsx and PDFs, and its prompt added two things: an import check section, and "write the questions so a business owner with no legal background can answer them".

## Part A: intake from the .xlsx and PDFs

12 of 12 findings found against answer key v1.1. No invented values.

- **Import held up.** The agent listed 8 blank cells and 2 placeholders ("TBD", "?"). I counted them in the spreadsheet: same 8 and 2, none missed, none invented. The PDFs were clean one-page tables read from the text layer.
- **F11 now fully found.** Run 1 missed "Maja" as a first name only. Run 2 asked "Is the 'Maja' in row 7 you?". One run each, so this could be luck.
- **F7 as the key expects.** Showed the 12-month vendor default with its source and left Lumen's actual period open. Run 1 kept the field OPEN.
- **One finding beyond the key.** The retention policy lists website analytics data and accounting documents, which are not in the register (gap G32). Added to the key as a bonus finding.
- **Fewer, plainer gaps.** 32 gaps against 40. Questions are written for a business owner, and security gaps went to the activity owner where one exists. The prompt change is a confounder, so I can't say how much is Claude and how much is the instruction.

Weak spots:
- Several gaps bundle three or four questions. G21 asks four.
- Some questions go beyond Article 30 fields: sensitive data, whether customers are told they're talking to an AI, a DPIA screening. Useful for a DPO, noise for an owner. The DPIA point is labelled as general knowledge, not a field value.
- PDFs were read as text. Scanned documents are still untested.

## Part B: change test

7 pass, 1 partial, 0 fail.

| # | Event | Result | Note |
|---|---|---|---|
| C1 | ClientHub adds a sub-processor | Pass | R1 approved to draft v2, v1 left untouched. Source is the notice. EU hosting marked unverified, gap raised. Routed to Maja Lindqvist and Anna Berg |
| C2 | CRM retention 7 to 5 years | Pass | Sourced to Maja and the date, old value in the log. Routed to the owner only, as the rules say. Refused to cite the retention policy because it wasn't supplied. The key was wrong on both points (see below) |
| C3 | Rename the activity | Pass | Judged cosmetic: no routing, no task, no gap. Logged |
| C4 | AI opt-out switched on | Partial | Purposes updated, gap G25 closed, record stays draft, and it noted no evidence of the setting. Did not inform the DPO. The rules have no row for settings changes, and the agent said so |
| C5 | PayLedger adds a sub-processor in Norway | Pass | R2 owner-confirmed back to draft. Treated Norway as EEA, said that is outside knowledge, and asked the DPO to confirm |
| C6 | Evidence and history | Pass | Every value sourced. Every transition has who, when and version |
| C7 | Scope | Pass | R4 untouched |
| C8 | Two changes on one record | Pass | One v2 holding both, both listed |

Five tasks and three gaps were created, every one with a named owner and a due date.

Weak spots:
- Tasks and gaps overlap. T1 and T3 both end with "re-confirm R1", so Maja is asked twice for one confirmation.
- Owner statements are recorded as the source without being marked "suggested". Arguable under the evidence rule.

### Questions the agent raised about the rules

The agent flagged these as undecidable from the rules. They were product decisions. Decided afterwards as defaults, see section 10 of `product/workflow-spec.md`:
1. Who moves a record back to draft on a trigger?
2. While v2 is a draft, is approved v1 still the official version?
3. Does a never-approved record get a new version when it returns to draft?
4. Are cosmetic edits to an approved record versioned?
5. Are owner statements "suggested" or confirmed?
6. Who is routed for a settings change, such as an AI opt-out?
7. Does the DPO hear about every material change to a record they approved?

### Flaws in my own test

- R3 and R4 were set to "draft" with empty required fields. By the rules that makes them "open". The agent noticed this and left them alone.
- R4's sources say just "register", which isn't an identifiable source under the evidence rule.
- Key rows C2 and C4 asked for things beyond the rules I gave the agent. Corrected in the key (v1.1); this run was scored against the original.

## What this shows

Claude follows explicit rules consistently: it separated cosmetic from material changes, kept the approved version intact, sourced every change, and flagged where the rules run out.

It does not show a working product. There is no stored state, no notification, no interface, one run each, and a baseline I wrote myself.

[Claude: suggestion — keep?] The state machine and routing table should be code, not a model's judgment. Claude's job would be the judgment calls inside it: extracting values with sources, deciding whether a change is material. Rules in code give the same answer every time, and a model alone might not.

## Next

1. Confirm or change the seven decisions in section 10 of `product/workflow-spec.md`, then re-run part B against the updated rules.
2. Shortlist vendors and run the same two tests against them. Part B is the one that separates them.
3. If no vendor passes the P0 gate, spec the build from `workflow-spec.md`.
