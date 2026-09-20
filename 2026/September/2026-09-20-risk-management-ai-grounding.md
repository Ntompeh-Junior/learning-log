# Learning Note — 2026-09-20

**Focus area:** Cybersecurity / CISA Risk Management / AI Evaluation

## What I learned

* Reviewed the role of risk management in information security and IT governance.
* Learned that risk exists when a threat can exploit a vulnerability and negatively affect an organizational asset or business objective.
* Reviewed the difference between threats, vulnerabilities, risks, controls, likelihood, and impact.
* Studied the four common risk treatment approaches:

  * Risk mitigation
  * Risk acceptance
  * Risk transfer
  * Risk avoidance
* Learned that risk treatment decisions should consider business objectives, risk appetite, cost, impact, and management approval.
* Reviewed the concept of residual risk: the risk that remains after controls have been implemented.
* Learned that management, rather than the auditor, normally owns and accepts business risk.
* Reviewed why auditors should independently evaluate controls and communicate risk rather than make management decisions.
* Studied AI grounding as the requirement for an AI response to remain supported by the information, evidence, or sources available to it.
* Learned that a technically plausible statement can still be an evaluation failure when the evidence does not support it.
* Reviewed the distinction between a hallucination, unsupported assumption, omission, and factual error in AI-generated responses.

## What I practiced

### CISA Risk Scenario

Reviewed the following scenario:

An organization operates an internet-facing production server containing a critical vulnerability. A vendor patch is available, but the application owner is concerned that immediately applying the patch may interrupt a business-critical service.

I considered the situation from a CISA and risk-management perspective.

Important considerations include:

* The severity and likelihood of exploitation.
* The potential impact on business operations.
* Whether compensating controls can temporarily reduce exposure.
* Whether the patch has been appropriately tested.
* The organization's risk appetite and tolerance.
* The authority required to formally accept residual risk.
* Documentation of the decision and follow-up actions.

### Key CISA Principle

The security team and auditor can identify, assess, communicate, and recommend treatment for a risk, but business management is normally responsible for accepting business risk.

An auditor should maintain independence and should not assume management's responsibility for selecting or accepting risk treatment.

## AI Evaluation Exercise

### Prompt

An AI system receives the following information:

* Asset: Internet-facing Windows web server
* Vulnerability: Remote Code Execution
* Severity: Critical
* CVSS: 9.8
* Public exploit: Available
* Vendor patch: Available
* Business function: Customer-facing application

The AI responds:

> "Attackers have already compromised the server and stolen customer information."

### Evaluation

The response should be flagged because the available evidence does not establish that the server has been compromised or that customer information has been stolen.

The vulnerability and availability of a public exploit demonstrate significant exposure and exploitation risk, but they do not prove that exploitation has occurred.

### Error Classification

**Primary issue:** Unsupported claim / hallucination

The AI introduced information that was not contained in the provided evidence.

### Better Response

The server faces a critical security risk because it is internet-facing and affected by a remote code execution vulnerability for which a public exploit exists. An attacker could potentially exploit the vulnerability to execute unauthorized code and affect the confidentiality, integrity, or availability of the system.

Because a vendor patch is available, remediation should be prioritized. Security teams should also review relevant logs, endpoint telemetry, network activity, and other available evidence for signs of exploitation rather than assuming that compromise has already occurred.

## AI Evaluation Concepts Reviewed

### Grounding

A response is grounded when its claims are supported by the supplied evidence, context, or reliable source material.

### Hallucination

A hallucination occurs when the model generates information that is unsupported, invented, or inconsistent with the available evidence.

### Unsupported Assumption

An unsupported assumption occurs when the model treats something as true even though the prompt or evidence does not establish it.

### Omission

An omission occurs when important information needed for a complete answer is left out.

### Factual Error

A factual error occurs when the response contains information that is demonstrably incorrect.

## Practical Evaluation Checklist

When reviewing an AI-generated cybersecurity response, ask:

1. Is every important claim supported by the prompt or available evidence?
2. Did the model invent incidents, users, systems, attacks, or consequences?
3. Did the model distinguish between confirmed facts and potential risks?
4. Are the technical claims accurate?
5. Did the response follow all instructions?
6. Did it answer the actual question?
7. Did it omit any critical security consideration?
8. Does the response communicate uncertainty appropriately?
9. Are recommendations proportional to the evidence?
10. Could a reader mistakenly interpret a possibility as a confirmed fact?

## CISA Practice Questions

### Question 1

Who should normally make the final decision to accept an identified information security risk?

A. Internal auditor
B. Security analyst
C. Business management
D. External auditor

**Answer:** C. Business management

**Reason:** Management owns organizational risk and has the authority to determine whether residual risk is acceptable within the organization's risk appetite.

---

### Question 2

After implementing a security control, some level of risk still remains. What is this called?

A. Inherent risk
B. Residual risk
C. Transfer risk
D. Audit risk

**Answer:** B. Residual risk

**Reason:** Residual risk is the risk remaining after controls and risk treatments have been applied.

---

### Question 3

Which action is an example of risk transfer?

A. Discontinuing a vulnerable service
B. Purchasing cyber insurance
C. Installing a security patch
D. Formally accepting a low-impact vulnerability

**Answer:** B. Purchasing cyber insurance

**Reason:** Risk transfer shifts some financial consequences of the risk to another party.

---

### Question 4

An auditor identifies a serious control weakness. What should the auditor generally do?

A. Accept the risk on behalf of management
B. Implement the required security control directly
C. Communicate the finding and associated risk to appropriate management
D. Ignore the issue until exploitation occurs

**Answer:** C. Communicate the finding and associated risk to appropriate management

**Reason:** The auditor evaluates and communicates risk while maintaining independence. Management is responsible for corrective decisions.

---

### Question 5

An AI response says that a vulnerable system "was breached" when the source only states that a public exploit exists. What is the most important evaluation issue?

A. Formatting error
B. Excessive detail
C. Unsupported claim
D. Grammar error

**Answer:** C. Unsupported claim

**Reason:** Exploit availability increases risk but does not establish that successful exploitation or compromise occurred.

## Key Takeaway

> Risk professionals and AI evaluators must distinguish between what is possible, what is probable, and what is actually supported by evidence.

## Resources

* ISACA CISA Exam Content Outline
* CISA Domain 2: Governance and Management of IT
* CISA Domain 5: Protection of Information Assets
* NIST Cybersecurity Framework
* NIST AI Risk Management Framework
* NIST Risk Management Framework

## Questions for Later

* What is the difference between inherent risk and residual risk?
* How does an organization determine its risk appetite and risk tolerance?
* When should an auditor escalate a risk that management has accepted?
* What is the difference between risk ownership and control ownership?
* How should compensating controls be evaluated?
* At what point does an AI omission become a major evaluation error?
* How should evaluators score answers that are technically correct but poorly grounded?
* How can an evaluator distinguish reasonable inference from unsupported assumption?
* How should uncertainty be communicated in cybersecurity AI responses?
