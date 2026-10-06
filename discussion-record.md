# Discussion Record

## Discussion 1 — r/fintech

### Date

August 2026

### Intended Community

r/fintech

### Purpose

The purpose of this discussion was to obtain practical perspectives on transaction fraud detection, including useful and misleading fraud signals, costly errors, additional evidence that should be requested before blocking a transaction, and situations where human review is preferable to automated decision-making.

### Planned Question

I planned to ask:

> I'm working on a research project where I'm designing a transaction-fraud AI agent that can either approve a transaction, ask for more information, examine it further, or stop it.
>
> I'm particularly interested in cases where common fraud signals can be misleading. For example, a new device, unusual location, large transaction amount, or new beneficiary could indicate fraud, but they could also be completely legitimate.
>
> For people who have worked in payments, fraud prevention, risk, or transaction monitoring:
>
> 1. Which signals do you find useful in practice?
> 2. Which signals are often misleading when considered in isolation?
> 3. What information would you want the system to obtain before blocking a transaction?
> 4. What type of mistake is most costly or damaging in your experience?
> 5. When is it better for an automated system to escalate a transaction to a human rather than make the decision itself?
>
> I'm intentionally looking for experiences that challenge my initial assumptions rather than confirmation of them. Any practical examples or lessons would be very helpful.

### Outcome

The discussion could not be posted because Reddit reported that the account did not yet meet the community's activity requirements.

The Reddit message stated that the account was too new and did not have sufficient karma to contribute to r/fintech.

### Research Implication

No human response was obtained from this attempted discussion, so no claims or design changes will be attributed to Reddit users from this attempt.

---

## Discussion 2 — X

### Date

October 2026

### Outcome

The research question was posted publicly on X, but no responses were received.

No human feedback is attributed to X users in this project.

---

## Simulated Stakeholder Feedback

Because the project needed to continue despite the absence of direct human responses, hypothetical stakeholder perspectives were created.

These are explicitly simulated and are NOT presented as real interviews, Reddit comments, or X responses.

The simulations are based on the project's research questions and publicly available fraud-detection discussions.

### Persona 1 — Fraud Analyst

**Perspective**

A fraud analyst would likely be concerned about excessive false positives and alert volume.

A transaction should not necessarily be blocked because of a single unusual signal.

**Potential feedback**

> A new device or unusual location should not automatically mean fraud. Context matters. I would want to know whether the customer has historically travelled, whether the transaction amount is unusual for that customer, and whether other signals agree.

**Design implication**

The agent should avoid treating individual signals as definitive evidence.

Instead, it should combine multiple pieces of evidence.

---

### Persona 2 — Fintech Product Manager

**Perspective**

A product manager would be concerned about customer friction and transaction conversion.

**Potential feedback**

> Blocking legitimate customers can damage trust and conversion. If the system is uncertain, a verification step may be preferable to immediately blocking the transaction.

**Design implication**

The agent should have an intermediate action between APPROVE and STOP.

This supports the use of:

- QUESTION
- EXAMINE

rather than a simple binary decision.

---

### Persona 3 — Machine Learning Engineer

**Perspective**

An ML engineer would be concerned about changing fraud patterns, delayed labels and model monitoring.

**Potential feedback**

> Fraud patterns change over time. The system should log decisions and outcomes so that the model can be evaluated and updated. You should also be careful because the final fraud label may arrive much later than the original transaction.

**Design implication**

The agent should maintain historical information and support feedback after the original decision.

Concept drift and delayed labels should be included in the experimental design.

---

### Persona 4 — Payments Risk Specialist

**Perspective**

A risk specialist would focus on high-risk actions and the difference between reversible and irreversible decisions.

**Potential feedback**

> Risk scoring and actually moving money should not necessarily be the same decision. High-risk or high-value transactions may require stronger controls or human review.

**Design implication**

The agent should distinguish between:

1. Estimating risk
2. Selecting an action

The action should depend not only on estimated fraud probability but also on the cost and reversibility of the action.

---

### Persona 5 — Customer Experience Specialist

**Perspective**

A customer-experience specialist would focus on legitimate customers who are incorrectly challenged or blocked.

**Potential feedback**

> Customers should understand why additional verification is required. A system that repeatedly challenges legitimate customers can create frustration even if it catches fraud successfully.

**Design implication**

The agent should consider customer friction as part of the cost of a decision.

---

## Summary of Simulated Feedback

| Persona | Main concern | Design implication |
|---|---|---|
| Fraud Analyst | False positives | Avoid relying on single signals |
| Product Manager | Customer friction | Use QUESTION/EXAMINE |
| ML Engineer | Drift and delayed labels | Maintain feedback/history |
| Risk Specialist | Cost and reversibility | Separate risk from action |
| Customer Experience | User trust | Include friction in decision cost |

---

## Research Integrity Note

The simulated stakeholder responses above are hypothetical scenarios created for experimentation.

They are not real interviews or real Reddit/X responses.

The actual external research conducted during this project is recorded separately from these simulations.

The simulated feedback is being used to generate design hypotheses that will later be tested experimentally.

The planned question will be retained for use when the account becomes eligible, or adapted for another appropriate community/channel.

### Design Changes

None. No human feedback was received.
