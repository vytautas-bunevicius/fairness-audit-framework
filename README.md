# Fairness Audit Framework

A comprehensive methodology for systematic fairness assessment in AI systems.

## Overview

The Fairness Audit Framework addresses the fundamental challenge of systematically assessing fairness in AI systems. Without structured evaluation methodologies, fairness remains an aspirational goal rather than a verifiable property. This framework integrates four critical components into a cohesive audit system:

1.  **Historical Context Assessment** - Identifies and maps historical patterns of discrimination to specific AI application risks.
2.  **Fairness Definition Selection** - Provides guidance for selecting appropriate fairness definitions based on context.
3.  **Bias Source Identification** - Delivers systematic approaches for locating potential bias sources throughout the AI lifecycle.
4.  **Metrics Implementation & Analysis** - Establishes techniques for selecting, implementing, and interpreting fairness metrics.

This structured approach helps organizations determine whether their AI systems perpetuate historical biases, satisfy fairness requirements, or require intervention.

## Getting Started

**The main entry point to understanding and using this framework is `framework/core-guide.md`.**

This guide explains the core concepts, the four main components, how they integrate, and how to plan your assessment. It will direct you to:

1.  Choose an appropriate **workflow** from `framework/workflows/` based on your application context:
    *   `rapid-assessment.md` for initial screening.
    *   `comprehensive-assessment.md` for high-stakes applications.
    *   `regulatory-compliance.md` for documentation focused on compliance.
    *   `continuous-monitoring.md` for ongoing checks of deployed systems.
2.  Use the standardized **templates** from the `templates/` directory for documentation.
3.  Consult the detailed **guides** in `framework/` and `resources/` for implementation details, evaluation, versioning, interfaces, domain adaptation, advanced methods (causal fairness, intersectionality), stakeholder engagement, and regulatory compliance.
4.  Reference **case studies** in `case-studies/` for practical examples.

## Key Features

*   **Integrated Approach:** Connects historical context, definitions, bias sources, and metrics.
*   **Standardized Documentation:** Uses templates for consistent and verifiable assessments.
*   **Adaptable Workflows:** Offers processes for rapid, comprehensive, regulatory, and monitoring needs.
*   **Operational Support:** Includes guides for implementation, evaluation, and versioning.
*   **Advanced Methods:** Provides resources for intersectionality, causal fairness, and stakeholder co-design.

## References

This framework builds upon work from:

-   [Mehrabi, N., Morstatter, F., Saxena, N., Lerman, K., & Galstyan, A. (2021). A survey on bias and fairness in machine learning. ACM Computing Surveys](https://dl.acm.org/doi/10.1145/3457607)
-   [Barocas, S., Hardt, M., & Narayanan, A. (2023). Fairness and Machine Learning: Limitations and Opportunities](https://fairmlbook.org)
-   [Mitchell, S., Potash, E., Barocas, S., D'Amour, A., & Lum, K. (2021). Algorithmic fairness: Choices, assumptions, and definitions. Annual Review of Statistics and Its Application](https://www.annualreviews.org/doi/10.1146/annurev-statistics-042720-125902)
-   [IEEE Standard 7003-2023 for Algorithmic Bias Considerations](https://sagroups.ieee.org/7003/)
-   NIST AI Risk Management Framework, EU AI Act, and other relevant standards.

## License

This project is released under the [Unlicense](https://unlicense.org/). See the `LICENSE` file.
