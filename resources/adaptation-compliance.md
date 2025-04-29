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
    *   **Historical Context (HCA):** Prioritize researching and documenting the domain-specific patterns identified above.
    *   **Fairness Definitions (FDS):** Select definitions that directly address the key harms and values of the domain. For example, "Equal access opportunity" might be critical in healthcare, while "Equalized odds" might be key for risk assessments.
    *   **Bias Sources (BSI):** Focus investigation on lifecycle stages and data types known to be problematic in the domain (e.g., interview data in HR, credit history data in finance).
    *   **Metrics (MIA):** Choose metrics that reflect domain-specific outcomes and align with selected definitions (e.g., 4/5ths rule in hiring, disparate impact ratios in lending).

3.  **Engage Domain Stakeholders:** Include people with deep domain expertise *and* individuals representing groups typically affected by decisions in this domain. Their insights are crucial for context. See `resources/stakeholder-intersectionality.md`.

### Example Domain Considerations (Summary)

*   **Hiring/Employment:** Focus on EEOC guidelines, disparate impact (4/5ths rule), equal opportunity, bias in resumes/interviews/performance data.
*   **Finance/Lending:** Focus on ECOA/FHA regulations, redlining history, credit access, disparate impact metrics, proxy variables (like ZIP code).
*   **Healthcare:** Focus on health equity, access disparities, clinical algorithm bias history, equal needs satisfaction, biases in EHR data or clinical guidelines.
*   **Criminal Justice:** Focus on constitutional rights, sentencing/policing disparities, equal false positive/negative rates (especially for risk assessments), transparency.
*   **Education:** Focus on resource allocation, testing bias, equal opportunity, tracking/placement bias.
*   **Content Platforms:** Focus on representation, moderation bias, exposure fairness, echo chambers, platform guidelines.

---

## Part 2: Using the Framework for Regulatory Compliance

Many laws and regulations require demonstrating fairness or non-discrimination in AI systems. This framework helps structure the necessary analysis and documentation.

### General Compliance Strategy

1.  **Identify ALL Applicable Regulations:** Determine which laws/rules apply based on *where* the system is used, *what* it does (domain), and its *risk level*. This is crucial for the `assessment-plan.md`.
2.  **Map Requirements:** For each regulation, list its specific requirements regarding fairness assessment, bias mitigation, documentation, validation, and monitoring.
3.  **Select Regulatory Workflow:** Use the `framework/workflows/regulatory.md` workflow, which is designed for this purpose.
4.  **Focus Assessment Activities:** Tailor HCA, FDS, BSI, and MIA to directly address the mapped requirements.
    *   *Example (ECOA):* Your FDS must consider definitions relevant to lending discrimination; your MIA must calculate metrics like approval rate ratios and analyze disparate impact.
    *   *Example (EU AI Act High-Risk):* Your HCA must consider fundamental rights impacts; your BSI must feed into the required risk management documentation; your MIA results go into the technical documentation (Annex IV).
5.  **Generate Core Documentation:** Complete the standard framework templates thoroughly.
6.  **Create Regulation-Specific Artifacts:** Produce any additional documents required by the specific regulation (e.g., an EU AI Act Annex IV package, an EEOC validation report, an Adverse Action notice rationale for ECOA). These should *reference* the core framework documentation.
7.  **Emphasize Justification & Evidence:** Regulatory documentation needs strong justification for choices (especially fairness definitions) and robust evidence (statistical validation for metrics).
8.  **Document Limitations:** Be transparent about assessment limitations (`templates/limitations-acknowledgment.md`), as regulators often look for this.

### Key Regulatory Considerations (Examples)

*   **EU AI Act (High-Risk):** Requires extensive technical documentation (see Annex IV), risk management documentation, data governance evidence, and potentially a Fundamental Rights Impact Assessment (FRIA). The framework's templates provide inputs for these.
*   **US EEOC (Employment):** Focus on disparate impact analysis (often using the 4/5ths rule), validation of job-relatedness and business necessity if impact is found, and consideration of less discriminatory alternatives. ADA compliance is also key.
*   **US Fair Lending (ECOA/FHA):** Requires analysis of disparate treatment and disparate impact, specific requirements for adverse action notices, and alignment with model risk management guidelines (like SR 11-7 for banks).
*   **UK Algorithmic Transparency Standard (Public Sector):** Requires filling out a specific standard record covering purpose, data, development, impact, and governance. The framework's templates provide the content needed.

### Tips for Compliance Documentation

*   **Work with Legal/Compliance:** Engage legal experts early and throughout the process.
*   **Be Specific:** Clearly reference regulations and how your assessment addresses them.
*   **Maintain Traceability:** Show how historical context led to definitions, how definitions guided bias source identification, how sources influenced metrics, and how results inform mitigation and compliance status.
*   **Validate Rigorously:** Ensure statistical methods used in MIA meet regulatory expectations where applicable.
*   **Plan for Updates:** Regulations change; have a process for monitoring changes and updating assessments.

By using the framework systematically and tailoring it with regulatory requirements in mind, you can produce comprehensive and defensible compliance documentation.