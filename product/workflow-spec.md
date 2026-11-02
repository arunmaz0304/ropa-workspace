# Workflow spec

Written so it can become an n8n flow or a Lovable build. Product design, not legal requirement.

Version 0.2, 2 November 2026. Section 10 records the decisions made after the change test.

## 1. Intake

For each processing activity:

1. Ask in business language (examples below).
2. Map answers to Article 30 fields (see `ropa-record-template.md`).
3. Import any existing documents and extract candidate values.

Example questions:

| Business question | Maps to |
|---|---|
| What is this used for in the business? | Purposes |
| Whose information is in it? (customers, staff, applicants) | Categories of data subjects |
| What kind of information? (contact, pay, CVs, chat logs) | Categories of personal data |
| Who else gets to see it? | Recipients |
| Is any of it handled or stored outside the EU/EEA? | Transfers |
| How long do you keep it, and what happens after? | Erasure time limits |
| How is it protected? | Security measures |

Owner-facing text uses business words. A legal term appears only in brackets after a plain explanation, for example "the data-transfer clauses (SCCs)".

## 2. Evidence rule

Every field holds one of:

- `value` + `source_ref` + `captured_at` + `status`
- `empty` (no support found)

Never a value without a source. A source is a document with page or row, or a person with a date. Status is one of:

| Status | Meaning |
|---|---|
| suggested | Taken from a document or an extraction. Nobody has checked it |
| owner-stated | A named person told us. Counts as sourced |
| confirmed | The owner has confirmed the whole record |

## 3. Gap to action

A gap is created when a required field is empty, a suggested value is unconfirmed, or two sources disagree.

Gap object:

| Field | Description |
|---|---|
| gap_id | |
| activity_id, field | What is missing |
| question | One plain-language question for the owner |
| owner | Named person, by activity |
| due_date | Default set per organisation |
| priority | 1 unsupported or conflicting Article 30 field, 2 missing detail |
| status | open / answered / escalated / closed |
| escalation | Who is told if overdue |

Rules:
- One question per gap.
- No gap without an owner. If none is known, the gap goes to the DPO or workspace admin.
- Answering a gap fills the field with `source_ref` = the answerer and date, status `owner-stated`.
- An owner-stated change to an AI setting or a transfer safeguard also creates a gap asking for evidence, such as a screenshot or the vendor's confirmation.
- The owner sees the gaps for one record as a single list, priority 1 first, five at a time. The rest appear as these are answered.
- Overdue gaps escalate once, then show on the DPO view.

## 4. States and approval

A record has at most one official (approved) version and at most one working draft.

```
open -> draft -> owner-confirmed -> dpo-reviewed -> approved
           ^           |                 |              |
           +-- changes requested --------+              |
           +--- material change: new working draft -----+
                (approved version stays official until replaced)
```

| State | Who moves it | Meaning |
|---|---|---|
| open | system | Any required field has no value |
| draft | system, or anyone with edit rights | Every required field has a value (suggested or owner-stated) or is marked not applicable by the owner. Nobody has confirmed |
| owner-confirmed | business owner | Owner says this reflects reality |
| dpo-reviewed | DPO / privacy lead | Reviewed for completeness and accuracy |
| approved | approver (DPO or controller's designated person) | Current official version |

Rules:
- Each transition records who (a person or "system"), when, and the trigger.
- A material change to an approved record opens a new working draft. The approved version stays official, marked "change pending", until the draft is approved and replaces it.
- A material change to an owner-confirmed or dpo-reviewed record sends it back to draft.
- The system moves a record back to draft when a material change is recorded. The owner or DPO can also send it back by hand.
- Roles can't skip states.
- Version numbers belong to approved versions. The first approval creates v1, the next v2. A record that has never been approved is a working draft with a change log and no version number.
- Article 30 field values are frozen in each approved version. Metadata (activity name, owner, notes) sits outside the version. Changing it creates no version, no state change and no review, and is logged.

## 5. Change and revalidation

Triggers:

| Trigger | Routed to | Effect |
|---|---|---|
| New vendor / sub-processor added | Activity owner + DPO | Linked activities get a new working draft |
| New purpose or system added | Activity owner | New activity or amended one |
| Retention period changed | Activity owner | Erasure field revalidated |
| New AI feature enabled | Activity owner + DPO | Linked AI-use record created, activity revalidated |
| Tool or vendor setting changed that affects an Article 30 field (for example an AI opt-out) | Activity owner + DPO | Affected field revalidated, evidence gap raised |
| Contract or DPA updated | DPO | Evidence refs refreshed, affected fields flagged |
| Owner leaves or role changes | Admin | Activities reassigned |
| Scheduled review date reached | Activity owner | Revalidation task |

Rules:
- Material change = anything that changes an Article 30 field value. Metadata edits aren't material.
- The DPO is told of every material change to a record that is dpo-reviewed or approved, whatever the table says.
- One owner task and one DPO review task per record, covering all pending changes. Not one per event. The specific questions stay as gaps.

## 6. Roles

| Role | Can |
|---|---|
| Business owner | Edit and confirm own activities, answer gaps |
| DPO / privacy lead | Review, request changes, approve |
| Admin | Manage users, owners, templates |
| External adviser (P1) | Delegated DPO functions per client workspace, no cross-client visibility |

## 7. Data model (minimum)

- Organisation
- Activity (role, owner, metadata, official version, working draft)
- Field value (activity, field, value, source_ref, status, version or draft)
- Source (document id, page/row, hash, uploaded by, date)
- Gap
- Vendor / sub-processor (reused across activities)
- Version (frozen snapshot of Article 30 fields, approval details)
- Transition log (who, when, trigger, from and to state)
- Change event (trigger type, reporter, affected activities)

## 8. Exports

Each export contains:

- Records in editable format (CSV and JSON; DOCX or XLSX on top)
- Evidence references per field
- Version history and state transitions
- Open gaps list

A PDF alone doesn't count as an export.

## 9. Build notes

- Interface and review screens: Lovable
- Extraction of candidate values with source spans: Claude API, with an explicit "no support found" output
- Routing, reminders, revalidation triggers: n8n
- Storage: EU/EEA region; decide who is processor for uploaded client documents before first real client data
- The state machine and the trigger table run as code, so the same event always gives the same result. Claude handles the judgment inside it: extracting values with sources, and deciding whether a change is material.

## 10. Decisions

Raised by the change test in `evaluation/dry-run/dry-run-2-score.md`. Decided on 2 November 2026 by Claude, on instruction, as defaults. Change any you disagree with and update sections 2 to 5 to match.

| # | Question | Decision | Why |
|---|---|---|---|
| 1 | Who moves a record back to draft on a trigger? | The system, automatically. The log shows "system", the trigger and the person who reported it. Owner or DPO can also do it by hand | Nobody has to remember. The log still shows who reported the change |
| 2 | While a new version is a draft, is the approved version still official? | Yes, marked "change pending" | A producible approved record should always exist |
| 3 | Does a never-approved record get a new version when it returns to draft? | No. Version numbers belong to approved versions. First approval is v1 | Less version noise. Every change is still in the log |
| 4 | Are cosmetic edits to an approved record versioned? | No. Metadata sits outside the version. Logged only | A rename shouldn't force a review. Frozen means the Article 30 values |
| 5 | Are owner statements "suggested" or confirmed? | Neither: `owner-stated`, with the owner as source. The owner still confirms the whole record | Shows where a value came from without treating a statement as a document |
| 6 | Who is routed for a settings change such as an AI opt-out? | Owner and DPO, with an evidence gap | It changes AI use, and an owner's word needs backing |
| 7 | Does the DPO hear about every material change to a record they approved? | Yes | They signed it off. They shouldn't find out from an export |

Also changed after the two dry runs:

- **Duplicate tasks.** One owner task and one DPO task per record, not one per event. In the test, two tasks both asked Maja to re-confirm the same record.
- **Too many gaps.** One question per gap, shown to the owner five at a time, priority first. Run 1 produced 40 gaps for 6 activities, and some run 2 gaps asked four questions.
- **Jargon.** Plain words first, legal terms in brackets.
- **Draft versus open.** A record with any empty required field is `open`. The test baseline had drafts with empty fields.
