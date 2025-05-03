# Rapid Assessment Workflow

This workflow provides a streamlined approach for initial fairness evaluation of AI systems. Use this workflow for screening assessments, lower-risk applications, or when time and resources are limited.

## Workflow Overview

<div align="center">
<img src="/resources/diagrams/rapid-workflow.png" alt="Rapid Assessment Workflow" width="600">
</div>

The rapid assessment follows this streamlined structure:

1. **Scoping & Context**
2. **Key Fairness Definitions**
3. **Critical Bias Analysis**
4. **Core Metrics Evaluation**
5. **Findings & Recommendations**

## Detailed Workflow Steps

### 1. Scoping & Context

**Objective**: Quickly identify system purpose, key stakeholders, and relevant historical context.

**Activities**:
- Complete the abbreviated "Assessment Plan Light" (focused on system purpose and stakeholders)
- Conduct targeted literature review of 3-5 key sources on historical discrimination in the domain
- Map highest-priority historical patterns to application risks
- Identify key protected attributes requiring evaluation

**Outputs**:
- Mini Historical Context Report (key patterns only)
- System Risk Profile

**Time Allocation**: 1-2 days

**Documentation**:
- Complete the *essential sections only* from the [Historical Context Report Template](../../templates/assessment/historical-context.md)

### 2. Key Fairness Definitions

**Objective**: Select 1-2 primary fairness definitions most relevant to the application context.

**Activities**:
- Apply the streamlined definition selection decision tree
- Focus on definitions addressing the highest-priority historical patterns
- Document clear rationale for selected definitions
- Identify the most critical potential tensions or trade-offs

**Outputs**:
- Primary Fairness Definition with rationale
- Secondary Definition (if needed)

**Time Allocation**: 0.5-1 day

**Documentation**:
- Complete the *core sections only* from the [Fairness Definition Rationale Template](../../templates/assessment/fairness-definition.md)

### 3. Critical Bias Analysis

**Objective**: Identify the highest-risk bias sources requiring immediate attention.

**Activities**:
- Conduct abbreviated lifecycle analysis focusing on highest-risk stages
- Identify 3-5 critical bias sources most likely to impact fairness
- Perform root cause analysis on these key sources
- Document direct connections to selected fairness definitions

**Outputs**:
- Critical Bias Source List
- Abbreviated Risk Assessment

**Time Allocation**: 1-2 days

**Documentation**:
- Complete the *priority sections only* from the [Bias Source Mapping Template](../../templates/assessment/bias-source-mapping.md)

### 4. Core Metrics Evaluation

**Objective**: Measure performance against selected fairness definitions using targeted metrics.

**Activities**:
- Implement 2-3 metrics directly aligned with primary fairness definitions
- Analyze results for key protected attributes
- Conduct basic significance testing
- Perform limited intersectional analysis on highest-priority intersections

**Outputs**:
- Core Metrics Results
- Initial Disparity Assessment

**Time Allocation**: 1-2 days

**Documentation**:
- Complete the *essential sections only* from the [Metrics Implementation Template](../../templates/assessment/metrics-implementation.md)

### 5. Findings & Recommendations

**Objective**: Synthesize key findings and provide actionable recommendations.

**Activities**:
- Connect metrics results to identified bias sources
- Prioritize 3-5 key findings based on risk and impact
- Develop targeted recommendations for highest-priority issues
- Document limitations of the rapid assessment

**Outputs**:
- Key Findings Report
- Prioritized Recommendations
- Assessment Limitations

**Time Allocation**: 1 day

**Documentation**:
- Complete the [Executive Summary Template](../../templates/assessment/executive-summary.md)
- Complete the [Limitations Acknowledgment Template](../../templates/assessment/limitations.md)

## Adaptation Guidelines

### When to Expand Assessment

Consider expanding to a comprehensive assessment if:

- Rapid assessment reveals critical fairness issues
- System impacts individuals in high-stakes domains
- Legal or regulatory requirements demand more thorough evaluation
- Significant disparities are found that require deeper analysis

### Domain-Specific Streamlining

Adjust focus based on domain requirements:

**Healthcare**:
- Prioritize patterns of access disparity and unequal treatment
- Focus on equal opportunity and individual fairness definitions
- Emphasize data representation and feature relevance bias sources

**Financial Services**:
- Prioritize historical exclusion patterns
- Focus on demographic parity and equalized odds
- Emphasize proxy discrimination and representation bias sources

**Content Recommendation**:
- Prioritize representation and visibility patterns
- Focus on exposure fairness definitions
- Emphasize feedback loop and presentation bias sources

## Quality Assurance

To maintain assessment quality while streamlining:

1. **Documentation Focus**: Prioritize quality over quantity in documentation
2. **Traceability**: Maintain clear connections between components even in abbreviated format
3. **Limitations**: Explicitly document what was excluded from the rapid assessment
4. **Follow-up Plan**: Include recommendations for areas requiring deeper assessment

## From Rapid to Comprehensive

To transition from rapid to comprehensive assessment:

1. Use rapid assessment outputs as foundation for comprehensive components
2. Expand historical context research beyond initial patterns
3. Consider additional fairness definitions beyond primary focus
4. Conduct thorough bias source analysis across all lifecycle stages
5. Implement comprehensive metrics suite with detailed statistical validation

## References

- [ACM FAccT 2024 Tutorial: Rapid Fairness Assessment Methods](https://facctconference.org/2024/acceptedtutorials)
- [Google's Responsible AI Toolkit: Model Cards for Rapid Documentation](https://www.tensorflow.org/responsible_ai/model_card_toolkit/guide)
- [Fairness Indicators: Lightweight Metrics for Initial Assessment](https://www.tensorflow.org/tfx/guide/fairness_indicators)
- [NIST AI RMF: Scalable Assessment Approaches](https://www.nist.gov/itl/ai-risk-management-framework)
- [Singapore's Model AI Governance Framework: Right-sized Assessment Approaches](https://www.imda.gov.sg/resources/press-releases-factsheets-and-speeches/press-releases/2024/public-consult-model-ai-governance-framework-genai)