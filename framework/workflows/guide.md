# AI Fairness Audit Framework: Core Guide

Welcome! This guide explains how to use the Fairness Audit Framework to assess your AI system.

## 1. Understanding the Framework: Four Key Parts

Think of a fairness audit like building a case. You need evidence and reasoning. This framework breaks it down into four main parts, done in order:

1.  **Understand the Past (Historical Context Assessment - HCA)**
    *   **Goal:** Find out about real-world discrimination related to what your AI does (e.g., bias in past hiring for a hiring AI).
    *   **Why:** History often repeats in data and algorithms. Knowing the past helps spot risks.
    *   **Output:** You'll document findings in the `templates/historical-context-report.md`.

2.  **Define "Fairness" (Fairness Definition Selection - FDS)**
    *   **Goal:** Decide exactly what "fair" means for *your* AI in *this* situation. There are many ways to define fairness (like ensuring equal opportunity vs. equal outcomes), and they often conflict.
    *   **Why:** You can't measure fairness without defining it first. Your choice depends on the context (from HCA), ethics, rules, and what stakeholders value.
    *   **Output:** Justify your chosen definition(s) in `templates/fairness-definition-rationale.md`.

3.  **Find Potential Problems (Bias Source Identification - BSI)**
    *   **Goal:** Look through how your AI was built and how it's used to find *where* bias could get in. This includes the data, the features, the model itself, and how people use it.
    *   **Why:** Knowing *where* bias might come from helps you focus your testing and fixes. Your chosen fairness definition (from FDS) helps you know what *kind* of bias sources are most important to look for.
    *   **Output:** Map out potential issues in `templates/bias-source-mapping.md`.

4.  **Measure the Results (Metrics Implementation & Analysis - MIA)**
    *   **Goal:** Use data to check if the AI meets the fairness definitions you chose, paying attention to the bias sources you identified.
    *   **Why:** This gives you evidence about whether the AI is actually fair according to your chosen standard. It involves looking at different groups, including combinations (like older women vs. younger men - see `resources/stakeholder-intersectionality.md`).
    *   **Output:** Document your measurements and analysis in `templates/metrics-implementation.md` and `templates/intersectional-analysis.md`.

## 2. How the Parts Connect (Integration)

These four parts aren't isolated; they build on each other:

*   The **History** (HCA) helps you choose relevant **Definitions** (FDS).
*   The **Definitions** (FDS) help you prioritize which **Bias Sources** (BSI) matter most.
*   The **Bias Sources** (BSI) and **Definitions** (FDS) tell you which **Metrics** (MIA) to use.
*   The **Metrics** (MIA) provide evidence, which you interpret by looking back at the **Sources** (BSI) and **History** (HCA).

This connection is key! It makes the audit logical and links technical measurements back to real-world context. Using the `templates/` consistently helps document these connections. For more detail on how they link technically, see `framework/integration.md`.

## 3. Planning Your Audit

Before diving in, make a plan using `templates/assessment-plan.md`:

*   **What system are you auditing?** Be specific.
*   **Why are you auditing?** (e.g., pre-launch check, regulatory need, investigate a problem).
*   **What are the main fairness concerns or risks?** (Initial thoughts).
*   **Who needs to be involved?** (Team members, stakeholders - see `resources/stakeholder-intersectionality.md`).
*   **What resources (time, data, people) do you have?**
*   **Which workflow will you use?** (See next section).
*   **Are there specific rules or laws to follow?** (See `resources/adaptation-compliance.md`).

## 4. Choosing a Workflow

We offer different processes depending on your needs. Choose one from `framework/workflows/` and follow its steps:

*   **[Rapid Workflow (`workflows/rapid.md`)]**: Best for initial checks, low-risk systems, or when time is short. It covers the basics quickly.
*   **[Comprehensive Workflow (`workflows/comprehensive.md`)]**: Best for high-stakes systems or when a deep dive is needed. It involves thorough work on all four components.
*   **[Regulatory Workflow (`workflows/regulatory.md`)]**: Use this if you need to produce specific documents for legal or regulatory compliance (like for the EU AI Act or fair lending laws). See `resources/adaptation-compliance.md`.
*   **[Monitoring Workflow (`workflows/monitoring.md`)]**: Use this *after* an initial assessment for systems already in use. It focuses on tracking fairness over time and catching problems.

**Each workflow file lists specific steps, telling you what information you need (inputs) and which template to fill out (outputs) for each step.**

## 5. Using the Documentation Templates

The `templates/` folder contains standard documents for recording your findings at each stage. **Using these templates consistently is crucial for creating a clear, traceable audit.**

Key templates include:
*   `assessment-plan.md`
*   `historical-context-report.md`
*   `fairness-definition-rationale.md`
*   `bias-source-mapping.md`
*   `metrics-implementation.md`
*   `intersectional-analysis.md` (Important for understanding combined effects)
*   `stakeholder-documentation.md` (Tracks who you talked to and their input)
*   `limitations-acknowledgment.md` (Crucial for honesty about what the audit *couldn't* cover)
*   `executive-summary.md` (For communicating key findings)
*   `model-card.md` (A standard way to summarize AI model details, including fairness)
*   `monitoring-report.md` (Used by the monitoring workflow)

Fill these out as you complete each step of your chosen workflow.

## 6. Evaluating Your Audit

How do you know if your fairness audit was good? Check for:

*   **Completeness:** Did you follow the workflow and fill out the required templates?
*   **Cohesion:** Does the story make sense? Does the history link to the definitions, the sources, and the measurements?
*   **Rigor:** Is your analysis sound? Is evidence provided? Are statistics used correctly?
*   **Context:** Is it relevant to the specific AI system and its real-world use? Did you consider the right stakeholders and domain issues? (See `resources/` guides).
*   **Honesty:** Did you clearly state the limitations of your audit? (See `templates/limitations-acknowledgment.md`).
*   **Actionability:** Does the audit provide clear recommendations for what to do next?

Use peer review or checklists based on these points.

## 7. Tracking Changes (Versioning)

AI systems and our understanding of fairness change over time. It's important to track different versions of your audits.

*   **Assessment ID**: Give each *initial* audit a unique ID, maybe like `FAF-[SystemName]-[Date]`, e.g., `FAF-HiringAI-20241027`.
*   **Version Number**: Use `1.0` for the first audit. Use `1.1`, `1.2` for minor updates or corrections. Use `2.0` if you do a major reassessment later (e.g., after big changes to the AI).
*   **Record Keeping**:
    *   Put the Assessment ID and Version number on every template document you create for that audit.
    *   Keep a simple change log (maybe in your `assessment-plan.md` or `executive-summary.md`) explaining what changed between versions (e.g., "v1.1: Added intersectional analysis for race/gender").

## 8. Adapting the Framework

This framework is a starting point. You'll likely need to adapt it:

*   **For Your Industry/Domain:** Fairness issues look different in hiring vs. healthcare vs. finance. See `resources/adaptation-compliance.md` for guidance.
*   **For Regulations:** If you need to meet specific laws (like EU AI Act, ADA, ECOA), use the Regulatory Workflow and see `resources/adaptation-compliance.md`.
*   **For Complex Social Issues:** Engaging stakeholders and analyzing intersectionality require care. See `resources/stakeholder-intersectionality.md`.

## 9. Conclusion

By following a structured workflow, using standard templates, and connecting the different parts of the assessment, this framework helps make AI fairness auditing more systematic, understandable, and accountable. Remember to start with the plan, choose the right workflow, and document your steps clearly.