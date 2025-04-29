# AI Fairness Audit Framework: Core Guide

**(Modified from Version 1's `guide.md` to serve as the central entry point)**

Welcome! This guide explains how to understand and implement the Fairness Audit Framework to assess your AI system. It provides an overview of the core components and directs you to more detailed resources within the framework.

## 1. Framework Overview: The Four Key Parts

Think of a fairness audit like building a case. You need evidence and reasoning. This framework breaks it down into four main parts, typically performed in sequence:

1.  **Understand the Past (Historical Context Assessment - HCA)**
    *   **Goal:** Find out about real-world discrimination related to what your AI does (e.g., bias in past hiring for a hiring AI).
    *   **Why:** History often repeats in data and algorithms. Knowing the past helps spot risks.
    *   **Output Template:** [`templates/historical-context-report.md`](../templates/historical-context-report.md)
    *   **Detailed Guidance:** See domain-specific examples in [`resources/domain-adaptation-guide.md`](../resources/domain-adaptation-guide.md).

2.  **Define "Fairness" (Fairness Definition Selection - FDS)**
    *   **Goal:** Decide exactly what "fair" means for *your* AI in *this* situation. There are many ways to define fairness (like ensuring equal opportunity vs. equal outcomes), and they often conflict.
    *   **Why:** You can't measure fairness without defining it first. Your choice depends on the context (from HCA), ethics, rules, and stakeholder input.
    *   **Output Template:** [`templates/fairness-definition-rationale.md`](../templates/fairness-definition-rationale.md)
    *   **Detailed Guidance:** Consult definition comparisons and selection strategies. Consider input from stakeholder engagement (see [`resources/stakeholder-co-design.md`](../resources/stakeholder-co-design.md)).

3.  **Find Potential Problems (Bias Source Identification - BSI)**
    *   **Goal:** Look through how your AI was built and how it's used to find *where* bias could get in. This includes the data, the features, the model itself, and how people use it.
    *   **Why:** Knowing *where* bias might come from helps you focus your testing and fixes. Your chosen fairness definition (from FDS) helps you know what *kind* of bias sources are most important to look for.
    *   **Output Template:** [`templates/bias-source-mapping.md`](../templates/bias-source-mapping.md)
    *   **Detailed Guidance:** Analyze the full ML lifecycle. Consider technical and socio-technical sources. For deeper analysis, see [`resources/causal-fairness.md`](../resources/causal-fairness.md).

4.  **Measure the Results (Metrics Implementation & Analysis - MIA)**
    *   **Goal:** Use data to check if the AI meets the fairness definitions you chose, paying attention to the bias sources you identified.
    *   **Why:** This gives you evidence about whether the AI is actually fair according to your chosen standard. It involves looking at different groups, including combinations (intersectionality).
    *   **Output Templates:** [`templates/metrics-implementation.md`](../templates/metrics-implementation.md), [`templates/intersectional-analysis.md`](../templates/intersectional-analysis.md)
    *   **Detailed Guidance:** Select metrics aligned with definitions and bias sources. Use statistical validation. For advanced techniques, see [`resources/intersectional-methodologies.md`](../resources/intersectional-methodologies.md).

## 2. How the Parts Connect (Integration)

These four parts aren't isolated; they build on each other in a logical flow:

*   The **History** (HCA) helps you choose relevant **Definitions** (FDS).
*   The **Definitions** (FDS) help you prioritize which **Bias Sources** (BSI) matter most.
*   The **Bias Sources** (BSI) and **Definitions** (FDS) tell you which **Metrics** (MIA) to use.
*   The **Metrics** (MIA) provide evidence, which you interpret by looking back at the **Sources** (BSI) and **History** (HCA).

This connection is key! It makes the audit logical and links technical measurements back to real-world context.
*   **Detailed Integration:** For technical details on how components connect, including data formats and orchestration, see [`framework/integration-methodology.md`](integration-methodology.md) and [`resources/component-interfaces.md`](../resources/component-interfaces.md).

## 3. Planning Your Audit

Before diving in, make a plan using [`templates/assessment-plan.md`](../templates/assessment-plan.md):

*   What system are you auditing?
*   Why are you auditing? (e.g., pre-launch, compliance, problem investigation)
*   What are the main fairness concerns or risks initially?
*   Who needs to be involved? (Stakeholders - see Section 8 below and [`resources/stakeholder-co-design.md`](../resources/stakeholder-co-design.md))
*   What resources (time, data, people) do you have?
*   Which workflow will you use? (See Section 4)
*   Are there specific rules or laws to follow? (See Section 8 and [`resources/regulatory-compliance-guide.md`](../resources/regulatory-compliance-guide.md))

**Detailed Implementation Steps:** Consult the [`framework/implementation-guide.md`](implementation-guide.md) for a step-by-step walkthrough.

## 4. Choosing and Using Workflows

We offer different processes depending on your needs. Choose one from `framework/workflows/` and follow its steps:

*   **[`rapid-assessment.md`](workflows/rapid-assessment.md)**: Best for initial checks, low-risk systems, or when time is short. Covers basics quickly.
*   **[`comprehensive-assessment.md`](workflows/comprehensive-assessment.md)**: Best for high-stakes systems or when a deep dive is needed. Thorough work on all components.
*   **[`regulatory-compliance.md`](workflows/regulatory-compliance.md)**: Use if you need specific documents for legal or regulatory compliance. See also [`resources/regulatory-compliance-guide.md`](../resources/regulatory-compliance-guide.md).
*   **[`continuous-monitoring.md`](workflows/continuous-monitoring.md)**: Use *after* an initial assessment for deployed systems. Focuses on tracking fairness over time.

Each workflow file lists specific steps, inputs, and output templates.

## 5. Core Implementation Steps (General Summary)

Your chosen workflow will guide you, but generally involves:

1.  **Plan**: Complete [`assessment-plan.md`](../templates/assessment-plan.md).
2.  **Assess Historical Context**: Research and document in [`historical-context-report.md`](../templates/historical-context-report.md).
3.  **Select Fairness Definitions**: Analyze options, justify choices in [`fairness-definition-rationale.md`](../templates/fairness-definition-rationale.md).
4.  **Identify Bias Sources**: Analyze lifecycle, assess risks, document in [`bias-source-mapping.md`](../templates/bias-source-mapping.md).
5.  **Implement Metrics & Analyze**: Calculate metrics, perform disaggregated/intersectional analysis, document in [`metrics-implementation.md`](../templates/metrics-implementation.md) and [`intersectional-analysis.md`](../templates/intersectional-analysis.md).
6.  **Synthesize & Report**: Analyze connections, document limitations ([`limitations-acknowledgment.md`](../templates/limitations-acknowledgment.md)), record stakeholder input ([`stakeholder-documentation.md`](../templates/stakeholder-documentation.md)), summarize ([`executive-summary.md`](../templates/executive-summary.md)).

**Detailed Implementation:** Refer to [`framework/implementation-guide.md`](implementation-guide.md).

## 6. Essential Documentation: Using Templates

Consistent documentation using the [`templates/`](../templates/) directory is crucial. Key templates are listed in the steps above. Fill these out as you complete each step of your chosen workflow.

## 7. Evaluating Your Audit (Assessment Quality)

How do you know if your fairness audit was good? Use the criteria defined in [`framework/evaluation-criteria.md`](evaluation-criteria.md), covering:

*   **Functional Assessment:** Was the process followed correctly?
*   **Fairness Effectiveness:** Were relevant issues identified and addressed?
*   **Usability:** Was the framework practical?
*   **Limitations Assessment:** Were boundaries acknowledged?

Use peer review, checklists, or stakeholder feedback based on these criteria.

## 8. Advanced Topics & Adaptation

*   **Domain/Regulatory Adaptation**: Fairness issues vary by context. See [`resources/domain-adaptation-guide.md`](../resources/domain-adaptation-guide.md) and [`resources/regulatory-compliance-guide.md`](../resources/regulatory-compliance-guide.md) for tailoring the framework.
*   **Stakeholder Engagement**: Involving affected communities is vital. See [`resources/stakeholder-co-design.md`](../resources/stakeholder-co-design.md) for methods.
*   **Intersectionality**: Fairness often differs at the intersection of identities (e.g., race and gender). Basic analysis is covered in MIA, but for advanced methods see [`resources/intersectional-methodologies.md`](../resources/intersectional-methodologies.md).
*   **Causal Fairness**: To understand root causes beyond correlations, see [`resources/causal-fairness.md`](../resources/causal-fairness.md).

## 9. Tracking Changes (Versioning)

AI systems and fairness understanding evolve. It's essential to track assessment versions.
*   **Protocol:** Follow the detailed protocol in [`framework/versioning-protocol.md`](versioning-protocol.md).
*   **Examples:** See practical examples in [`resources/versioning-examples.md`](../resources/versioning-examples.md).

## 10. Conclusion

This framework provides a structured, integrated, and documented approach to AI fairness assessment. By following the component flow, selecting an appropriate workflow, using the templates, consulting detailed guides, and considering context, practitioners can move towards more systematic and accountable fairness evaluations. Remember to start with the plan, choose the right workflow, and document your steps clearly using the provided resources.