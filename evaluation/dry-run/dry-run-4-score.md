# Dry run 4: the change test against the final rules

2 November 2026. One blind Claude agent, only the rules, the baseline and six events. No answer key. It reported reading only its three input files (self-reported). Scored by Claude against [dry-run-4-key.md](dry-run-4-key.md), which was committed to GitHub before the run started.

Output, unedited: [claude-change-output-run4.md](claude-change-output-run4.md).

This repeats [dry run 3](dry-run-3-score.md) against `product/workflow-spec.md` v0.3, which applies the seven defaults from run 3. The baseline and the first five events are the same. E6 is new: ClientHub sends its updated sub-processor list. InsightLoop starts on 2026-12-03 and hosts the data in Singapore, which contradicts the earlier notice that said EU.

## Result

14 pass, 0 partial, 0 fail.

| # | Check | Result | Note |
|---|---|---|---|
| G1 | E1, new sub-processor | Pass | R1 stays approved v1, official, "change pending". Working draft opens. InsightLoop added to (d), `suggested`, `announced`. Gap asks for the effective date. DPO gets a notice |
| G2 | E2, retention | Pass | Same working draft, `owner-stated`, no new task. Retention policy not cited |
| G3 | E3, rename | Pass | Logged only. It labelled the rename `owner-stated`, though metadata has no status. Cosmetic |
| G4 | E4, AI opt-out | Pass | R3 stays `open`. G25 closes. Separate priority-1 evidence gap. DPO gets a notice |
| G5 | E5, PayLedger sub-processor | Pass | R2 back to draft, "system". Norway checked as EEA, labelled a general-knowledge check for the DPO |
| G6 | Tasks after E1 to E5 | Pass | Three owner tasks, no DPO tasks, DPO notices only |
| G7 | E6, effective date | Pass | 2026-12-03 recorded on the announced entry. The date gap closes |
| G8 | E6, conflict | Pass | Recorded the newer document and opened a priority-1 gap saying the EU and Singapore sources disagree. Did not pick silently |
| G9 | E6, country check | Pass | Singapore not on the EEA list, so a priority-1 transfer-safeguard gap. (e) no longer says "None". No new task. DPO notice |
| G10 | E6, state | Pass | v1 untouched, no v2 |
| G11 | Gap form | Pass | One question each, owner, due date 14 days after opening, priority. Run 3's two-part gap did not repeat |
| G12 | Log | Pass | Every change shows reported by, recorded by, date and trigger. It used "system" for every recorded-by, since the events don't say who entered anything |
| G13 | Scope | Pass | R4 untouched |
| G14 | Honesty | Pass | Sixteen points listed as undecided |

## Against dry run 3

| | Run 3 | Run 4 |
|---|---|---|
| Events | 5 | 6 |
| Owner tasks | 3 | 3 |
| DPO tasks | 3 | 0 (notices only) |
| New gaps opened | 7 | 6 |
| Points listed as undecided | 15 | 16 |

The DPO task problem is fixed: six tasks became three. The other numbers barely moved. Run 4 had an extra event, so the gap count is lower per event, but I wouldn't read more into it than that.

## Reviewing the agent's "rule gap" labels

The agent labelled 12 of its 16 points RULE GAP. I don't agree with all 12. My reading:

**Real gaps in the rules (5)**
- **Task deadlines (its points 2 and 11).** Owner tasks have no due date rule. T1 was due 2026-11-17 while its gaps were due 2026-11-24. Separately, nothing ties an announced effective date to approval: if the R1 draft isn't approved before 2026-12-03, the official record is out of date once InsightLoop starts.
- **Mixed statuses in one field (point 4).** A field can now hold old confirmed text and a new owner-stated part. A field has one status.
- **Conflicting vendor documents (point 9).** Which value shows in the draft when a later document contradicts an earlier one?
- **DPO task after a record returns to draft (point 6).** Is a DPO task created again, or does an old one persist?
- **State of a working draft of an approved record (point 5).** The agent called it "draft" and left the record "approved". Reasonable, but the spec doesn't say.

**Minor (2)**
- A notice that says "EU" with no country (point 8). The agent handled it with a gap.
- A metadata edit on a record with a pending draft (point 13).

**Not rule gaps (5)**
- Points 7, 10 and 12 come from my baseline: it had no DPO task for R2, gaps that don't match the rules for every suggested field, and no gap priorities.
- Points 1 and 3 are cases the rules handle. The agent followed them and then called them gaps.

So five real gaps and two minor ones, against seven in run 3.

## What this shows

The seven defaults from run 3 held up. None came back as a gap, and the DPO task problem is fixed. New gaps appeared in places the new rules created: task deadlines, mixed statuses, and what happens when a vendor document is replaced by a later one.

The bar I set in the key was "at most one or two real rule gaps". Five is not that. The spec is better, but I can't call it finished on this evidence.

The 14 of 14 mostly reflects that I wrote the key from the rules after run 3. It tests that the agent applies the rules, not that the rules are right.

Limits:
- One run, the same model family as the scorer, and a key and baseline I wrote.
- Another run could list different gaps.
- Each round fixes the holes the last one found and exposes new ones. A build will find more than any text test.

## Next

1. Decide the five questions in section 12 of `product/workflow-spec.md`. Each has a proposed default, not yet applied.
2. After that, I'd stop running text tests. Returns are diminishing, and the evidence that matters now is whether a vendor passes the same two tests.
3. Shortlist 2 or 3 vendors and run part A and part B against them. If none passes the P0 gate, build from the spec and treat these questions as known open items.
