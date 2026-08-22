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

To be completed during research.

## 6. Search Queries

To be completed during research.

## 7. Reddit Communities

To be completed after verification.

## 8. X Accounts

To be completed after verification.

## 9. Papers / Articles / Repositories / Datasets

To be completed after research and verification.

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
