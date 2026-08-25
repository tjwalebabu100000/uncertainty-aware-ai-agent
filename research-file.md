# Research File

## 1. Problem

The agent observes transaction details and available contextual evidence. It must select approve, question, examine, or stop because the true legitimacy of the transaction is not known.

## 2. Project Objective

The objective of this project is to design and test an AI agent that can make transaction decisions when information about whether a transaction is legitimate or fraudulent is incomplete.

The project will investigate whether explicitly modeling uncertainty and allowing the agent to escalate uncertain cases can reduce costly decision errors.

## 3. Agent Type

A decision-making AI agent for transactional fraud detection.

The agent will receive transaction evidence, estimate the probability of different hidden states, and select an action based on a decision policy and the costs of incorrect decisions.

## 4. Information We Do Not Have

The true legitimacy of a transaction is not directly observable when the agent makes its initial decision.

The agent may also lack information about:
- The actual identity of the person initiating the transaction
- Whether the account has been compromised
- The reason for an unusual transaction
- Whether unusual transaction behavior is legitimate or fraudulent
- Additional evidence that may become available after the initial decision

These assumptions will be investigated and refined through research and human discussions.

## 5. Technical Terms

### Fraud Detection
The task of identifying transactions that may be fraudulent.

### Anomaly Detection
The identification of transaction behaviour that differs substantially from expected or historical behaviour.

### Class Imbalance
A situation where legitimate transactions greatly outnumber fraudulent transactions. This means accuracy alone may be misleading when evaluating a fraud detection system.

### False Positive
A legitimate transaction that is incorrectly identified as fraudulent or suspicious.

### False Negative
A fraudulent transaction that is incorrectly treated as legitimate.

### Cost-Sensitive Learning
An approach where different types of errors are assigned different costs. This is important because approving a fraudulent transaction may be much more costly than unnecessarily reviewing or blocking a legitimate transaction.

### Concept Drift
Changes over time in the underlying behaviour or distribution of legitimate transactions and fraudulent transactions. Fraudsters may adapt their behaviour and customers may also change their transaction patterns.

### Probability Calibration
The process of making predicted probabilities meaningful as estimates of the likelihood of an outcome. This is important because our agent will use probabilities to make decisions.

### Decision Threshold
A boundary in the agent's estimated risk or probability that determines when the agent changes from one action to another.

### Human-in-the-Loop
A system design in which a human is involved in selected cases, particularly cases where the automated system is uncertain or where the consequences of an error are high.

### Label Uncertainty
A situation where the true fraud status of a transaction may not be immediately known or may remain unresolved.

### Sources Consulted

1. Reserve Bank of India — Master Directions on Digital Payment Security Controls.
2. Reserve Bank of India — Master Directions on Fraud Risk Management in Commercial Banks and All India Financial Institutions.
3. Lucas, Y. and Jurgovsky, J. — "Credit card fraud detection using machine learning: A survey."
4. Höppner, S., Baesens, B., Verbeke, W. and Verdonck, T. — "Instance-dependent cost-sensitive learning for detecting transfer fraud."
5. Vasquez, C. O., De Weerdt, J. and vanden Broucke, S. — "The Hidden Cost of Fraud: An Instance-Dependent Cost-Sensitive Approach for Positive and Unlabeled Learning."

## 6. Search Queries

Initial search queries:

- transaction fraud detection uncertainty
- cost-sensitive fraud detection
- Bayesian decision making fraud detection
- fraud detection probability calibration
- human in the loop fraud detection
- fraud detection false positive false negative cost
- transaction fraud detection anomaly detection
- uncertainty estimation fraud detection
- human review fraud detection systems
- fraud detection historical transaction patterns

## 7. Reddit Communities

### r/MachineLearning

Relevant for the technical and machine-learning perspective on fraud detection. Discussions include fraud classification, anomaly detection, class imbalance, reproducibility, production deployment, retraining and model evaluation.

Example discussions identified during research:
- Fraud detection problem involving labelled and unlabelled data.
- Reproducible machine learning for credit-card fraud detection.
- Production machine-learning systems for fraud detection and questions around retraining.

### r/fintech

Relevant for the payment-industry and production perspective. Discussions include real-time transaction monitoring, payment fraud, risk scoring, false positives, transaction velocity, device signals and operational challenges.

### r/FraudPrevention

Relevant for the fraud-operations perspective. Discussions cover AI-based fraud detection, anomaly detection, behavioural analytics, graph analytics and practical fraud-prevention approaches.

### Why These Communities Were Selected

The three communities provide complementary perspectives:

1. r/MachineLearning — technical and modeling perspective.
2. r/fintech — payment and product perspective.
3. r/FraudPrevention — operational fraud-prevention perspective.

These communities will be used to identify practical concerns, missing hidden states, useful evidence, costly errors and potential improvements to the agent design.

## 8. X Accounts

### @DataMiningApps

A KU Leuven data-science and analytics research group associated with research in fraud detection, data mining, Bayesian networks, model monitoring and backtesting.

Relevant because the account provides research-oriented material related to fraud analytics and machine learning.

### @finnonfraud

Frank McKenna's account, focused on fraud-industry topics.

Relevant because the project needs practitioner perspectives in addition to academic machine-learning research.

### Why These Accounts Were Selected

The accounts were selected to provide research and practitioner perspectives on fraud analytics rather than generic AI commentary.

Future research will record specific posts or discussions that influence the agent design.

## 9. Papers / Articles / Repositories / Datasets

To be researched and verified.

## 10. Research Questions

1. What information is most useful for distinguishing legitimate transactions from fraudulent transactions?
2. Which important hidden states are missing from the initial agent design?
3. Which incorrect transaction decision has the highest cost?
4. When should the agent ask for more information or escalate to a human?
5. Which evidence should cause the agent to change its belief about whether a transaction is fraudulent?
6. How should the agent behave when the available evidence is ambiguous?
7. Does explicitly modeling uncertainty improve decision-making compared with a simple rule-based baseline?
8. Does allowing human review reduce costly errors?

## 11. AI Prompts Used

To be recorded during the project.

## 12. Important AI Errors

To be recorded whenever an AI tool provides incorrect, unsupported, or misleading information.

## 13. Claims Requiring Verification

To be recorded during research.

## 14. Initial Agent Design

### Input

The agent initially observes:

- Transaction amount
- Transaction type
- Time
- Location
- Device status
- Merchant or beneficiary status
- Previous transaction patterns
- Recent transaction frequency
- Account history
- Previous fraud indicators

These inputs are initial assumptions and will be refined through research and human discussions.

### Hidden State

The true state of the transaction is hidden from the agent at the time of its initial decision.

Possible hidden states:

- Legitimate
- Fraudulent

### Belief

The agent will represent its belief about the hidden state using probabilities:

- P(Legitimate)
- P(Fraudulent)

The probabilities must sum to 100%.

### Actions

The agent can:

1. APPROVE — allow the transaction.
2. QUESTION — request additional information or confirmation.
3. EXAMINE — gather additional evidence before making a final decision.
4. STOP — prevent the transaction.

### Initial Error-Cost Assumptions

The initial experiment will use an abstract cost scale:

| Actual State | Action | Initial Cost |
|---|---|---:|
| Legitimate | APPROVE | 0 |
| Legitimate | QUESTION | 2 |
| Legitimate | EXAMINE | 4 |
| Legitimate | STOP | 10 |
| Fraudulent | APPROVE | 100 |
| Fraudulent | QUESTION | 15 |
| Fraudulent | EXAMINE | 8 |
| Fraudulent | STOP | 2 |

These costs are experimental assumptions, not factual monetary estimates. They will be reviewed and tested later.

### Memory

The agent may need to use:

- Previous transaction amounts
- Previous locations
- Previous devices
- Previous beneficiaries
- Transaction frequency
- Previous fraud outcomes
- Similar historical cases

### Human Escalation

The agent should consider requesting additional information or escalating uncertain cases rather than always making an immediate approve/stop decision.

### Initial Research Question

Can an uncertainty-aware transaction agent that can request additional evidence or escalate uncertain cases reduce costly fraud-detection errors compared with a simple rule-based decision system?

### Open Design Questions

The following questions remain open and will be investigated through research and human discussions:

- Which transaction features are actually useful?
- Which hidden states are missing?
- Which error has the highest cost?
- When should the agent ask a question?
- When should the agent gather additional evidence?
- When should the agent involve a human?
- Which evidence should change the agent's belief?
- How should historical cases be used?
- How should the agent learn from the result of an action?
