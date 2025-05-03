# Case Study: Fairness Assessment of Healthcare Resource Allocation Model

## System Overview

**System Name**: CareAlloc AI  
**Purpose**: Prioritization of patients for specialized care services and resource allocation  
**Organization**: Integrated Healthcare Network  
**Deployment Context**: Large hospital system serving diverse urban and rural populations  

### System Specifications

- **Model Type**: Multi-objective optimization with random forest risk prediction components
- **Training Data**: Electronic health records from 200,000 patients over 5 years
- **Features**: Clinical indicators, diagnostic codes, service utilization history, demographics, social determinants of health
- **Output**: Priority score (1-100) with resource allocation recommendations
- **Usage**: Decision support for care management teams and resource allocation committees

## Assessment Approach

The assessment followed the Comprehensive Assessment Workflow due to:
- High stakes of healthcare resource allocation decisions
- Documented healthcare disparities across multiple dimensions
- Ethical complexity of balancing clinical need, benefit, and equity
- Regulatory requirements for non-discrimination in healthcare

### Key Stakeholders

- Clinical leadership team
- Health equity office
- Patient advocacy representatives
- Ethics committee
- Community advisory board members
- Care management staff

## Historical Context Assessment

### Identified Historical Patterns

| Pattern ID | Description | Relevance Score | Application Risks |
|------------|-------------|-----------------|-------------------|
| HP001 | Racial disparities in pain assessment and treatment | 0.90 | Underestimation of need, delayed care |
| HP002 | Geographic barriers to care access | 0.85 | Transportation-related service utilization bias |
| HP003 | Gender bias in symptom recognition for cardiovascular conditions | 0.80 | Underdiagnosis, severity underestimation |
| HP004 | Socioeconomic disparities in preventive care | 0.85 | Late diagnosis, service utilization patterns |
| HP005 | Age discrimination in intensive treatment allocation | 0.75 | Benefit assessment bias, preference bias |
| HP006 | Disability status impact on quality of life assessment | 0.80 | Resource allocation bias based on QALY |

### Evidence Sources

- Institute of Medicine reports on healthcare disparities (2002-2023)
- Medical literature on clinical algorithm bias (2015-2024)
- Regional community health needs assessment data
- Hospital system's own service utilization data by demographic groups
- Patient satisfaction survey analysis by demographics
- National Healthcare Disparities Reports

### Application Risk Mapping

Analysis identified specific system elements at risk of perpetuating historical patterns:

- **Clinical History Features**: Differential documentation quality across patient groups
- **Prior Utilization Patterns**: Historical access barriers reflected in utilization data
- **Diagnostic Code Patterns**: Differential diagnosis patterns for similar presentations
- **Risk Assessment Components**: Clinical risk scores with embedded biases
- **Benefit Prediction**: Quality-adjusted life year calculations with preference biases
- **ZIP Code Features**: Geographic proxy for social determinants of health

## Fairness Definition Selection

### Primary Selected Definitions

1. **Equalized Needs Satisfaction**
   - **Formal Definition**: Equal resource allocation for equal assessed clinical need across groups
   - **Rationale**: Ensures patients with similar clinical needs receive similar resources
   - **Connection to Patterns**: Addresses HP001, HP003, HP006

2. **Calibrated Predictions Across Groups**
   - **Formal Definition**: Equal error distributions in clinical risk prediction across groups
   - **Rationale**: Ensures clinical risk is neither over- nor under-estimated for any group
   - **Connection to Patterns**: Addresses HP001, HP003, HP005

3. **Equal Access Opportunity**
   - **Formal Definition**: Equal probability of resource receipt for patients who would benefit
   - **Rationale**: Ensures benefit potential determines resource allocation, not group membership
   - **Connection to Patterns**: Addresses HP002, HP004, HP005

### Trade-off Analysis

| Trade-off | Analysis | Decision |
|-----------|----------|----------|
| Individual vs. Group Fairness | Both relevant in healthcare context | Implemented both with primary focus on group fairness |
| Clinical Efficiency vs. Equity | Some tension between pure efficiency and equity | Established minimum equity thresholds with multi-objective optimization |
| Need vs. Benefit Assessment | Differential ability to benefit complicates need-based allocation | Combined approach with safeguards against historical benefit assessment biases |

## Bias Source Identification

### Critical Bias Sources

| Source ID | Description | Lifecycle Stage | Risk Level | Connected Patterns |
|-----------|-------------|-----------------|------------|-------------------|
| BS001 | Clinical documentation quality disparities | Data collection | High | HP001, HP003 |
| BS002 | Historical utilization as proxy for need | Feature engineering | High | HP002, HP004 |
| BS003 | Biased risk scores in training data | Data preparation | High | HP001, HP003, HP005 |
| BS004 | Social determinants of health proxies | Feature selection | Medium | HP002, HP004 |
| BS005 | Quality of life assessments in benefit calculation | Algorithm design | High | HP005, HP006 |
| BS006 | ZIP code as proxy for race and socioeconomic status | Feature engineering | Medium | HP002, HP004 |
| BS007 | Differential diagnosis patterns by demographics | Data collection | Medium | HP001, HP003 |

### Risk Assessment Matrix

A comprehensive risk assessment considered:
- Clinical impact (potential harm to patients)
- Scalability of impact (number of affected patients)
- Detection difficulty (how easily bias would be noticed)
- Ethical significance (alignment with medical ethics)

BS001, BS003, and BS005 were identified as highest priority based on combined risk assessment.

## Metrics Implementation

### Implemented Metrics

| Metric | Definition | Results | Interpretation |
|--------|------------|---------|----------------|
| Need Satisfaction Gap | Difference in resource allocation for equal clinical need | 0.15 | 15% disparity in resource allocation for similar clinical needs |
| Prediction Calibration Error | Difference in calibration error across groups | 0.12 | 12% difference in risk prediction accuracy |
| Opportunity Ratio | Ratio of resource receipt probability for equal benefit potential | 0.82 | Disadvantaged groups receive 82% of resources compared to advantaged groups with same benefit potential |
| False Negative Rate Disparity | Difference in missed care opportunities | 0.09 | 9% higher rate of missed care opportunities for disadvantaged groups |
| ZIP Code Correlation | Correlation between ZIP code and priority score after controlling for clinical factors | 0.23 | ZIP code explains 23% of priority variation beyond clinical factors |

### Intersectional Analysis

Intersectional analysis revealed:

- Race × Geography: Rural minority patients faced 22% lower resource allocation for equal need
- Gender × Age: Older women faced 18% higher false negative rates in cardiovascular risk assessment
- Disability × Socioeconomic Status: Low-income patients with disabilities faced 25% lower opportunity ratio
- Multiple Chronic Conditions × Race: Minority patients with multiple conditions faced more fragmented resource allocation

## Identified Issues

1. **Clinical documentation quality** varied systematically by patient demographics
2. **Historical utilization patterns** reflected access barriers rather than true need
3. **Embedded biases in clinical risk scores** led to systematic underestimation for certain groups
4. **Quality of life assessments** devalued conditions more prevalent in certain populations
5. **Geographic features** created proxy discrimination against rural and disadvantaged urban communities
6. **Benefit assessment models** incorporated implicit value judgments about age and disability

## Ethical Analysis

The assessment included specific ethical analysis given healthcare context:

- **Justice Principles**: Analysis of distributive and procedural justice in resource allocation
- **Beneficence/Non-maleficence**: Assessment of differential harm potential across groups
- **Autonomy**: Evaluation of how patient preferences were incorporated
- **Transparency**: Assessment of explainability to patients and providers

## Interventions

Based on the assessment, the following interventions were implemented:

1. **Documentation Quality Standardization**: Implemented structured documentation protocols to reduce quality disparities
2. **Need Estimation Refinement**: Developed alternative need estimates less dependent on historical utilization
3. **Risk Score Recalibration**: Recalibrated clinical risk scores by demographic group
4. **Value Framework Adjustment**: Modified quality of life assessments to reduce disability and age bias
5. **Multi-objective Optimization**: Implemented explicit equity constraints alongside efficiency objectives
6. **Counterfactual Analysis**: Added counterfactual analysis of service utilization assuming no access barriers
7. **Systematic Review Triggers**: Implemented automatic review for cases with high disparity potential

## Results After Intervention

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Need Satisfaction Gap | 0.15 | 0.06 | 60% reduction |
| Prediction Calibration Error | 0.12 | 0.04 | 67% reduction |
| Opportunity Ratio | 0.82 | 0.94 | 67% improvement |
| False Negative Rate Disparity | 0.09 | 0.03 | 67% reduction |
| ZIP Code Correlation | 0.23 | 0.08 | 65% reduction |

Clinical outcomes demonstrated overall improvement with reduced disparities in:
- 30-day readmission rates across demographic groups
- Time to appropriate specialist referral
- Patient-reported outcome measures
- Care plan completion rates

## Health Equity Impact

The fairness interventions produced measurable health equity improvements:

1. **Reduced outcome disparities**: 35% reduction in outcome disparities for chronic condition management
2. **Improved access**: 28% increase in appropriate service utilization for historically underserved groups
3. **Increased patient satisfaction**: Significant improvements in satisfaction scores from minority patients
4. **Enhanced trust**: Improved trust metrics from community surveys
5. **Provider alignment**: Increased provider satisfaction with allocation recommendations

## Implementation Challenges

Several challenges emerged during implementation:

1. **Clinical autonomy concerns**: Some providers expressed concerns about algorithmic constraints on clinical judgment
2. **Data collection burden**: Enhanced documentation requirements initially increased clinician workload
3. **Explainability trade-offs**: More complex fairness mechanisms reduced simple explainability
4. **Local vs. system optimization**: Optimizing system-wide equity created perceived local inefficiencies
5. **Resource constraints**: Some equity interventions required additional resources

These challenges were addressed through:
- Clinician education and engagement
- Documentation workflow optimization
- Development of simplified explanation tools
- Transparent communication about equity goals
- Securing additional grant funding for equity initiatives

## Lessons Learned

1. **Healthcare equity requires multiple fairness definitions**: No single fairness definition adequately captured all relevant healthcare equity dimensions.

2. **Clinical and social factors interact complexly**: The interaction between clinical indicators and social determinants of health required nuanced modeling approaches.

3. **Stakeholder involvement was essential**: Clinical staff and patient representatives identified bias sources and practical implementation challenges that technical analysis alone missed.

4. **Documentation quality is a critical upstream factor**: Disparities in clinical documentation quality created downstream allocation biases that required upstream intervention.

5. **Explainability affects implementation success**: Clinician acceptance required clear explanation of fairness interventions and their clinical rationale.

6. **Ethical frameworks provided critical guidance**: Established healthcare ethics principles helped navigate complex trade-offs between fairness dimensions.

7. **Incremental improvement with monitoring works best**: Phased implementation with continuous monitoring provided better outcomes than attempting comprehensive change at once.

## Framework Effectiveness

The Fairness Audit Framework demonstrated particular value in healthcare through:

1. **Connecting historical healthcare disparities to technical features**: The explicit mapping from documented healthcare inequities to system features provided clear intervention targets.

2. **Multiple fairness definition approach**: The framework's support for multiple complementary fairness definitions accommodated healthcare's ethical complexity.

3. **Lifecycle perspective**: Identifying bias sources throughout the ML lifecycle revealed upstream data issues that would have been missed in a pure algorithmic focus.

4. **Stakeholder integration**: The structured approach to stakeholder engagement facilitated meaningful clinical and patient input.

5. **Ethical alignment**: The framework's flexibility allowed integration with healthcare-specific ethical frameworks.

## References

- [Agency for Healthcare Research and Quality. (2023). National Healthcare Disparities Report](https://ahrq-stage.ahrq.gov/sites/default/files/wysiwyg/research/findings/nhqrdr/2023nhqdr-introduction-rev.pdf)
- [World Health Organization. (2022). Ethics and Governance of Artificial Intelligence for Health](https://www.who.int/publications/i/item/9789240029200)
- [Obermeyer, Z., Powers, B., Vogeli, C., & Mullainathan, S. (2019). Dissecting racial bias in an algorithm used to manage the health of populations. Science](https://www.science.org/doi/10.1126/science.aax2342)
- [Institute of Medicine. (2003). Unequal Treatment: Confronting Racial and Ethnic Disparities in Health Care](https://www.ncbi.nlm.nih.gov/books/NBK220358/)