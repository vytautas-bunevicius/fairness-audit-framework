# Fairness Audit Framework: Integration Details

This document explains *how* the four main components of the framework connect and work together. It covers the flow of
information, the structure of that information, and how to analyze findings across components.

## 1. The Flow: How Information Connects Components

The framework follows a logical sequence where the output of one step becomes crucial input for the next:

1. **History Informs Definitions**: The [Historical Context Report](../../templates/assessment/historical-context.md)
   identifies past discrimination patterns relevant to the AI's task. This knowledge is essential for
   the [Fairness Definition Selection](../../templates/assessment/fairness-definition.md) step, helping you choose
   definitions that directly address those historical harms or risks. For example, knowing about historical redlining
   strongly suggests using fairness definitions that check for geographic or racial disparities in loan approvals.

2. **Definitions Guide Bias Search**:
   The [Fairness Definition Rationale](../../templates/assessment/fairness-definition.md) clarifies *what kind* of
   fairness you're aiming for. This focuses
   the [Bias Source Identification](../../templates/assessment/bias-source-mapping.md) step. If you chose "Equal
   Opportunity" (meaning equally qualified people should have equal success rates), you'll look more closely for bias
   sources that might incorrectly assess qualifications for different groups (e.g., biased training labels, proxies for
   qualifications). If you chose "Demographic Parity" (meaning different groups should have similar selection rates
   overall), you'll focus more on sources causing representation issues (e.g., sampling bias, feature proxies).

3. **Sources and Definitions Guide Measurement**:
   The [Bias Source Mapping](../../templates/assessment/bias-source-mapping.md) identifies *where* problems might exist,
   and the [Fairness Definition Rationale](../../templates/assessment/fairness-definition.md) defines *what* unfairness
   looks like. Together, they guide
   the [Metrics Implementation & Analysis](../../templates/assessment/metrics-implementation.md). You select metrics
   that can measure the chosen definitions and are sensitive to the identified bias sources. If biased training labels (
   a bias source) are a risk for achieving Equal Opportunity (a definition), you'd implement metrics like True Positive
   Rate difference between groups.

4. **Measurements Inform Understanding**:
   The [Metrics Implementation](../../templates/assessment/metrics-implementation.md) results provide quantitative data.
   These numbers are interpreted by relating them back to the
   likely [Bias Sources](../../templates/assessment/bias-source-mapping.md) and
   the [Historical Context](../../templates/assessment/historical-context.md). A measured disparity isn't just a number;
   the framework helps explain *why* it might be happening, connecting it to specific parts of the AI lifecycle and
   broader societal patterns. This understanding guides effective interventions.

## 2. Information Structure: What Gets Passed Along

While we use Markdown templates in the [templates/](../../templates/) directory for documentation, conceptually,
specific information packages link the steps. Understanding these helps ensure nothing gets lost.

* **From HCA to FDS**: A **List of Relevant Historical Patterns** including their description, relevance score, and the
  specific risks they pose to *this* AI system.
    * *Template containing this*: [historical-context.md](../../templates/assessment/historical-context.md)
* **From FDS to BSI & MIA**: A **Specification of Selected Fairness Definitions**, including their formal meaning, the
  rationale (linking back to history/values), and implementation needs.
    * *Template containing this*: [fairness-definition.md](../../templates/assessment/fairness-definition.md)
* **From BSI to MIA & Analysis**: A **Catalog of Prioritized Bias Sources**, detailing potential biases, where they
  occur in the lifecycle, their risk level, and which fairness definitions they might impact.
    * *Template containing this*: [bias-source-mapping.md](../../templates/assessment/bias-source-mapping.md)
* **From MIA to Analysis & Reporting**: **Detailed Metric Results**, including the metric values, statistical
  validation (like confidence intervals), breakdowns by group (disaggregation), intersectional results, and
  interpretation.
    * *Templates containing
      this*: [metrics-implementation.md](../../templates/assessment/metrics-implementation.md), [intersectional-analysis.md](../../templates/assessment/intersectional-analysis.md)

**(Note:** For technical teams building tools around this framework, defining these interfaces more formally, perhaps
using JSON schemas, would be beneficial. However, for manual assessments, the templates structure this information.)

## 3. Connecting the Dots: Cross-Component Analysis

The real value comes from looking across the components:

* **Consistency Check**: Do the pieces fit together? Are the metrics measuring the chosen definitions? Do the high-risk
  bias sources relate to the key historical patterns? Are there contradictions?
    * *How*: Review the links documented in each template. For example, check if the selection rationale in
      the [fairness-definition.md](../../templates/assessment/fairness-definition.md) template aligns with
      high-relevance patterns in the [historical-context.md](../../templates/assessment/historical-context.md) template.
* **Coverage Check**: Did we investigate the most important issues? Are the main historical risks addressed by the
  chosen definitions and metrics? Are the riskiest bias sources being measured?
    * *How*: Map high-priority items from HCA and BSI forward to FDS and MIA. Identify any major risks that weren't
      quantitatively assessed.
* **Root Cause Exploration**: *Why* are we seeing certain metric results? Can we trace a measured disparity back through
  a likely bias source identified earlier, which relates to a chosen definition and connects to a known historical
  pattern?
    * *How*: Start with a significant finding
      in [metrics-implementation.md](../../templates/assessment/metrics-implementation.md). Look up connected bias
      sources in [bias-source-mapping.md](../../templates/assessment/bias-source-mapping.md). Check if those sources
      relate to the relevant definition in [fairness-definition.md](../../templates/assessment/fairness-definition.md)
      and if that definition connects to patterns
      in [historical-context.md](../../templates/assessment/historical-context.md).

## 4. Managing the Process

* **Workflows**: Use the defined workflows in the [workflows/](../workflows/) directory to manage the sequence and
  ensure steps aren't missed.
* **Templates**: Use the templates in [templates/](../../templates/) consistently for standardized outputs that
  facilitate information flow and review.
* **Versioning**: Track assessment versions as described in [06-versioning-protocol.md](./06-versioning-protocol.md) to
  manage changes and updates effectively. When updating one component's output, consider the downstream impact and
  potentially update subsequent component documents and the overall assessment version.
* **Review**: Conduct reviews not just of individual component outputs, but specifically of the *connections* between
  them.

* **Domain/Regulatory Adaptation**: See [domain-adaptation.md](../../resources/guides/domain-adaptation.md). Tailor the
  focus based on industry (hiring, finance, health) and legal requirements (EU AI Act, EEOC, etc.).
* **Stakeholder Engagement & Intersectionality**:
  See [stakeholder-engagement.md](../../resources/guides/stakeholder-engagement.md) for methods on involving people
  effectively and analyzing overlapping identities.
* **(Optional) Causal Fairness**: For deeper root cause analysis,
  see [causal-fairness-analysis.md](../../resources/guides/causal-fairness-analysis.md).

By consciously linking these components through information flow and cross-analysis, the framework moves beyond a simple
checklist to a more integrated and insightful fairness assessment process.