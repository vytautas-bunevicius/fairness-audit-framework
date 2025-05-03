# Case Study: Fairness Assessment of Resume Screening Algorithm

## Table of Contents

- [System Overview](#system-overview)
    - [System Specifications](#system-specifications)
- [Assessment Approach](#assessment-approach)
    - [Key Stakeholders](#key-stakeholders)
- [Historical Context Assessment](#historical-context-assessment)
    - [Identified Historical Patterns](#identified-historical-patterns)
    - [Evidence Sources](#evidence-sources)
    - [Application Risk Mapping](#application-risk-mapping)
- [Fairness Definition Selection](#fairness-definition-selection)
    - [Primary Selected Definitions](#primary-selected-definitions)
    - [Trade-off Analysis](#trade-off-analysis)
- [Bias Source Identification](#bias-source-identification)
    - [Critical Bias Sources](#critical-bias-sources)
    - [Risk Assessment Matrix](#risk-assessment-matrix)
- [Metrics Implementation](#metrics-implementation)
    - [Implemented Metrics](#implemented-metrics)
    - [Statistical Validation](#statistical-validation)
- [Intersectional Analysis](#intersectional-analysis)
- [Identified Issues](#identified-issues)
- [Interventions](#interventions)
- [Results After Intervention](#results-after-intervention)
- [Lessons Learned](#lessons-learned)
- [References](#references)

## System Overview

**System Name**: TalentMatch AI
**Purpose**: Automated resume screening and candidate ranking for initial hiring pipeline
**Organization**: Fortune 500 Technology Company
**Deployment Context**: High-volume IT recruitment

### System Specifications

- **Model Type**: Ensemble model combining gradient boosting and neural networks
- **Training Data**: 50,000 historical resumes with hiring decisions
- **Features**: Education, experience, skills, projects, languages, certifications
- **Output**: Binary classification (recommend/not recommend) with confidence score
- **Usage**: Pre-screening before human review, reducing applicant pool by 70%

## Assessment Approach

The assessment followed the Comprehensive Assessment Workflow due to:

- High impact on employment opportunities
- Large-scale deployment affecting thousands of candidates
- Regulatory requirements under EEOC guidelines
- Previous concerns about diversity in technical hiring

### Key Stakeholders

- Recruitment team
- Legal and compliance department
- HR leadership
- Representatives from employee resource groups
- External fairness consultant

## Historical Context Assessment

### Identified Historical Patterns

| Pattern ID | Description                              | Relevance Score | Application Risks                                  |
|------------|------------------------------------------|-----------------|----------------------------------------------------|
| HP001      | Gender discrimination in technical roles | 0.85            | Feature selection bias, representation disparities |
| HP002      | Racial disparities in callback rates     | 0.90            | Label bias in training data, proxy discrimination  |
| HP003      | Educational institution bias             | 0.75            | Credential preferences, socioeconomic exclusion    |
| HP004      | Age discrimination in tech hiring        | 0.80            | Temporal feature bias, career gap penalties        |

### Evidence Sources

- Industry hiring data comparing callback rates by demographic groups
- Research studies on resume name-based discrimination
- EEOC technical hiring cases and settlements
- Company's historical diversity metrics in technical roles

### Application Risk Mapping

Analysis identified specific system elements at risk of perpetuating historical patterns:

- **Training Data**: Historical hiring decisions may already contain biases
- **Feature Engineering**: Emphasis on prestigious institutions may disadvantage underrepresented groups
- **Proxy Variables**: Geographic and educational features may correlate with protected characteristics
- **Temporal Features**: Career gap handling may disproportionately impact women and caregivers

## Fairness Definition Selection

### Primary Selected Definitions

1. **Equal Opportunity**
    - **Formal Definition**: Equal true positive rates across protected groups
    - **Rationale**: Ensures qualified candidates have equal chances regardless of group membership
    - **Connection to Patterns**: Directly addresses HP001 and HP002

2. **Demographic Parity**
    - **Formal Definition**: Equal selection rates across protected groups
    - **Rationale**: Supports remediation of historical underrepresentation
    - **Connection to Patterns**: Addresses historical exclusion from HP001-HP004

### Trade-off Analysis

| Trade-off                               | Analysis                                                             | Decision                                                        |
|-----------------------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------|
| Equal Opportunity vs. Predictive Parity | Equal opportunity prioritized due to historical callback disparities | Equal opportunity set as primary constraint                     |
| Individual vs. Group Fairness           | Group fairness prioritized given documented systemic patterns        | Group fairness metrics as primary measures                      |
| Accuracy vs. Fairness                   | Willing to accept 3-5% reduction in overall accuracy                 | Established fairness thresholds with acceptable accuracy impact |

## Bias Source Identification

### Critical Bias Sources

| Source ID | Description                               | Lifecycle Stage        | Risk Level | Connected Patterns |
|-----------|-------------------------------------------|------------------------|------------|--------------------|
| BS001     | Underrepresentation in training data      | Data collection        | High       | HP001, HP002       |
| BS002     | Prestigious institution bias              | Feature engineering    | High       | HP003              |
| BS003     | Career gap penalization                   | Feature engineering    | Medium     | HP004, HP001       |
| BS004     | Geographic location as proxy              | Feature selection      | Medium     | HP002              |
| BS005     | Technical terminology gender associations | Feature interpretation | Medium     | HP001              |

### Risk Assessment Matrix

A comprehensive analysis assessed each bias source for:

- Likelihood (probability of manifestation)
- Impact (severity if manifested)
- Detectability (ease of identification)
- Mitigation potential (feasibility of addressing)

BS001 and BS002 were identified as highest priority based on combined risk scores.

## Metrics Implementation

### Implemented Metrics

| Metric                           | Definition                                        | Results   | Interpretation                                                      |
|----------------------------------|---------------------------------------------------|-----------|---------------------------------------------------------------------|
| Equal Opportunity Difference     | TPR_men - TPR_women                               | 0.14      | Women with equivalent qualifications had 14% lower selection rate   |
| Demographic Parity Ratio         | Selection_rate_minority / Selection_rate_majority | 0.78      | Minority candidates selected at 78% the rate of majority candidates |
| Disparate Impact Ratio           | Selection_rate_older / Selection_rate_younger     | 0.81      | Candidates over 40 selected at 81% the rate of younger candidates   |
| Intersectional Equal Opportunity | TPR disparity for gender×race groups              | 0.09-0.22 | Largest disparity for women of color (22%)                          |

### Statistical Validation

- Bootstrap confidence intervals calculated for all metrics
- Sensitivity analysis with different threshold settings
- Intersectional analysis across multiple demographic dimensions

## Intersectional Analysis

The assessment revealed compounding disadvantages at intersections:

- Women of color faced substantially higher disadvantage (22% TPR gap) than either women overall (14%) or people of
  color overall (12%)
- Candidates from non-prestigious schools who were also from underrepresented groups faced the highest disadvantage
- Older women faced higher disadvantage than either older candidates or women separately

## Identified Issues

1. **Model demonstrated significant disparities** in selection rates that correlated with gender and race
2. **Feature importance analysis** revealed overweighting of prestigious institutions
3. **Career gap handling** disproportionately penalized candidates with caregiving interruptions
4. **Geographic information** served as a proxy for race in several metropolitan areas
5. **Technical keyword emphasis** favored terminology more commonly used by male candidates

## Interventions

Based on the assessment, the following interventions were implemented:

1. **Data Augmentation**: Synthetic sample generation to balance representation
2. **Feature Modification**: Reduced weight of institution prestige, normalized career gaps
3. **Constraint-based Training**: Added fairness constraints during model optimization
4. **Threshold Adjustment**: Different thresholds across groups to equalize opportunity
5. **Process Change**: Modified human review allocation to prioritize edge cases
6. **Documentation**: Created model cards documenting fairness characteristics

## Results After Intervention

| Metric                           | Before    | After     | Improvement      |
|----------------------------------|-----------|-----------|------------------|
| Equal Opportunity Difference     | 0.14      | 0.05      | 64% reduction    |
| Demographic Parity Ratio         | 0.78      | 0.91      | 59% improvement  |
| Disparate Impact Ratio           | 0.81      | 0.92      | 58% improvement  |
| Intersectional Equal Opportunity | 0.09-0.22 | 0.04-0.08 | 64-73% reduction |

Overall accuracy decreased by 2.3%, within the acceptable range established during fairness definition trade-off
analysis.

## Lessons Learned

1. **Historical context directly informs metrics selection**: Understanding specific patterns of discrimination in
   technical hiring was crucial for selecting appropriate fairness definitions and metrics.

2. **Intersectional analysis revealed issues missed by single-dimension assessment**: Single-attribute analysis
   significantly underestimated disparities faced by candidates with multiple underrepresented characteristics.

3. **Feature engineering proved more effective than post-processing**: Addressing bias in feature engineering produced
   more robust improvements than threshold adjustments alone.

4. **Stakeholder involvement improved intervention quality**: Input from employee resource groups identified bias
   sources that technical analysis alone missed.

5. **Documentation created accountability**: Standardized documentation created clear accountability for fairness
   considerations throughout development and evaluation.

## References

- [Raghavan, M., Barocas, S., Kleinberg, J., & Levy, K. (2020). Mitigating bias in algorithmic hiring: Evaluating claims and practices](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3408010)
- [EEOC Guidance on Artificial Intelligence and ADA Compliance (2023)](https://ogletree.com/insights-resources/blog-posts/eeoc-issues-new-guidance-on-employer-use-of-ai-and-disparate-impact-potential/)
- [Oxford Internet Institute. (2024). Best Practices for Algorithmic Hiring Assessment](https://www.oii.ox.ac.uk/research/projects/algorithmic-hiring-assessment/)
- [World Economic Forum. (2023). Global Framework for Responsible AI in Employment](https://www.weforum.org/press/2023/11/global-leaders-advance-responsible-ai-development-at-governance-summit/)