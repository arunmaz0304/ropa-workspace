# Process

Seven steps. Each has two lanes.

- **Evaluate**: choosing a RoPA tool.
- **Build**: making the product.

You can run one lane or both. Where they share a step, the output of one feeds the other.

Rule that runs through every step: a field is either sourced or open. Never guessed.

---

## Step 0. Frame the decision

**Evaluate.** Who is choosing, what are they replacing, and what is the deadline? Write it in two sentences.

**Build.** Who is the user: SME owner, internal privacy lead, external DPO serving several clients? Pick one primary. The adviser workspace (P1) only matters if the answer is external DPO.

**Output.** Top of `scenario.md` filled in.

**Done when.** You can say in one sentence what decision this process will support.

---

## Step 1. Fix the scenario and the requirements

**Evaluate.** Lock the demo scenario in `scenario.md`. Every vendor gets the same one. Set the weights in `evaluation/weights.csv` with the client. Write down why any weight changed.

**Build.** Review `product/mvp-requirements.md`. Move features between P0, P1, P2 only with a reason. Keep P0 small enough to build and test.

**Output.** `scenario.md`, `weights.csv`, `mvp-requirements.md` agreed.

**Done when.** Someone else could run the demo or start building from these files without asking you anything.

---

## Step 2. Intake and evidence

What happens: existing documents (Excel register, supplier contracts, retention policy) go in, candidate values come out with their source, unsupported fields stay empty.

**Evaluate.** Run demo steps 1 and 2 in `evaluation/demo-script.md`. Note what the tool imports, what it invents, and whether each value shows its source.

**Build.** Design the intake: business-language questions per activity, the evidence model (value + source reference + confidence note), and the rule that unsupported means blank. See `product/workflow-spec.md`, sections 1 and 2.

**Output.** Scored demo steps 1-2. Evidence model confirmed.

**Done when.** For every field you can answer: where did this value come from?

---

## Step 3. Gap to action

What happens: every open field becomes a question with an owner and a due date. No red score without an assigned task.

**Evaluate.** Demo step 3. Does the tool create assignable tasks, or just a compliance percentage?

**Build.** Gap object and assignment rules: `workflow-spec.md`, section 3.

**Output.** Scored demo step 3. Gap rules confirmed.

**Done when.** A missing field produces a named person with a question to answer.

---

## Step 4. Validate and approve

What happens: four separate states (draft, owner-confirmed, DPO-reviewed, approved). Controller and processor records come out separately.

**Evaluate.** Demo steps 4 and 5. Can a non-lawyer confirm an activity? Are controller and processor outputs actually different structures? Is there version history?

**Build.** State machine and role permissions: `workflow-spec.md`, section 4. Record structure: `product/ropa-record-template.md`.

**Output.** Scored demo steps 4-5. Record template confirmed.

**Done when.** You can show who confirmed what, when, and which version was approved.

---

## Step 5. Maintain and handle change

This is where the choice should be decided. Discovery gets you a first draft. Maintenance keeps it true.

**Evaluate.** Demo step 6. Add a new vendor, change a retention period, switch on a new AI feature. Does the tool route it to the right owner and force revalidation?

**Build.** Change triggers and revalidation rules: `workflow-spec.md`, section 5.

**Output.** Scored demo step 6. Trigger table confirmed.

**Done when.** A change in the business produces a review task, not silence.

---

## Step 6. Decide or ship

**Evaluate.**
1. Send `evaluation/procurement-questions.md` to shortlisted vendors, in writing.
2. Complete `evaluation/scorecard.csv`.
3. Recommend, with the maintenance score front and centre. Don't infer hosting or support access from a vendor's headquarters or marketing.

**Build.**
1. Check the Evaluate results: did any vendor pass all P0 checks? If yes, the gap may not exist. Say so.
2. If a gap remains, turn `workflow-spec.md` into a first build (Lovable for the interface, Claude API for evidence extraction, n8n for routing).
3. Test the first build against `scenario.md`.

**Output.** A vendor recommendation, a build decision, or both.

**Done when.** The decision and the reasons are written down and the client or you can defend them.

---

## Working rules

- Same scenario for every vendor and for the build.
- Weights are a starting proposal. Clients adjust them.
- Procurement answers come in writing.
- Update this repo when something changes. Version history is part of the product.
