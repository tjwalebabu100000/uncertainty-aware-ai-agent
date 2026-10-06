# Transactional Fraud Agent — Agent Specification

## 1. Agent Objective

The agent's objective is to make transaction-risk decisions under incomplete information.

The agent should attempt to minimize the expected cost of incorrect or unnecessary decisions while explicitly representing uncertainty.

The agent is designed as a research prototype, not as a production banking system.

---

## 2. Problem Definition

For each transaction, the agent observes available transaction information and must decide what action to take.

The true state of the transaction is initially hidden from the agent.

Possible hidden states:

- LEGITIMATE
- FRAUDULENT

The agent must make decisions using incomplete information and may request additional evidence when the available information is insufficient.

---

## 3. Observed Transaction Information

The initial observation space includes:

- Transaction amount
- Transaction type
- Transaction time
- Transaction location
- Device status
- Merchant or beneficiary status
- Recent transaction frequency
- Previous transaction amounts
- Previous transaction locations
- Previous devices
- Previous beneficiaries
- Account history
- Previous fraud indicators

These variables represent the initial research design and may be refined during experimentation.

---

## 4. Agent Belief State

The agent maintains a belief about the hidden transaction state.

The initial belief representation is:

P(LEGITIMATE)

P(FRAUDULENT)

The two probabilities must sum to 1.

Example:

P(LEGITIMATE) = 0.80
P(FRAUDULENT) = 0.20

The belief state represents uncertainty rather than a guaranteed prediction.

---

## 5. Available Actions

The agent can take four actions:

### APPROVE

Allow the transaction to proceed.

### QUESTION

Request additional information or evidence before making a final decision.

### EXAMINE

Perform deeper analysis using additional available evidence or historical cases.

### STOP

Block or prevent the transaction.

The distinction between QUESTION and EXAMINE will be refined during experimentation.

---

## 6. Experimental Cost Model

The initial experimental cost matrix is:

| True State | APPROVE | QUESTION | EXAMINE | STOP |
|------------|---------|----------|---------|------|
| LEGITIMATE | 0 | 2 | 4 | 10 |
| FRAUDULENT | 100 | 15 | 8 | 2 |

These costs are experimental assumptions created for the research prototype.

They are not intended to represent actual banking or financial losses.

The purpose of the cost matrix is to make the agent explicitly reason about asymmetric consequences.

---

## 7. Uncertainty Handling

The agent should not be forced to make an immediate approve/stop decision when uncertainty is high.

When the agent has insufficient confidence, it may:

1. Request additional evidence.
2. Perform deeper examination.
3. Escalate the case for human review.

The uncertainty mechanism will be experimentally defined and evaluated later.

---

## 8. Historical Memory

The agent may use historical transaction information including:

- Previous transaction amounts
- Previous locations
- Previous devices
- Previous beneficiaries
- Transaction frequency
- Previous fraud outcomes
- Similar historical transactions

Historical information should be treated as evidence rather than absolute truth.

---

## 9. Decision Process

The initial conceptual decision process is:

Transaction
↓
Observe available information
↓
Estimate belief about LEGITIMATE / FRAUDULENT
↓
Evaluate uncertainty
↓
If sufficiently confident → choose an action
↓
If uncertain → QUESTION / EXAMINE / human review
↓
Update belief using additional evidence
↓
Make final decision
↓
Record outcome and decision information

---

## 10. Learning and Feedback

The system should record:

- Transaction information
- Initial belief
- Evidence requested
- Evidence received
- Action selected
- Final outcome
- Whether the transaction was actually fraudulent
- Cost incurred
- Human-review outcome where applicable

These records can later be used to evaluate whether the agent improves its decisions over time.

---

## 11. Baseline System

The uncertainty-aware agent will eventually be compared against a simpler baseline.

The initial baseline will be a rule-based transaction fraud detector.

Example rules may include:

- Flag unusually large transactions.
- Flag unusually high transaction frequency.
- Flag transactions from unusual locations.
- Flag transactions from unfamiliar devices.

The baseline will not explicitly reason about uncertainty or request additional evidence.

---

## 12. Main Research Question

Can an uncertainty-aware transaction agent that can request additional evidence or escalate uncertain cases reduce costly fraud-detection errors compared with a simple rule-based decision system?

---

## 13. Initial Evaluation Questions

The experiments should investigate:

1. Does uncertainty-aware decision-making reduce costly errors?

2. When does requesting additional evidence improve decisions?

3. Does deeper examination improve decisions enough to justify its cost?

4. When should the agent escalate to human review?

5. Does historical transaction information improve decision quality?

6. How does the agent behave when fraud patterns change?

7. Does the uncertainty-aware agent outperform the rule-based baseline under the same cost assumptions?

---

## 14. Research Constraints

This project is a research prototype.

It will use synthetic and/or publicly available datasets rather than real customer banking data.

The experimental cost assumptions must be clearly separated from real-world financial costs.

The project should not claim that the resulting agent is production-ready.

---

## 15. Current Status

Agent concept: Defined

Research question: Defined

Initial actions: Defined

Initial cost model: Defined

Uncertainty concept: Defined

Historical memory concept: Defined

Baseline concept: Defined

Experimental implementation: Not started
