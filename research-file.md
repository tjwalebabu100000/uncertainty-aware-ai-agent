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

Initial technical terms to investigate:

- Transaction fraud detection
- Fraud risk scoring
- Anomaly detection
- Cost-sensitive classification
- Bayesian decision-making
- Probability calibration
- Uncertainty estimation
- Human-in-the-loop AI
- Decision thresholds
- False positives
- False negatives
- Selective classification
- Abstention
- Concept drift

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

To be researched and verified.

## 8. X Accounts

To be researched and verified.

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
