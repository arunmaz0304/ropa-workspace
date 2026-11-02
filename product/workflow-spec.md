# Workflow spec

Written so it can become an n8n flow or a Lovable build. Product design, not legal requirement.

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

## 2. Evidence rule

Every field holds one of:

- `value` + `source_ref` (document, page/row, or person who stated it) + `captured_at`
- `empty` (no support found)

Never a value without a source. Suggested values from extraction are marked `suggested` until a person confirms them.

## 3. Gap to action

A gap is created when a required field is empty or a suggested value is unconfirmed.

Gap object:

| Field | Description |
|---|---|
| gap_id | |
| activity_id, field | What is missing |
| question | Plain-language question for the owner |
| owner | Named person, by activity |
| due_date | Default set per organisation |
| status | open / answered / escalated / closed |
| escalation | Who is told if overdue |

Rules:
- No gap without an owner. If none is known, the gap goes to the DPO or workspace admin.
- Answering a gap fills the field with `source_ref` = the answerer and date.
- Overdue gaps escalate once, then show on the DPO view.

## 4. States and approval

```
open -> draft -> owner-confirmed -> dpo-reviewed -> approved
                      ^                  |               |
                      +---- changes -----+---- change ---+
```

| State | Who moves it | Meaning |
|---|---|---|
| open | system | Required fields missing |
| draft | anyone with edit rights | Fields filled, nobody has confirmed |
| owner-confirmed | business owner | Owner says this reflects reality |
| dpo-reviewed | DPO / privacy lead | Reviewed for completeness and accuracy |
| approved | approver (DPO or controller's designated person) | Current official version |

Rules:
- Each transition records who, when and the version.
- A material change to an approved record returns it to `draft` and creates a new version.
- Roles can't skip states.
- Approved versions are immutable. Edits create a new version.

## 5. Change and revalidation

Triggers:

| Trigger | Routed to | Effect |
|---|---|---|
| New vendor / sub-processor added | Activity owner + DPO | Linked activities back to `draft` |
| New purpose or system added | Activity owner | New activity or amended one |
| Retention period changed | Activity owner | Erasure field revalidated |
| New AI feature enabled | Activity owner + DPO | Linked AI-use record created, activity revalidated |
| Contract or DPA updated | DPO | Evidence refs refreshed, affected fields flagged |
| Owner leaves or role changes | Admin | Activities reassigned |
| Scheduled review date reached | Activity owner | Revalidation task |

Material change = anything that changes an Article 30 field value. Cosmetic edits don't trigger revalidation.

## 6. Roles

| Role | Can |
|---|---|
| Business owner | Edit and confirm own activities, answer gaps |
| DPO / privacy lead | Review, request changes, approve |
| Admin | Manage users, owners, templates |
| External adviser (P1) | Delegated DPO functions per client workspace, no cross-client visibility |

## 7. Data model (minimum)

- Organisation
- Activity (role, owner, current state, current version)
- Field value (activity, field, value, source_ref, status, version)
- Source (document id, page/row, hash, uploaded by, date)
- Gap
- Vendor / sub-processor (reused across activities)
- Version (snapshot, state transitions with who and when)
- Change event (trigger type, affected activities)

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
