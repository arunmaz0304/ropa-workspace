# Dry run 4: change-test key (written before the run)

Written on 2 November 2026 before the agent ran, so it can't be adjusted to fit the results. The agent never saw this file.

The test: [dry run 3](dry-run-3-score.md) repeated against `product/workflow-spec.md` v0.3, which applies the seven defaults from section 11. Same baseline, same five events, plus a sixth.

E6 (2026-11-10): ClientHub sends its updated sub-processor list. InsightLoop starts on 2026-12-03 and hosts the data in Singapore. This contradicts the earlier notice, which said EU hosting. It tests the new rules directly: announced values and their effective date, two sources disagreeing, and the country check.

What this run can and can't show: the seven new rules answer the seven holes from run 3, so a good result is mostly the agent applying them. The things to watch are the task count, the number of rule gaps the agent finds, and whether E6 is handled without a silent choice.

## What a good result looks like

| # | Check | A good result |
|---|---|---|
| G1 | E1 | R1 stays approved v1, official, "change pending". A working draft opens. InsightLoop is added to (d), `suggested`, sourced to the notice, marked `announced`. No effective date is stated, so a gap asks for it. Routed to Maja Lindqvist, with a notice to Anna Berg |
| G2 | E2 | Goes into the same working draft. `owner-stated`, sourced to Maja and the date. v1 still shows 7 years. No new owner task. The retention policy is not cited |
| G3 | E3 | Metadata. Logged only. No state change, gap, task or review |
| G4 | E4 | R3 stays `open` because (f) is empty. (b) is updated and `owner-stated`. The gap about the setting closes when answered. A separate evidence gap, priority 1, asks for a screenshot or HelpPilot's confirmation. Owner informed, DPO sent a notice |
| G5 | E5 | R2 goes from owner-confirmed to draft, moved by "system". NordCloud Backup AB is added to (d), `suggested`, `announced`, with a gap for the effective date. Norway is checked as EEA and the result is labelled a general-knowledge check for the DPO to confirm. No transfer gap needed for Norway |
| G6 | Tasks after E1 to E5 | Exactly three owner tasks (R1, R2, R3). No DPO review tasks, because no record has reached owner-confirmed. DPO notices instead. No two tasks ask for the same thing |
| G7 | E6, dates | The effective date 2026-12-03 is recorded on the announced InsightLoop entry. The gap asking for the date closes |
| G8 | E6, conflict | The earlier notice said EU hosting. The updated list says Singapore. The agent does not silently pick one. A priority-1 gap records that two sources disagree, owned by Maja |
| G9 | E6, country check | Singapore is not an EEA country. This raises a transfer gap, priority 1. R1 field (e) in the working draft must not still say "None" as if it were confirmed. The DPO gets a notice. No new owner task: it joins the existing one. No DPO task, because R1's draft hasn't reached owner-confirmed |
| G10 | E6, state | R1 remains approved v1 plus a working draft. No v2 is created. The official version still shows no InsightLoop |
| G11 | Gap form | Every new gap has one question, a named owner, a due date 14 days after it was opened, and a priority. The two-part question in run 3 (what data, and about whom) is split into two or kept to one |
| G12 | Log | Every change shows who reported it, who recorded it ("system" or a person), when, and the trigger. Old values kept |
| G13 | Scope | R4 untouched. R1 to R3 change only because of an event |
| G14 | Honesty | Anything the rules still don't decide is listed as undecided |

## Scoring

Pass, partial or fail per row. Partial means the right outcome with a missing source, a missing route or a wrong owner.

Also record: total tasks, owner and DPO separately, new gaps, and every point the agent says the rules don't settle, split into rule gaps and scenario content.

Compared with run 3: tasks should drop from 6 to 3. If the number of rule gaps doesn't fall below the 7 from run 3, the rules still have holes.

## What would count as the spec being ready to build from

The "rules don't say" list is mostly scenario content, with at most one or two real rule gaps. Run 3's list had seven.
