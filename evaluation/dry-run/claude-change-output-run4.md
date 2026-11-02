# Change result: Lumen Outdoor AB RoPA (baseline 2026-11-02, events E1-E6)

Conventions used throughout (explained in Section 4): new gap IDs continue from G32; owner tasks and new gaps are due 14 days after creation; "system" is recorded-by wherever the event does not say who entered it; "WD" = working draft.

# Section 1: Event by event

## E1, 2026-11-03: ClientHub notice, new sub-processor InsightLoop Analytics AB
(a) Material. It adds a recipient, so Article 30(1)(d) changes. Rules: "New vendor / sub-processor added".
(b) R1 Customer management (the only record using ClientHub AB).
(c) Field changes (in the new WD only; official v1 unchanged):

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (d) Recipients | ClientHub AB (processor). Sub-processors: CloudHost Europe GmbH (EU), MailRelay SE AB (EU) | Same, plus InsightLoop Analytics AB (product analytics on CRM usage data; "hosted in the EU" per vendor, no country named). Effective date not stated | ClientHub AB written notice, forwarded by Maja Lindqvist, 2026-11-03 | suggested, announced (effective date unknown) |

Other fields untouched: they keep `confirmed` with their dates. (e) is not changed by E1: the notice says EU hosting and names no country, so the country check cannot run yet.
(d) R1 approved -> approved (v1 stays official, marked "change pending") + new WD in state draft. WD created, no version created. Moved by: system.
(e) Routed to Maja Lindqvist (owner, task) and the DPO Anna Berg. DPO gets a NOTICE (R1 is approved). DPO gets NO task (no DPO review task until the record reaches owner-confirmed).
(f) Task T1 created (first material change on R1; covers all pending changes): "Review and confirm pending changes to Customer management". Owner Maja Lindqvist. Due 2026-11-17. She must answer the R1 gaps, check the announced sub-processor entry and any later changes in the WD, then confirm the WD.
(g) Opened:
- G32 | R1 (d) | "On what date will InsightLoop Analytics AB start processing CRM data?" | Maja Lindqvist | due 2026-11-17 | priority 2.
- G33 | R1 (d)/(e) | "In which country is InsightLoop Analytics AB hosting the analytics data?" | Maja Lindqvist | due 2026-11-17 | priority 2.

## E2, 2026-11-03: Maja reports 5-year retention after last purchase
(a) Material. It changes (f). Rules: "Retention period changed".
(b) R1.
(c)

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (f) Erasure | 7 years | 5 years after last purchase, applies from 2026-11-03 | Maja Lindqvist, 2026-11-03 | owner-stated |

(d) No transition. R1 is already approved with a WD open from E1, so the change goes into the same WD (at most one WD). No new version. Moved by: n/a.
(e) Maja Lindqvist (T1 updated). DPO gets a NOTICE (approved record, material change). No DPO task.
(f) T1 updated, not duplicated. It now also covers the (f) change. Owner Maja, due stays 2026-11-17. She must confirm the new retention as part of the WD.
(g) None opened or closed. Her statement is owner-stated, which counts as sourced. The "retention policy" she mentions is not cited, because its content is not in the inputs.

## E3, 2026-11-03: Rename activity
(a) Metadata. Activity name is outside the version and not an Article 30 field.
(b) R1.
(c) Activity name | Customer management | Customer management (CRM) | Maja Lindqvist, 2026-11-03 | owner-stated (metadata, not a field-evidence item).
(d) None. No state change, no version, no review. Logged only. R1 stays approved / change pending (from E1-E2).
(e) No routing. No DPO notice, no DPO task (not material).
(f) No task change.
(g) None.

## E4, 2026-11-04: Sofia switches ON the HelpPilot model-improvement opt-out
(a) Material. It changes the AI setting recorded inside (b). Rules: "Tool or vendor setting changed that affects an Article 30 field".
(b) R3 AI customer support.
(c)

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (b) Purposes | "...HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out is currently OFF" | "...HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out is ON (switched on 2026-11-04); HelpPilot no longer uses Lumen's transcripts to improve its models" | Sofia Nyberg, 2026-11-04 (plus AI support contract / Service, Model improvement for the unchanged text) | owner-stated for the changed statement; rest stays suggested |

(d) R3 open -> open. (f) is still empty, so the record cannot reach draft. No WD, no version (never approved). Moved by: n/a.
(e) Routed to Sofia Nyberg (owner, task) and the DPO. DPO gets a NOTICE (R3 has not reached owner-confirmed). DPO gets NO task.
(f) Task T2 created (first material change on R3): "Review and complete AI customer support". Owner Sofia Nyberg. Due 2026-11-18. She must answer G23 and G24, provide evidence for G34, then confirm once (f) is filled and the record is draft.
(g) Closed: G25, answered by this report (source Sofia Nyberg, 2026-11-04). Opened: G34 | R3 (b) | "Please send a screenshot of the HelpPilot admin setting, or HelpPilot's written confirmation, showing the model-improvement opt-out is ON." | Sofia Nyberg | due 2026-11-18 | priority 1 (missing evidence for an AI setting). G23 and G24 unchanged (due 2026-11-16).

## E5, 2026-11-04: PayLedger notice, NordCloud Backup AB (Norway)
(a) Material. It adds a recipient, so (d) changes. Rules: "New vendor / sub-processor added".
(b) R2 Payroll (the only record using PayLedger).
(c)

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (d) Recipients | PayLedger Nordic AB (processor); Skatteverket. Sub-processors: NordCloud AB (hosting, Sweden), SupportBridge Inc. (tier 2 support, United States) | Same, plus NordCloud Backup AB (backup hosting, Norway). Effective date not stated | PayLedger Nordic AB written notice, forwarded by Erik Holm, 2026-11-04 | suggested, announced (effective date unknown) |

(e) Transfers is unchanged. Country check: Norway is in the EEA by general knowledge, so no transfer gap. This is marked a general-knowledge check for the DPO to confirm.
(d) R2 owner-confirmed -> draft. R2 has no approved version, so the record itself is the working draft: no WD, no version. Moved by: system. Untouched fields keep `confirmed` with their dates. Erik must re-confirm.
(e) Routed to Erik Holm (owner, task) and the DPO. DPO gets a NOTICE (including the Norway general-knowledge check to confirm). DPO gets NO task now. A DPO review task is created when R2 reaches owner-confirmed again.
(f) Task T3 created (first material change on R2): "Review and re-confirm Payroll". Owner Erik Holm. Due 2026-11-18. He must answer G31 and G35, check the announced entry in (d), then confirm the record.
(g) Opened: G35 | R2 (d) | "On what date will NordCloud Backup AB start hosting backups?" | Erik Holm | due 2026-11-18 | priority 2. G31 unchanged (due 2026-11-16).

## E6, 2026-11-10: ClientHub updated sub-processor list (start 2026-12-03, Singapore)
(a) Material. The date completes the (d) entry, and Singapore changes (e) and conflicts with E1 and the contract.
(b) R1.
(c)

| Field | Old (WD) | New (WD) | Source | Status |
|---|---|---|---|---|
| (d) Recipients | InsightLoop: effective date unknown, "hosted in the EU" | InsightLoop Analytics AB: effective 2026-12-03, hosts analytics data in Singapore | ClientHub AB updated sub-processor list, forwarded by Maja Lindqvist, 2026-11-10 | suggested, announced (effective 2026-12-03) |
| (e) Transfers | None. Hosting EU only, support EU-based (confirmed; source crm-vendor contract / International transfers, Hosting) | Singapore: InsightLoop Analytics AB, product analytics hosting, from 2026-12-03. Safeguard not known. Other content (support EU-based) unchanged | ClientHub AB updated sub-processor list, forwarded by Maja Lindqvist, 2026-11-10 | suggested, announced (effective 2026-12-03) |

Official v1 (d) and (e) stay as they were. Singapore is not on the EEA list (general-knowledge check, DPO to confirm), which forces a transfer gap.
(d) No transition. R1 stays approved / change pending, with the existing WD (state draft). No new WD. Moved by: n/a.
(e) Routed to Maja Lindqvist (T1 updated) and the DPO. DPO gets a NOTICE with the country-check result. No DPO task.
(f) T1 updated. It now also covers the (e) change and the new gaps. Owner Maja, due stays 2026-11-17. She must resolve G36 and G37 with ClientHub and confirm the WD.
(g) Closed: G32 (date 2026-12-03, answered by the forwarded list), G33 (country: Singapore). Opened:
- G36 | R1 (e) | "ClientHub's 3 Nov notice said InsightLoop is hosted in the EU, but its 10 Nov list says Singapore (and the contract says hosting is EU only). Which is correct?" | Maja Lindqvist | due 2026-11-24 | priority 1 (two sources disagree).
- G37 | R1 (e) | "What transfer safeguard (for example Standard Contractual Clauses) covers sending data to InsightLoop in Singapore? Please ask ClientHub for a copy." | Maja Lindqvist | due 2026-11-24 | priority 1 (country not on EEA list; missing transfer safeguard evidence).
Maja's R1 list shows G36 and G37 first (priority 1).

# Section 2: Resulting state (after E6)

| Record | Record state | Official version | Change pending | Open tasks | Open gaps | Different from baseline |
|---|---|---|---|---|---|---|
| R1 Customer management (CRM) | approved (WD in state draft) | v1 (unchanged) | yes | T1 Maja, due 2026-11-17 | G36 (P1), G37 (P1), both due 2026-11-24 | Was: no change pending, no task, no gaps. Renamed. WD holds (d) InsightLoop (announced 2026-12-03), (e) Singapore, (f) 5 years after last purchase |
| R2 Payroll | draft | none (never approved) | no (no official version) | T3 Erik, due 2026-11-18 | G31 (due 2026-11-16), G35 (P2, due 2026-11-18) | Was owner-confirmed. Back to draft. (d) has NordCloud Backup AB (announced). New task and gap |
| R3 AI customer support | open | none | no (never approved) | T2 Sofia, due 2026-11-18 | G23 (P1), G24 (P2), G34 (P1, due 2026-11-18). G25 closed | (b) opt-out now ON (owner-stated). New task. G25 closed, G34 opened |
| R4 Recruitment | open | none | no | none | G17, G29, G30 (unchanged) | No change |

Priorities for baseline gaps are not given in the inputs. Under the rules I read G23 and G29 as priority 1 and G17, G24 and G30 as priority 2. That reading is not stated in the baseline.

# Section 3: Change log

Recorded by is "system" for every line; the events do not name who entered them (Section 4, point 3).

| Date | Record | Field | Old | New | Source | Reported by | Recorded by | Trigger |
|---|---|---|---|---|---|---|---|---|
| 2026-11-03 | R1 | (d) Recipients | no InsightLoop | + InsightLoop Analytics AB (analytics, "EU"), announced, date unknown | ClientHub notice | Maja Lindqvist (forwarded vendor notice) | system | New sub-processor (E1) |
| 2026-11-03 | R1 | State | approved v1 | approved v1 + WD (change pending) | n/a | n/a | system | Material change |
| 2026-11-03 | R1 | (f) Erasure | 7 years | 5 years after last purchase, from 2026-11-03 | Maja Lindqvist, 2026-11-03 | Maja Lindqvist | system | Retention period changed (E2) |
| 2026-11-03 | R1 | Activity name (metadata) | Customer management | Customer management (CRM) | Maja Lindqvist, 2026-11-03 | Maja Lindqvist | system | Rename request (E3) |
| 2026-11-04 | R3 | (b) Purposes | Opt-out currently OFF | Opt-out ON, no model-improvement use of transcripts | Sofia Nyberg, 2026-11-04 | Sofia Nyberg | system | Vendor setting changed (E4) |
| 2026-11-04 | R2 | (d) Recipients | no NordCloud Backup | + NordCloud Backup AB (backup hosting, Norway), announced, date unknown | PayLedger notice | Erik Holm (forwarded vendor notice) | system | New sub-processor (E5) |
| 2026-11-04 | R2 | State | owner-confirmed | draft | n/a | n/a | system | Material change |
| 2026-11-10 | R1 | (d) Recipients | InsightLoop date unknown, "EU" | InsightLoop effective 2026-12-03, Singapore | ClientHub updated sub-processor list | Maja Lindqvist (forwarded) | system | Vendor list update (E6) |
| 2026-11-10 | R1 | (e) Transfers | None. Hosting EU only | Singapore (InsightLoop) from 2026-12-03, safeguard unknown | ClientHub updated sub-processor list | Maja Lindqvist (forwarded) | system | Vendor list update (E6) |

# Section 4: Ambiguities, undecided points and choices not covered by the rules

1. RULE GAP: "30 days'" and "14 days'" notice give no date. The rules say a notice with no date gets a gap. I did NOT compute a date (the start could count from notice, receipt or forwarding). 30 days from 2026-11-03 happens to equal the later E6 date; 14 days from 2026-11-04 would be 2026-11-18, which I did not record.
2. RULE GAP: no due date is defined for owner tasks. I used 14 days after creation, copying the gap rule. T1 (due 2026-11-17) falls before gaps G36 and G37 (due 2026-11-24), so it cannot be completed on time. I did not move T1's date.
3. RULE GAP: the events do not say who entered each change. The log needs "recorded by" a person or "system". I used "system" and "reported by" the named person.
4. RULE GAP: a field holds one status, but some fields now mix origins (old confirmed or suggested text plus a new announced or owner-stated part, e.g. R3 (b), R1 (d), (e)). I recorded the new part's status and left untouched text with its old status. The rules do not say how to show this per field. How `announced` combines with `suggested` is also not defined; I used "suggested, announced".
5. RULE GAP: the state of a working draft of an approved record is not defined. I labelled it "draft" while the record stays "approved / change pending".
6. RULE GAP: when a record goes back to draft, or a new WD opens, the rules do not say whether a DPO review task is created again or an old one persists. I created none and assumed one is created when the record next reaches owner-confirmed.
7. SCENARIO: the baseline shows R2 owner-confirmed on 2026-10-22 but no DPO review task, although the rules create one at that point. I did not create one at E5 and could not tell whether one exists.
8. RULE GAP: the EEA reference list is not in the inputs. I judged Norway (EEA) and Singapore (not EEA) from general knowledge and marked them as general-knowledge checks for the DPO to confirm. The rules do not say what to do when a notice says only "EU" and names no country (E1); I opened G33 (priority 2).
9. RULE GAP: no rule says how a later vendor document supersedes an earlier one (E6 over E1). I recorded the later document in the WD and opened conflict gap G36 (priority 1) rather than overwriting silently. The contract line "Hosting EU only" also conflicts, and G36 covers it.
10. RULE GAP: the rules open a gap for any unconfirmed suggested value, but the baseline does not do this for every suggested field. I followed the baseline practice: no extra gap per announced entry; the owner task covers confirmation.
11. RULE GAP: an announced effective date (2026-12-03) is not linked to approval. If the R1 WD is not approved before then, official v1 will be out of date once InsightLoop starts. The rules give no deadline or escalation for that.
12. RULE GAP: gap IDs, the numbering scheme and baseline gap priorities are not specified. I continued from G32 and inferred baseline priorities.
13. RULE GAP: a metadata change on an approved record with a pending WD (E3). I applied it once to the record, visible in both official and draft, since metadata sits outside the version.
14. SCENARIO: E2 says "in line with the retention policy" but the policy's content for customer data is not in the inputs, so no source beyond Maja is recorded. Open: does 5 years apply to data already kept between 5 and 7 years? Does "after last purchase" replace the old trigger in full?
15. SCENARIO: E1/E6 "CRM usage data" sent to InsightLoop. Whose data it is (customers, or Lumen staff using the CRM) and which categories are sent is unknown. (c) may need updating. No contract amendment was attached. I did not open a gap because no rule triggers one.
16. SCENARIO: whether NordCloud Backup AB is related to NordCloud AB (Sweden), and whether the backups hold the same data as the primary hosting, is unknown. Nothing else in R2 was changed.
