# Stakeholder Co-design Methodology for AI Fairness

This document provides a structured approach for meaningful stakeholder engagement throughout the fairness assessment process, with specific methodologies for collaborative fairness definition development, power dynamics management, and integration of diverse perspectives.

## Why Stakeholder Co-design Matters

Traditional approaches to AI fairness often rely primarily on technical metrics and expert evaluations, potentially missing critical perspectives from affected communities and end-users. Co-design represents a more participatory approach that:

1. **Surfaces lived experiences** of discrimination and bias that might be missed by technical analysis
2. **Incorporates diverse perspectives** on what constitutes "fairness" in specific contexts
3. **Builds legitimacy and trust** by involving affected communities in the assessment process
4. **Identifies potential harms** that technical experts might not anticipate
5. **Leads to more effective interventions** by incorporating practical knowledge from stakeholders

## Stakeholder Identification and Mapping

### Comprehensive Stakeholder Mapping

Begin with a systematic identification of all relevant stakeholders:

#### 1. Primary Stakeholder Categories

| Category | Description | Examples |
|----------|-------------|----------|
| **Directly Affected** | Individuals subject to the AI system's decisions | Loan applicants, job candidates, patients |
| **System Operators** | Those who implement or use the system | HR professionals, loan officers, clinicians |
| **System Developers** | Those who build or maintain the system | Data scientists, engineers, product managers |
| **Domain Experts** | Those with specialized domain knowledge | Industry experts, academic researchers |
| **Advocacy Groups** | Organizations representing affected communities | Civil rights organizations, consumer advocacy groups |
| **Regulators** | Entities with regulatory oversight | Government agencies, compliance officers |

#### 2. Stakeholder Analysis Matrix

For each identified stakeholder group, assess:

| Dimension | Description | Assessment Scale |
|-----------|-------------|------------------|
| **Impact Level** | How significantly the stakeholder is affected by the system | High/Medium/Low |
| **Influence Level** | How much power the stakeholder has over the system | High/Medium/Low |
| **Fairness Knowledge** | Stakeholder's expertise in fairness concepts | High/Medium/Low |
| **Domain Knowledge** | Stakeholder's expertise in the application domain | High/Medium/Low |
| **Representation Need** | Priority for including this stakeholder perspective | Essential/Important/Helpful |

#### 3. Intersectional Representation

Ensure representation across relevant demographic dimensions:
- Gender identity
- Race and ethnicity
- Age groups
- Disability status
- Socioeconomic status
- Geographic location
- Educational background
- Other context-specific dimensions

#### 4. Power Mapping

Map power relationships between stakeholders to identify:
- Power imbalances that need to be managed
- Stakeholders whose voices may be marginalized
- Gatekeepers who control access to certain stakeholders
- Potential conflicts of interest

**Template for Power Mapping**:
```
## Power Dynamics Analysis

| Stakeholder Group | Power Level | Power Source | Potential Impact on Process | Mitigation Strategy |
|-------------------|-------------|--------------|----------------------------|---------------------|
| [Group name] | [High/Medium/Low] | [Organizational, economic, knowledge-based, etc.] | [How this might affect participation] | [Approach to balance power] |
```

## Co-design Workshop Methodologies

### Workshop Design Principles

Effective co-design workshops for fairness assessment should:

1. **Be accessible** to participants with diverse backgrounds and abilities
2. **Balance structure and flexibility** to ensure productivity while allowing emergent insights
3. **Use multiple modalities** to accommodate different communication styles
4. **Explicitly address power dynamics** to ensure all voices are heard
5. **Connect directly to assessment components** to ensure actionable outcomes

### Workshop Templates

#### 1. Historical Context Co-design Workshop

**Purpose**: Identify and validate relevant historical patterns of discrimination

**Duration**: 3-4 hours

**Participants**: 10-15 participants from directly affected communities, advocacy organizations, domain historians, and system operators

**Preparation**:
- Pre-reading on historical discrimination in the domain
- Collection of personal experiences from participants (optional)
- Preparation of example historical patterns

**Agenda**:

| Time | Activity | Description |
|------|----------|-------------|
| 30 min | Introduction | Welcome, introductions, explain purpose and process |
| 45 min | Historical Pattern Identification | Small group work to identify patterns of discrimination relevant to the domain |
| 30 min | Pattern Sharing | Groups present identified patterns |
| 15 min | Break | |
| 45 min | Pattern Validation | Dot voting and discussion to validate and prioritize patterns |
| 45 min | Application Risk Mapping | Map patterns to system features and decisions |
| 30 min | Wrap-up | Summarize findings, explain next steps |

**Materials**:
- Large posters or digital whiteboards
- Post-it notes in multiple colors
- Voting dots
- Pattern documentation templates

**Documentation Template**:
```
## Historical Pattern Documentation

### Pattern: [Name]

#### Description
[Comprehensive description of the pattern]

#### Evidence Sources
[Sources that document this pattern]

#### Personal Experiences
[Anonymous experiences shared by participants - with permission]

#### Pattern Validation
[Number of validation votes from participants]

#### Application Risks
[Identified risks for the AI system]

#### Priority Level
[Determined by group consensus]
```

#### 2. Fairness Definition Workshop

**Purpose**: Develop shared understanding of fairness definitions and select appropriate definitions for the context

**Duration**: 3-4 hours

**Participants**: 10-15 participants including directly affected individuals, system operators, data scientists, ethicists, legal experts

**Preparation**:
- Pre-reading on fairness definitions in simple language
- Collection of fairness concerns from participants
- Preparation of fairness definition examples relevant to the domain

**Agenda**:

| Time | Activity | Description |
|------|----------|-------------|
| 30 min | Introduction | Welcome, introductions, explain fairness definitions |
| 45 min | Fairness Values Elicitation | Small group discussions on what fairness means in this context |
| 30 min | Value Sharing | Groups present their fairness values |
| 15 min | Break | |
| 45 min | Definition Evaluation | Facilitated discussion of predefined fairness definitions against values |
| 45 min | Trade-off Analysis | Structured activity to explore trade-offs between definitions |
| 30 min | Consensus Building | Work toward consensus on primary fairness definitions |

**Materials**:
- Visual representations of fairness definitions
- Trade-off analysis worksheet
- Scenarios for discussion
- Definition selection matrix

**Documentation Template**:
```
## Fairness Definition Co-Design

### Values Identified
[List of fairness values identified by participants]

### Definition Evaluation
| Definition | Strengths | Concerns | Alignment with Values | Overall Support |
|------------|-----------|----------|----------------------|----------------|
| [Definition name] | [Perceived strengths] | [Concerns raised] | [High/Medium/Low] | [Strong/Mixed/Low] |

### Key Trade-offs Identified
[Description of trade-offs discussed and how they were resolved]

### Selected Definitions
[Definitions selected with rationale]

### Dissenting Perspectives
[Documentation of alternative viewpoints not reflected in final selection]
```

#### 3. Bias Source Identification Workshop

**Purpose**: Identify potential sources of bias throughout the system lifecycle

**Duration**: 4 hours

**Participants**: 12-18 participants including affected individuals, domain experts, system developers, data scientists

**Preparation**:
- System documentation accessible to non-technical participants
- Examples of bias sources in similar systems
- Pre-workshop interviews with key stakeholders

**Agenda**:

| Time | Activity | Description |
|------|----------|-------------|
| 30 min | Introduction | Welcome, introductions, explain bias source framework |
| 60 min | Lifecycle Stage Analysis | Rotating small groups analyze different lifecycle stages for bias |
| 30 min | Break | |
| 45 min | Pattern Sharing | Groups present identified bias sources |
| 45 min | Risk Assessment | Collectively assess risk level of identified sources |
| 30 min | Mitigation Brainstorming | Generate initial ideas for addressing priority sources |
| 30 min | Wrap-up | Summarize findings, explain next steps |

**Materials**:
- Lifecycle stage posters
- Bias source identification templates
- Risk assessment matrix
- Mitigation idea cards

**Documentation Template**:
```
## Bias Source Co-Identification

### Bias Source: [Name]

#### Description
[Comprehensive description of the bias source]

#### Lifecycle Stage
[Where in the AI lifecycle this bias occurs]

#### Identification Method
[How this source was identified]

#### Stakeholder Concerns
[Specific concerns raised by stakeholders]

#### Supporting Evidence
[Evidence supporting this as a bias source]

#### Risk Assessment
| Likelihood | Impact | Detectability | Overall Risk |
|------------|--------|---------------|--------------|
| [H/M/L] | [H/M/L] | [H/M/L] | [Critical/High/Medium/Low] |

#### Mitigation Ideas
[Initial ideas for addressing this source]
```

#### 4. Metrics Review Workshop

**Purpose**: Review implemented metrics and interpret results for fairness assessment

**Duration**: 3 hours

**Participants**: 10-15 participants including affected individuals, system operators, data scientists, domain experts

**Preparation**:
- Preparation of metric results in accessible formats
- Development of scenario-based discussions using the metrics
- Compilation of potential intervention options

**Agenda**:

| Time | Activity | Description |
|------|----------|-------------|
| 30 min | Introduction | Welcome, introductions, explain metrics and results |
| 45 min | Metric Interpretation | Small group interpretation of metric results |
| 30 min | Interpretation Sharing | Groups share their interpretations |
| 15 min | Break | |
| 45 min | Intervention Discussion | Discuss potential interventions based on metrics |
| 30 min | Prioritization | Collectively prioritize interventions |
| 15 min | Wrap-up | Summarize findings, explain next steps |

**Materials**:
- Visual displays of metric results
- Interpretation worksheets
- Intervention cards
- Prioritization matrix

**Documentation Template**:
```
## Metrics Interpretation Co-Analysis

### Metric: [Name]

#### Technical Definition
[Simple explanation of the metric]

#### Results
[Summary of measured results]

#### Stakeholder Interpretations
[Range of interpretations offered by stakeholders]

#### Points of Consensus
[Areas where interpretations aligned]

#### Points of Divergence
[Areas where interpretations differed]

#### Recommended Interventions
[Interventions prioritized by the group]

#### Implementation Considerations
[Practical considerations for implementing interventions]
```

## Facilitation Techniques for Equitable Participation

### Power Balancing Methods

To address power imbalances during co-design activities:

#### 1. **Structured Turn-Taking**

- **Round Robin**: Ensure everyone speaks in turn before anyone speaks twice
- **Progressive Stack**: Prioritize voices from marginalized groups
- **Talking Token**: Use physical objects that must be held to speak
- **Time Allocation**: Ensure balanced speaking time across participants

#### 2. **Anonymous Input Methods**

- **Anonymous Sticky Notes**: Allow written contributions without attribution
- **Digital Polling**: Use anonymous polling tools for sensitive topics
- **Suggestion Box**: Provide physical or digital means for anonymous feedback
- **Pre-workshop Surveys**: Collect input before the workshop anonymously

#### 3. **Group Composition Strategies**

- **Homogeneous Breakouts**: Create safe spaces for similar stakeholders to speak freely
- **Balanced Mixed Groups**: Ensure diversity within each small group
- **Rotating Membership**: Change group composition throughout the workshop
- **Role Assignment**: Assign specific roles (facilitator, note-taker) to different participants

#### 4. **Facilitation Interventions**

- **Gentle Interruption**: "Thank you for that point. Let's hear from someone who hasn't spoken yet."
- **Direct Invitation**: "I'd like to hear what [person] thinks about this."
- **Reflection Prompts**: "Let's take a moment to reflect on what we've heard so far."
- **Process Check**: "Let's check how we're doing with ensuring everyone is being heard."

#### 5. **Physical and Temporal Space Management**

- **Accessible Venues**: Ensure physical spaces accommodate all participants
- **Flexible Timing**: Offer multiple session times to accommodate different schedules
- **Remote Options**: Provide hybrid participation options
- **Comfort Breaks**: Schedule regular breaks for accessibility needs

### Creating Psychological Safety

To create an environment where all participants feel safe contributing:

1. **Establish Clear Ground Rules**:
   - Confidentiality boundaries
   - Respectful disagreement norms
   - Right to pass on activities
   - Language expectations

2. **Acknowledge Positionality**:
   - Have facilitators acknowledge their own positionality
   - Recognize the diversity of experiences in the room
   - Validate different forms of expertise (including lived experience)

3. **Provide Multiple Participation Modes**:
   - Verbal discussion
   - Written contribution
   - Visual/drawing activities
   - Small group conversation
   - Individual reflection

4. **Responsive Facilitation**:
   - Pay attention to nonverbal cues of discomfort
   - Address harmful comments immediately
   - Privately check in with quieter participants
   - Adjust activities based on group dynamics

### Documentation and Attribution

For ethically documenting stakeholder input:

1. **Consent Protocols**:
   - Obtain explicit consent for how input will be used
   - Clarify attribution options (named, anonymous, group attribution)
   - Allow review of documentation before finalization
   - Provide withdrawal options for contributions

2. **Compensation Considerations**:
   - Acknowledge the value of stakeholder time and expertise
   - Provide appropriate compensation for participation
   - Consider differential impacts of participation on stakeholders

3. **Transparent Documentation**:
   - Clearly document which inputs influenced which decisions
   - Explain why some input was not incorporated
   - Share documentation back with participants
   - Maintain the nuance of stakeholder perspectives

## Reconciling Diverse Stakeholder Perspectives

### Structured Methods for Managing Disagreement

1. **Principled Negotiation**:
   - Focus on interests, not positions
   - Generate multiple options before deciding
   - Use objective criteria for evaluation
   - Separate people from the problem

2. **Value-Based Reconciliation**:
   - Identify underlying values behind positions
   - Look for higher-order values that may be shared
   - Find solutions that honor multiple values simultaneously
   - Acknowledge value trade-offs explicitly

3. **Consensus Building Approaches**:
   - Gradients of agreement voting (1-5 scale)
   - Consent-based decision making ("Can you live with this?")
   - Minority report documentation
   - Future commitment to revisit contested decisions

### Documentation of Divergent Perspectives

When full agreement cannot be reached:

1. **Perspective Documentation Matrix**:
   - Document each distinct perspective
   - Record the stakeholders holding each view
   - Note areas of partial agreement
   - Explain implications of each perspective

2. **Decision Rationale Documentation**:
   - Clearly explain the basis for final decisions
   - Document which perspectives influenced the decision
   - Acknowledge perspectives not reflected in the decision
   - Explain steps taken to mitigate concerns raised

**Template**:
```
## Divergent Perspectives Documentation

### Issue: [Topic with divergent views]

| Perspective | Stakeholders | Key Arguments | Supporting Evidence | Value Priorities |
|-------------|--------------|---------------|---------------------|------------------|
| [Position 1] | [Groups holding this view] | [Main arguments] | [Evidence cited] | [Underlying values] |
| [Position 2] | [Groups holding this view] | [Main arguments] | [Evidence cited] | [Underlying values] |

### Decision Resolution
[Final decision and rationale]

### Consideration of Alternative Views
[How alternative perspectives were considered]

### Mitigation Measures
[Steps taken to address concerns from non-prevailing perspectives]

### Future Commitments
[Plans to revisit or monitor the issue]
```

## Integration with Assessment Components

### Integrating Stakeholder Input into Framework Components

#### 1. Historical Context Assessment

**Integration Points**:
- Identification of relevant historical patterns
- Validation of pattern relevance
- Connection of patterns to system features
- Prioritization of historical contexts

**Documentation Requirements**:
- Source of stakeholder input (workshop, interview, etc.)
- Level of stakeholder consensus
- Specific contributions to pattern identification
- Stakeholder validation of expert-identified patterns

#### 2. Fairness Definition Selection

**Integration Points**:
- Value elicitation to inform definition selection
- Evaluation of proposed definitions
- Analysis of definition trade-offs
- Prioritization of competing definitions

**Documentation Requirements**:
- Values identified by different stakeholder groups
- Stakeholder evaluation of different definitions
- Areas of consensus and disagreement
- Basis for final selection incorporating stakeholder input

#### 3. Bias Source Identification

**Integration Points**:
- Identification of potential bias sources
- Validation of technical bias analysis
- Contribution of domain-specific bias knowledge
- Risk assessment of identified sources

**Documentation Requirements**:
- Bias sources identified by stakeholders vs. technical analysis
- Stakeholder risk assessment of bias sources
- Domain-specific insights on bias mechanisms
- Synthesis of technical and stakeholder perspectives

#### 4. Metrics Implementation

**Integration Points**:
- Metric selection and prioritization
- Threshold determination for acceptable disparities
- Interpretation of metric results
- Development of interventions based on metrics

**Documentation Requirements**:
- Stakeholder influence on metric selection
- Stakeholder views on appropriate thresholds
- Diverse interpretations of metric results
- Stakeholder-generated intervention ideas

### Structured Integration Process

For each framework component:

1. **Preparation Phase**:
   - Identify specific questions for stakeholder input
   - Prepare accessible materials on technical aspects
   - Identify appropriate engagement methods

2. **Engagement Phase**:
   - Conduct co-design activities
   - Document inputs systematically
   - Synthesize diverse perspectives

3. **Integration Phase**:
   - Explicitly map stakeholder input to framework decisions
   - Document how input influenced (or didn't influence) decisions
   - Validate integration with stakeholder representatives

4. **Feedback Phase**:
   - Share integration results with stakeholders
   - Collect feedback on quality of integration
   - Address concerns about misinterpretation

## Case Studies in Stakeholder Co-design

### Case Study 1: Healthcare Resource Allocation

#### Context
A hospital system was implementing an AI system to prioritize patients for specialized care resources.

#### Stakeholder Approach
- **Directly Affected**: Patients with diverse conditions, family advocates
- **System Operators**: Physicians, nurses, care coordinators
- **Domain Experts**: Medical ethicists, health equity researchers
- **Special Focus**: Patients with disabilities, rural patients, non-English speakers

#### Key Co-design Activities
1. **Patient Journey Mapping**: Collaborative creation of journey maps for different patient types
2. **Fairness Definition Workshop**: Multiple definitions emerged, with emphasis on "equalized needs satisfaction"
3. **Bias Source Walkthrough**: Clinical staff identified documentation quality disparities affecting resource allocation
4. **Ethics Committee Review**: Formal ethical analysis of fairness trade-offs

#### Integration Impact
1. Quality of life assessment methodologies were redesigned based on disability advocate input
2. Transportation barriers were incorporated into resource allocation decisions after rural patient input
3. Documentation protocols were standardized to reduce disparities after clinician identification of bias sources
4. Monitoring metrics were expanded to include patient-centered outcome measures

### Case Study 2: Employment Algorithm

#### Context
A technology company was developing an AI-based resume screening system for technical roles.

#### Stakeholder Approach
- **Directly Affected**: Job seekers from diverse backgrounds, career changers
- **System Operators**: HR professionals, hiring managers
- **Domain Experts**: Industrial psychologists, diversity experts
- **Special Focus**: Women in tech, older tech workers, self-taught programmers

#### Key Co-design Activities
1. **Barrier Identification Workshop**: Job seekers identified historical barriers in tech hiring
2. **HR Integration Workshop**: HR professionals designed integration with human review processes
3. **Resume Review Simulation**: Live testing of algorithm with diverse stakeholders reviewing results
4. **Intervention Co-creation**: Collaborative design of bias mitigation strategies

#### Integration Impact
1. Feature engineering was modified to address career gap penalties identified by women returners
2. Threshold adjustments were implemented for underrepresented groups based on equity considerations
3. Human review allocation was increased for edge cases based on HR input
4. Alternative credential pathways were created based on self-taught programmer feedback

## Best Practices Summary

1. **Begin early**: Involve stakeholders from the planning phase, not just for validation
2. **Diversify methods**: Use multiple engagement approaches to capture different perspectives
3. **Prioritize accessibility**: Ensure materials and activities are accessible to all participants
4. **Manage power explicitly**: Acknowledge and address power dynamics proactively
5. **Document thoroughly**: Create transparent records of all stakeholder contributions
6. **Close the loop**: Share how input was incorporated back with stakeholders
7. **Compensate fairly**: Recognize the value of stakeholder time and expertise
8. **Iterate continuously**: Treat co-design as an ongoing process, not a one-time event
9. **Balance structure and flexibility**: Have clear processes but allow for emergent insights
10. **Be willing to change**: Be prepared to significantly revise approaches based on stakeholder input

## References

- Sloane, M., Moss, E., Awomolo, O., & Forlano, L. (2020). Participation is not a Design Fix for Machine Learning. In Proceedings of the 37th International Conference on Machine Learning. https://arxiv.org/abs/2007.02423
- Delgado, F., Yang, S., Madaio, M., & Yang, Q. (2021). Stakeholder Participation in AI: Beyond "Add Diverse Stakeholders and Stir". In Proceedings of the 2021 AAAI/ACM Conference on AI, Ethics, and Society. https://doi.org/10.1145/3461702.3462612
- Harrington, C., Erete, S., & Piper, A. M. (2019). Deconstructing Community-Based Collaborative Design: Towards More Equitable Participatory Design Engagements. In Proceedings of the ACM on Human-Computer Interaction, 3(CSCW), 1-25. https://doi.org/10.1145/3359318
- Lee, M. K., Jain, A., Cha, H. J., Ojha, S., & Kusbit, D. (2019). Procedural Justice in Algorithmic Fairness: Leveraging Transparency and Outcome Control for Fair Algorithmic Mediation. In Proceedings of the ACM on Human-Computer Interaction, 3(CSCW), 1-26. https://doi.org/10.1145/3359284
- Madaio, M. A., Stark, L., Wortman Vaughan, J., & Wallach, H. (2020). Co-Designing Checklists to Understand Organizational Challenges and Opportunities around Fairness in AI. In Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems (pp. 1-14). https://doi.org/10.1145/3313831.3376445
- Holstein, K., Wortman Vaughan, J., Daumé III, H., Dudik, M., & Wallach, H. (2019). Improving Fairness in Machine Learning Systems: What Do Industry Practitioners Need? In Proceedings of the 2019 CHI Conference on Human Factors in Computing Systems (pp. 1-16). https://doi.org/10.1145/3290605.3300830
- Costanza-Chock, S. (2020). Design Justice: Community-Led Practices to Build the Worlds We Need. MIT Press. https://mitpress.mit.edu/9780262043458/design-justice/
- Wong-Villacres, M., DiSalvo, C., Kumar, N., & Disalvo, B. (2021). Culture in Action: Unpacking Capacities to Inform Assets-Based Design. In Proceedings of the 2021 CHI Conference on Human Factors in Computing Systems. https://doi.org/10.1145/3411764.3445257
- Srivastava, M., & Rossi, F. (2023). Beyond Participation: A Review of Methodologies for Pluralistic AI Governance. In Proceedings of the 2023 AAAI/ACM Conference on AI, Ethics, and Society. https://www.research.ed.ac.uk/en/publications/beyond-participation-a-review-of-methodologies-for-pluralistic-ai