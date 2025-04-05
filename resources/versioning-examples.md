# Versioning Examples

This document provides practical examples of the versioning protocol in action, demonstrating how to properly version fairness assessments and track changes over time.

## Example 1: Initial Assessment Version

### Assessment Information

- **System Name**: TalentMatch AI
- **Assessment ID**: FAF-2025-03-002
- **Version**: 1.0
- **Date**: March 15, 2025

### VERSION.md File

```markdown
# Version Information

## Current Version
- Version Number: 1.0
- Release Date: 2025-03-15
- Lead Assessor: Alex Johnson

## Component Versions
| Component | Version |
|-----------|---------|
| Historical Context Assessment | 1.2.0 |
| Fairness Definition Selection | 1.3.0 |
| Bias Source Identification | 1.1.0 |
| Comprehensive Metrics | 1.4.0 |
| Integration Methodology | 1.2.0 |

## Version History
- v1.0: 2025-03-15 - Initial assessment
```

### Version Documentation in Executive Summary

```markdown
## Assessment Methodology

This assessment (FAF-2025-03-002 v1.0) follows the Comprehensive Assessment Workflow of the Fairness Audit Framework v1.3.0. The assessment uses current component versions as documented in VERSION.md.

All findings represent point-in-time analysis based on system functionality as of March 1, 2025. A reassessment is recommended if significant system changes occur or within 12 months, whichever comes first.
```

## Example 2: Minor Update Version

### Assessment Information

- **System Name**: TalentMatch AI
- **Assessment ID**: FAF-2025-03-002
- **Version**: 1.1
- **Date**: April 20, 2025

### VERSION.md File Update

```markdown
# Version Information

## Current Version
- Version Number: 1.1
- Release Date: 2025-04-20
- Lead Assessor: Alex Johnson

## Component Versions
| Component | Version |
|-----------|---------|
| Historical Context Assessment | 1.2.0 |
| Fairness Definition Selection | 1.3.0 |
| Bias Source Identification | 1.1.0 |
| Comprehensive Metrics | 1.4.1 | # Updated metrics component
| Integration Methodology | 1.2.0 |

## Version History
- v1.1: 2025-04-20 - Updated metrics implementation with intersectional analysis
- v1.0: 2025-03-15 - Initial assessment
```

### Change Log Entry

```markdown
## Version Change Log

### Version 1.1 (2025-04-20)
- **Author**: Alex Johnson
- **Change Type**: Update
- **Components Modified**: Metrics Implementation
- **Change Summary**: Added intersectional analysis examining gender×race and age×education level intersections
- **Rationale**: Initial stakeholder feedback indicated the need for deeper intersectional analysis
- **Impact Assessment**: Intersectional analysis revealed 12% higher disparity at the intersection of gender and race than was visible in single-dimension analysis, leading to one new critical recommendation
```

### Executive Summary Addendum

```markdown
## Assessment Updates

This document (v1.1) updates the original assessment (v1.0) from March 15, 2025. The update adds intersectional analysis examining gender×race and age×education level intersections.

Key findings from this update include:
1. Women of color face 12% higher disparity than was evident in single-dimension analysis
2. Older workers without advanced degrees face increased false negative rates

These findings have resulted in one additional critical recommendation (#7) and modification of the implementation priority for recommendation #3.

All other findings and recommendations from the original assessment remain valid.
```

## Example 3: Major Update Version

### Assessment Information

- **System Name**: TalentMatch AI
- **Assessment ID**: FAF-2025-03-002
- **Version**: 2.0
- **Date**: August 10, 2025

### VERSION.md File Update

```markdown
# Version Information

## Current Version
- Version Number: 2.0
- Release Date: 2025-08-10
- Lead Assessor: Taylor Smith

## Component Versions
| Component | Version |
|-----------|---------|
| Historical Context Assessment | 1.3.0 | # Updated component
| Fairness Definition Selection | 1.4.0 | # Updated component
| Bias Source Identification | 1.2.0 | # Updated component
| Comprehensive Metrics | 1.5.0 | # Updated component
| Integration Methodology | 1.3.0 | # Updated component

## Version History
- v2.0: 2025-08-10 - Major reassessment following system algorithm change
- v1.1: 2025-04-20 - Updated metrics implementation with intersectional analysis
- v1.0: 2025-03-15 - Initial assessment
```

### Change Log Entry

```markdown
## Version Change Log

### Version 2.0 (2025-08-10)
- **Author**: Taylor Smith
- **Change Type**: Major Reassessment
- **Reason for Major Version**: System algorithm changed from gradient boosting to deep learning architecture
- **Components Modified**: All components
- **Change Summary**: 
  - Historical Context: Added two new relevant patterns
  - Fairness Definitions: Added counterfactual fairness as third primary definition
  - Bias Sources: Complete reanalysis with new model architecture
  - Metrics: Implemented six new metrics appropriate for deep learning models
  - Integration: Updated cross-component analysis with new findings
- **Rationale**: Major system architecture change required comprehensive reassessment
- **Impact Assessment**: 
  - Overall fairness improved by approximately 25% across most metrics
  - New architecture eliminated three previous bias sources but introduced two new ones
  - Recommendations substantially revised with five previous items resolved and three new items added
```

### System Change Documentation

```markdown
## System Changes Prompting Reassessment

This major reassessment (v2.0) was triggered by the following system changes:
1. Algorithm architecture changed from gradient boosting to deep learning
2. Training dataset expanded by 40% with new data sources
3. Feature engineering approach completely revised
4. New post-processing fairness interventions implemented
5. Deployment context expanded to three new job categories

These changes were substantial enough to require a complete reassessment rather than an incremental update.
```

### Longitudinal Analysis

```markdown
## Longitudinal Analysis

### Fairness Metric Trends
| Metric | v1.0 | v1.1 | v2.0 | Trend |
|--------|------|------|------|-------|
| Demographic Parity | 0.76 | 0.76 | 0.91 | Significant Improvement |
| Equal Opportunity | 0.82 | 0.82 | 0.94 | Significant Improvement |
| False Negative Rate Disparity | 0.11 | 0.11 | 0.03 | Significant Improvement |
| Intersectional Disparity (Gender×Race) | - | 0.18 | 0.07 | Significant Improvement |

### Bias Source Evolution
| Bias Source | v1.0 Status | v2.0 Status |
|-------------|-------------|-------------|
| BS001: Training data underrepresentation | High Risk | Medium Risk |
| BS002: Proxy variables in features | High Risk | Resolved |
| BS003: Geographic feature bias | Medium Risk | Resolved |
| BS004: Career gap penalization | Medium Risk | Low Risk |
| BS005: Educational institution bias | High Risk | Medium Risk |
| BS006: Neural network representation bias | - | New - Medium Risk |
| BS007: Feature interaction opacity | - | New - High Risk |

### Recommendation Progress
- 5 recommendations from v1.0 fully implemented
- 2 recommendations from v1.0 partially implemented
- 3 new recommendations added in v2.0
```

## Example 4: Framework Component Update

### Framework Component Update Notification

```markdown
# Fairness Definition Selection Component Update

## Update Details
- **Component**: Fairness Definition Selection
- **Version**: Updated from v1.3.0 to v1.4.0
- **Release Date**: July 1, 2025
- **Compatibility**: Compatible with all other components v1.x.x

## What's Changed
- Added support for counterfactual fairness definitions
- Improved decision trees for selecting appropriate definitions in ranking systems
- Added new trade-off analysis templates for competing fairness definitions
- Enhanced documentation guidance for regulatory contexts

## Impact on Assessments
- **New Assessments**: Should use version 1.4.0
- **In-Progress Assessments**: Can continue with 1.3.0 or upgrade to 1.4.0
- **Completed Assessments**: No action needed unless reassessment occurs

## Updating Existing Assessments
If integrating this update into an existing assessment:
1. Increment assessment version (minor version update)
2. Document component version change in VERSION.md
3. Consider whether new counterfactual fairness options are relevant
4. If applicable, update fairness definition selection documentation
```

### Assessment Update Due to Framework Change

```markdown
## Component Update Integration

This assessment update from v1.1 to v1.2 integrates the new Fairness Definition Selection component (v1.4.0) released on July 1, 2025. The update adds consideration of counterfactual fairness, which is particularly relevant to this hiring system.

Key changes:
1. Added counterfactual fairness as a supplementary fairness definition
2. Updated trade-off analysis using new templates
3. Enhanced regulatory documentation for EEOC compliance

These changes do not alter the primary conclusions but strengthen the theoretical foundation and compliance documentation of the assessment.
```

## Example 5: Version Control for Assessment Templates

### Template Version Control

```markdown
# Assessment Plan Template

## Template Information
- **Template Name**: Assessment Plan
- **Version**: 2.1
- **Last Updated**: June 15, 2025
- **Changes From Previous Version**:
  - Added regulatory mapping section
  - Enhanced stakeholder engagement planning
  - Updated resource allocation guidelines
  - Added version control section

## Compatibility
- **Framework Version**: Compatible with Framework v1.3.x and above
- **Related Templates**: Works with Historical Context Report v2.0+
```

### Template Usage Documentation

```markdown
## Template Information

This assessment uses the following template versions:
- Assessment Plan: v2.1
- Historical Context Report: v2.0
- Fairness Definition Rationale: v1.5
- Bias Source Mapping: v2.2
- Metrics Implementation: v2.1
- Executive Summary: v1.8
- Intersectional Analysis: v1.3
- Limitations Acknowledgment: v1.4

All templates are compatible with Framework v1.3.2 currently in use.
```

## Example 6: Multi-Version Comparison for Continuous Improvement

### Multi-Version Metrics Comparison

```markdown
## TalentMatch AI Fairness Evolution

### Demographic Parity Ratio (Selection Rate Parity)
![Demographic Parity Trend](../resources/images/demographic_parity_trend.png)

| Version | Date | Value | Change | Catalyst for Change |
|---------|------|-------|--------|---------------------|
| v1.0 | 2025-03-15 | 0.76 | Baseline | Initial assessment |
| v1.1 | 2025-04-20 | 0.76 | No change | Added intersectional analysis only |
| v2.0 | 2025-08-10 | 0.91 | +0.15 | Algorithm change to deep learning |
| v2.1 | 2025-11-05 | 0.93 | +0.02 | Training data enhancements |
| v3.0 | 2026-03-20 | 0.96 | +0.03 | Comprehensive fairness interventions |

### Equal Opportunity Difference (Qualified Candidate Selection Parity)
![Equal Opportunity Trend](../resources/images/equal_opportunity_trend.png)

| Version | Date | Value | Change | Catalyst for Change |
|---------|------|-------|--------|---------------------|
| v1.0 | 2025-03-15 | 0.14 | Baseline | Initial assessment |
| v1.1 | 2025-04-20 | 0.14 | No change | Added intersectional analysis only |
| v2.0 | 2025-08-10 | 0.05 | -0.09 | Algorithm change to deep learning |
| v2.1 | 2025-11-05 | 0.04 | -0.01 | Training data enhancements |
| v3.0 | 2026-03-20 | 0.02 | -0.02 | Comprehensive fairness interventions |
```

### Assessment Maturity Evolution

```markdown
## Assessment Maturity Evolution

| Dimension | v1.0 | v2.0 | v3.0 |
|-----------|------|------|------|
| Historical Context Depth | Basic industry patterns | Enhanced with legal precedents | Comprehensive with quantitative evidence |
| Fairness Definitions | Two primary definitions | Three definitions with counterfactual | Multiple definitions with formal verification |
| Bias Source Coverage | Key lifecycle stages | All lifecycle stages | Lifecycle stages with interaction analysis |
| Metrics Implementation | Basic metrics suite | Expanded suite with validation | Comprehensive suite with causal analysis |
| Intersectional Analysis | None | Two key intersections | Comprehensive intersectional analysis |
| Stakeholder Engagement | Limited consultation | Structured engagement | Continuous participatory process |
| Documentation Quality | Standard templates | Enhanced documentation | Comprehensive with traceability |
| Validation Approach | Basic verification | Statistical validation | Formal verification with adversarial testing |
```

## Best Practices Summary

Based on these examples, follow these versioning best practices:

1. **Consistent Identification**: Use consistent identifiers (FAF-YYYY-MM-###) for all assessments
2. **Clear Version Numbering**: Use MAJOR.MINOR versioning with clear criteria for each
3. **Detailed Change Logs**: Document all changes with rationale and impact assessment
4. **Component Version Tracking**: Explicitly track which component versions are used
5. **Longitudinal Analysis**: Maintain trend analysis across versions when possible
6. **Impact Documentation**: Clearly document how changes affect findings and recommendations
7. **Template Version Control**: Track template versions used for each assessment
8. **Maturity Evolution**: Document how assessment quality evolves over time

## References

- IEEE Standard 7003-2023 for Algorithmic Bias Considerations
- ISO/IEC 24028:2020 Information technology — Overview of trustworthiness in artificial intelligence
- NIST AI Risk Management Framework: Documentation Guidance
- Global Financial Innovation Network (GFIN) Model Documentation Standards