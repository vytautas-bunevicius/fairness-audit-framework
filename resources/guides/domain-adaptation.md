# AI Fairness: Domain Adaptation and Regulatory Compliance Guide

This guide helps you tailor the Fairness Audit Framework for specific industries or applications (Part 1) and use it to meet fairness-related legal and regulatory requirements (Part 2).

## Part 1: Adapting the Framework to Your Domain

The core framework (HCA -> FDS -> BSI -> MIA) is flexible, but fairness issues are highly context-dependent. Here’s how to adapt it:

### Key Adaptation Steps

1.  **Analyze Your Domain:** Before starting, research:
    *   **Specific Harms:** What kinds of unfairness are common or particularly damaging in this domain (e.g., unequal access to healthcare, discriminatory hiring, biased loan decisions)?
    *   **Historical Context:** What specific historical patterns of discrimination are relevant (e.g., redlining in housing finance, gender bias in medical research)? Focus your HCA here.
    *   **Data Nuances:** What data is typically used? What are its known biases (e.g., EHR data reflecting access bias, resume language reflecting gender norms)? This informs BSI.
    *   **Domain Values & Ethics:** Are there established ethical principles or codes of conduct (e.g., medical ethics, journalistic standards)? This informs FDS.
    *   **Typical AI Use Cases:** How are AI systems commonly used in this sector? What decisions do they influence?

2.  **Tailor Each Component:**
    *   **Historical Context (HCA):** Prioritize researching and documenting the domain-specific patterns identified above in `templates/historical-context-report.md`.
    *   **Fairness Definitions (FDS):** Select definitions in `templates/fairness-definition-rationale.md` that directly address the key harms and values of the domain.
    *   **Bias Sources (BSI):** Focus investigation in `templates/bias-source-mapping.md` on lifecycle stages and data types known to be problematic in the domain.
    *   **Metrics (MIA):** Choose metrics in `templates/metrics-implementation.md` that reflect domain-specific outcomes and align with selected definitions.

3.  **Engage Domain Stakeholders:** Include people with deep domain expertise *and* individuals representing groups typically affected by decisions in this domain. Document engagement in `templates/stakeholder-documentation.md`. See `resources/stakeholder-intersectionality.md` for methods.

### Example Domain Considerations (Summary - Expand based on need)

*   **Hiring/Employment:** Focus on EEOC guidelines, disparate impact (4/5ths rule), equal opportunity, bias in resumes/interviews/performance data. Metrics often include selection rate comparisons.
*   **Finance/Lending:** Focus on ECOA/FHA, redlining, credit access, disparate impact metrics, proxy variables (ZIP code). Metrics often include approval rates, loan term comparisons.
*   **Healthcare:** Focus on health equity, access disparities, clinical algorithm bias, equal needs satisfaction, EHR data bias. Metrics relate to resource allocation, diagnostic accuracy across groups.
*   **Criminal Justice:** Focus on constitutional rights, sentencing/policing disparities, equal error rates (FPR/FNR), transparency. Metrics focus on risk score calibration and error parity.
*   **Education:** Focus on resource allocation, testing bias, equal opportunity, tracking bias. Metrics include access ratios, outcome gaps.
*   **Content Platforms:** Focus on representation, moderation bias, exposure fairness, echo chambers. Metrics include diversity indices, error rates by group/topic.

---

## Part 2: Using the Framework for Regulatory Compliance

This framework helps structure analysis and documentation for regulatory needs.

### General Compliance Strategy

1.  **Identify Regulations:** Determine applicable laws based on jurisdiction, domain, and risk level (document in `assessment-plan.md`).
2.  **Map Requirements:** List specific fairness requirements from each regulation (documentation, testing, process, monitoring).
3.  **Select Workflow:** Use `framework/workflows/regulatory.md`.
4.  **Focus Assessment:** Tailor HCA, FDS, BSI, MIA to *directly address* the mapped requirements. Justify choices explicitly in relation to the regulation.
5.  **Generate Core Docs:** Complete the standard templates (`templates/*.md`).
6.  **Create Supplements:** Produce any *additional* documents required by specific regulations (e.g., EU AI Act Annex IV package, EEOC validation report). These supplements should *reference* the core documentation.
7.  **Emphasize Evidence:** Ensure robust justification (especially for FDS) and statistical validation (in MIA) where required.
8.  **Document Limitations:** Use `templates/limitations-acknowledgment.md` transparently.

### Key Regulatory Considerations (Examples - Refer to specific laws for full detail)

*   **EU AI Act (High-Risk):** Requires extensive *Technical Documentation* (aligns with BSI, MIA, plan templates), *Risk Management* documentation (aligns with BSI, HCA), *Data Governance* records (aligns with BSI). May require a *Fundamental Rights Impact Assessment (FRIA)*. Use Regulatory workflow and create specific output packages referencing framework templates.
*   **US EEOC (Employment):** Requires demonstrating *job-relatedness* and *business necessity* if disparate impact (e.g., violation of 4/5ths rule) is found. Requires considering *less discriminatory alternatives*. Document this analysis in BSI, MIA, and Executive Summary templates. Ensure ADA compliance is considered.
*   **US Fair Lending (ECOA/FHA):** Requires analysis of *disparate impact* and *disparate treatment*. Specific rules for *Adverse Action Notices*. Aligns with *Model Risk Management* (e.g., SR 11-7), requiring validation (MIA), monitoring, and governance documentation (Plan, Summary templates).
*   **UK Algorithmic Transparency Standard:** Requires specific fields to be filled. The framework's templates (Plan, BSI, MIA, Summary) provide the necessary content.

### Tips for Compliance

*   **Involve Legal Early:** Essential for interpreting regulations correctly.
*   **Be Explicit:** Clearly state which regulation requirement each part of your assessment addresses.
*   **Traceability:** Show the logical chain from requirements to analysis to findings.
*   **Rigorous Validation:** Meet the expected level of statistical proof.
*   **Stay Updated:** Regulations evolve; plan for periodic reviews.

Using the framework systematically helps build a strong foundation for meeting diverse regulatory demands.