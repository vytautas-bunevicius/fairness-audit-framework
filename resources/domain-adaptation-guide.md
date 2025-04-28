# Domain Adaptation Guide

This guide provides detailed instructions for adapting the Fairness Audit Framework to different application domains. While the core framework structure remains consistent, domain-specific considerations require adaptations to effectively assess fairness in various contexts.

## General Adaptation Principles

### 1. Core Framework Preservation

When adapting the framework, maintain these essential elements:

- The four core components (Historical Context, Fairness Definitions, Bias Sources, Metrics)
- Standard data exchange formats between components
- Documentation requirements for each component
- Validation criteria for assessment quality

### 2. Adaptation Dimensions

Adapt the framework along these key dimensions:

- **Historical pattern emphasis**: Prioritize patterns most relevant to the domain
- **Fairness definition selection**: Emphasize definitions that address domain-specific concerns
- **Bias source focus**: Concentrate on lifecycle stages with highest domain risk
- **Metrics selection**: Implement metrics aligned with domain-specific fairness requirements
- **Stakeholder composition**: Include domain-specific expertise and affected communities
- **Validation approach**: Use domain-appropriate benchmarks and evaluation criteria

### 3. Evidence Standards

Adjust evidence standards based on domain characteristics:

- **Regulated domains**: Higher evidence standards with statistical validation
- **Emerging applications**: More emphasis on qualitative assessment when limited precedent exists
- **High-stakes domains**: More comprehensive documentation and validation requirements
- **Rapidly evolving domains**: More frequent reassessment and version control

## Domain-Specific Adaptation Guidelines

### Employment and Hiring

#### Historical Context Focus
- Employment discrimination precedents and patterns
- Occupational segregation history
- Credential access disparities
- Interview and evaluation bias research

#### Recommended Fairness Definitions
- Equal opportunity (equal true positive rates)
- Predictive parity for job success
- Demographic parity where legally required
- Counterfactual fairness for qualification assessment

#### Priority Bias Sources
- Resume and application data representation
- Credential and experience proxies
- Interview data collection inconsistencies
- Performance metric design and application

#### Key Metrics
- Four-fifths rule compliance
- Group benefit analysis (selection, promotion, compensation)
- Qualification assessment calibration
- Representation metrics with significance testing

#### Documentation Emphasis
- Legal compliance evidence
- Validation of job-relatedness
- Consideration of alternative practices
- Ongoing monitoring documentation

#### Relevant Regulations
- Equal Employment Opportunity Commission (EEOC) guidelines
- Uniform Guidelines on Employee Selection Procedures
- Title VII of the Civil Rights Act
- Local fair employment practices laws

### Financial Services

#### Historical Context Focus
- Redlining and geographic exclusion
- Credit access disparities
- Banking service availability patterns
- Pricing discrimination history

#### Recommended Fairness Definitions
- Demographic parity in access
- Equal opportunity for creditworthy applicants
- Calibration across groups for risk assessment
- Individual fairness for similar credit profiles

#### Priority Bias Sources
- Credit history modeling
- Geographic feature proxies
- Income stability assessment
- Non-traditional financial data interpretation

#### Key Metrics
- Disparate impact analysis with significance testing
- Approval rate ratios
- Pricing differentials analysis
- Terms and conditions comparisons

#### Documentation Emphasis
- Regulatory compliance evidence
- Model risk management alignment
- Adverse action rationale
- Alternative data validation

#### Relevant Regulations
- Equal Credit Opportunity Act (ECOA) and Regulation B
- Fair Housing Act
- Community Reinvestment Act
- Federal Reserve SR 11-7 (Model Risk Management)

### Healthcare

#### Historical Context Focus
- Clinical algorithm bias history
- Healthcare access disparities
- Medical research representation gaps
- Treatment recommendation patterns

#### Recommended Fairness Definitions
- Equal needs satisfaction
- Calibrated predictions across groups
- Equal access opportunity
- Benefit assessment equity

#### Priority Bias Sources
- Clinical documentation quality disparities
- Differential diagnosis patterns
- Social determinants of health proxies
- Quality of life assessment bias

#### Key Metrics
- Need satisfaction ratio
- False negative rate disparity
- Risk calibration error by group
- Resource allocation proportion

#### Documentation Emphasis
- Clinical effectiveness alongside equity
- Patient engagement evidence
- Ethical framework alignment
- Health outcome monitoring

#### Relevant Regulations
- Section 1557 of the Affordable Care Act
- Health Insurance Portability and Accountability Act (HIPAA)
- Americans with Disabilities Act (ADA)
- Regulatory guidance on healthcare algorithms

### Criminal Justice

#### Historical Context Focus
- Sentencing disparity research
- Policing pattern documentation
- Pretrial detention impact studies
- Recidivism prediction bias literature

#### Recommended Fairness Definitions
- Equal false positive rates (minimize unequal harm)
- Predictive parity across groups
- Individual fairness for similar cases
- Counterfactual fairness for defendant assessment

#### Priority Bias Sources
- Criminal history feature encoding
- Geographic and demographic proxies
- Data collection during policing
- Outcome variable definition

#### Key Metrics
- False positive rate parity
- Calibration by group
- Disparate impact analysis
- Recommendation disparity assessment

#### Documentation Emphasis
- Constitutional compliance
- Due process alignment
- Transparency for defendants
- Human oversight mechanisms

#### Relevant Regulations
- Constitutional requirements (Equal Protection, Due Process)
- Relevant case law on algorithmic decision-making
- State-specific requirements for risk assessment tools
- Pretrial reform legislation

### Education

#### Historical Context Focus
- Educational resource allocation disparities
- Standardized testing bias research
- Disciplinary disparity documentation
- Tracking and placement patterns

#### Recommended Fairness Definitions
- Equal opportunity for qualified students
- Predictive parity for educational success
- Demographic parity for enrichment access
- Consistency across similar student profiles

#### Priority Bias Sources
- Prior achievement data interpretation
- School quality variations
- Assessment format bias
- Behavioral assessment inconsistency

#### Key Metrics
- Opportunity access ratio
- Resource allocation proportionality
- Intervention recommendation parity
- Outcome gap analysis

#### Documentation Emphasis
- Educational effectiveness alongside equity
- Student and family engagement
- Consideration of systemic factors
- Intervention impact monitoring

#### Relevant Regulations
- Family Educational Rights and Privacy Act (FERPA)
- Individuals with Disabilities Education Act (IDEA)
- Title VI of the Civil Rights Act
- State educational equity requirements

### Content Recommendation and Moderation

#### Historical Context Focus
- Representation disparities in media
- Content moderation impact studies
- Platform access and reach patterns
- Engagement disparity documentation

#### Recommended Fairness Definitions
- Equal quality of service across groups
- Representation parity where appropriate
- Equal error rates in content moderation
- Equal voice and visibility opportunity

#### Priority Bias Sources
- Training data representativeness
- User interaction history bias
- Engagement metric design
- Concept classification imbalance

#### Key Metrics
- Representation disparity index
- Recommendation diversity ratio
- Moderation error distribution
- Exposure opportunity balance

#### Documentation Emphasis
- Value alignment transparency
- User control mechanisms
- Cultural sensitivity evidence
- Community impact assessment

#### Relevant Regulations
- Platform-specific guidelines
- Digital Services Act (EU)
- Content moderation regulations
- Emerging algorithmic transparency requirements

## Adaptation Process

Follow this process when adapting the framework to a new domain:

### 1. Domain Analysis Phase

**Activities**:
- Research domain-specific fairness concerns and literature
- Identify relevant regulations and standards
- Document domain-specific fairness definitions and metrics
- Map common bias sources in the domain

**Outputs**:
- Domain Fairness Profile
- Regulatory Requirement Inventory
- Bias Pattern Catalog

### 2. Framework Customization Phase

**Activities**:
- Select appropriate assessment workflow
- Adapt component interfaces for domain-specific information
- Customize documentation templates
- Develop domain-specific validation criteria

**Outputs**:
- Customized Assessment Plan
- Adapted Documentation Templates
- Domain-specific Assessment Checklist

### 3. Stakeholder Engagement Phase

**Activities**:
- Identify domain-specific stakeholders
- Develop engagement strategy appropriate to domain
- Collect domain expert input on adaptation
- Validate approach with affected communities

**Outputs**:
- Stakeholder Engagement Plan
- Expert Validation Report
- Community Feedback Summary

### 4. Validation and Refinement Phase

**Activities**:
- Test framework on domain-specific case studies
- Gather feedback on effectiveness
- Refine adaptation based on testing
- Document domain-specific best practices

**Outputs**:
- Adaptation Effectiveness Report
- Refinement Recommendations
- Domain Best Practices Guide

## Domain-Specific Resources

### Employment and Hiring

- [Society for Industrial and Organizational Psychology. (2023). Principles for the Validation and Use of Personnel Selection Procedures](https://www.houstontx.gov/hr/hrfiles/classified_testing/siop_principles.pdf)
- [Raghavan, M., & Barocas, S. (2023). Challenges for mitigating bias in algorithmic hiring](https://dl.acm.org/doi/10.1145/3696457)
- [Equal Employment Opportunity Commission. (2022). The Americans with Disabilities Act and the Use of Software, Algorithms, and Artificial Intelligence to Assess Job Applicants and Employees](https://www.eeoc.gov/laws/guidance/americans-disabilities-act-and-use-software-algorithms-and-artificial-intelligence-assess)

### Financial Services

- [Federal Financial Institutions Examination Council. (2024). Interagency Fair Lending Examination Procedures](https://www.ffiec.gov/press/pdf/InteragencyFairLendingExaminationProcedures.pdf)
- [The Brookings Institution. (2023). Algorithmic Bias in Financial Services](https://www.brookings.edu/articles/algorithmic-bias-in-financial-services/)
- [Consumer Financial Protection Bureau. (2023). Consumer Financial Protection Circular 2023-03: Adverse action notification requirements for credit decisions based on complex algorithms](https://www.consumerfinance.gov/compliance/circulars/circular-2023-03/)

### Healthcare

- [National Academy of Medicine. (2022). Assessing and Addressing Algorithmic Bias in Healthcare](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2812958)
- [World Health Organization. (2022). Ethics and Governance of Artificial Intelligence for Health](https://www.who.int/publications/i/item/9789240029200)
- [Obermeyer, Z., & Mullainathan, S. (2023). Addressing bias in prediction models: A framework for healthcare applications](https://www.science.org/doi/10.1126/science.aax2342)

### Criminal Justice

- [Partnership on AI. (2023). Report on Algorithmic Risk Assessment Tools in the U.S. Criminal Justice System](https://www.partnershiponai.org/paper/report-on-algorithmic-risk-assessment-tools-in-the-u-s-criminal-justice-system/)
- [The Leadership Conference on Civil and Human Rights. (2022). The Use of Pretrial Risk Assessment Instruments: A Shared Statement of Civil Rights Concerns](https://civilrights.org/resource/pretrial-risk-assessment-tools/)
- [National Institute of Justice. (2023). Fairness and Effectiveness in Risk Assessment Tools](https://nij.ojp.gov/topics/articles/overview-predictive-policing)

### Education

- [UNESCO. (2023). AI in Education: Guidance for Policy-makers](https://unesdoc.unesco.org/ark:/48223/pf0000376709)
- [National Education Association. (2022). AI in Schools: Guidance for Educators and Administrators](https://accutrain.com/nea-approves-classroom-ai-guidance/)
- [Stanford University Institute for Human-Centered AI. (2023). Algorithmic Fairness in Educational Technologies](https://hai.stanford.edu/education/algorithmic-fairness)

### Content Recommendation and Moderation

- [IEEE. (2023). Ethically Aligned Design for Recommendation Systems](https://sagroups.ieee.org/global-initiative/wp-content/uploads/sites/542/2023/01/ead1e.pdf)
- [Partnership on AI. (2022). Best Practices for Content Moderation](https://www.partnershiponai.org/paper/content-moderation-best-practices/)
- [World Wide Web Foundation. (2024). Algorithmic Bias in Content Recommendation Systems](https://webfoundation.org/research/algorithmic-bias-content-recommendation/)

## Domain Adaptation Examples

The framework includes case studies demonstrating successful adaptation:

- [Hiring Algorithm](../case-studies/hiring-algorithm.md): Adaptation for employment screening
- [Loan Approval](../case-studies/loan-approval.md): Adaptation for financial services
- [Healthcare Allocation](../case-studies/healthcare-allocation.md): Adaptation for clinical resource allocation

## References

- [ACM Conference on Fairness, Accountability, and Transparency (FAccT). Domain-specific Fairness Papers (2020-2024)](https://facctconference.org)
- [Crawford, K. (2021). Atlas of AI: Power, Politics, and the Planetary Costs of Artificial Intelligence. Yale University Press](https://yalebooks.yale.edu/)
- [D'Ignazio, C., & Klein, L. F. (2020). Data Feminism. MIT Press](https://data-feminism.mitpress.mit.edu)
- [NIST. (2023). AI Risk Management Framework: Domain-specific Applications](https://www.nist.gov/itl/ai-risk-management-framework)
- [Selbst, A. D., boyd, d., Friedler, S. A., Venkatasubramanian, S., & Vertesi, J. (2019). Fairness and abstraction in sociotechnical systems. In Proceedings of the Conference on Fairness, Accountability, and Transparency](https://dl.acm.org/doi/10.1145/3287560.3287598)