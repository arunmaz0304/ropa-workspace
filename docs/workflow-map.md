# Workflow map

Visual guide to the process. Diagrams render automatically on GitHub. Full detail is in [PROCESS.md](../PROCESS.md).

## 1. The seven steps, and the decision at the end

```mermaid
flowchart TD
    S0["0. Frame the decision"] --> S1["1. Fix scenario and requirements"]
    S1 --> S2["2. Intake and evidence"]
    S2 --> S3["3. Gap to action"]
    S3 --> S4["4. Validate and approve"]
    S4 --> S5["5. Maintain and handle change"]
    S5 --> S6{"6. Does any vendor pass all P0 checks?"}
    S6 -- Yes --> D1["Choose the vendor. Don't build."]
    S6 -- No --> D2["Build from product/workflow-spec.md"]
    D2 --> D3["Test the build against scenario.md"]
```

## 2. The two lanes and how they feed each other

```mermaid
flowchart LR
    subgraph EV["Evaluate lane"]
        E1["Lock scenario and weights"] --> E2["Run the 10 demo steps"]
        E2 --> E3["Send procurement questions"]
        E3 --> E4["Score vendors"]
    end
    subgraph BU["Build lane"]
        B1["Set P0, P1, P2 requirements"] --> B2["Design evidence and gap model"]
        B2 --> B3["Spec states and change triggers"]
        B3 --> B4["First build"]
    end
    B1 -. "P0 list becomes the must-have checks" .-> E2
    E4 -. "Vendor weaknesses shape the build" .-> B3
    E4 --> G{"Gap left after scoring?"}
    G -- No --> V["Pick a vendor"]
    G -- Yes --> B4
```

## 3. Evidence rule: a field is sourced or open

```mermaid
flowchart TD
    A["Existing documents: register, contracts, policy"] --> B["Extract candidate values"]
    B --> C{"Source found for the field?"}
    C -- Yes --> D["Suggested value, shown with its source"]
    C -- No --> E["Field stays empty"]
    D --> F{"Owner confirms?"}
    F -- Yes --> G["Owner-confirmed"]
    F -- No --> H["Gap: question assigned to the owner"]
    E --> H
    H --> I["Owner answers, with date"]
    I --> G
```

## 4. Record states

```mermaid
stateDiagram-v2
    [*] --> open
    open --> draft: required fields filled
    draft --> owner_confirmed: owner confirms
    owner_confirmed --> dpo_reviewed: DPO reviews
    dpo_reviewed --> approved: approver signs off
    owner_confirmed --> draft: changes requested
    dpo_reviewed --> draft: changes requested
    approved --> draft: material change opens a new draft
```

The approved version stays official, marked "change pending", until the new draft is approved and replaces it. Details and decisions are in [product/workflow-spec.md](../product/workflow-spec.md), sections 4 and 10.

## 5. Change handling

```mermaid
flowchart LR
    T["Trigger: new vendor, new purpose, retention change, new AI feature, contract update, owner change, review date"] --> R["Route to activity owner and DPO"]
    R --> M{"Does it change an Article 30 field?"}
    M -- No --> N["Log only"]
    M -- Yes --> Q["New working draft. Approved version stays official until replaced. DPO is told"]
    Q --> V["One owner task per record. Owner revalidates. DPO review task opens when the owner confirms. Approver signs off"]
```

## Which file belongs to which step

| Step | Evaluate lane | Build lane |
|---|---|---|
| 0 Frame | `scenario.md` (framing block) | `scenario.md` (framing block) |
| 1 Scenario and requirements | `scenario.md`, `evaluation/weights.csv` | `product/mvp-requirements.md` |
| 2 Intake and evidence | `evaluation/demo-script.md` steps 1-2, `demo-data/` | `product/workflow-spec.md` sections 1-2 |
| 3 Gap to action | `evaluation/demo-script.md` step 3 | `product/workflow-spec.md` section 3 |
| 4 Validate and approve | `evaluation/demo-script.md` steps 4, 5, 7 | `product/workflow-spec.md` section 4, `product/ropa-record-template.md` |
| 5 Maintain and change | `evaluation/demo-script.md` step 6 | `product/workflow-spec.md` section 5 |
| 6 Decide or ship | `evaluation/procurement-questions.md`, `evaluation/scorecard.xlsx` (scores, P0 gate) | `product/workflow-spec.md` sections 7-9 |
