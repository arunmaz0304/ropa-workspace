# Dry run 3: the change test against the updated rules

2 November 2026. One blind Claude agent, only the rules, the corrected baseline and the five events. No answer key. It reported reading only its three input files (self-reported). Scored by Claude against [dry-run-3-key.md](dry-run-3-key.md), written before the run.

Output, unedited: [claude-change-output-run3.md](claude-change-output-run3.md).

This repeats [dry run 2 part B](dry-run-2-score.md) with three changes: the rules are `product/workflow-spec.md` v0.2, the baseline is corrected (R3 and R4 are `open`, every value has a source and a status, R4's empty fields have gaps), and the events are the same five.

## Result

10 pass, 1 partial, 0 fail.

| # | Check | Result | Note |
|---|---|---|---|
| D1 | New sub-processor at ClientHub | Pass | R1 stays approved v1 and official, marked "change pending". A working draft opens with InsightLoop in (d), `suggested`, sourced to the notice. EU hosting left unverified with a gap |
| D2 | CRM retention 7 to 5 years | Pass | Went into the same working draft. `owner-stated`, sourced to Maja and the date. v1 still shows 7 years. Did not cite the retention policy. No new owner task |
| D3 | Rename the activity | Pass | Metadata, logged only. No state change, task, gap or review |
| D4 | AI opt-out switched on | Pass | R3 stays `open` because (f) is empty. (b) updated, G25 answered, a new gap asks for a screenshot or HelpPilot's confirmation. Owner and DPO both routed |
| D5 | New sub-processor at PayLedger | Pass | R2 owner-confirmed back to draft, moved by "system". Norway/EEA reasoning labelled as outside knowledge for the DPO to confirm |
| D6 | Versions | Pass | R1 keeps v1 and gets no v2. R2, R3 and R4 never get a version number |
| D7 | Task counts | Pass | Exactly one owner task and one DPO task for each of R1, R2 and R3. No two tasks ask for the same re-confirmation |
| D8 | One question per gap | Partial | Six of seven new gaps are one question. G34 asks what data and about whom, which is two |
| D9 | Log | Pass | Who, when and trigger on every change. Task and gap creation share one log row |
| D10 | Scope | Pass | R4 untouched |
| D11 | Honesty | Pass | Fifteen points listed as undecided, not decided silently |

## Against dry run 2

| | Run 2, part B | Run 3 |
|---|---|---|
| Tasks created | 5 (3 owner, 2 DPO) | 6 (3 owner, 3 DPO) |
| New gaps | 3 | 7 |
| Duplicate re-confirmation asks | Yes, Maja asked twice for R1 | None |
| Points the agent said the rules don't settle | 21 | 15 |

The duplicate ask is gone. The volume did not fall, and I had expected it to. Two causes:

- One question per gap splits what used to be one bundled gap, so gaps went from 3 to 7.
- The rule of one DPO task per record adds a DPO task for R3, which run 2 had no task for at all.

The agent's own note (point 11) names the real problem: the DPO can only review a record once the owner has confirmed it, but the task is created at the start. See open question 4 below.

The 21 and 15 are not like for like. Run 2's list included three baseline problems the agent noticed. Run 3's list has none, because I corrected the baseline. The rest are about the rules or the scenario.

## New holes in the rules

Seven of the fifteen points are real gaps in the spec. The rest are content questions about this scenario (what "CRM usage data" contains, what happens to prospects) or minor logging detail. The seven are now in section 11 of `product/workflow-spec.md`, each with a proposed default that is not yet applied. They are:

1. Record an announced sub-processor on receipt of the notice, or on its effective date?
2. What status do untouched fields keep when a record returns to draft?
3. Default due date for gaps, and who is told when one is overdue?
4. When is the DPO review task created?
5. When does a gap count as closed, and what priority does an evidence gap get?
6. How is a change logged when an owner reported it but didn't enter it?
7. Who decides that a new country is outside the EU/EEA?

## What this shows

The agent applied the updated rules consistently, with no wrong outcomes against the key. The seven decisions from section 10 do what they were meant to: one official version stays intact, a rename triggers nothing, owner statements are labelled, and the DPO hears about changes.

It does not show the rules are complete. Seven holes appeared in a five-event test, and a real organisation will produce more.

Limits:
- This is an easier test than run 2, because the rules now answer most of what run 2 asked.
- The key and the baseline are mine, and the agent is the same model family.
- One run. A second run could well list different ambiguities.

## Next

1. Confirm or change the proposed defaults in section 11 of `workflow-spec.md`. Question 4 matters most, because it cuts the task count.
2. Re-run once more after that. If the "rules don't say" list is mostly scenario content and no longer rule gaps, the spec is ready to build from.
3. Shortlist vendors and run the same test against them.
