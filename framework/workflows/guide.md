# AI Fairness Audit Framework: Core Guide

Welcome! This guide explains how to understand and implement the Fairness Audit Framework to assess your AI system.

## 1. Framework Overview: The Four Key Parts

Think of a fairness audit like building a case. You need evidence and reasoning. This framework breaks it down into four main parts, done in order:

1.  **Understand the Past (Historical Context Assessment - HCA)**
    *   **Goal:** Find out about real-world discrimination related to what your AI does (e.g., bias in past hiring for a hiring AI).
    *   **Why:** History often repeats in data and algorithms. Knowing the past helps spot risks.
    *   **Output Template:** [historical-context-report.md](../../templates/historical-context-report.md)

2.  **Define "Fairness" (Fairness Definition Selection - FDS)**
    *   **Goal:** Decide exactly what "fair" means for *your* AI in *this* situation. There are many ways to define fairness (like ensuring equal opportunity vs. equal outcomes), and they often conflict.
    *   **Why:** You can't measure fairness without defining it first. Your choice depends on the context (from HCA), ethics, rules, and what stakeholders value.
    *   **Output Template:** [fairness-definition-rationale.md](../../templates/fairness-definition-rationale.md)

3.  **Find Potential Problems (Bias Source Identification - BSI)**
    *   **Goal:** Look through how your AI was built and how it's used to find *where* bias could get in. This includes the data, the features, the model itself, and how people use it.
    *   **Why:** Knowing *where* bias might come from helps you focus your testing and fixes. Your chosen fairness definition (from FDS) helps you know what *kind* of bias sources are most important to look for.
    *   **Output Template:** [bias-source-mapping.md](../../templates/bias-source-mapping.md)

4.  **Measure the Results (Metrics Implementation & Analysis - MIA)**
    *   **Goal:** Use data to check if the AI meets the fairness definitions you chose, paying attention to the bias sources you identified.
    *   **Why:** This gives you evidence about whether the AI is actually fair according to your chosen standard. It involves looking at different groups, including combinations (like older women vs. younger men - see [stakeholder-intersectionality.md](../../resources/stakeholder-intersectionality.md)).
    *   **Output Templates:** [metrics-implementation.md](../../templates/metrics-implementation.md), [intersectional-analysis.md](../../templates/intersectional-analysis.md)

## 2. How the Parts Connect (Integration)

These four parts aren't isolated; they build on each other:

*   The **History** (HCA) helps you choose relevant **Definitions** (FDS).
*   The **Definitions** (FDS) help you prioritize which **Bias Sources** (BSI) matter most.
*   The **Bias Sources** (BSI) and **Definitions** (FDS) tell you which **Metrics** (MIA) to use.
*   The **Metrics** (MIA) provide evidence, which you interpret by looking back at the **Sources** (BSI) and **History** (HCA).

This connection is key! It makes the audit logical and links technical measurements back to real-world context. Using the [templates/](../../templates/) consistently helps document these connections. For more detail on how they link technically, see [integration.md](../integration.md).

## 3. Planning Your Audit

Before diving in, make a plan using [assessment-plan.md](../../templates/assessment-plan.md):

*   **What system are you auditing?** Be specific.
*   **Why are you auditing?** (e.g., pre-launch check, regulatory need, investigate a problem).
*   **What are the main fairness concerns or risks?** (Initial thoughts).
*   **Who needs to be involved?** (Team members, stakeholders - see [stakeholder-intersectionality.md](../../resources/stakeholder-intersectionality.md)).
*   **What resources (time, data, people) do you have?**
*   **Which workflow will you use?** (See next section).
*   **Are there specific rules or laws to follow?** (See [adaptation-compliance.md](../../resources/adaptation-compliance.md)).

## 4. Choosing and Using Workflows

We offer different processes depending on your needs. Choose one from [workflows/](.) and follow its steps:

*   **[Rapid Workflow](rapid.md)**: Best for initial checks, low-risk systems, or when time is short. It covers the basics quickly.
*   **[Comprehensive Workflow](comprehensive.md)**: Best for high-stakes systems or when a deep dive is needed. It involves thorough work on all four components.
*   **[Regulatory Workflow](regulatory.md)**: Use this if you need to produce specific documents for legal or regulatory compliance (like for the EU AI Act or fair lending laws). See [adaptation-compliance.md](../../resources/adaptation-compliance.md).
*   **[Monitoring Workflow](monitoring.md)**: Use this *after* an initial assessment for systems already in use. It focuses on tracking fairness over time and catching problems.

**Each workflow file lists specific steps, telling you what information you need (inputs) and which template to fill out (outputs) for each step.**

## 5. Core Implementation Steps (General)

Refer to your chosen workflow file for specifics, but generally, you will:

1.  **Plan**: Complete [assessment-plan.md](../../templates/assessment-plan.md).
2.  **Assess Historical Context**: Research and document findings in [historical-context-report.md](../../templates/historical-context-report.md).
3.  **Select Fairness Definitions**: Analyze options, justify choices in [fairness-definition-rationale.md](../../templates/fairness-definition-rationale.md).
4.  **Identify Bias Sources**: Analyze the lifecycle, assess risks, document in [bias-source-mapping.md](../../templates/bias-source-mapping.md).
5.  **Implement Metrics & Analyze**: Calculate metrics, perform disaggregated/intersectional analysis, document in [metrics-implementation.md](../../templates/metrics-implementation.md) and [intersectional-analysis.md](../../templates/intersectional-analysis.md).
6.  **Synthesize & Report**: Analyze connections across components, document limitations ([limitations-acknowledgment.md](../../templates/limitations-acknowledgment.md)), record stakeholder input ([stakeholder-documentation.md](../../templates/stakeholder-documentation.md)), and summarize findings ([executive-summary.md](../../templates/executive-summary.md), potentially [model-card.md](../../templates/model-card.md)).

## 6. Essential Documentation: Using Templates

Consistent documentation is key. Use the provided Markdown templates in the [templates/](../../templates/) directory for the outputs of each step defined in your chosen workflow. Key templates include:

*   [assessment-plan.md](../../templates/assessment-plan.md)
*   [historical-context-report.md](../../templates/historical-context-report.md)
*   [fairness-definition-rationale.md](../../templates/fairness-definition-rationale.md)
*   [bias-source-mapping.md](../../templates/bias-source-mapping.md)
*   [metrics-implementation.md](../../templates/metrics-implementation.md)
*   [intersectional-analysis.md](../../templates/intersectional-analysis.md) (Important for understanding combined effects)
*   [stakeholder-documentation.md](../../templates/stakeholder-documentation.md) (Tracks who you talked to and their input)
*   [limitations-acknowledgment.md](../../templates/limitations-acknowledgment.md) (Crucial for honesty about what the audit *couldn't* cover)
*   [executive-summary.md](../../templates/executive-summary.md) (For communicating key findings)
*   [model-card.md](../../templates/model-card.md) (A standard way to summarize AI model details, including fairness)
*   [monitoring-report.md](../../templates/monitoring-report.md) (Used by the monitoring workflow)

Fill these out as you complete each step of your chosen workflow.

## 7. Evaluating Your Audit (Assessment Quality)

How do you know if your fairness audit was good? Check these aspects:

*   **Completeness & Cohesion (Functionality):**
    *   Was the chosen workflow followed? Are all required templates completed?
    *   Is the information flow logical? Does the HCA inform FDS, FDS inform BSI, BSI inform MIA, and do the MIA results connect back?
    *   Is the documentation clear, consistent, and traceable?
*   **Fairness Effectiveness:**
    *   Does the audit identify relevant fairness issues for the specific context?
    *   Does it cover multiple dimensions (history, definitions, sources, metrics)?
    *   Does it analyze intersectionality appropriately? (See [stakeholder-intersectionality.md](../../resources/stakeholder-intersectionality.md))
    *   Does it attempt to link disparities to potential root causes (bias sources, historical context)?
    *   Are the recommendations clear, specific, and actionable?
*   **Usability & Process:**
    *   Is the assessment understandable to its audience?
    *   Was stakeholder input appropriately gathered and integrated? (See [stakeholder-documentation.md](../../templates/stakeholder-documentation.md))
    *   Was the process efficient for the chosen scope?
*   **Honesty (Limitations):**
    *   Are the limitations (data, scope, methods) clearly documented? (See [limitations-acknowledgment.md](../../templates/limitations-acknowledgment.md))
    *   Is the confidence in findings appropriately stated?

Use peer review, checklists based on these points, or stakeholder feedback to evaluate the assessment quality.

## 8. Tracking Changes (Versioning)

AI systems and fairness understanding evolve. Track audit versions:

*   **Assessment ID**: Use a unique ID `FAF-[SystemName]-[YYYYMMDD]` (e.g., `FAF-HiringAI-20241027`).
*   **Version Number**: Use `MAJOR.MINOR` (e.g., `1.0`, `1.1`, `2.0`).
    *   `MINOR` (+0.1): For corrections, minor updates (like adding intersectional analysis later), or integrating minor framework methodology updates.
    *   `MAJOR` (+1.0): For substantial reassessments triggered by significant system changes (new algorithm, data overhaul) or major framework overhauls.
*   **Documentation**:
    *   Include `Assessment ID` and `Version` on all templates.
    *   Maintain a change log (e.g., in [assessment-plan.md](../../templates/assessment-plan.md) or [executive-summary.md](../../templates/executive-summary.md)) detailing changes between versions, the author, date, reason, and impact.
    *   Note the overall *Framework Version* (if the framework itself is versioned) that the assessment was based on in the [assessment-plan.md](../../templates/assessment-plan.md).

**Example Change Log Entry:**
```markdown
### Version 1.1 (2024-11-15) - Author: J. Doe
*   **Change:** Added intersectional analysis for Gender x Race.
*   **Reason:** Stakeholder feedback highlighted this as a key concern.
*   **Impact:** Found higher disparity for women of color; added Recommendation #5.
```

## 9. Adapting the Framework and Advanced Topics

*   **Domain/Regulatory Adaptation**: See [adaptation-compliance.md](../../resources/adaptation-compliance.md). Tailor the focus based on industry (hiring, finance, health) and legal requirements (EU AI Act, EEOC, etc.).
*   **Stakeholder Engagement & Intersectionality**: See [stakeholder-intersectionality.md](../../resources/stakeholder-intersectionality.md) for methods on involving people effectively and analyzing overlapping identities.
*   **(Optional) Causal Fairness**: For deeper root cause analysis, see [causal-fairness.md](../../resources/causal-fairness.md).

## 10. Conclusion

This framework provides a structured, integrated, and documented approach to AI fairness assessment. By following the component flow, selecting an appropriate workflow, using the templates, and considering context, practitioners can move towards more systematic and accountable fairness evaluations. Remember to start with the plan, choose the right workflow, and document your steps clearly.