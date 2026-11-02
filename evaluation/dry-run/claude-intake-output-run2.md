# RoPA draft: Lumen Outdoor AB (Art. 30 GDPR)

Prepared 2026-11-02. All gap due dates: 2026-11-16 (14 days). Every filled value below is "suggested" (taken from a source, not confirmed by any owner). Nothing is confirmed. OPEN = no source supports it.

Source notation: `XLS rN` = excel-register.xlsx, sheet "Register", row N (row 1 is the header). `PDF item 'X'` = the table row labelled X in that PDF. Files: excel-register.xlsx, crm-vendor.pdf, payroll-provider.pdf, ai-support-vendor.pdf, retention-policy.pdf.

## Section 0. Import check

| File | Type | Read fully? | Not read / unsure |
|---|---|---|---|
| excel-register.xlsx | Excel workbook, 1 sheet "Register", range A1:K8 (header + 7 data rows, 11 columns) | Yes. Every non-empty cell read with openpyxl. | No merged cells, hidden rows/columns, comments or extra sheets found. Blank cells (treated as OPEN): B6 (System, Newsletter), C8 (Owner, Returns portal), G7 (Shared with, CRM duplicate), G8 (Shared with, Returns portal), H4 (Keep for, Recruitment), I3 (Outside EU?, Payroll), I4 (Outside EU?, Recruitment), I7 (Outside EU?, CRM duplicate). Placeholder values "TBD" (H5) and "?" (I5) treated as OPEN. Cell formatting/colours not inspected. The company name appears nowhere in the Excel; it is taken from the PDFs. |
| crm-vendor.pdf | PDF, 1 page, "data processing terms (summary)", one 2-column table | Yes. Text layer extracted with pdftotext. | A summary, not the signed contract. Page not visually rendered, so any non-text content (logos, stamps, images) was not checked. Marked "Fictional. For demo use only." |
| payroll-provider.pdf | PDF, 1 page, same layout | Yes (same method). | Same limits. The PDF itself says the signed SCC copy and transfer assessment are not attached. |
| ai-support-vendor.pdf | PDF, 1 page, same layout | Yes (same method). | Same limits. The PDF says no SCC copy is attached. Wording of "Opt-out is off by default" is ambiguous (see Section 4). |
| retention-policy.pdf | PDF, 1 page, excerpt, v2.1 approved 2023-05, one table | Yes (same method). | It is an excerpt only; other categories may exist in the full policy. Page not visually rendered. |

Not provided: the actual signed contracts, any contract for TalentTrail, the newsletter tool, or the returns portal.

## Section 1. Controller records (Art. 30(1))

Controller identity, common to all five records below: Lumen Outdoor AB (source: crm-vendor.pdf, payroll-provider.pdf, ai-support-vendor.pdf, PDF item 'Parties'; retention-policy.pdf title). Rows (a) below repeat it.

### C1. Customer management (ClientHub CRM)
Merges XLS r2 and XLS r7, which look like duplicates (see G3).

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB | crm-vendor.pdf, PDF item 'Parties' | suggested |
| (a) Controller contact details, joint controller, representative, DPO | OPEN | none | OPEN |
| (b) Purposes | Manage customer relationships and sales follow-up (r2); "Sales" (r7, thinner wording) | excel-register.xlsx r2 col D; r7 col D | suggested |
| (c) Data subjects | Customers and prospects | excel-register.xlsx r2 col E; crm-vendor.pdf, PDF item 'Data subjects' | suggested |
| (c) Personal data | Name, email, phone, purchase history (r2); contact details, company, purchase history, email correspondence (contract) | excel-register.xlsx r2 col F; crm-vendor.pdf, PDF item 'Personal data' | suggested |
| (d) Recipients | ClientHub AB (processor); sub-processors CloudHost Europe GmbH (infrastructure) and MailRelay SE AB (email delivery) | excel-register.xlsx r2 col G; crm-vendor.pdf, PDF items 'Parties', 'Sub-processors' | suggested |
| (e) Third-country transfers | None. Hosting EU only (Frankfurt, Dublin); support EU-based staff only. | crm-vendor.pdf, PDF items 'International transfers', 'Hosting', 'Support access'; excel-register.xlsx r2 col I = "No" | suggested |
| (f) Erasure time limits | Conflicting: 7 years (r2); 5 years (r7); policy: 5 years after last purchase for customer accounts and order history. Vendor deletes within 30 days after contract end. Prospects: OPEN. | excel-register.xlsx r2 col H, r7 col H; retention-policy.pdf, row 'Customer accounts and order history'; crm-vendor.pdf, PDF item 'Retention' | suggested (conflict unresolved); prospects OPEN |
| (g) Security measures | Vendor-side: encryption at rest and in transit, role-based access, annual penetration test, ISO 27001 certified. Lumen's own measures: OPEN. | crm-vendor.pdf, PDF item 'Security' | suggested (vendor only); own OPEN |
| Activity owner | Maja Lindqvist (r2); "Maja" (r7) | excel-register.xlsx r2 col C, r7 col C | suggested |

### C2. Payroll (PayLedger Nordic)

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB | payroll-provider.pdf, PDF item 'Parties' | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN |
| (b) Purposes | Pay salaries and report to authorities | excel-register.xlsx r3 col D; payroll-provider.pdf, PDF item 'Service' | suggested |
| (c) Data subjects | Employees | excel-register.xlsx r3 col E; payroll-provider.pdf, PDF item 'Data subjects' | suggested |
| (c) Personal data | Name, personal ID number, bank account, salary, absence; contract adds tax details | excel-register.xlsx r3 col F; payroll-provider.pdf, PDF item 'Personal data' | suggested |
| (d) Recipients | PayLedger Nordic AB (processor); Skatteverket; sub-processors NordCloud AB (hosting, Sweden) and SupportBridge Inc. (tier 2 support, United States) | excel-register.xlsx r3 col G; payroll-provider.pdf, PDF items 'Parties', 'Sub-processors' | suggested |
| (e) Third-country transfers | United States: remote access to customer data by SupportBridge Inc. when tier 2 support is escalated. Safeguard: Standard Contractual Clauses "referenced in the contract"; signed copy and transfer assessment not attached. Excel says nothing (I3 blank). | payroll-provider.pdf, PDF items 'Support access', 'International transfers'; excel-register.xlsx r3 col I (blank) | suggested; safeguard unverified |
| (f) Erasure time limits | 7 years after year-end (Excel, policy). Contract: contract term plus up to 7 years, or as instructed in writing. | excel-register.xlsx r3 col H; retention-policy.pdf, row 'Payroll and employment records'; payroll-provider.pdf, PDF item 'Retention' | suggested (two different triggers) |
| (g) Security measures | Vendor-side: encryption, multi-factor authentication for vendor staff, access logging. Lumen's own measures: OPEN. | payroll-provider.pdf, PDF item 'Security' | suggested (vendor only); own OPEN |
| Activity owner | Erik Holm | excel-register.xlsx r3 col C | suggested |

### C3. Recruitment (TalentTrail)

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB (company name from other files; no recruitment document names it) | retention-policy.pdf title; other PDFs 'Parties' | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN |
| (b) Purposes | "Hiring" | excel-register.xlsx r4 col D | suggested (very thin) |
| (c) Data subjects | Applicants | excel-register.xlsx r4 col E | suggested |
| (c) Personal data | CV, contact details, interview notes | excel-register.xlsx r4 col F | suggested |
| (d) Recipients | TalentTrail (no legal entity name, role or contract) | excel-register.xlsx r4 col G | suggested |
| (e) Third-country transfers | OPEN (Excel I4 blank; no contract) | none | OPEN |
| (f) Erasure time limits | OPEN (Excel H4 blank; policy states applicant data is not covered) | retention-policy.pdf footer note; excel-register.xlsx r4 col H (blank) | OPEN |
| (g) Security measures | OPEN | none | OPEN |
| Activity owner | Erik Holm | excel-register.xlsx r4 col C | suggested |

### C4. AI customer support (HelpPilot AI)
Excel labels this "Processor"; the contract makes Lumen the customer and HelpPilot the processor, so Lumen is controller here (see G16).

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB (customer) | ai-support-vendor.pdf, PDF item 'Parties' | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN |
| (b) Purposes | AI chat assistant answering customer questions on Lumen's website, with handover to human agents (Excel: "AI chat") | ai-support-vendor.pdf, PDF item 'Service'; excel-register.xlsx r5 col D | suggested |
| (c) Data subjects | Customers and website visitors (Excel: customers only) | ai-support-vendor.pdf, PDF item 'Data subjects'; excel-register.xlsx r5 col E | suggested |
| (c) Personal data | Chat transcripts; email address and order number if the customer provides them | ai-support-vendor.pdf, PDF item 'Personal data'; excel-register.xlsx r5 col F | suggested |
| (d) Recipients | HelpPilot AI Ltd (processor); sub-processors CloudHost Europe GmbH (EU) and an unnamed third-party LLM provider (United States) | ai-support-vendor.pdf, PDF items 'Parties', 'Sub-processors', 'AI model provider' | suggested |
| (e) Third-country transfers | United States: LLM provider, inference hosted there. Safeguard: contract "refers to" Standard Contractual Clauses; no copy attached. Application and transcripts hosted in Ireland (EU). Excel I5 = "?". | ai-support-vendor.pdf, PDF items 'International transfers', 'AI model provider', 'Hosting'; excel-register.xlsx r5 col I | suggested; safeguard unverified |
| (f) Erasure time limits | Vendor default 12 months, configurable by Lumen. Period Lumen actually set: OPEN. Excel "TBD". Policy does not cover chat transcripts. | ai-support-vendor.pdf, PDF item 'Retention'; excel-register.xlsx r5 col H; retention-policy.pdf footer note | suggested (vendor default only); actual OPEN |
| (g) Security measures | Vendor-side: encryption, access controls, SOC 2 Type II report available on request; EU-based support staff only. Lumen's own measures: OPEN. | ai-support-vendor.pdf, PDF items 'Security', 'Support access' | suggested (vendor only); own OPEN |
| Activity owner | Sofia Nyberg | excel-register.xlsx r5 col C | suggested |

### C5. Newsletter

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Controller name | Lumen Outdoor AB (from other files) | retention-policy.pdf title | suggested |
| (a) Contact details, joint controller, representative, DPO | OPEN | none | OPEN |
| (b) Purposes | Email marketing | excel-register.xlsx r6 col D | suggested |
| (c) Data subjects | Customers | excel-register.xlsx r6 col E | suggested |
| (c) Personal data | Email address | excel-register.xlsx r6 col F | suggested |
| (d) Recipients | "Mailer tool" (supplier not named) | excel-register.xlsx r6 col G | suggested (unidentified) |
| (e) Third-country transfers | Excel says "No"; tool not identified, so not verifiable | excel-register.xlsx r6 col I | suggested; unverified |
| (f) Erasure time limits | Until unsubscribe (Excel); policy: until unsubscribe or 24 months of no engagement | excel-register.xlsx r6 col H; retention-policy.pdf, row 'Marketing email addresses' | suggested |
| (g) Security measures | OPEN | none | OPEN |
| Activity owner | "Marketing" (a team, no named person) | excel-register.xlsx r6 col C | suggested |

## Section 2. Processor records (Art. 30(2))

Only one Excel row has Lumen acting as processor and is supported by the inputs. The three vendor PDFs describe Lumen's suppliers as processors for Lumen; their own Art. 30(2) records are theirs, not Lumen's.

### P1. Returns portal for partner shops (in-house portal)

| Art 30 field | Value or OPEN | Source | Status |
|---|---|---|---|
| (a) Processor name | Lumen Outdoor AB (company name from other files; no document on this activity names it) | retention-policy.pdf title | suggested |
| (a) Processor contact details, DPO | OPEN | none | OPEN |
| (a) Each controller (partner shop) and its DPO | OPEN. Excel only says "Partner shops"; no shop is named. | excel-register.xlsx r8 col D, E | OPEN |
| (b) Categories of processing per controller | Handle returns for partner shops; data: name, address, order number; data subjects: partner shops' customers. What Lumen actually does with the data (store, forward, refund) is not stated. | excel-register.xlsx r8 cols D, E, F | suggested (purpose only); processing steps OPEN |
| (c) Third-country transfers and safeguards | Excel says "No". Hosting and any subcontractors of the in-house portal not documented. | excel-register.xlsx r8 col I | suggested; unverified |
| (d) Security measures | OPEN | none | OPEN |
| Retention (not an Art 30(2) field, noted) | "Per partner contract"; contracts not provided; policy excludes partner-shop returns data | excel-register.xlsx r8 col H; retention-policy.pdf footer note | suggested |
| Activity owner | OPEN (Excel C8 blank) | none | OPEN |

## Section 3. Gaps

Due date for all: 2026-11-16. "Confirm" gaps ask the owner to check every "suggested" value in that record.

| id | activity | field | question | owner | due |
|---|---|---|---|---|---|
| G1 | All | Art 30(1)(a) / 30(2)(a) | What is Lumen's official address and the contact email/phone for privacy questions? Have you appointed a data protection officer (DPO)? If yes, who? Does anyone else decide together with you why and how data is used (a joint arrangement)? | unassigned, DPO | 2026-11-16 |
| G2 | C1 CRM | Confirm | Please read the CRM record above. Is each item correct and current? Mark anything wrong. (Excel last updated 2024-03 and 2022-09.) | Maja Lindqvist | 2026-11-16 |
| G3 | C1 CRM | Duplicate rows | The register lists ClientHub twice (rows 2 and 7: "Customer management" and "Customers - CRM"). Is this one activity or two different uses? Which entry is the current one? Is the "Maja" in row 7 you? | Maja Lindqvist | 2026-11-16 |
| G4 | C1 CRM | (f) Time limits | The register says 7 years and 5 years; the company policy says 5 years after the customer's last purchase. How long do you really keep customer records? And for prospects who never bought, how long are they kept? | Maja Lindqvist | 2026-11-16 |
| G5 | C1 CRM | (c)/(d) Data and recipients | The supplier's terms say the CRM also stores email correspondence, and uses two subcontractors (CloudHost Europe, MailRelay SE). Do you store customer emails in ClientHub? Does anyone else receive CRM data (for example an agency or accountant)? | Maja Lindqvist | 2026-11-16 |
| G6 | C1 CRM | (g) Security | Besides what ClientHub provides, what do you do yourselves to protect CRM data? For example: who has a login, is two-step login required, are leavers removed? | Maja Lindqvist | 2026-11-16 |
| G7 | C2 Payroll | Confirm | Please read the payroll record above. Is each item correct and current? Mark anything wrong. (Excel last updated 2024-03.) | Erik Holm | 2026-11-16 |
| G8 | C2 Payroll | (e) Transfers | PayLedger's contract says a US partner (SupportBridge Inc.) can see employee pay data when a support case is escalated, but your register says nothing about this. Were you aware? Please ask PayLedger for the signed copy of the data-transfer clauses (SCCs) and their transfer assessment. | Erik Holm | 2026-11-16 |
| G9 | C2 Payroll | (f) Time limits | The policy says 7 years after year-end; PayLedger's contract says the contract term plus up to 7 years, or as you instruct in writing. Which applies to you? Have you given PayLedger written instructions on deletion? | Erik Holm | 2026-11-16 |
| G10 | C2 Payroll | (d)/(c) Recipients and data | Besides PayLedger and Skatteverket, does payroll data go to anyone else (for example pension, insurance, union, accountant)? The contract also lists "tax details"; do you also hold other data, such as health-related sick-leave detail? | Erik Holm | 2026-11-16 |
| G11 | C2 Payroll | (g) Security | What do you do yourselves to protect payroll data? For example: who in Lumen can see salaries, how are files sent to PayLedger? | Erik Holm | 2026-11-16 |
| G12 | C3 Recruitment | Confirm | Please read the recruitment record above. Is each item correct and current? Mark anything wrong. (Excel last updated 2023-11.) | Erik Holm | 2026-11-16 |
| G13 | C3 Recruitment | (d)/(e) Supplier contract and transfers | Is there a signed agreement with TalentTrail about personal data? Please send it, and the supplier's full company name. Where is the data stored, and can anyone outside the EU access it? | Erik Holm | 2026-11-16 |
| G14 | C3 Recruitment | (f) Time limits | How long do you keep CVs and interview notes after a hiring decision, for people who were hired and not hired? Do you keep them for future roles, and do applicants know? (Your retention policy does not cover applicants.) | Erik Holm | 2026-11-16 |
| G15 | C3 Recruitment | (b)/(c) Purposes and data | "Hiring" is very short. Do you also collect things like photos, references, background checks, health or disability information? Who in Lumen sees applications, and does anyone outside Lumen (e.g. recruitment agency)? | Erik Holm | 2026-11-16 |
| G16 | C4 AI support | Role | The register says Lumen is a "processor" for the AI assistant, but HelpPilot's terms say HelpPilot works for Lumen. Is the assistant used only on Lumen's own website to answer Lumen's own customers? Does it also serve anyone else's customers? | Sofia Nyberg | 2026-11-16 |
| G17 | C4 AI support | Confirm | Please read the AI support record above. Is each item correct and current? Mark anything wrong. (Excel last updated 2025-01.) | Sofia Nyberg | 2026-11-16 |
| G18 | C4 AI support | (f) Time limits | The register says "TBD". HelpPilot keeps chats 12 months unless you change it. Has anyone changed this setting? How long do you want chats kept? | Sofia Nyberg | 2026-11-16 |
| G19 | C4 AI support | Model improvement | HelpPilot may use anonymised chats to improve its AI unless you switch this off in the admin settings. Is it switched on or off today? Did Lumen decide that? | Sofia Nyberg | 2026-11-16 |
| G20 | C4 AI support | (e) Transfers | Chats go to an AI provider in the United States. Please ask HelpPilot for that provider's name and the copy of the data-transfer clauses (SCCs) their contract refers to. | Sofia Nyberg | 2026-11-16 |
| G21 | C4 AI support | (c) Data subjects and data | Can people who are not customers use the chat? Do customers type sensitive things (health, children, ID numbers)? Are customers told they are chatting with an AI? Where do handed-over chats go (which helpdesk tool), and are they stored there too? | Sofia Nyberg | 2026-11-16 |
| G22 | C4 AI support | (g) Security | What do you do yourselves to protect chat data? For example: who at Lumen can read transcripts, and is that access reviewed? | Sofia Nyberg | 2026-11-16 |
| G23 | C5 Newsletter | Owner | Who is the named person responsible for newsletters? The register says only "Marketing". | unassigned, DPO | 2026-11-16 |
| G24 | C5 Newsletter | (d)/(e) Supplier and transfers | Which tool sends the newsletter, and which company supplies it? Is there a signed agreement? Where is the mailing list stored, and can anyone outside the EU see it? | unassigned, DPO | 2026-11-16 |
| G25 | C5 Newsletter | (f) Time limits | The register says "until unsubscribe". The policy also says remove after 24 months without engagement. Which do you really do? Is it done automatically? | unassigned, DPO | 2026-11-16 |
| G26 | C5 Newsletter | Confirm / (c) / (g) | Please read the newsletter record above. Is it correct? Besides email address, do you store name, signup date, or click data? What do you do to protect the list? (Excel last updated 2023-06.) | unassigned, DPO | 2026-11-16 |
| G27 | P1 Returns portal | (a) Controllers | Which partner shops do you handle returns for? Please list each shop's company name, contact person and privacy/DPO contact. | unassigned, DPO | 2026-11-16 |
| G28 | P1 Returns portal | Contract | Is there a signed agreement with each partner shop covering personal data? Please send them. What do they say about how long data is kept? | unassigned, DPO | 2026-11-16 |
| G29 | P1 Returns portal | (b) Processing | What exactly does the portal do with the partner shops' customer data (store, look up, send to carrier, refund)? Does it send data to anyone else, and is any subcontractor involved? | unassigned, DPO | 2026-11-16 |
| G30 | P1 Returns portal | (c)/(d) Transfers and security | Where is the portal hosted, and can anyone outside the EU access it? What protects it (logins, backups, who can see data)? | unassigned, DPO | 2026-11-16 |
| G31 | P1 Returns portal | Owner and confirm | Who owns the returns portal? The register has no owner. Once named, please confirm the record above is correct. (Excel last updated 2024-08.) | unassigned, DPO | 2026-11-16 |
| G32 | Not in register | Missing activities | The retention policy covers "website analytics data" (14 months) and "accounting documents" (7 years), which are not in the register. Do these activities exist, who owns them, and what tools and suppliers are involved? | unassigned, DPO | 2026-11-16 |

## Section 4. Other observations for the owner or DPO

1. **Role mismatch (C4).** Excel r5 says Processor; ai-support-vendor.pdf makes Lumen the customer and HelpPilot the processor. Drafted as controller pending G16.
2. **Undisclosed US access (C2).** Excel r3 leaves "Outside EU?" blank, while payroll-provider.pdf shows remote US access to payroll data by SupportBridge Inc. Excel also does not list NordCloud or SupportBridge among recipients.
3. **Transfer safeguards unverified (C2, C4).** Both contracts only "refer to" Standard Contractual Clauses; no signed copy or transfer assessment was provided. Whether the safeguard exists is unverified.
4. **Model-training default (C4).** The contract says "Opt-out is off by default". Read literally, the opt-out is not active, so HelpPilot may use anonymised transcripts to improve its models unless Lumen acts. The text is ambiguous and should be confirmed with the vendor (G19). Whether "anonymised" holds up is unverified.
5. **Conflicting retention (C1).** Excel r2 (7 years), Excel r7 (5 years) and the policy (5 years after last purchase) disagree. Payroll: policy and contract use different triggers (year-end versus contract end).
6. **Retention policy gaps.** Policy v2.1 (approved 2023-05) expressly excludes applicant data, chat transcripts and partner-shop returns data, so three activities have no Lumen-set retention rule.
7. **Stale register.** All "Last updated" values are 2022-09 to 2025-01; none is within the last 12 months. Duplicate rows (r2/r7) suggest the register is not maintained consistently.
8. **Sensitive data possible.** Payroll "absence" may reveal health information; "personal ID number" is a high-risk identifier. Neither is marked as such in Excel. Whether special-category data is processed is unverified (G10).
9. **Contracts are summaries only.** No signed contracts were provided, so sub-processor lists, audit rights, notice periods (CRM 30 days, payroll 14 days, AI 30 days) and security claims are as summarised, not checked against signed terms. Vendor security statements describe the vendors' measures, not Lumen's own.
10. **Same sub-processor in two systems.** CloudHost Europe GmbH appears for both ClientHub and HelpPilot; worth treating as one recipient in the register.
11. **Possible transparency and risk assessment follow-ups (not from the inputs).** An AI chat assistant with US inference and possible model-improvement use may call for a privacy-notice check and a DPIA screening; the DPO should decide. This is a suggestion from general knowledge, not an evidenced field value.
12. **Unverified overall.** Everything above is "suggested" from the five files. No owner has confirmed any value, the legal entity details are OPEN, and no external source was consulted.
