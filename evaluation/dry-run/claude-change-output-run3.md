# Change result: Lumen Outdoor AB RoPA workspace

Events processed in order: E1, E2, E3 (2026-11-03), E4, E5 (2026-11-04). Task and gap due dates = event date + 14 days (2026-11-17 for E1-E3, 2026-11-18 for E4-E5). New gap IDs continue after G31 (my numbering).

## Section 1: Event by event

### E1, 2026-11-03: ClientHub adds sub-processor InsightLoop Analytics AB (R1)

(a) Material. It changes field (d) recipients, which lists sub-processors (rules s5: new sub-processor trigger; material = changes an Article 30 field value).

(b) Affects R1 only (ClientHub AB is used only by R1).

(c) Field changes:

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (d) Recipients | ClientHub AB (processor). Sub-processors: CloudHost Europe GmbH (infrastructure, EU), MailRelay SE AB (email delivery, EU) | ClientHub AB (processor). Sub-processors: CloudHost Europe GmbH (infrastructure, EU), MailRelay SE AB (email delivery, EU), InsightLoop Analytics AB (product analytics on CRM usage data; EU hosting per vendor notice; not yet in effect, effective date not stated) | ClientHub AB 30-day notice email, forwarded by Maja Lindqvist, 2026-11-03 | suggested |

Fields (a), (b), (c), (e), (f), (g) unchanged in this event. (e) "None, hosting EU only" is left as is: the notice's EU claim is unverified and no contract is attached (covered by gap below).

(d) State: R1 approved -> new working draft in state `draft`. Moved by system, trigger E1 (material change to approved record). v1 stays official, marked "change pending". No new version created.

(e) Routed to: Maja Lindqvist (activity owner) and Anna Berg (DPO). The table requires both for a new sub-processor.

(f) Tasks (one owner task and one DPO task per record, covering all pending changes):
- Owner task, owner Maja Lindqvist, due 2026-11-17: "R1 Customer management (CRM): review and confirm pending draft changes". Check the updated field (d), answer the open R1 gaps, then confirm the draft if it reflects reality (draft -> owner-confirmed).
- DPO task, owner Anna Berg, due 2026-11-17: "R1: DPO review of pending change". Note the pending change to the approved record; review (d) after the owner confirms. v1 remains official until a new version replaces it.

(g) Gaps opened (all owner Maja Lindqvist, due 2026-11-17):
- G32, R1 (d), priority 1: "Can you ask ClientHub for the updated sub-processor list or contract amendment that names InsightLoop Analytics AB and its hosting location?" (suggested value, no document, EU claim unverified)
- G33, R1 (d), priority 2: "From what date will InsightLoop Analytics AB start processing Lumen's CRM data?"
- G34, R1 (c), priority 2: "What personal data, and about whom (customers, prospects, Lumen staff), will InsightLoop receive as 'CRM usage data'?"

Gaps closed: none.

### E2, 2026-11-03: R1 retention changed to 5 years after last purchase

(a) Material. It changes field (f) erasure time limit.

(b) Affects R1.

(c) Field changes:

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (f) Erasure | 7 years | 5 years after last purchase, applies from 2026-11-03 | Maja Lindqvist, 2026-11-03 | owner-stated |

(d) State: R1 already has a working draft (from E1), so no second draft is created (at most one). Draft stays `draft`; no transition. v1 (7 years) stays official.

(e) Routed to: Maja Lindqvist (activity owner; she is the reporter, field revalidated by her statement). Anna Berg (DPO) is also told, because R1 is approved (rule: DPO told of every material change to a dpo-reviewed or approved record).

(f) Tasks: no new tasks. The existing R1 owner task and DPO task (E1) are updated to cover (f) as well. Due date stays 2026-11-17 (same event date). Owner must also check (f) wording; DPO reviews (f) together with (d).

(g) Gaps opened:
- G35, R1 (f), priority 2, owner Maja Lindqvist, due 2026-11-17: "How long do you keep data about prospects who never made a purchase?"

Gaps closed: none.

### E3, 2026-11-03: Rename activity to "Customer management (CRM)"

(a) Metadata. Activity name sits outside the approved version; no Article 30 field value changes.

(b) Affects R1 (name shown on the official v1 and the working draft).

(c) Field changes: none to Article 30 fields. Metadata: activity name | Customer management | Customer management (CRM) | Maja Lindqvist request, 2026-11-03 | not applicable (metadata has no status).

(d) State: no state change, no version, no draft, no review. Logged only.

(e) Routed to: nobody.

(f) Tasks: none created or updated.

(g) Gaps: none opened or closed.

### E4, 2026-11-04: HelpPilot model-improvement opt-out switched ON (R3)

(a) Material. A vendor setting change that affects an Article 30 field: (b) purposes states opt-out is OFF and that HelpPilot may use transcripts. Trigger: tool or vendor setting changed.

(b) Affects R3 (HelpPilot AI Ltd is used only by R3).

(c) Field changes:

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (b) Purposes | AI chat assistant answering customer questions on the website, with handover to human agents. HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out is currently OFF | AI chat assistant answering customer questions on the website, with handover to human agents. HelpPilot may use anonymised transcripts to improve its models unless Lumen opts out. Opt-out switched ON by Lumen on 2026-11-04, so HelpPilot no longer uses Lumen's transcripts to improve its models | Sofia Nyberg, 2026-11-04; AI support contract / Service, Model improvement | owner-stated (changed part) |

(d) State: R3 `open` -> `open` (unchanged; (f) still has no value). No version (never approved). The record stays a working draft with change log. The "back to draft" rule applies only to owner-confirmed or dpo-reviewed records, so it does not apply. No transition moved by anyone.

(e) Routed to: Sofia Nyberg (activity owner) and Anna Berg (DPO), per the table.

(f) Tasks (R3 had none):
- Owner task, owner Sofia Nyberg, due 2026-11-18: "R3 AI customer support: revalidate after opt-out change". Check the new (b) wording, supply the evidence asked in G36, and answer G23 and G24 (needed to fill (f) and move the record to draft).
- DPO task, owner Anna Berg, due 2026-11-18: "R3: DPO review of pending change". Note the AI setting change and the evidence status. Formal review of the record only when it reaches owner-confirmed.

(g) Gaps:
- G25 ("Is the opt-out on or off today?") answered by Sofia Nyberg, 2026-11-04 -> status answered/closed; it filled (b) as above.
- Opened G36, R3 (b), priority 2, owner Sofia Nyberg, due 2026-11-18: "Can you send a screenshot of the HelpPilot admin setting, or a confirmation from HelpPilot, showing that the model-improvement opt-out is ON?" (required because an owner-stated change to an AI setting needs evidence)
- G23 and G24 remain open (due 2026-11-16).

### E5, 2026-11-04: PayLedger adds sub-processor NordCloud Backup AB (R2)

(a) Material. It changes field (d) recipients (sub-processors).

(b) Affects R2 only.

(c) Field changes:

| Field | Old | New | Source | Status |
|---|---|---|---|---|
| (d) Recipients | PayLedger Nordic AB (processor); Skatteverket. Sub-processors: NordCloud AB (hosting, Sweden), SupportBridge Inc. (tier 2 support, United States) | PayLedger Nordic AB (processor); Skatteverket. Sub-processors: NordCloud AB (hosting, Sweden), SupportBridge Inc. (tier 2 support, United States), NordCloud Backup AB (backup hosting, Norway; not yet in effect, effective date not stated) | PayLedger Nordic AB 14-day notice email, forwarded by Erik Holm, 2026-11-04 | suggested |

(e) Transfers left unchanged (see section 4, item 5).

(d) State: R2 owner-confirmed -> draft. Moved by system, trigger E5 (material change to owner-confirmed record). No new working draft: the existing working draft returns to `draft`. No version (R2 was never approved). The owner's earlier confirmation (2026-10-22) no longer covers the record.

(e) Routed to: Erik Holm (activity owner) and Anna Berg (DPO), per the table (even though R2 is not yet dpo-reviewed).

(f) Tasks (R2 had none besides gap G31):
- Owner task, owner Erik Holm, due 2026-11-18: "R2 Payroll: review pending change and re-confirm". Check new (d), answer G37 and G38, then re-confirm the record (draft -> owner-confirmed). G31 stays a separate gap.
- DPO task, owner Anna Berg, due 2026-11-18: "R2: DPO review of pending change". Note the new sub-processor; review once the owner re-confirms.

(g) Gaps opened (owner Erik Holm, due 2026-11-18):
- G37, R2 (d), priority 1: "Can you ask PayLedger for the updated sub-processor list or contract amendment that names NordCloud Backup AB and its backup location?"
- G38, R2 (d), priority 2: "From what date will NordCloud Backup AB start processing payroll backups?"

Gaps closed: none. G31 (due 2026-11-16) remains open.

## Section 2: Resulting state

| Record | Record state | Official version | Change pending | Open tasks | Open gaps | Different from baseline |
|---|---|---|---|---|---|---|
| R1 "Customer management (CRM)" | approved (v1 official) with working draft in `draft` | v1 | Yes | Maja Lindqvist owner task (due 2026-11-17); Anna Berg DPO task (due 2026-11-17) | G32, G33, G34, G35 | Name changed; working draft opened; (d) and (f) changed in draft only; change pending; 2 tasks, 4 gaps |
| R2 Payroll | draft | none | No (never approved, so no "change pending"; record went back to draft) | Erik Holm owner task; Anna Berg DPO task (both due 2026-11-18) | G31, G37, G38 | owner-confirmed -> draft; (d) changed; 2 tasks, 2 new gaps |
| R3 AI customer support | open | none | No | Sofia Nyberg owner task; Anna Berg DPO task (both due 2026-11-18) | G23, G24, G36 (G25 answered) | (b) changed; 2 tasks; G25 answered, G36 opened; state unchanged |
| R4 Recruitment | open | none | No | none | G17, G29, G30 | No change |

## Section 3: Change log

| Date | Record | Field | Old | New | Source | Who | Trigger |
|---|---|---|---|---|---|---|---|
| 2026-11-03 | R1 | state | approved (v1), no draft | approved (v1) + working draft `draft`, change pending | n/a | system | E1 material change to approved record |
| 2026-11-03 | R1 | (d) Recipients | ...CloudHost, MailRelay | ...plus InsightLoop Analytics AB (EU per notice, not yet effective) | ClientHub AB notice email fwd by Maja Lindqvist, 2026-11-03 | system | E1 new sub-processor |
| 2026-11-03 | R1 | (f) Erasure | 7 years | 5 years after last purchase, from 2026-11-03 | Maja Lindqvist, 2026-11-03 | system (recording Maja Lindqvist's report) | E2 retention changed |
| 2026-11-03 | R1 | activity name (metadata) | Customer management | Customer management (CRM) | Maja Lindqvist, 2026-11-03 | Maja Lindqvist (requested; applied without review) | E3 rename, not material |
| 2026-11-04 | R3 | (b) Purposes | Opt-out currently OFF | Opt-out ON since 2026-11-04; no model-improvement use | Sofia Nyberg, 2026-11-04 | system (recording Sofia Nyberg's report) | E4 vendor setting change |
| 2026-11-04 | R3 | gap G25 | open | answered | Sofia Nyberg, 2026-11-04 | system | E4 |
| 2026-11-04 | R2 | state | owner-confirmed | draft | n/a | system | E5 material change to owner-confirmed record |
| 2026-11-04 | R2 | (d) Recipients | ...NordCloud AB, SupportBridge Inc. | ...plus NordCloud Backup AB (Norway, not yet effective) | PayLedger Nordic AB notice email fwd by Erik Holm, 2026-11-04 | system | E5 new sub-processor |
| 2026-11-03/04 | R1, R2, R3 | tasks and gaps | none | tasks and gaps as listed in section 1 (G32-G38) | n/a | system | E1, E2, E4, E5 |

## Section 4: Ambiguities, undecided points, choices beyond the rules

1. Announced vs effective sub-processors (E1, E5). The rules say "sub-processor added" but both notices announce a future addition and give no effective date. I recorded the field change on receipt, marked "not yet in effect", and raised an effective-date gap. The alternative (wait until the effective date) is not excluded by the rules. I did not compute effective dates because the notice dates are not given (the forwarding date is not necessarily the notice date).
2. Status of unchanged fields. The rules define `confirmed` as the owner confirming the whole record. They do not say what happens to the `confirmed` status of untouched fields in R1's new draft and in R2 after reverting to draft. I left them as in baseline; the owner must re-confirm the record anyway.
3. Statuses of changed fields. E1 and E5 are documents forwarded by the owner, so I used `suggested`, not `owner-stated`. E2 and E4 are stated by the owner, so `owner-stated`. Field (b) in R3 mixes a contract-based and an owner-stated element; I gave it `owner-stated`.
4. E4 gap priority. Rules define priority 1 as unsupported or conflicting Article 30 field. (b) has an owner-stated source, so I chose priority 2 for the evidence gap G36. Priority 1 is arguable.
5. E5 and Norway. I left (e) transfers unchanged on the basis that Norway is in the EEA. That is general knowledge, not given by any input, and was not checked. Whether NordCloud Backup AB is related to NordCloud AB, and whether backups leave Norway, is unknown. DPO to confirm.
6. E1 data subjects. "CRM usage data" may involve personal data of Lumen staff or customers. R1 (c) lists only customers and prospects. I did not change (c); G34 asks.
7. E2 retention source. Maja says the change is "in line with the retention policy". No retention policy for R1 is in the inputs, so I cited only Maja. I did not check the claim against retention-policy.pdf.
8. E2 scope. The new rule is silent on prospects with no purchase (G35) and on data already older than 5 years; the latter is not asked about.
9. G25 status. Allowed statuses are open/answered/escalated/closed. I marked it answered; whether it counts as closed once the evidence gap exists is not specified.
10. Gap numbering, due dates and escalation. Gap IDs (G32-G38) are mine. Default gap due date is "set per organisation" and no value is given; I used event date + 14 days (matching the baseline pattern and the task rule). The escalation recipient is not given by the rules or inputs; I did not set one (assumption that it would be the DPO is untested).
11. DPO tasks on records not yet reviewable (R2 and R3). The rules require DPO routing and one DPO review task per record, but the state machine only lets the DPO review after owner-confirmed. I created the DPO tasks as "note and review once the record reaches the right state".
12. R2 "change pending". The rules define change pending only for approved records. R2 has no official version, so I show "No" and rely on the state returning to draft.
13. "Who" for E2, E3, E4. The owners reported the changes; I logged "system" for E2 and E4 (the system recorded the report) and Maja Lindqvist for E3 (a metadata edit by an owner with edit rights). The rules do not say how to log a report that was not entered by the person.
14. E3 and the DPO. Rules say metadata changes cause no review; the DPO is told only about material changes, so no one is notified of the rename.
15. Vendor table in baseline not updated (it lists vendors only, not sub-processors).
