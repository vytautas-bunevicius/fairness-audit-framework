# Component Interfaces

This document defines the standardized interfaces between components in the Fairness Audit Framework, enabling consistent integration regardless of specific implementation details.

## Interface Design Principles

The component interfaces follow these key principles:

1. **Standardization**: Consistent data formats and exchange patterns
2. **Independence**: Components can be updated independently
3. **Completeness**: All necessary information is included in exchanges
4. **Traceability**: Elements maintain identifiers for cross-component references
5. **Extensibility**: Formats allow for domain-specific extensions

## Component Interface Specifications

### 1. Historical Context Assessment → Fairness Definition Selection

#### Output: Historical Pattern Registry

```json
{
  "assessment_id": "HCA-2025-04-001",
  "version": "1.0",
  "timestamp": "2025-04-05T14:30:00Z",
  "domain": "employment",
  "patterns": [
    {
      "pattern_id": "HP001",
      "name": "Gender discrimination in technical roles",
      "description": "Historical pattern of discrimination against women in technical hiring and advancement",
      "relevance_score": 0.85,
      "evidence": [
        {
          "evidence_id": "E001",
          "type": "research_study",
          "citation": "Journal of Applied Psychology (2023)",
          "summary": "Technical hiring audit showing 35% lower callback rates for equivalent female candidates"
        },
        {
          "evidence_id": "E002",
          "type": "legal_precedent",
          "citation": "EEOC v. Tech Corporation (2022)",
          "summary": "Settlement over systematic discrimination in technical roles"
        }
      ],
      "application_risks": [
        {
          "risk_id": "R001",
          "risk_type": "data_representation",
          "description": "Underrepresentation of women in training data",
          "severity": "high"
        },
        {
          "risk_id": "R002",
          "risk_type": "feature_bias",
          "description": "Gendered language in credential descriptions",
          "severity": "medium"
        }
      ],
      "affected_groups": ["Women", "Non-binary individuals"],
      "remediation_history": [
        {
          "approach": "Blind resume screening",
          "effectiveness": "Partial - reduced but did not eliminate disparity",
          "limitations": "Did not address interview stage disparities"
        }
      ]
    }
  ],
  "limitations": {
    "data_gaps": ["Limited evidence on non-binary individuals", "Geographic focus on US/Europe"],
    "confidence": "Medium-high based on consistent patterns across multiple sources"
  }
}
```

#### Interface Requirements

1. **Mandatory Fields**: pattern_id, name, description, relevance_score, application_risks
2. **Optional Fields**: evidence, affected_groups, remediation_history, limitations
3. **Relevance Scoring**: 0.0 (irrelevant) to 1.0 (highly relevant) with justification
4. **Minimum Patterns**: At least 3 historical patterns must be documented
5. **Risk Mapping**: Each pattern must map to at least one specific application risk

### 2. Fairness Definition Selection → Bias Source Identification

#### Output: Fairness Definition Specification

```json
{
  "assessment_id": "FDS-2025-04-001",
  "version": "1.0",
  "timestamp": "2025-04-06T10:15:00Z",
  "domain": "employment",
  "selected_definitions": [
    {
      "definition_id": "FD003",
      "name": "Equal opportunity",
      "formal_description": "Equal true positive rates across protected groups",
      "mathematical_formulation": "P(Ŷ=1|Y=1,A=0) = P(Ŷ=1|Y=1,A=1)",
      "selection_rationale": "Addresses historical pattern HP001 by ensuring qualified candidates have equal chances",
      "historical_patterns": ["HP001", "HP004"],
      "implementation_requirements": [
        {
          "requirement_id": "IR001",
          "type": "data_access",
          "description": "Access to protected attribute information for assessment"
        },
        {
          "requirement_id": "IR002",
          "type": "ground_truth",
          "description": "Labels for qualification assessment independent of hiring decisions"
        }
      ],
      "applicable_metrics": ["Equal opportunity difference", "Recall parity ratio"],
      "priority_level": "primary"
    }
  ],
  "considered_alternatives": [
    {
      "definition_id": "FD001",
      "name": "Demographic parity",
      "formal_description": "Equal selection rates across protected groups",
      "rejection_rationale": "Could force selection of less qualified candidates in context where qualification differences may exist"
    }
  ],
  "trade_off_analysis": {
    "fairness_accuracy_tradeoff": {
      "description": "Equal opportunity allows for accuracy optimization within fairness constraints",
      "acceptable_accuracy_reduction": "3-5%"
    },
    "competing_definitions": [
      {
        "definitions": ["Equal opportunity", "Predictive parity"],
        "tension": "Cannot generally satisfy both simultaneously with unbalanced base rates",
        "prioritization": "Equal opportunity prioritized given historical discrimination pattern"
      }
    ]
  },
  "limitations": {
    "measurement_challenges": "Requires accurate labels for true qualification",
    "contextual_constraints": "Most applicable to binary classification settings"
  }
}
```

#### Interface Requirements

1. **Mandatory Fields**: definition_id, name, formal_description, selection_rationale, implementation_requirements
2. **Optional Fields**: mathematical_formulation, considered_alternatives, trade_off_analysis
3. **Minimum Definitions**: At least one primary definition must be selected
4. **Historical Connection**: Each selected definition must reference at least one historical pattern
5. **Trade-off Documentation**: When multiple definitions are selected, trade-offs must be explicitly documented

### 3. Bias Source Identification → Comprehensive Metrics

#### Output: Bias Source Catalog

```json
{
  "assessment_id": "BSI-2025-04-001",
  "version": "1.0",
  "timestamp": "2025-04-07T16:45:00Z",
  "domain": "employment",
  "identified_sources": [
    {
      "source_id": "BS005",
      "name": "Sampling bias in training data",
      "description": "Underrepresentation of certain demographic groups in training data",
      "lifecycle_stage": "Data collection",
      "technical_manifestation": "Lower representation percentages for protected groups in training samples",
      "risk_assessment": {
        "likelihood": "High",
        "impact": "Severe",
        "priority": "Critical",
        "justification": "Historical hiring data reflects past discriminatory patterns"
      },
      "fairness_definitions_affected": [
        {
          "definition_id": "FD003",
          "impact_description": "Undermines equal opportunity by learning from biased historical decisions"
        }
      ],
      "detection_methods": [
        {
          "method_id": "DM001",
          "name": "Representation analysis",
          "description": "Statistical comparison of group representation in training data vs. population"
        }
      ],
      "mitigation_strategies": [
        {
          "strategy_id": "MS001",
          "name": "Data augmentation",
          "description": "Generate synthetic samples for underrepresented groups",
          "implementation_complexity": "Medium",
          "effectiveness_evidence": "Research shows 40-60% reduction in opportunity gaps"
        }
      ],
      "connected_patterns": ["HP001", "HP002"]
    }
  ],
  "systematic_analysis": {
    "methodology": "FMEA-based risk assessment with lifecycle stage mapping",
    "coverage": {
      "lifecycle_stages_analyzed": ["Data collection", "Data preparation", "Feature engineering", "Model training", "Deployment"],
      "gaps_or_limitations": "Limited analysis of feedback loop risks due to pre-deployment stage"
    }
  },
  "prioritization": {
    "criteria": ["Severity", "Likelihood", "Mitigation feasibility"],
    "high_priority_sources": ["BS001", "BS005", "BS008"],
    "rationale": "Focusing on highest impact sources with feasible mitigation strategies"
  }
}
```

#### Interface Requirements

1. **Mandatory Fields**: source_id, name, description, lifecycle_stage, risk_assessment, fairness_definitions_affected
2. **Optional Fields**: detection_methods, mitigation_strategies, connected_patterns
3. **Lifecycle Coverage**: Bias sources must span multiple ML lifecycle stages
4. **Definition Connection**: Each bias source must connect to at least one fairness definition
5. **Prioritization**: Sources must be prioritized with explicit criteria and rationale

### 4. Comprehensive Metrics → Integration & Analysis

#### Output: Metrics Implementation Package

```json
{
  "assessment_id": "CMP-2025-04-001",
  "version": "1.0",
  "timestamp": "2025-04-08T11:30:00Z",
  "domain": "employment",
  "implemented_metrics": [
    {
      "metric_id": "M012",
      "name": "Equal opportunity difference",
      "category": "Classification fairness",
      "associated_definition": "FD003",
      "formula": "TPR_group_a - TPR_group_b",
      "implementation_details": {
        "code_reference": "compute_equal_opportunity.py",
        "statistical_approach": "95% bootstrap confidence intervals",
        "data_requirements": "Protected attributes and ground truth labels required"
      },
      "results": {
        "value": 0.15,
        "confidence_interval": [0.11, 0.19],
        "reference_threshold": 0.05,
        "interpretation": "15% disparity in selection rates between qualified candidates across groups",
        "threshold_assessment": "Exceeds acceptable threshold"
      },
      "disaggregated_results": [
        {
          "slice_definition": "Gender: Women vs Men",
          "value": 0.15
        },
        {
          "slice_definition": "Race: Underrepresented vs Majority",
          "value": 0.12
        },
        {
          "slice_definition": "Intersectional: Women from underrepresented groups vs Others",
          "value": 0.22
        }
      ],
      "bias_source_connection": {
        "primary_source": "BS005",
        "evidence": "Disparities correlate strongly with training data representation imbalances"
      }
    }
  ],
  "metric_selection_rationale": {
    "alignment_with_definitions": "Metrics selected to measure each selected fairness definition",
    "coverage_justification": "Combination of metrics addresses both group and subgroup fairness",
    "measurement_limitations": "Potential confounding factors in qualification assessment"
  },
  "intersectional_analysis": {
    "approach": "Disaggregated measurement across demographic intersections",
    "key_findings": "Compounding disadvantages identified at gender x race intersections",
    "limitations": "Small sample sizes for some intersectional groups"
  },
  "significance_assessment": {
    "statistical_approach": "Bootstrap confidence intervals with multiple hypothesis correction",
    "significant_disparities": ["Gender: Equal opportunity", "Race x Gender: Equal opportunity"],
    "confidence_level": "95%"
  }
}
```

#### Interface Requirements

1. **Mandatory Fields**: metric_id, name, category, associated_definition, formula, results
2. **Optional Fields**: implementation_details, disaggregated_results, bias_source_connection
3. **Statistical Validation**: All metrics must include confidence intervals or significance assessments
4. **Intersectional Analysis**: At least one intersectional dimension must be analyzed
5. **Interpretation**: Each metric must include result interpretation with reference thresholds

## Cross-Component Analysis Interface

For integrated analysis across components, a Cross-Component Analysis package combines insights:

```json
{
  "assessment_id": "CCA-2025-04-001",
  "version": "1.0",
  "timestamp": "2025-04-09T14:00:00Z",
  "domain": "employment",
  "integrated_findings": [
    {
      "finding_id": "IF001",
      "title": "Gender disparity in technical hiring opportunities",
      "description": "Qualified female candidates have 15% lower selection rates",
      "severity": "High",
      "evidence_chain": {
        "historical_pattern": "HP001",
        "fairness_definition": "FD003",
        "bias_source": "BS005",
        "metric_result": "M012"
      },
      "recommended_actions": [
        {
          "action_id": "RA001",
          "description": "Training data augmentation to balance gender representation",
          "implementation_complexity": "Medium",
          "expected_impact": "40-60% reduction in opportunity gap"
        }
      ]
    }
  ],
  "consistency_analysis": {
    "alignment_assessment": "Strong alignment between historical patterns and measured disparities",
    "gaps_identified": "Career gap handling identified in bias source analysis but not fully captured in metrics"
  },
  "impact_analysis": {
    "business_impact": "Current approach may exclude qualified candidates and reduce talent diversity",
    "ethical_impact": "Perpetuates historical patterns of exclusion in technical roles",
    "legal_risk": "Potential disparate impact liability under EEOC guidelines"
  }
}
```

## Interface Extensions

### Domain-Specific Extensions

For domain customization, each interface includes extension points:

1. **Domain Attributes**: Domain-specific attributes can be added to any component
2. **Custom Metrics**: Domain-relevant metrics can be added to the metrics package
3. **Specialized Evidence**: Domain-specific evidence types can be added to historical patterns

### Versioning and Change Management

Each interface includes versioning to manage changes:

1. **Version Tracking**: All components include version numbers and timestamps
2. **Dependency Documentation**: Each component references specific versions of prior components
3. **Change Impact**: When updating components, downstream impacts are explicitly documented

## Interface Implementation Guidelines

For consistent implementation:

1. **Data Schema Validation**: Use JSON Schema validation to ensure interface compliance
2. **Naming Conventions**: Follow consistent ID patterns across components
3. **Documentation Requirements**: Each interface element includes description fields
4. **Enumeration Standards**: Use standard enumerations for fields like severity, priority
5. **Reference Preservation**: Maintain consistent references across components

## References

- [IEEE Standard 7003-2023 for Algorithmic Bias Considerations](https://standards.ieee.org/ieee/7003/10789/)
- [W3C Data Catalog Vocabulary (DCAT)](https://www.w3.org/TR/vocab-dcat-3/)
- [ISO/IEC 25012:2008 Data Quality Model](https://www.iso.org/standard/35736.html)
- [NIST AI Risk Management Framework (AI RMF)](https://www.nist.gov/itl/ai-risk-management-framework)
- [ML Commons Bias and Fairness Working Group Standards](https://mlcommons.org/en/groups/research-bias-fairness/)