# Monitoring Metrics and Thresholds

## Assessment Information

- **System Name**: [Name of AI system]
- **Assessment ID**: [Unique identifier: FAF-yyyy-mm-number]
- **Version**: [e.g., 1.0]
- **Date**: [Date of document creation]
- **Author**: [Name and role]

## Metrics Selection Rationale

[Explain the process and rationale for selecting the metrics below for continuous monitoring, referencing the initial fairness assessment, fairness definitions, and identified risks.]

## Core Fairness Metrics

| Metric ID | Name | Definition Link | Subgroups | Monitoring Threshold(s) | Alert Level | Rationale |
|-----------|------|-----------------|-----------|-------------------------|-------------|-----------|
| [M001] | [e.g., Equal Opportunity Difference] | [Link to definition/implementation] | [e.g., Gender, Race] | [e.g., > 0.05 change from baseline] | [Warning/Critical] | [Justification] |
| [M002] | [e.g., Demographic Parity Ratio] | [Link to definition/implementation] | [e.g., Age Group] | [e.g., < 0.85] | [Critical] | [Justification] |
| [M003] | [e.g., Calibration Error Disparity] | [Link to definition/implementation] | [e.g., Intersection: Gender x Race] | [e.g., > 10% relative increase] | [Warning] | [Justification] |

## Supporting Metrics (Data Drift, Model Performance)

| Metric ID | Name | Category | Monitoring Threshold(s) | Alert Level | Rationale |
|-----------|------|----------|-------------------------|-------------|-----------|
| [S001] | [e.g., Feature Distribution Shift (PSI)] | [Data Drift] | [e.g., PSI > 0.2 for key features] | [Warning] | [Justification] |
| [S002] | [e.g., Overall Accuracy] | [Model Performance] | [e.g., < 90% of baseline accuracy] | [Warning] | [Justification] |
| [S003] | [e.g., Prediction Confidence Drift] | [Model Behavior] | [e.g., Mean confidence change > 5%] | [Warning] | [Justification] |
| [S004] | [e.g., Input Data Volume Change] | [Data Integrity] | [e.g., > 20% deviation from expected] | [Info] | [Justification] |

## Threshold Definitions

[Provide detailed explanations for how thresholds were set, including statistical methods, regulatory requirements, or practical significance considerations.]

### Threshold Setting Methodology
- [Statistical Process Control details, if used]
- [Regulatory references, if applicable]
- [Stakeholder input summary]
- [Baseline variability analysis]

### Alert Level Definitions
- **Info**: [Circumstances triggering informational alerts]
- **Warning**: [Circumstances triggering warning alerts, requiring investigation]
- **Critical**: [Circumstances triggering critical alerts, potentially requiring immediate action]

## Statistical Validation Approach for Monitoring

[Describe the statistical methods used to distinguish genuine drift or threshold breaches from random noise in the monitoring process (e.g., control charts, significance testing over time windows).]

## Metrics Implementation Details

[Reference where the specific implementation details for these metrics can be found (e.g., code repository, Metrics Implementation Details template from the initial assessment).]

## Review and Update Schedule

- **Metrics Review Frequency**: [e.g., Quarterly, Annually]
- **Review Triggers**: [Events triggering metrics/threshold review]
- **Update Process**: [Procedure for updating metrics and thresholds]

---

## Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Monitoring Lead | | | |
| Data Science Lead | | | |
| Fairness Assessment Lead | | | |
| Compliance Officer | | | |