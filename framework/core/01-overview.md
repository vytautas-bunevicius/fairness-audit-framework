# AI Fairness Audit Framework: Overview and Navigation

Welcome! This guide explains how to understand and implement the Fairness Audit Framework to assess your AI system. It
provides an overview of the core components and directs you to more detailed resources within the framework.

## Framework Core Documentation

- **[01-overview.md](./01-overview.md)**: This document - Overview and Navigation (you are here)
- **[02-component-interfaces.md](./02-component-interfaces.md)**: Integration Methodology between components
- **[03-evaluation-criteria.md](./03-evaluation-criteria.md)**: Criteria for evaluating framework effectiveness
- **[04-implementation-guide.md](./04-implementation-guide.md)**: Practical implementation steps
- **[05-integration-concepts.md](./05-integration-concepts.md)**: Advanced integration concepts
- **[06-versioning-protocol.md](./06-versioning-protocol.md)**: Framework versioning and updates

## 1. Framework Overview: The Four Key Parts

Think of a fairness audit like building a case. You need evidence and reasoning. This framework breaks it down into four
main parts, typically performed in sequence:

1. **Understand the Past (Historical Context Assessment - HCA)**
    * **Goal:** Find out about real-world discrimination related to what your AI does (e.g., bias in past hiring for a
      hiring AI).
    * **Why:** History often repeats in data and algorithms. Knowing the past helps spot risks.
    * **Output Template:** [
      `templates/assessment/historical-context.md`](../../templates/assessment/historical-context.md)
    * **Detailed Guidance:** See domain-specific examples in [
      `resources/guides/domain-adaptation.md`](../../resources/guides/domain-adaptation.md).

2. **Define "Fairness" (Fairness Definition Selection - FDS)**
    * **Goal:** Decide exactly what "fair" means for *your* AI in *this* situation. There are many ways to define
      fairness (like ensuring equal opportunity vs. equal outcomes), and they often conflict.
    * **Why:** You can't measure fairness without defining it first. Your choice depends on the context (from HCA),
      ethics, rules, and stakeholder input.
    * **Output Template:** [
      `templates/assessment/fairness-definition.md`](../../templates/assessment/fairness-definition.md)
    * **Detailed Guidance:** Consult definition comparisons and selection strategies. Consider input from stakeholder
      engagement (see [`resources/guides/stakeholder-engagement.md`](../../resources/guides/stakeholder-engagement.md)).

3. **Find Potential Problems (Bias Source Identification - BSI)**
    * **Goal:** Look through how your AI was built and how it's used to find *where* bias could get in. This includes
      the data, the features, the model itself, and how people use it.
    * **Why:** Knowing *where* bias might come from helps you focus your testing and fixes. Your chosen fairness
      definition (from FDS) helps you know what *kind* of bias sources are most important to look for.
    * **Output Template:** [
      `templates/assessment/bias-source-mapping.md`](../../templates/assessment/bias-source-mapping.md)
    * **Detailed Guidance:** Analyze the full ML lifecycle. Consider technical and socio-technical sources. For deeper
      analysis, see [
      `resources/guides/causal-fairness-analysis.md`](../../resources/guides/causal-fairness-analysis.md).

4. **Measure the Results (Metrics Implementation & Analysis - MIA)**
    * **Goal:** Use data to check if the AI meets the fairness definitions you chose, paying attention to the bias
      sources you identified.
    * **Why:** This gives you evidence about whether the AI is actually fair according to your chosen standard. It
      involves looking at different groups, including combinations (intersectionality).
    * **Output Templates:** [
      `templates/assessment/metrics-implementation.md`](../../templates/assessment/metrics-implementation.md), [
      `templates/assessment/intersectional-analysis.md`](../../templates/assessment/intersectional-analysis.md)
    * **Detailed Guidance:** Select metrics aligned with definitions and bias sources. Use statistical validation.

## 2. How the Parts Connect (Integration)

These four parts aren't isolated; they build on each other in a logical flow with clear data handoffs between
components:

* The **History** (HCA) helps you choose relevant **Definitions** (FDS).
    * **Output → Input Flow**: Historical pattern registry with relevance scores feeds directly into fairness definition
      selection.
    * **Integration Metric**: Historical Pattern Utilization Rate (% of identified patterns addressed in definitions).

* The **Definitions** (FDS) help you prioritize which **Bias Sources** (BSI) matter most.
    * **Output → Input Flow**: Selected fairness definitions with justifications guide bias source prioritization.
    * **Integration Metric**: Definition-Source Alignment Score (how well bias sources map to chosen definitions).

* The **Bias Sources** (BSI) and **Definitions** (FDS) tell you which **Metrics** (MIA) to use.
    * **Output → Input Flow**: Bias source catalog with risk scores determines which metrics to implement.
    * **Integration Metric**: Source Coverage Rate (% of high-risk bias sources measured by selected metrics).

* The **Metrics** (MIA) provide evidence, which you interpret by looking back at the **Sources** (BSI) and **History** (
  HCA).
    * **Output → Input Flow**: Quantitative metrics results inform root cause analysis and mitigation strategies.
    * **Integration Metric**: Finding-to-Action Conversion Rate (% of identified issues with clear mitigation plans).

This connection is key! It makes the audit logical and links technical measurements back to real-world context. The
framework's effectiveness can be measured using Task Completion Rate metrics for each component handoff, ensuring the
outputs from one stage successfully feed into subsequent stages.

* **Detailed Integration:** For technical details on how components connect, including data formats and orchestration,
  see [`framework/core/05-integration-concepts.md`](05-integration-concepts.md) and [
  `framework/core/02-component-interfaces.md`](02-component-interfaces.md).

## 3. Planning Your Audit

Before diving in, make a plan using [
`templates/assessment/assessment-plan.md`](../../templates/assessment/assessment-plan.md):

* What system are you auditing?
* Why are you auditing? (e.g., pre-launch, compliance, problem investigation)
* What are the main fairness concerns or risks initially?
* Who needs to be involved? (Stakeholders - see Section 8 below and [
  `resources/guides/stakeholder-engagement.md`](../../resources/guides/stakeholder-engagement.md))
* What resources (time, data, people) do you have?
* Which workflow will you use? (See Section 4)
* Are there specific rules or laws to follow? (See Section 8)

**Detailed Implementation Steps:** Consult the [`framework/core/04-implementation-guide.md`](04-implementation-guide.md)
for a step-by-step walkthrough.

## 4. Choosing and Using Workflows

We offer different processes depending on your needs. Choose one from `framework/workflows/` and follow its steps:

* **[`01-rapid-assessment.md`](../workflows/01-rapid-assessment.md)**: Best for initial checks, low-risk systems, or
  when time is short. Covers basics quickly.
* **[`02-comprehensive-assessment.md`](../workflows/02-comprehensive-assessment.md)**: Best for high-stakes systems or
  when a deep dive is needed. Thorough work on all components.
* **[`04-regulatory-compliance.md`](../workflows/04-regulatory-compliance.md)**: Use if you need specific documents for
  legal or regulatory compliance.
* **[`03-continuous-monitoring.md`](../workflows/03-continuous-monitoring.md)**: Use *after* an initial assessment for
  deployed systems. Focuses on tracking fairness over time.

Each workflow file lists specific steps, inputs, and output templates.

## 5. Core Implementation Steps (General Summary)

Your chosen workflow will guide you, but generally involves:

1. **Plan**: Complete [`templates/assessment/assessment-plan.md`](../../templates/assessment/assessment-plan.md).
2. **Assess Historical Context**: Research and document in [
   `templates/assessment/historical-context.md`](../../templates/assessment/historical-context.md).
3. **Select Fairness Definitions**: Analyze options, justify choices in [
   `templates/assessment/fairness-definition.md`](../../templates/assessment/fairness-definition.md).
4. **Identify Bias Sources**: Analyze lifecycle, assess risks, document in [
   `templates/assessment/bias-source-mapping.md`](../../templates/assessment/bias-source-mapping.md).
5. **Implement Metrics & Analyze**: Calculate metrics, perform disaggregated/intersectional analysis, document in [
   `templates/assessment/metrics-implementation.md`](../../templates/assessment/metrics-implementation.md) and [
   `templates/assessment/intersectional-analysis.md`](../../templates/assessment/intersectional-analysis.md).
6. **Synthesize & Report**: Analyze connections, document limitations ([
   `templates/assessment/limitations.md`](../../templates/assessment/limitations.md)), record stakeholder input ([
   `templates/stakeholder/engagement-documentation.md`](../../templates/stakeholder/engagement-documentation.md)),
   summarize ([`templates/assessment/executive-summary.md`](../../templates/assessment/executive-summary.md)).

**Detailed Implementation:** Refer to [`framework/core/04-implementation-guide.md`](04-implementation-guide.md).

## 6. Essential Documentation: Using Templates

Consistent documentation using the organized `templates/` subdirectories is crucial. Key templates are listed in the
steps above. Fill these out as you complete each step of your chosen workflow.

## 7. Evaluating Your Audit (Assessment Quality)

How do you know if your fairness audit was good? Use the criteria defined in [
`framework/core/03-evaluation-criteria.md`](03-evaluation-criteria.md), covering:

* **Functional Assessment:** Was the process followed correctly?
    * **Key Metrics**: Documentation Error Rate, Process Compliance Rate, Component Integration Completeness
    * **Measurement Approach**: Trace key data elements through complete assessment workflow

* **Fairness Effectiveness:** Were relevant issues identified and addressed?
    * **Key Metrics**: Issue Detection Accuracy, Root Cause Identification Rate, Recommendation Specificity
    * **Measurement Approach**: Compare with known bias sources and validate against systems with known issues

* **Usability:** Was the framework practical?
    * **Key Metrics**: Time-to-Completion, Consistency Across Assessors, Learning Curve Steepness
    * **Measurement Approach**: Measure time to proficiency for new users and compare assessment results across
      different teams

* **Limitations Assessment:** Were boundaries acknowledged?
    * **Key Metrics**: Limitation Documentation Completeness, Uncertainty Quantification Accuracy
    * **Measurement Approach**: Verify transparency about constraints and limitations

Use peer review, checklists, or stakeholder feedback based on these criteria. For quantitative evaluation, implement the
Task Completion Rate methodology to measure the efficiency and effectiveness of your audit process.

## 8. Advanced Topics & Adaptation

* **Domain Adaptation**: Fairness issues vary by context. See [
  `resources/guides/domain-adaptation.md`](../../resources/guides/domain-adaptation.md) for tailoring the framework.
    * **Regulatory Alignment**: The framework maps directly to key regulations including:
        * **EEOC Guidelines**: Templates align with the 4/5ths rule requirements and adverse impact analysis
        * **IEEE Standard 7003-2023**: Documentation templates satisfy the Algorithmic Bias Considerations standard
        * **EU AI Act**: Workflow supports high-risk AI system documentation requirements
        * **Model Risk (SR 11-7)**: Integration with model risk governance frameworks

* **Stakeholder Engagement**: Involving affected communities is vital. See [
  `resources/guides/stakeholder-engagement.md`](../../resources/guides/stakeholder-engagement.md) for methods.
    * **Documentation**: Use [
      `templates/stakeholder/engagement-documentation.md`](../../templates/stakeholder/engagement-documentation.md) to
      record input and demonstrate inclusive development.

* **Intersectionality**: Fairness often differs at the intersection of identities (e.g., race and gender). Basic
  analysis is covered in MIA.
    * **Implementation**: Use [
      `templates/assessment/intersectional-analysis.md`](../../templates/assessment/intersectional-analysis.md) to
      document compound disadvantages.

* **Causal Fairness**: To understand root causes beyond correlations, see [
  `resources/guides/causal-fairness-analysis.md`](../../resources/guides/causal-fairness-analysis.md).
    * **Advanced Methods**: Includes Peer-induced Fairness approaches for algorithmic audits that identify causal
      mechanisms of bias rather than just statistical correlations.

## 9. Tracking Changes (Versioning)

AI systems and fairness understanding evolve. It's essential to track assessment versions.

* **Protocol:** Follow the detailed protocol in [`framework/core/06-versioning-protocol.md`](06-versioning-protocol.md).
* **Examples:** *(See protocol file for guidance, specific examples file removed for consolidation)*

## 10. Third-Party Validation and Certification

For organizations seeking external validation of their fairness assessments, the framework supports third-party
certification processes:

* **Fairness Certification Frameworks**: The documentation produced by this framework aligns with emerging certification
  standards for AI fairness.
* **Audit Evidence Package**: The completed templates form a comprehensive evidence package suitable for external
  review.
* **Validation Methodology**: External auditors can use the framework's evaluation criteria to validate assessment
  quality.
* **Continuous Compliance**: The monitoring workflow supports ongoing compliance verification after initial
  certification.

## 11. Conclusion

This framework provides a structured, integrated, and documented approach to AI fairness assessment. By following the
component flow, selecting an appropriate workflow, using the templates, consulting detailed guides, and considering
context, practitioners can move towards more systematic and accountable fairness evaluations.

The framework's effectiveness can be measured using its own evaluation criteria, including Task Completion Rate metrics
for process efficiency and Documentation Error Rate for quality assessment. These metrics help organizations
continuously improve their fairness assessment practices.

Remember to start with the plan, choose the right workflow, and document your steps clearly using the provided
resources. By connecting technical measurements to real-world context and regulatory requirements, the framework helps
bridge the gap between fairness principles and practical implementation.