# Dataset

## Dataset Selected

The project will initially use the PaySim synthetic mobile-money transaction dataset.

PaySim provides simulated transaction records containing legitimate and fraudulent transactions.

The dataset is suitable for this research prototype because:

- It contains transaction-level information.
- It contains a fraud label.
- It provides transaction attributes that can be used to construct behavioral signals.
- It allows experimentation without using real customer financial information.
- It is commonly used in fraud-detection research.

---

## Expected Transaction Information

The dataset contains transaction information such as:

- Transaction type
- Transaction amount
- Origin account information
- Destination account information
- Account balances
- Transaction timing
- Fraud label

The exact columns will be inspected during data exploration rather than assumed in advance.

---

## Target Variable

The primary target variable is:

`isFraud`

Possible values:

- `0` — legitimate transaction
- `1` — fraudulent transaction

The target represents the hidden state that the agent is ultimately trying to infer.

---

## How the Dataset Will Be Used

The dataset will be divided conceptually into:

1. Transaction observations
2. Historical transaction information
3. Fraud labels
4. Derived behavioral features

The fraud label will be treated as the ground-truth outcome during evaluation.

The agent should not have access to the fraud label while making a decision.

---

## Important Research Considerations

### Class Imbalance

Fraudulent transactions are expected to be much less common than legitimate transactions.

Therefore, accuracy alone will not be sufficient to evaluate the system.

Metrics such as:

- Precision
- Recall
- F1 score
- False-positive rate
- False-negative rate
- Expected decision cost

will be considered.

### Data Leakage

Information that would only become available after the transaction or after fraud confirmation must not be used when simulating the agent's initial decision.

### Temporal Information

Transaction ordering and historical behavior may be important.

Where appropriate, transactions will be treated in temporal order rather than randomly mixing all historical information.

---

## Research Objective

The dataset will be used to compare:

1. A simple rule-based fraud detector.
2. A conventional fraud prediction model.
3. The proposed uncertainty-aware transaction agent.

The main comparison will focus not only on prediction performance but also on the cost of decisions and the ability to defer uncertain cases.

---

## Dataset Status

Dataset selected: Yes

Dataset downloaded: Not yet

Data exploration: Not started

Feature engineering: Not started

Agent implementation: Not started
