# Change result: Lumen Outdoor AB RoPA workspace

Baseline: 2026-11-02. Events E1 to E5 applied in date order. E1, E2 and E3 share the date 2026-11-03 and were applied in file order (see Section 4). DPO: Anna Berg. Task and gap due dates are 14 days after the event date.

## Section 1: Event by event

### E1, 2026-11-03: ClientHub AB adds sub-processor InsightLoop Analytics AB

(a) Material: yes. The Art. 30(1)(d) recipients field changes. The rule row "New vendor or sub-processor added" applies. The notice is the only source. No updated contract is attached, so the "Contract or DPA updated" row is not triggered.

(b) Affected: R1 (ClientHub AB is used only by R1).

(c) Field changes:

| Field | Old | New | Source |
|---|---|---|---|
| R1 (d) Recipients | ClientHub AB (processor). Sub-processors: CloudHost Europe GmbH (infrastructure, EU), MailRelay SE AB (email delivery, EU) | ClientHub AB (processor). Sub-processors: CloudHost Europe GmbH (infrastructure, EU), MailRelay SE AB (email delivery, EU), InsightLoop Analytics AB (product analytics on CRM usage data; EU-hosted per ClientHub's notice, not verified). Status: suggested | ClientHub AB 30-day written notice, email forwarded by Maja Lindqvist, 2026-11-03 |

R1 (c) and (e) keep their values. Nothing in the notice establishes a change to them. They are queried in G27 below.

(d) State: R1 moves from approved v1 to draft v2. Mover: system, on the sub-processor trigger (the rules do not name an actor; see Section 4). 2026-11-03. v1 stays as the immutable approved version.

(e) Routed to: Maja Lindqvist (activity owner) and Anna Berg (DPO).

(f) Tasks (due 2026-11-17):
- T1. Title: "R1: confirm InsightLoop as sub-processor". Owner: Maja Lindqvist. She must answer G26 and G27, obtain from ClientHub an updated sub-processor list or contract extract for InsightLoop, then re-confirm R1 (draft to owner-confirmed).
- T2. Title: "R1: assess new sub-processor InsightLoop". Owner: Anna Berg. She must assess InsightLoop against the ClientHub contract's sub-processor terms and decide whether to object within the notice period. If 30 days run from 2026-11-03, the period ends 2026-12-03; the contract's objection terms have not been seen. She must also check whether InsightLoop acts for Lumen or for ClientHub's own product purposes. Once ClientHub supplies an updated contract or sub-processor list, she must refresh the evidence references. She can review R1 only after the owner has confirmed it.

(g) Gaps opened (status open):
- G26. R1, field (d). Owner: Maja Lindqvist. Due 2026-11-17. Question: "ClientHub has told us it will add InsightLoop Analytics AB for product analytics. Please confirm it should be listed, and get from ClientHub where it is hosted, who it is, and from when it applies."
- G27. R1, fields (c) and (e). Owner: Maja Lindqvist. Due 2026-11-17. Question: "What does 'CRM usage data' contain, and whose data is it (customers and prospects, or Lumen's own CRM users)? Does it change who the data subjects are or what data is processed, and does any of it leave the EU?"

Gaps closed: none.

### E2, 2026-11-03: R1 retention changes from 7 years to 5 years after last purchase

(a) Material: yes. The Art. 30(1)(f) erasure time limit changes. The rule row "Retention period changed" applies.

(b) Affected: R1.

(c) Field changes:

| Field | Old | New | Source |
|---|---|---|---|
| R1 (f) Erasure | 7 years | 5 years after last purchase, applies from 2026-11-03 | Maja Lindqvist, 2026-11-03 |

The statement says "in line with the retention policy". The policy was not supplied, so it is not cited as a source.

(d) State: no transition. R1 is already draft v2 from E1, so the change goes into v2 and no further version is created.

(e) Routed to: Maja Lindqvist (activity owner) only, per the rules.

(f) Task (due 2026-11-17):
- T3. Title: "R1: revalidate erasure field". Owner: Maja Lindqvist. She must confirm the 5-year rule and its trigger and give the retention policy reference. She must say what applies to prospects who never purchased, and how customer data already older than 5 years after last purchase is handled. Then she must re-confirm R1.

(g) Gaps opened or closed: none.

### E3, 2026-11-03: rename "Customer management" to "Customer management (CRM)"

(a) Material: no. The activity name is not an Art. 30(1)(a) to (g) field. The rules say cosmetic edits do not trigger revalidation.

(b) Affected: R1.

(c) Change (not an Art. 30 field):

| Field | Old | New | Source |
|---|---|---|---|
| R1 activity name | Customer management | Customer management (CRM) | Maja Lindqvist, 2026-11-03 |

(d) State: no transition. It is recorded in draft v2 because R1 is already a draft at this point (see Section 4).

(e) Routed to: nobody. (f) Tasks: none. (g) Gaps: none.

### E4, 2026-11-04: HelpPilot model-improvement opt-out switched ON

(a) Material: yes. The text of field (b) in R3 changes: the baseline says "Opt-out is currently OFF". "Anything that changes an Article 30 field value" is material. No row in the change table covers this event, so the routing is my choice (see Section 4).

(b) Affected: R3 (HelpPilot AI Ltd is used only by R3).

(c) Field changes:

| Field | Old | New | Source |
|---|---|---|---|
| R3 (b) Purposes | AI chat assistant answering customer questions on the website, with handover to human agents. HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out is currently OFF | AI chat assistant answering customer questions on the website, with handover to human agents. HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out was switched ON on 2026-11-04; HelpPilot no longer uses Lumen's transcripts to improve its models | Setting and effect: Sofia Nyberg, 2026-11-04. Contract clause: AI support contract / Service, Model improvement |

(d) State: no transition. R3 stays draft v1 (draft is editable; no approved version is involved).

(e) Routed to: Sofia Nyberg (activity owner and reporter). No DPO routing is required by the rules.

(f) Tasks: none.

(g) Gap closed: G25 ("current admin setting for model improvement? Has Lumen decided whether to allow it?"). It is answered by Sofia Nyberg on 2026-11-04. The setting is stated. The decision is only implied by her action (see Section 4). No new gaps. G23 and G24 remain open.

### E5, 2026-11-04: PayLedger Nordic AB adds sub-processor NordCloud Backup AB

(a) Material: yes. The Art. 30(1)(d) recipients field changes. The rule row "New vendor or sub-processor added" applies.

(b) Affected: R2 (PayLedger Nordic AB is used only by R2).

(c) Field changes:

| Field | Old | New | Source |
|---|---|---|---|
| R2 (d) Recipients | PayLedger Nordic AB (processor); Skatteverket. Sub-processors: NordCloud AB (hosting, Sweden), SupportBridge Inc. (tier 2 support, United States) | PayLedger Nordic AB (processor); Skatteverket. Sub-processors: NordCloud AB (hosting, Sweden), SupportBridge Inc. (tier 2 support, United States), NordCloud Backup AB (backup hosting, Norway). Status: suggested | PayLedger Nordic AB 14-day written notice, email forwarded by Erik Holm, 2026-11-04 |

R2 (e) is unchanged: it is a transfers field and the notice says nothing that changes it (see Section 4 on Norway).

(d) State: R2 moves from owner-confirmed v1 to draft v1. Mover: system, on the sub-processor trigger. 2026-11-04. Erik Holm's confirmation of 2026-10-22 no longer covers the record.

(e) Routed to: Erik Holm (activity owner) and Anna Berg (DPO).

(f) Tasks (due 2026-11-18):
- T4. Title: "R2: confirm NordCloud Backup AB". Owner: Erik Holm. He must answer G28, supply the PayLedger notice or updated sub-processor list, and re-confirm R2 (draft to owner-confirmed).
- T5. Title: "R2: assess new sub-processor NordCloud Backup AB". Owner: Anna Berg. She must assess the sub-processor and decide whether to object within the notice period. If 14 days run from 2026-11-04, the period ends 2026-11-18; the contract's objection terms have not been seen. She must also confirm that the Norway hosting needs no entry in (e), and check that the contract's security measures in (g) cover backups. She can review R2 only after the owner has confirmed it.

(g) Gap opened:
- G28. R2, field (d). Owner: Erik Holm. Due 2026-11-18. Question: "PayLedger has told us it will add NordCloud Backup AB for backup hosting in Norway. Please confirm it should be listed, and get from PayLedger what data is backed up, where all processing and access happens, and from what date."

Gaps closed: none.

## Section 2: Resulting state

| Record | State | Current version | Open items | Difference from baseline |
|---|---|---|---|---|
| R1 Customer management (CRM) | draft | v2 (last approved: v1) | Gaps G26, G27. Tasks T1, T2 (due 2026-11-17), T3 (due 2026-11-17). Approval chain must be repeated | State approved to draft. Version v1 to v2. Name changed. (d) adds InsightLoop. (f) is 5 years after last purchase |
| R2 Payroll | draft | v1 | Gap G28. Tasks T4, T5 (due 2026-11-18). Owner confirmation needed again | State owner-confirmed to draft. (d) adds NordCloud Backup AB |
| R3 AI customer support | draft | v1 | Gaps G23, G24 (both due 2026-11-16). (f) still OPEN | (b) now records opt-out ON. G25 closed. State unchanged |
| R4 Recruitment | draft | v1 | Gap G17 (due 2026-11-16). (e), (f), (g) still OPEN | None |

## Section 3: Change log

| Date | Record | Field | Old | New | Source | Who | Version |
|---|---|---|---|---|---|---|---|
| 2026-11-03 | R1 | State | approved | draft | Rule: new sub-processor added (E1) | system | v2 |
| 2026-11-03 | R1 | (d) Recipients | ClientHub AB; CloudHost Europe GmbH; MailRelay SE AB | Same, plus InsightLoop Analytics AB (product analytics, EU per notice), suggested | ClientHub 30-day notice, forwarded by Maja Lindqvist | Reported by Maja Lindqvist; recorded by system | v2 |
| 2026-11-03 | R1 | Gap G26 | n/a | opened, owner Maja Lindqvist, due 2026-11-17 | E1 | system | v2 |
| 2026-11-03 | R1 | Gap G27 | n/a | opened, owner Maja Lindqvist, due 2026-11-17 | E1 | system | v2 |
| 2026-11-03 | R1 | Tasks T1, T2 | n/a | created, due 2026-11-17 (Maja Lindqvist, Anna Berg) | E1 | system | v2 |
| 2026-11-03 | R1 | (f) Erasure | 7 years | 5 years after last purchase, from 2026-11-03 | Maja Lindqvist, 2026-11-03 | Maja Lindqvist | v2 |
| 2026-11-03 | R1 | Task T3 | n/a | created, due 2026-11-17 (Maja Lindqvist) | E2 | system | v2 |
| 2026-11-03 | R1 | Activity name | Customer management | Customer management (CRM) | Maja Lindqvist, 2026-11-03 | Requested by Maja Lindqvist | v2 |
| 2026-11-04 | R3 | (b) Purposes | "... Opt-out is currently OFF" | "... Opt-out switched ON 2026-11-04; transcripts no longer used for model improvement" | Sofia Nyberg, 2026-11-04 | Sofia Nyberg | v1 |
| 2026-11-04 | R3 | Gap G25 | open | closed, answered by Sofia Nyberg 2026-11-04 | E4 | Sofia Nyberg | v1 |
| 2026-11-04 | R2 | State | owner-confirmed | draft | Rule: new sub-processor added (E5) | system | v1 |
| 2026-11-04 | R2 | (d) Recipients | PayLedger Nordic AB; Skatteverket; NordCloud AB; SupportBridge Inc. | Same, plus NordCloud Backup AB (backup hosting, Norway), suggested | PayLedger 14-day notice, forwarded by Erik Holm | Reported by Erik Holm; recorded by system | v1 |
| 2026-11-04 | R2 | Gap G28 | n/a | opened, owner Erik Holm, due 2026-11-18 | E5 | system | v1 |
| 2026-11-04 | R2 | Tasks T4, T5 | n/a | created, due 2026-11-18 (Erik Holm, Anna Berg) | E5 | system | v1 |

## Section 4: Ambiguities, undecidable points, and choices the rules do not cover

Ordering and versions
1. E1, E2 and E3 are all dated 2026-11-03. I applied them in file order. The outcome would differ only for E3 (point 4).
2. The rules do not say who moves an approved record back to draft on a material change, nor an owner-confirmed record on a trigger. I recorded "system, on the trigger rule". The alternative is the owner, or anyone with edit rights.
3. The rules do not say whether approved v1 stays the official version while v2 is a draft. I recorded v1 as "last approved" and did not decide.
4. I put E2 and E3 into R1 v2 because R1 was already a draft. Had E3 been applied to R1 while approved, the rules are unclear: "Edits create a new version" could apply even to a cosmetic edit, with no state change.
5. R2 goes owner-confirmed to draft with no version bump. The new-version rule names only approved records, and R2 has never been approved. I kept v1. The alternative is to create v2.

Confirmed or suggested
6. Values stated by an owner (E2, E4) are recorded with the owner as source and not logged as "suggested". Values taken from vendor notices (E1, E5) are marked suggested and have gaps. The rules say values from a source are suggested until a person confirms them, so one could treat the owner statements as suggested too. The owner re-confirmation tasks cover this either way.
7. Gap IDs continue from G25 (G26 to G28). Gap due dates follow the baseline pattern of 14 days after the event. The rules fix the 14 days only for tasks.
8. Gaps and tasks overlap by design: the gap holds the question, the task holds the owner action including re-confirming the record.

E1 (InsightLoop)
9. "CRM usage data" may be data about Lumen's own CRM users. Those are not in R1 (c), which lists customers and prospects. I did not change (c); I asked in G27.
10. The notice says product analytics. It is not clear whether InsightLoop acts for Lumen or for ClientHub's own purposes. If the latter, it raises a processor-or-controller question, which I left to the DPO (T2). I did not treat it as a "new purpose" trigger.
11. EU hosting rests only on the notice. R1 (e) "None" rests on the contract, which does not cover InsightLoop. I left (e) unchanged and asked in G27.
12. The notice date is assumed to equal the event date. The objection end date (2026-12-03) is derived from that. The contract's objection terms have not been seen, so whether an objection right exists is not decidable from the inputs.

E2 (retention)
13. The retention policy was not supplied. "In line with the retention policy" is not used as a source.
14. The statement covers customers after last purchase. Prospects who never purchased and data already older than 5 years are not addressed. These are raised in T3, not decided.

E4 (opt-out)
15. No row of the change table covers an opt-out switch, so the routing (owner only) is my choice. I treated it as material because the field (b) text changes.
16. G25 asked two questions. The setting is answered. That Lumen decided not to allow model improvement is implied by Sofia's action, but nobody stated who decided. I closed G25 on that basis; the DPO may reopen it at review.
17. Whether HelpPilot used any transcripts before today, while the opt-out was OFF, is unknown. No evidence of the setting (screenshot, vendor confirmation) was supplied. I created no gap for either, because the rules create gaps only for empty fields or unconfirmed values.

E5 (NordCloud Backup AB)
18. Norway is an EEA state, so I assumed it is not a third country for Art. 30(1)(e) and left (e) unchanged. This is outside knowledge, not from the inputs; the DPO should confirm (T5). Whether NordCloud Backup AB is related to NordCloud AB, whether the notice takes effect on 2026-11-18, and whether anyone outside the EEA can access the backups are all unknown. G28 asks.

Baseline issues I noticed and did not change (no event touches them)
19. R3 and R4 are "draft" but have empty required fields. The rules define "open" as "required fields missing".
20. R4 has no gaps for the empty (e) and (g). R4 (b) to (d) cite only "register", which is not an identifiable document, page or person under the evidence rule. TalentTrail has no contract seen.
21. R2 (e) says the SCC copy was "not seen" and R2 has no gap for it. R3 has the equivalent gap G23.
