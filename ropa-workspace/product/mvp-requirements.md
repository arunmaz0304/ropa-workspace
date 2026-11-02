# MVP requirements

Hypothesis: an evidence-backed RoPA workspace for SMEs and external DPOs that turns existing documents into reviewable records, keeps owners accountable, and shows exactly what remains unverified.

This is not a proven market gap. Reviewed competitors already cover substantial parts of mapping, workflow, risk and automation. Run the Evaluate track first and update this file with what you find.

The controller/processor split comes from Article 30. Everything else here is suggested product design, not a statutory RoPA requirement.

## P0: needed for the first usable version

| Feature | Requirement | Test in demo/build |
|---|---|---|
| Guided activity intake | Ask business-language questions and produce structured records. Users shouldn't need GDPR terminology first | A non-lawyer completes an activity |
| Controller/processor separation | Generate the appropriate Article 30 structure for each role | Two different outputs from the same activity set |
| Evidence-backed drafting | Import spreadsheets and documents; show the source for each suggested value; leave unsupported fields unanswered | Click any field, see the source or an empty state |
| Gap-to-action workflow | Turn missing information into an assigned question or task, not just a red score | Every gap has an owner and a date |
| Owner and DPO approval | Keep draft, confirmed, reviewed and approved as distinct states | History shows who and when for each |
| Portable outputs | Export editable records, evidence references and version history, not only a presentation PDF | Export opens and is usable outside the tool |

## P1: after P0 works

| Feature | Requirement |
|---|---|
| Change propagation | Update connected records and route material changes for review |
| Linked AI-use inventory | Reuse activity, vendor, data and owner information across privacy and AI assessments |
| External-adviser workspace | Separate client workspaces, delegated review, controlled client access |

## P2: later

| Feature | Requirement |
|---|---|
| Deeper discovery | Connectors to source systems, once the validation and maintenance workflow is proven useful |

## Out of scope for v0.1

- Risk scoring and DPIA workflow
- Data subject request handling
- Automated legal conclusions

## Open questions

- Which vendor, if any, already passes all P0 checks?
- Is the external DPO or the SME the paying customer?
- Where does extracted text from client documents live, and who is the processor for that?
