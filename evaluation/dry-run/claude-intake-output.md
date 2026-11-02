# RoPA draft records: Lumen Outdoor AB

Prepared 2026-11-02. Gap due date for all items: 2026-11-16 (14 days).
Status: every value below is "suggested" (taken from an input file). Nothing is confirmed; no owner has confirmed anything.

Source conventions (all files are in `input/`):
- `excel-register.csv` line N = file line number. Line 1 is the header; line 2 = Customer management, 3 = Payroll, 4 = Recruitment, 5 = AI customer support, 6 = Newsletter, 7 = Customers - CRM, 8 = Returns portal.
- Contract files are cited by table item (the "Item" column label), e.g. `crm-vendor.md / Sub-processors`.
- `retention-policy.md` is cited by table row (Category).
- The company name "Lumen Outdoor AB" appears only in the contract summaries and the retention policy, not in the register. For Recruitment and Newsletter it is taken from `retention-policy.md` title and assumed to be the same entity.

## Section 1: Controller records (Art 30(1))

### 1.1 Customer management (ClientHub CRM) - owner Maja Lindqvist

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB | crm-vendor.md / Parties | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN (G01) |
| (b) Purposes | Manage customer relationships and sales follow-up | excel-register.csv line 2 (Purpose). Line 7 says only "Sales" | suggested |
| (c) Data subjects | Customers and prospects | excel-register.csv line 2; crm-vendor.md / Data subjects | suggested |
| (c) Personal data | Name, email, phone, purchase history (register); contract also lists company and email correspondence | excel-register.csv line 2; crm-vendor.md / Personal data | suggested (register and contract differ, G04) |
| (d) Recipients | ClientHub AB (processor); sub-processors CloudHost Europe GmbH (infrastructure, EU) and MailRelay SE AB (email delivery, EU) | excel-register.csv line 2 (Shared with: ClientHub); crm-vendor.md / Parties, Sub-processors | suggested (register lists only ClientHub, G07) |
| (e) Third-country transfers | None. Hosting EU only (Frankfurt, Dublin); support EU-based | excel-register.csv line 2 (Outside EU?: No); crm-vendor.md / International transfers, Hosting, Support access | suggested |
| (f) Time limits for erasure | OPEN. Conflict: 7 years (register line 2), 5 years (register line 7), 5 years after last purchase (policy) | excel-register.csv lines 2 and 7; retention-policy.md / Customer accounts and order history | OPEN (G03) |
| (g) Security measures | Vendor-side only: encryption at rest and in transit, role-based access, annual penetration test, ISO 27001 certified. Lumen's own measures OPEN | crm-vendor.md / Security | suggested (partial, G06) |

### 1.2 Payroll (PayLedger Nordic) - owner Erik Holm

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB | payroll-provider.md / Parties | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN (G01) |
| (b) Purposes | Pay salaries and report to authorities | excel-register.csv line 3; payroll-provider.md / Service | suggested |
| (c) Data subjects | Employees | excel-register.csv line 3; payroll-provider.md / Data subjects | suggested |
| (c) Personal data | Name, personal ID number, bank account, salary, absence; contract also lists tax details | excel-register.csv line 3; payroll-provider.md / Personal data | suggested (register omits tax details, G11) |
| (d) Recipients | PayLedger Nordic AB (processor); Skatteverket; sub-processors NordCloud AB (hosting, Sweden) and SupportBridge Inc. (tier 2 support, United States) | excel-register.csv line 3 (Shared with); payroll-provider.md / Parties, Sub-processors | suggested (register omits sub-processors, G10) |
| (e) Third-country transfers | United States: SupportBridge Inc., tier 2 support with remote access to customer data when escalated. Safeguard: Standard Contractual Clauses referenced in contract; signed copy and transfer assessment not seen | payroll-provider.md / Support access, Sub-processors, International transfers. Register line 3 "Outside EU?" is blank | suggested (register blank, G09) |
| (f) Time limits for erasure | 7 years after year-end | excel-register.csv line 3 (Keep for); retention-policy.md / Payroll and employment records. Vendor keeps data for contract term plus up to 7 years or as instructed in writing (payroll-provider.md / Retention) | suggested (G12) |
| (g) Security measures | Vendor-side only: encryption, multi-factor authentication for vendor staff, access logging. Lumen's own measures OPEN | payroll-provider.md / Security | suggested (partial, G13) |

### 1.3 Recruitment (TalentTrail) - owner Erik Holm

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB (assumed same entity) | retention-policy.md (title) | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN (G01) |
| (b) Purposes | "Hiring" (no further detail) | excel-register.csv line 4 | suggested (thin, G16) |
| (c) Data subjects | Applicants | excel-register.csv line 4 | suggested |
| (c) Personal data | CV, contact details, interview notes | excel-register.csv line 4 | suggested |
| (d) Recipients | TalentTrail (role not stated in any input; no contract provided) | excel-register.csv line 4 (Shared with) | suggested (G15) |
| (e) Third-country transfers | OPEN | register line 4 "Outside EU?" is blank; no contract | OPEN (G18) |
| (f) Time limits for erasure | OPEN. Register field is blank; policy expressly excludes applicant data | excel-register.csv line 4; retention-policy.md (note below table) | OPEN (G17) |
| (g) Security measures | OPEN | none | OPEN (G20) |

### 1.4 AI customer support (HelpPilot AI) - owner Sofia Nyberg

Role conflict: the register records "Our role: Processor"; the contract summary names Lumen as customer and HelpPilot as processor. This record is drafted as a controller record on the contract evidence. Role is unconfirmed (G22). No Section 2 record is drafted for it.

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB | ai-support-vendor.md / Parties | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN (G01) |
| (b) Purposes | AI chat assistant answering customer questions on the website, with handover to human agents. Register says only "AI chat". Contract also allows HelpPilot to use anonymised transcripts to improve its models unless Lumen opts out (opt-out off by default) | ai-support-vendor.md / Service, Model improvement; excel-register.csv line 5 | suggested (G25) |
| (c) Data subjects | Customers and website visitors | ai-support-vendor.md / Data subjects; excel-register.csv line 5 (Customers only) | suggested (G26) |
| (c) Personal data | Chat transcripts; email address and order number if the customer provides them | ai-support-vendor.md / Personal data; excel-register.csv line 5 ("Chat logs") | suggested |
| (d) Recipients | HelpPilot AI Ltd (processor); sub-processors CloudHost Europe GmbH (EU) and an unnamed third-party LLM provider (United States); Lumen's human agents on handover | ai-support-vendor.md / Parties, Sub-processors, Service; excel-register.csv line 5 | suggested (G27) |
| (e) Third-country transfers | United States: LLM provider inference. Safeguard: contract refers to Standard Contractual Clauses; no copy attached. Application and transcripts hosted in Ireland (EU); support access EU-only | ai-support-vendor.md / AI model provider, International transfers, Hosting, Support access. Register line 5 "Outside EU?" is "?" | suggested (G23) |
| (f) Time limits for erasure | OPEN. Contract default is 12 months, configurable by Lumen. Register says "TBD"; policy excludes chat transcripts | ai-support-vendor.md / Retention; excel-register.csv line 5; retention-policy.md (note) | OPEN (G24) |
| (g) Security measures | Vendor-side only: encryption, access controls, SOC 2 Type II report available on request (not seen). Lumen's own measures OPEN | ai-support-vendor.md / Security | suggested (partial, G28) |

### 1.5 Newsletter (system not identified) - owner "Marketing" (team, no named person)

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB (assumed same entity) | retention-policy.md (title) | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN (G01) |
| (b) Purposes | Email marketing | excel-register.csv line 6 | suggested |
| (c) Data subjects | Customers | excel-register.csv line 6 | suggested (G33) |
| (c) Personal data | Email address | excel-register.csv line 6 | suggested |
| (d) Recipients | "Mailer tool" (vendor not named; no contract provided) | excel-register.csv line 6 (Shared with) | suggested (G30) |
| (e) Third-country transfers | Register says "No"; cannot be checked because the tool is unidentified | excel-register.csv line 6 | suggested (unverified, G31) |
| (f) Time limits for erasure | Until unsubscribe (register); policy adds "or 24 months of no engagement" | excel-register.csv line 6; retention-policy.md / Marketing email addresses | suggested (register incomplete, G32) |
| (g) Security measures | OPEN | none | OPEN (G34) |

### 1.6 Customers - CRM (register line 7), probable duplicate of 1.1

Not drafted as a separate record. Line 7 (owner "Maja", system "ClientHub", purpose "Sales", data "Name, email", retention 5 years, last updated 2022-09) appears to describe the same activity as 1.1. Merge decision is OPEN (G05). Its differing values are shown in 1.1.

## Section 2: Processor records (Art 30(2))

Only one activity is recorded as processing on behalf of others: the Returns portal (register line 8). The register's other "Processor" entry (AI customer support) conflicts with its contract and is handled in 1.4.

### 2.1 Returns portal for partner shops (in-house portal) - owner not named

| Art 30 field | value or OPEN | source | status |
|---|---|---|---|
| (a) Processor name | Lumen Outdoor AB (assumed same entity) | retention-policy.md (title) | suggested |
| (a) Processor contact details and DPO | OPEN | none | OPEN (G01) |
| (a) Each controller on whose behalf it acts (and their DPOs) | OPEN. Register says only "partner shops"; none named; no partner contracts provided | excel-register.csv line 8 (Whose data, Keep for) | OPEN (G37) |
| (b) Categories of processing per controller | OPEN per controller. Register describes the activity as "Handle returns for partner shops", of partner shops' customers' name, address, order number. This is a purpose description, not a defined list of processing operations | excel-register.csv line 8 (Purpose, Whose data, What data) | suggested (partial, G38) |
| (c) Third-country transfers | None, per register. Hosting and any sub-processors of the in-house portal not stated | excel-register.csv line 8 (Outside EU?: No) | suggested (unverified, G39) |
| (d) Security measures | OPEN | none | OPEN (G40) |

## Section 3: Gaps

Convention: each record has one "confirm all suggested values" gap, because no suggested field is confirmed. Specific gaps are listed separately for OPEN fields and conflicts. Due date for every gap: 2026-11-16. "Unassigned, DPO" means no owner is named in the inputs.

| id | activity | field | question | owner | due |
|---|---|---|---|---|---|
| G01 | All records (Sec 1 and 2) | 30(1)(a), 30(2)(a) | What are the contact details of Lumen Outdoor AB and of the DPO (or is there none)? Is there an EU representative? Is any activity run jointly with another company? | unassigned, DPO | 2026-11-16 |
| G02 | Customer management | all suggested fields | Please confirm or correct every value in record 1.1. | Maja Lindqvist | 2026-11-16 |
| G03 | Customer management | (f) erasure | The register says 7 years on one line and 5 years on another; the policy says 5 years after last purchase. Which applies, and when does the clock start? | Maja Lindqvist | 2026-11-16 |
| G04 | Customer management | (c) data | The contract also lists company and email correspondence. Do you hold these in the CRM? Is anything else held? | Maja Lindqvist | 2026-11-16 |
| G05 | Customer management | duplicate line | Is "Customers - CRM" (register line 7) the same activity as "Customer management"? Can the two be merged? | Maja Lindqvist | 2026-11-16 |
| G06 | Customer management | (g) security | What technical and organisational measures does Lumen itself apply to the CRM (access, logging, training)? | unassigned, DPO | 2026-11-16 |
| G07 | Customer management | (d) recipients | Does CRM data go to anyone beyond ClientHub and its two listed sub-processors? | Maja Lindqvist | 2026-11-16 |
| G08 | Payroll | all suggested fields | Please confirm or correct every value in record 1.2. | Erik Holm | 2026-11-16 |
| G09 | Payroll | (e) transfers | The register leaves "Outside EU?" blank, but the contract shows US tier 2 support with remote access. Please confirm this transfer exists. Please supply the signed SCCs and any transfer assessment. | Erik Holm | 2026-11-16 |
| G10 | Payroll | (d) recipients | Besides PayLedger and Skatteverket, who else receives payroll data? Do you accept the sub-processors named in the contract? | Erik Holm | 2026-11-16 |
| G11 | Payroll | (c) data | The contract lists tax details; the register does not. Is this data held? Anything else? | Erik Holm | 2026-11-16 |
| G12 | Payroll | (f) erasure | Is 7 years after year-end right for all payroll data? Have you instructed PayLedger in writing on post-contract retention? | Erik Holm | 2026-11-16 |
| G13 | Payroll | (g) security | What measures does Lumen itself apply to payroll data? | unassigned, DPO | 2026-11-16 |
| G14 | Recruitment | all suggested fields | Please confirm or correct every value in record 1.3. | Erik Holm | 2026-11-16 |
| G15 | Recruitment | (d) recipients, contract | Is there a data processing agreement with TalentTrail? Where is it established and who are its sub-processors? | Erik Holm | 2026-11-16 |
| G16 | Recruitment | (b) purposes | "Hiring" is the only purpose recorded. Is applicant data also kept for future vacancies or used for anything else? | Erik Holm | 2026-11-16 |
| G17 | Recruitment | (f) erasure | How long do you keep applicant data, and after what trigger? The policy does not cover it. | Erik Holm | 2026-11-16 |
| G18 | Recruitment | (e) transfers | Does applicant data leave the EU (TalentTrail or its sub-processors)? | Erik Holm | 2026-11-16 |
| G19 | Recruitment | (c) data | Is the data list complete? Do CVs or interview notes include sensitive information? | Erik Holm | 2026-11-16 |
| G20 | Recruitment | (g) security | What measures protect applicant data? | unassigned, DPO | 2026-11-16 |
| G21 | Recruitment | record age | Register line 4 was last updated 2023-11. Is it still accurate? | Erik Holm | 2026-11-16 |
| G22 | AI customer support | role | The register says Lumen is the processor; the contract says Lumen is the customer and HelpPilot the processor. Is Lumen the controller for chat data? If Lumen acts for another party, who? | Sofia Nyberg | 2026-11-16 |
| G23 | AI customer support | (e) transfers | Who is the LLM provider? Please supply the SCCs referenced in the contract and any transfer assessment. In which country is HelpPilot AI Ltd established (the summary does not say)? | Sofia Nyberg | 2026-11-16 |
| G24 | AI customer support | (f) erasure | What retention period is configured in HelpPilot (default 12 months)? What period should apply, and who decides? | Sofia Nyberg | 2026-11-16 |
| G25 | AI customer support | (b) purposes | What is the current admin setting for model improvement with anonymised transcripts? Has Lumen decided whether to allow it? | Sofia Nyberg | 2026-11-16 |
| G26 | AI customer support | (c) data subjects, data | Website visitors and email/order numbers appear in the contract but not the register. Please confirm. Can customers type other personal data into the chat? | Sofia Nyberg | 2026-11-16 |
| G27 | AI customer support | (d) recipients | Which Lumen teams or tools receive transcripts on handover to human agents? | Sofia Nyberg | 2026-11-16 |
| G28 | AI customer support | (g) security | What measures does Lumen itself apply? Has the SOC 2 Type II report been requested and reviewed? | unassigned, DPO | 2026-11-16 |
| G29 | AI customer support | all suggested fields | Please confirm or correct every value in record 1.4. | Sofia Nyberg | 2026-11-16 |
| G30 | Newsletter | (d) recipients, contract | Which mailer tool and vendor is used? Is there a contract or DPA? Where does it host data? | Marketing (team; no named person) | 2026-11-16 |
| G31 | Newsletter | (e) transfers | Once the tool is named: does any data leave the EU? | Marketing (team; no named person) | 2026-11-16 |
| G32 | Newsletter | (f) erasure | Is the rule "until unsubscribe" or also "after 24 months of no engagement" (policy)? Which is applied in practice? | Marketing (team; no named person) | 2026-11-16 |
| G33 | Newsletter | (c) data subjects | Are subscribers only customers, or also prospects and others? | Marketing (team; no named person) | 2026-11-16 |
| G34 | Newsletter | (g) security | What measures protect the mailing list? | unassigned, DPO | 2026-11-16 |
| G35 | Newsletter | all suggested fields, owner | Please confirm or correct every value in record 1.5. Which named person owns this activity? | Marketing (team; no named person) | 2026-11-16 |
| G36 | Returns portal | owner, all suggested fields | Who owns the portal? Please confirm or correct every value in record 2.1. | unassigned, DPO | 2026-11-16 |
| G37 | Returns portal | 30(2)(a) controllers | Which partner shops use the portal? What are their contacts and DPOs? Where are the written instructions? | unassigned, DPO | 2026-11-16 |
| G38 | Returns portal | 30(2)(b) processing | What processing operations does Lumen perform for each partner shop (e.g. storing, forwarding, deleting)? Is Lumen using the data for its own purposes? | unassigned, DPO | 2026-11-16 |
| G39 | Returns portal | 30(2)(c) transfers | Where is the portal hosted and does it use any sub-processors? Does any data leave the EU? | unassigned, DPO | 2026-11-16 |
| G40 | Returns portal | 30(2)(d) security | What measures protect the portal and its data? | unassigned, DPO | 2026-11-16 |

## Section 4: Other observations for the owner or DPO

1. Role conflict: the register labels AI customer support "Processor"; `ai-support-vendor.md` names Lumen as customer and HelpPilot as processor.
2. Possible duplicate: register lines 2 and 7 both cover the CRM, with different owner spelling, purposes, data lists and retention (7 vs 5 years). The policy says 5 years after last purchase.
3. Payroll register line 3 shows "Outside EU?" blank. The contract shows US tier 2 support with remote access to customer data. The SCCs are only "referenced"; the signed copy and any transfer assessment are not in the inputs.
4. AI support: inference runs in the United States through an unnamed LLM provider; SCCs referenced with no copy. The model-improvement clause reads "unless the customer opts out... Opt-out is off by default". I read this as: the use is active unless Lumen switches the opt-out on. The wording is ambiguous and should be checked in the admin settings. The anonymisation claim is the vendor's and is not evidenced in the inputs.
5. The retention policy (v2.1, approved 2023-05) expressly excludes applicant data, support chat transcripts and partner-shop returns data. These three activities therefore have no policy-backed erasure period.
6. Recruitment and Newsletter have no contract summary in the inputs, so processor status, hosting and transfers for TalentTrail and the "Mailer tool" are unevidenced. The register's "No" for Newsletter transfers cannot be checked.
7. The register's "Shared with" column omits every sub-processor named in the contracts (CloudHost Europe GmbH, MailRelay SE AB, NordCloud AB, SupportBridge Inc., LLM provider). Recipients in Section 1 include them from the contracts.
8. Contract terms differ: sub-processor change notice is 14 days (payroll) vs 30 days (CRM, AI); only the CRM contract states a right to object; audit rights are annual (CRM), on request (payroll), and a SOC 2 report in place of on-site audit (AI).
9. Register freshness: last-updated dates run from 2022-09 to 2025-01, so every line is at least about 21 months old. Dates by line: 2 and 3 = 2024-03; 4 = 2023-11; 5 = 2025-01; 6 = 2023-06; 7 = 2022-09; 8 = 2024-08.
10. Newsletter owner is "Marketing", a team rather than a person. The Returns portal has no owner.
11. The security fields in Section 1 contain vendor-side measures only. Article 30 asks for the controller's measures; Lumen's own are not in any input.
12. Not assessed (outside the inputs): lawful basis, DPIA need, and AI-specific transparency duties for the chat assistant. These were not in the product rules for this output and nothing here should be read as a view on them.
13. What remains unverified: everything. All values are "suggested" from a register that is out of date, and from vendor contract summaries rather than the signed contracts. The inputs are marked fictional demo data. No value has been confirmed by an owner. The Lumen entity for Recruitment, Newsletter and the Returns portal is assumed from the retention policy title.
