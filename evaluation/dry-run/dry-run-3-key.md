# Dry run 3: change-test key (written before the run)

Written on 2 November 2026 before the agent ran, so it can't be adjusted to fit the results. The agent never saw this file.

The test: [dry run 2 part B](dry-run-2-score.md) repeated against the updated rules (`product/workflow-spec.md` v0.2, sections 2 to 6). Same five events. The baseline is corrected: R3 and R4 are `open` because required fields are empty, every value has an identifiable source and a status, R2 has no version number (never approved), and R4's empty fields have gaps.

What this run can and can't show: the rules now answer the seven questions the agent raised in run 2, so a good result is mostly the agent applying them. The new things to watch are task counts, gap wording and whether the agent finds new holes in the rules.

## What a good result looks like

| # | Check | A good result |
|---|---|---|
| D1 | E1: new sub-processor at ClientHub | Material. R1 stays approved v1, official, marked "change pending". A new working draft opens with InsightLoop added to (d), sourced to the notice, status `suggested`. Routed to Maja Lindqvist and Anna Berg. EU hosting left unverified, with a gap |
| D2 | E2: CRM retention 7 to 5 years | Material. Goes into the same working draft, not a second one. Status `owner-stated`, source Maja and the date. Approved v1 still shows 7 years. Does not cite the retention policy as a source, since it wasn't supplied. No new owner task: it joins the existing one |
| D3 | E3: rename the activity | Metadata. Logged only. No state change, no gap, no task, no review, no version |
| D4 | E4: AI opt-out switched on | Material (settings change that affects (b)). R3 stays `open` because (f) is still empty. (b) updated, status `owner-stated`, source Sofia and the date. G25 closed as answered. A new evidence gap asks for a screenshot or the vendor's confirmation. Owner and DPO both informed |
| D5 | E5: new sub-processor at PayLedger | Material. R2 goes from owner-confirmed back to draft, moved by "system". (d) gains NordCloud Backup AB, `suggested`, sourced to the notice. Routed to Erik Holm and Anna Berg. Norway: says whether (e) changes and marks any assumption as outside the inputs, for the DPO to confirm |
| D6 | Versions | R1 keeps v1 and gets no v2 until a new version is approved. R2, R3 and R4 get no version number at any point |
| D7 | Task counts | At most one owner task and one DPO review task per affected record, so at most 6 across R1 to R3. No two tasks ask for the same re-confirmation. The specific questions live as gaps |
| D8 | Gaps | Every new gap has one question, a named owner, a due date and a priority. No gap bundles several questions |
| D9 | Log | Every state or value change records who (a person or "system"), when and the trigger. Old values are kept in the log |
| D10 | Scope | R4 is untouched. R1 to R3 change only because of an event |
| D11 | Honesty | Anything the rules still don't decide is listed as ambiguous, not decided silently |

## Scoring

Pass, partial or fail per row. Partial means the right outcome with a missing source, a missing route or a wrong owner.

Also record: total tasks and gaps created, and every point the agent says the rules don't settle.

Compared with dry run 2, the thing to look for is whether the task count drops and whether the "rules don't say" list shrinks. If it doesn't, the rules still have holes.
