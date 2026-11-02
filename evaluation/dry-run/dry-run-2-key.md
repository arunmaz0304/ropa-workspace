# Dry run 2: change-test key (written before the run)

Written on 2 November 2026 before the agent ran, so it can't be adjusted to fit the results. The agent never saw this file.

The test: a baseline of four records in different states (R1 approved, R2 owner-confirmed, R3 and R4 draft) plus five change events. Rules given to the agent: the evidence rule, gap rules, states, change triggers and roles from `product/workflow-spec.md`. Inputs are in the agent-facing files only; this key is for scoring.

## What a good result looks like

| # | Event | A good tool should |
|---|---|---|
| C1 | E1: ClientHub adds sub-processor InsightLoop Analytics AB | Treat it as material (new recipient). Move R1 from approved back to draft with a new version, leaving v1 untouched. Add InsightLoop to recipients with the notice as source. Route to Maja Lindqvist and Anna Berg. Mark "hosted in the EU" as unverified, since it comes from the notice and no contract is attached, and create a gap to confirm location and terms |
| C2 | E2: CRM retention changes to 5 years after last purchase | Treat it as material (erasure changes). Change 7 years to 5 years after last purchase in the new version, sourced to Maja's statement and date. Don't cite the retention policy as a source if it wasn't supplied. Keep the old value in history. Route to Maja Lindqvist for revalidation, as the change rules say |
| C3 | E3: rename activity label | Treat it as cosmetic. No state change, no revalidation, no task. Log it. Over-routing this is a failure |
| C4 | E4: AI opt-out switched on | Treat it as material (purposes change). Update R3 purposes, sourced to Sofia Nyberg and the date. Close gap G25 as answered. R3 is already draft, so it stays draft. Flag that the statement is owner-reported, with no admin evidence. Whether to inform the DPO is a rule gap: the change table has no row for settings changes |
| C5 | E5: PayLedger adds NordCloud Backup AB, Norway | Treat it as material (new recipient). Move R2 from owner-confirmed back to draft. Add the sub-processor with the notice as source. Don't assume the transfer answer: say whether Norway changes the transfers field and mark it to be verified. Route to Erik Holm and Anna Berg |
| C6 | Evidence and history | Every new or changed value cites a source. Approved v1 is never edited in place. Every state transition records who, when and version |
| C7 | Scope | R4 (recruitment) is untouched. No record changed without a triggering event |
| C8 | Same-record changes | E1 and E2 both hit R1 on the same day. Either one v2 containing both changes with both listed, or v2 then v3, is acceptable. Overwriting v1 is not |

## Scoring

Pass, partial or fail per row. Partial means the right outcome with a missing source, a missing route, or a wrong owner.

Also record: how many tasks were created, whether each has a named owner and due date, and anything the agent flagged as undecidable.

## Version

v1.1, 2 November 2026, after the run. C2 and C4 asked for things the change rules don't require (DPO routing for a retention change, citing a policy the agent wasn't given, informing the DPO of a settings change). Corrected. The run was scored against the original wording; see `dry-run-2-score.md`.
