# AI Fairness Audit Framework: Overview and Navigation

Welcome! This guide explains how to understand and implement the Fairness Audit Framework to assess your AI system. It provides an overview of the core components and directs you to more detailed resources within the framework.

## 1. Framework Overview: The Four Key Parts

Think of a fairness audit like building a case. You need evidence and reasoning. This framework breaks it down into four main parts, typically performed in sequence:

1.  **Understand the Past (Historical Context Assessment - HCA)**
    *   **Goal:** Find out about real-world discrimination related to what your AI does (e.g., bias in past hiring for a hiring AI).
    *   **Why:** History often repeats in data and algorithms. Knowing the past helps spot risks.
    *   **Output Template:** [`templates/template-historical-context-assessment-report.md`](../templates/template-historical-context-assessment-report.md)
    *   **Detailed Guidance:** See domain-specific examples in [`resources/guide-domain-adaptation-methodology.md`](../resources/guide-domain-adaptation-methodology.md).

2.  **Define "Fairness" (Fairness Definition Selection - FDS)**
    *   **Goal:** Decide exactly what "fair" means for *your* AI in *this* situation. There are many ways to define fairness (like ensuring equal opportunity vs. equal outcomes), and they often conflict.
    *   **Why:** You can't measure fairness without defining it first. Your choice depends on the context (from HCA), ethics, rules, and stakeholder input.
    *   **Output Template:** [`templates/template-fairness-definition-selection-rationale.md`](../templates/template-fairness-definition-selection-rationale.md)
    *   **Detailed Guidance:** Consult definition comparisons and selection strategies. Consider input from stakeholder engagement (see [`resources/guide-stakeholder-engagement-methodology.md`](../resources/guide-stakeholder-engagement-methodology.md)).

3.  **Find Potential Problems (Bias Source Identification - BSI)**
    *   **Goal:** Look through how your AI was built and how it's used to find *where* bias could get in. This includes the data, the features, the model itself, and how people use it.
    *   **Why:** Knowing *where* bias might come from helps you focus your testing and fixes. Your chosen fairness definition (from FDS) helps you know what *kind* of bias sources are most important to look for.
    *   **Output Template:** [`templates/template-bias-source-mapping-and-risk-assessment.md`](../templates/template-bias-source-mapping-and-risk-assessment.md)
    *   **Detailed Guidance:** Analyze the full ML lifecycle. Consider technical and socio-technical sources. For deeper analysis, see [`resources/guide-causal-fairness-analysis-methodology.md`](../resources/guide-causal-fairness-analysis-methodology.md).

4.  **Measure the Results (Metrics Implementation & Analysis - MIA)**
    *   **Goal:** Use data to check if the AI meets the fairness definitions you chose, paying attention to the bias sources you identified.
    *   **Why:** This gives you evidence about whether the AI is actually fair according to your chosen standard. It involves looking at different groups, including combinations (intersectionality).
    *   **Output Templates:** [`templates/template-metrics-implementation-and-results.md`](../templates/template-metrics-implementation-and-results.md), [`templates/template-intersectional-analysis-report.md`](../templates/template-intersectional-analysis-report.md)
    *   **Detailed Guidance:** Select metrics aligned with definitions and bias sources. Use statistical validation. For advanced techniques, see [`resources/guide-intersectional-analysis-methodology.md`](../resources/guide-intersectional-analysis-methodology.md).

## 2. How the Parts Connect (Integration)

These four parts aren't isolated; they build on each other in a logical flow:

*   The **History** (HCA) helps you choose relevant **Definitions** (FDS).
*   The **Definitions** (FDS) help you prioritize which **Bias Sources** (BSI) matter most.
*   The **Bias Sources** (BSI) and **Definitions** (FDS) tell you which **Metrics** (MIA) to use.
*   The **Metrics** (MIA) provide evidence, which you interpret by looking back at the **Sources** (BSI) and **History** (HCA).

This connection is key! It makes the audit logical and links technical measurements back to real-world context.
*   **Detailed Integration:** For technical details on how components connect, including data formats and orchestration, see [`framework/framework-integration-concepts.md`](framework-integration-concepts.md) and [`framework/framework-component-interfaces-and-dataformats.md`](framework-component-interfaces-and-dataformats.md).

## 3. Planning Your Audit

Before diving in, make a plan using [`templates/template-assessment-plan.md`](../templates/template-assessment-plan.md):

*   What system are you auditing?
*   Why are you auditing? (e.g., pre-launch, compliance, problem investigation)
*   What are the main fairness concerns or risks initially?
*   Who needs to be involved? (Stakeholders - see Section 8 below and [`resources/guide-stakeholder-engagement-methodology.md`](../resources/guide-stakeholder-engagement-methodology.md))
*   What resources (time, data, people) do you have?
*   Which workflow will you use? (See Section 4)
*   Are there specific rules or laws to follow? (See Section 8 and [`resources/guide-regulatory-compliance-mapping.md`](../resources/guide-regulatory-compliance-mapping.md))

**Detailed Implementation Steps:** Consult the [`framework/framework-implementation-step-by-step-guide.md`](framework-implementation-step-by-step-guide.md) for a step-by-step walkthrough.

## 4. Choosing and Using Workflows

We offer different processes depending on your needs. Choose one from `framework/workflows/` and follow its steps:

*   **[`workflow-process-rapid-assessment.md`](workflows/workflow-rapid-assessment.md)**: Best for initial checks, low-risk systems, or when time is short. Covers basics quickly.
*   **[`workflow-process-comprehensive-assessment.md`](workflows/workflow-comprehensive-assessment.md)**: Best for high-stakes systems or when a deep dive is needed. Thorough work on all components.
*   **[`workflow-process-regulatory-compliance.md`](workflows/workflow-regulatory-compliance.md)**: Use if you need specific documents for legal or regulatory compliance. See also [`resources/guide-regulatory-compliance-mapping.md`](../resources/guide-regulatory-compliance-mapping.md).
*   **[`workflow-process-continuous-monitoring.md`](workflows/workflow-continuous-monitoring.md)**: Use *after* an initial assessment for deployed systems. Focuses on tracking fairness over time.

Each workflow file lists specific steps, inputs, and output templates.

## 5. Core Implementation Steps (General Summary)

Your chosen workflow will guide you, but generally involves:

1.  **Plan**: Complete [`templates/template-assessment-plan.md`](../templates/template-assessment-plan.md).
2.  **Assess Historical Context**: Research and document in [`templates/template-historical-context-assessment-report.md`](../templates/template-historical-context-assessment-report.md).
3.  **Select Fairness Definitions**: Analyze options, justify choices in [`templates/template-fairness-definition-selection-rationale.md`](../templates/template-fairness-definition-selection-rationale.md).
4.  **Identify Bias Sources**: Analyze lifecycle, assess risks, document in [`templates/template-bias-source-mapping-and-risk-assessment.md`](../templates/template-bias-source-mapping-and-risk-assessment.md).
5.  **Implement Metrics & Analyze**: Calculate metrics, perform disaggregated/intersectional analysis, document in [`templates/template-metrics-implementation-and-results.md`](../templates/template-metrics-implementation-and-results.md) and [`templates/template-intersectional-analysis-report.md`](../templates/template-intersectional-analysis-report.md).
6.  **Synthesize & Report**: Analyze connections, document limitations ([`templates/template-assessment-limitations-acknowledgment.md`](../templates/template-assessment-limitations-acknowledgment.md)), record stakeholder input ([`templates/template-stakeholder-engagement-documentation.md`](../templates/template-stakeholder-engagement-documentation.md)), summarize ([`templates/template-assessment-executive-summary.md`](../templates/template-assessment-executive-summary.md)).

**Detailed Implementation:** Refer to [`framework/framework-implementation-step-by-step-guide.md`](framework-implementation-step-by-step-guide.md).

## 6. Essential Documentation: Using Templates

Consistent documentation using the [`templates/`](../templates/) directory is crucial. Key templates are listed in the steps above. Fill these out as you complete each step of your chosen workflow.

## 7. Evaluating Your Audit (Assessment Quality)

How do you know if your fairness audit was good? Use the criteria defined in [`framework/framework-evaluation-criteria-and-metrics.md`](framework-evaluation-criteria-and-metrics.md), covering:

*   **Functional Assessment:** Was the process followed correctly?
*   **Fairness Effectiveness:** Were relevant issues identified and addressed?
*   **Usability:** Was the framework practical?
*   **Limitations Assessment:** Were boundaries acknowledged?

Use peer review, checklists, or stakeholder feedback based on these criteria.

## 8. Advanced Topics & Adaptation

*   **Domain/Regulatory Adaptation**: Fairness issues vary by context. See [`resources/guide-domain-adaptation-methodology.md`](../resources/guide-domain-adaptation-methodology.md) and [`resources/guide-regulatory-compliance-mapping.md`](../resources/guide-regulatory-compliance-mapping.md) for tailoring the framework.
*   **Stakeholder Engagement**: Involving affected communities is vital. See [`resources/guide-stakeholder-engagement-methodology.md`](../resources/guide-stakeholder-engagement-methodology.md) for methods.
*   **Intersectionality**: Fairness often differs at the intersection of identities (e.g., race and gender). Basic analysis is covered in MIA, but for advanced methods see [`resources/guide-intersectional-analysis-methodology.md`](../resources/guide-intersectional-analysis-methodology.md).
*   **Causal Fairness**: To understand root causes beyond correlations, see [`resources/guide-causal-fairness-analysis-methodology.md`](../resources/guide-causal-fairness-analysis-methodology.md).

## 9. Tracking Changes (Versioning)

AI systems and fairness understanding evolve. It's essential to track assessment versions.
*   **Protocol:** Follow the detailed protocol in [`framework/framework-versioning-protocol.md`](framework-versioning-protocol.md).
*   **Examples:** *(See protocol file for guidance, specific examples file removed for consolidation)*

## 10. Conclusion

This framework provides a structured, integrated, and documented approach to AI fairness assessment. By following the component flow, selecting an appropriate workflow, using the templates, consulting detailed guides, and considering context, practitioners can move towards more systematic and accountable fairness evaluations. Remember to start with the plan, choose the right workflow, and document your steps clearly using the provided resources.