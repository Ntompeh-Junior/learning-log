# Learning Note — 2026-09-21

**Focus area:** CISA Auditing / Cybersecurity / AI Evaluation

## What I learned

### CISA — Audit Evidence

* Audit conclusions should be based on sufficient, reliable, relevant, and useful evidence.
* Evidence should support the auditor's findings rather than relying on assumptions or verbal statements alone.
* The reliability of audit evidence generally increases when it comes from independent and verifiable sources.
* Directly observed evidence is often stronger than evidence based only on interviews.
* Audit documentation should allow another qualified auditor to understand what was tested, what evidence was reviewed, and how the conclusion was reached.
* An auditor should distinguish between evidence of a control's design and evidence that the control is actually operating effectively.

### Types of Audit Evidence

Common evidence may include:

* Policies and procedures
* System configuration records
* Access-control listings
* Security logs
* Change-management records
* Screenshots
* Transaction records
* Backup reports
* Incident tickets
* Interviews
* Direct observation
* Reperformance of a control

The type of evidence required depends on the objective of the audit.

### Control Design vs. Operating Effectiveness

**Control design** asks:

> Is the control capable of addressing the identified risk if implemented correctly?

**Operating effectiveness** asks:

> Is the control actually being performed consistently and correctly?

Example:

A company may have a policy requiring terminated employees' accounts to be disabled within 24 hours.

The existence of the policy demonstrates control design.

Reviewing a sample of terminated employees and confirming that their accounts were disabled within the required time helps demonstrate operating effectiveness.

## Auditor Independence

Auditors must remain sufficiently independent from the activities they evaluate.

An auditor should:

* Assess controls objectively.
* Identify weaknesses.
* Gather supporting evidence.
* Report findings.
* Recommend improvements.

An auditor should generally avoid:

* Owning the control being audited.
* Making management decisions.
* Accepting risk on behalf of management.
* Implementing the same control they are expected to independently evaluate.
* Changing evidence to support a desired conclusion.

### Key CISA Principle

> Management owns and operates controls. Auditors independently evaluate whether those controls are appropriately designed and operating effectively.

## Audit Sampling

Auditors often cannot inspect every transaction, account, device, or event.

Sampling allows the auditor to evaluate a representative portion of a population.

### Population

The complete group being evaluated.

Example:

10,000 user-access records generated during the year.

### Sample

A subset selected from that population for testing.

Example:

100 access records selected for detailed review.

### Sampling Risk

Sampling risk is the possibility that the selected sample does not accurately represent the overall population.

A poorly selected sample can cause the auditor to reach an incorrect conclusion.

### Good Sampling Practice

The auditor should consider:

* Audit objective
* Population size
* Risk level
* Expected error rate
* Required confidence
* Selection method
* Whether unusual or high-risk items require separate testing

## Practical Cybersecurity Audit Scenario

### Scenario

An organization states that administrator access is reviewed every quarter.

The security manager provides the written access-review policy and says all reviews have been completed.

### Weak Audit Approach

Accepting the statement as sufficient evidence.

### Better Audit Approach

The auditor should obtain evidence such as:

* Completed quarterly access-review records
* Approval timestamps
* List of privileged accounts reviewed
* Evidence of identified inappropriate access
* Tickets showing removal or modification of unnecessary access

The auditor can then select a sample of privileged accounts and verify that the review process actually occurred.

### Key Lesson

A policy tells the auditor what should happen.

Audit evidence helps establish what actually happened.

---

# AI Evaluation — Instruction Following

Instruction following measures whether an AI response actually follows the user's requirements.

An answer may be factually correct but still fail evaluation if it ignores explicit instructions.

### Example Prompt

> Explain phishing in exactly three bullet points. Do not include recommendations.

### AI Response

* Phishing is a social-engineering technique used to trick users into revealing sensitive information.
* Attackers commonly impersonate trusted organizations through email, text messages, or websites.
* Users should enable MFA and complete security-awareness training.
* Organizations should also deploy email-filtering technologies.

### Evaluation

The answer has two instruction-following problems:

1. It contains four bullet points instead of exactly three.
2. It includes recommendations even though the prompt explicitly prohibited them.

The cybersecurity information itself may be accurate, but the response still fails to fully follow the instructions.

## AI Evaluation — Completeness

Completeness measures whether the response covers the information necessary to answer the user's request.

### Example Prompt

> Identify the vulnerability, explain its security impact, and recommend one remediation.

### AI Response

> The application contains a SQL injection vulnerability.

### Evaluation

The response correctly identifies the vulnerability but is incomplete.

It fails to:

* Explain the security impact.
* Recommend a remediation.

### Better Response

> The application contains a SQL injection vulnerability that could allow an attacker to manipulate database queries and potentially access, modify, or delete unauthorized data. The application should use parameterized queries or prepared statements instead of directly concatenating user input into SQL statements.

## Instruction Following vs. Completeness

These concepts overlap but are not identical.

**Instruction-following failure:**
The model fails to obey an explicit requirement.

**Completeness failure:**
The model leaves out important information required to adequately answer the request.

A response can therefore be:

* Correct but incomplete.
* Complete but factually wrong.
* Correct and complete but instructionally non-compliant.
* Well-written but poorly grounded.
* Technically accurate but irrelevant.

## AI Evaluation Exercise

### Prompt

> Analyze the following vulnerability. Identify its severity, explain the likely impact, and provide two remediation actions. Keep the response under 120 words.

**Finding:**
An internal administrative portal allows authentication without MFA. The portal is accessible through the public internet and contains functionality for creating and disabling user accounts.

### AI Response

> This is a serious security problem because administrators have powerful access. The organization should enable MFA.

### Evaluation

The response identifies the general risk and provides one reasonable recommendation, but it is incomplete.

### Issues

**1. Severity not explicitly identified**

The prompt specifically requested severity.

**2. Impact insufficiently explained**

The response does not explain that compromised administrative credentials could allow unauthorized account creation, account disabling, privilege abuse, or broader system compromise.

**3. Only one remediation provided**

The user explicitly requested two remediation actions.

**4. Word-limit instruction followed**

The answer remains under 120 words.

### Improved Response

> **Severity: High.** The internet-facing administrative portal relies on single-factor authentication despite providing privileged account-management functions. Compromised administrator credentials could allow an attacker to create unauthorized accounts, disable legitimate users, or gain further access to organizational systems. Remediation should prioritize enabling phishing-resistant MFA for all administrative accounts and restricting administrative portal access through trusted networks, VPN, or conditional-access controls.

## Evaluation Result

* **Correctness:** Mostly correct
* **Grounding:** Good
* **Instruction following:** Partial
* **Completeness:** Insufficient
* **Relevance:** Good
* **Overall issue:** Missing required components

## What I Practiced

* Differentiated control design from operating effectiveness.
* Identified stronger and weaker forms of audit evidence.
* Reviewed the importance of auditor independence.
* Practiced thinking about populations and audit samples.
* Evaluated an AI answer against explicit prompt requirements.
* Distinguished factual correctness from instruction following.
* Identified missing information as a completeness error.
* Rewrote an incomplete AI cybersecurity response.

## CISA Practice Questions

### Question 1

An IS auditor is evaluating whether terminated employees' accounts are removed promptly. Which evidence would provide the strongest support?

A. HR's access-termination policy
B. A statement from the IT manager
C. A sample of terminated employees matched against account-disablement records
D. An employee security-awareness document

**Answer:** C

**Reason:** Testing actual terminated users against system records provides evidence that the control operated, rather than merely demonstrating that a policy exists.

---

### Question 2

Which activity would most threaten an IS auditor's independence?

A. Reviewing firewall configuration evidence
B. Reporting a control deficiency
C. Designing and operating the control that the auditor will later audit
D. Interviewing the control owner

**Answer:** C

**Reason:** An auditor who owns or operates the control may later be evaluating their own work.

---

### Question 3

What is the primary reason for using audit sampling?

A. To eliminate the need for evidence
B. To evaluate part of a population when testing every item is impractical
C. To guarantee that no errors exist
D. To allow management to choose which records are audited

**Answer:** B

**Reason:** Sampling allows auditors to reach conclusions about a population without examining every item.

---

### Question 4

A written security policy exists, but the auditor cannot find evidence that employees actually follow it. What has primarily been demonstrated?

A. Operating effectiveness
B. Control design
C. Risk acceptance
D. Incident containment

**Answer:** B

**Reason:** The policy establishes the intended control, but further evidence is required to confirm that it operates effectively.

---

### Question 5

An AI prompt requests three specific outputs, but the response provides only two. The information provided is factually correct. What is the primary evaluation issue?

A. Hallucination
B. Grounding
C. Completeness/instruction following
D. Security vulnerability

**Answer:** C

**Reason:** The model failed to provide all explicitly requested components.

## Key Takeaway

> Good auditing and good AI evaluation both depend on evidence: verify what actually happened, check requirements systematically, and never confuse a plausible statement with sufficient proof.

## Resources

* ISACA CISA Exam Content Outline
* CISA Domain 1 — Information System Auditing Process
* ISACA auditing standards and guidance
* NIST Cybersecurity Framework
* NIST AI Risk Management Framework

## Questions for Later

* What makes audit evidence sufficient and appropriate?
* When is inquiry alone insufficient audit evidence?
* What is the difference between statistical and non-statistical sampling?
* How should exceptions discovered in an audit sample be handled?
* When does providing advisory support impair auditor independence?
* How should an AI evaluator prioritize multiple errors in one response?
* What is the difference between completeness and relevance?
* Can an answer receive a high correctness score while failing instruction following?
