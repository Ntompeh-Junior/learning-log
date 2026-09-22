# Learning Note — 2026-09-22

**Focus area:** CISA Audit Planning / Risk-Based Auditing / AI Evaluation

## What I learned

### CISA — Audit Planning

An information systems audit should begin with a clear understanding of:

* The business objective.
* The systems and processes supporting that objective.
* The risks that could prevent the objective from being achieved.
* The controls designed to reduce those risks.
* The evidence required to determine whether the controls are working.

Audit planning helps ensure that limited audit resources are focused on the areas that matter most.

A good audit plan should define:

* Audit objectives.
* Audit scope.
* Systems and processes included.
* Relevant risks.
* Key controls.
* Audit procedures.
* Required evidence.
* Resources and responsibilities.
* Timing and reporting expectations.

### Audit Objective vs. Audit Scope

**Audit objective** defines what the auditor is trying to determine.

Example:

Determine whether privileged-access controls adequately protect critical production systems.

**Audit scope** defines what systems, locations, processes, time periods, and business units will be examined.

Example:

Privileged accounts for production Windows and Linux servers used by the Finance and Operations departments between January and June 2026.

A poorly defined scope can cause an audit to miss important risks or waste effort on irrelevant systems.

### Risk-Based Auditing

Risk-based auditing prioritizes audit activities according to the significance of business and information-system risks.

Rather than giving every control equal attention, the auditor focuses more effort on areas where control failure could have the greatest impact.

Risk-based auditing considers factors such as:

* Business criticality.
* Financial impact.
* Security exposure.
* Regulatory obligations.
* Previous audit findings.
* Known vulnerabilities.
* Changes to systems or processes.
* Incident history.
* Control maturity.
* Dependency on third parties.

### Key Principle

The highest technical severity does not always represent the highest business risk.

A medium-severity technical vulnerability affecting a critical payment system may deserve more audit attention than a critical vulnerability on an isolated test system.

The auditor should consider both technical and business context.

### Inherent Risk

Inherent risk is the level of risk that exists before controls are considered.

Example:

An internet-facing administrative portal handling privileged user accounts has significant inherent risk because compromise could lead to unauthorized access.

### Control Risk

Control risk is the possibility that existing controls will fail to prevent, detect, or correct a problem.

Example:

The organization requires MFA for administrators, but several privileged accounts have been excluded from the MFA policy.

The control exists, but it may not operate effectively.

### Residual Risk

Residual risk is the risk remaining after controls are applied.

Example:

After implementing MFA, conditional access, privileged access management, and monitoring, some risk of administrator-account compromise still remains.

Management determines whether that remaining risk is acceptable.

## Practical Audit Planning Scenario

### Scenario

An organization recently migrated several business-critical applications to a cloud platform.

The environment contains:

* Customer information.
* Production databases.
* Administrative accounts.
* Third-party integrations.
* Internet-facing services.

Management asks internal audit to review the new environment.

### Weak Approach

Immediately begin checking random cloud configuration settings.

### Better Risk-Based Approach

First understand:

* Which business processes depend on the cloud environment.
* What sensitive information is stored there.
* Which services are internet-facing.
* Which identities have privileged access.
* What security responsibilities belong to the cloud provider versus the organization.
* What controls were changed during migration.
* Whether previous assessments identified significant weaknesses.

The auditor can then prioritize areas such as:

* Identity and access management.
* Privileged access.
* Encryption.
* Logging and monitoring.
* Network exposure.
* Backup and recovery.
* Change management.
* Third-party integrations.
* Incident-response readiness.

### Key Lesson

Audit procedures should be driven by risk, not by a generic checklist alone.

## CISA Audit Planning Exercise

### Situation

An organization has:

* 5,000 employee accounts.
* 150 privileged accounts.
* 35 internet-facing servers.
* 2 critical payment systems.
* 400 development servers.

You have limited audit time.

### Priority Thinking

A risk-based auditor may prioritize:

* Privileged accounts.
* Internet-facing assets.
* Payment systems.
* Systems containing sensitive information.
* Areas with previous control failures.

This does not mean lower-risk assets are ignored.

It means audit effort is allocated according to risk.

## AI Evaluation — Error Severity

Not every AI mistake should receive the same severity.

Evaluators should consider how much the error affects the usefulness, correctness, safety, or reliability of the response.

### Minor Error

A minor issue does not significantly change the usefulness or main conclusion of the answer.

Examples:

* Slightly awkward wording.
* Minor formatting inconsistency.
* Small omission that does not affect the requested outcome.
* Redundant explanation.

### Major Error

A major issue significantly affects correctness, completeness, instruction following, or usefulness.

Examples:

* Missing an explicitly required section.
* Recommending an inappropriate cybersecurity control.
* Misinterpreting an important part of the prompt.
* Making an unsupported claim that changes the conclusion.
* Giving technically incorrect remediation.

### Critical Error

In some evaluation frameworks, the most serious category may apply when a response could create substantial harm or is fundamentally unusable.

Examples could include:

* Dangerous security instructions presented as safe.
* Completely fabricated evidence.
* Advice that would disable an important security control.
* A conclusion that directly contradicts the supplied evidence.

Severity depends on the evaluation rubric being used.

## AI Evaluation Exercise — Severity Classification

### Prompt

Review this vulnerability finding and recommend a remediation.

**Finding:**
A production application stores database credentials in plaintext inside a publicly accessible source-code repository.

### AI Response

The organization should rotate the exposed credentials and move the credentials into a secure secrets-management solution.

### Evaluation

This response is directionally correct.

However, a stronger answer should also consider:

* Treating the credentials as compromised.
* Reviewing repository history.
* Determining whether the credentials were accessed.
* Checking authentication and database logs.
* Removing exposed secrets from active code and deployment processes.

If the task only asked for one remediation, the response may still satisfy the core instruction.

If the task asked for a complete incident-response plan, the response would be incomplete.

### Lesson

The same response may receive different severity depending on the exact prompt and rubric.

## Pairwise AI Evaluation

Pairwise evaluation compares two responses to the same prompt and determines which one better satisfies the evaluation criteria.

The evaluator should compare responses based on explicit dimensions rather than personal writing preference.

Important dimensions include:

* Correctness.
* Grounding.
* Relevance.
* Completeness.
* Instruction following.
* Clarity.
* Safety.
* Technical precision.

### Pairwise Evaluation Example

**Prompt**

Explain the risk of an internet-facing SSH server using password authentication and recommend one improvement.

**Response A**

SSH is insecure because hackers can connect to it. The server should be removed from the internet immediately.

**Response B**

An internet-facing SSH service using password authentication is exposed to credential attacks such as password spraying and brute-force attempts. A strong improvement is to disable password authentication and require SSH public-key authentication, ideally combined with additional access restrictions such as VPN or trusted-source filtering.

### Comparison

Response B is stronger because:

* It explains the specific risk.
* It avoids claiming that SSH itself is inherently insecure.
* It identifies realistic attack methods.
* It provides an actionable control.
* It remains relevant to the prompt.

Response A identifies a general concern but overstates the issue and provides a less precise recommendation.

## Pairwise Evaluation Exercise

### Prompt

A security analyst detects repeated failed login attempts against an employee account from several foreign IP addresses. What should the analyst do next?

### Response A

Immediately delete the employee account because it is being attacked.

### Response B

Review authentication logs and related telemetry to determine whether any successful login occurred, validate the activity with the user where appropriate, assess source reputation and attack patterns, and apply containment such as temporary account protection or credential reset if evidence suggests compromise.

### Evaluation

Response B provides the stronger security approach.

### Why

Response A:

* Makes an immediate destructive decision.
* Assumes compromise.
* Does not validate evidence.
* Could unnecessarily disrupt business operations.

Response B:

* Investigates before concluding.
* Distinguishes failed attempts from confirmed compromise.
* Uses available evidence.
* Includes proportional containment options.

## Practical AI Evaluation Method

When comparing two AI responses:

1. Read the prompt carefully.
2. Identify every explicit instruction.
3. Identify the factual claims in each response.
4. Check whether those claims are supported.
5. Compare technical accuracy.
6. Check for missing required information.
7. Look for unsupported assumptions.
8. Evaluate the usefulness of recommendations.
9. Determine whether any mistake changes the overall conclusion.
10. Choose the response that better satisfies the defined evaluation criteria.

Do not choose a response simply because it is:

* Longer.
* More confident.
* More formal.
* More technical sounding.

A shorter response can be better if it is more accurate, grounded, and relevant.

## What I Practiced

* Distinguished audit objectives from audit scope.
* Practiced prioritizing audit work based on business risk.
* Reviewed inherent, control, and residual risk.
* Applied risk-based thinking to a cloud-security audit.
* Practiced identifying minor and major AI evaluation errors.
* Compared two AI-generated cybersecurity responses.
* Evaluated technical correctness separately from writing style.
* Practiced identifying unsupported assumptions.
* Considered how prompt requirements affect error severity.

## CISA Practice Questions

### Question 1

What should primarily drive the scope and priority of an information systems audit?

A. The number of available auditors
B. Business and information-system risk
C. The age of the organization's hardware
D. The auditor's preferred technical tools

**Answer:** B

**Reason:** Risk-based auditing directs audit resources toward areas where control failures could have the greatest impact on business objectives.

---

### Question 2

What is inherent risk?

A. Risk remaining after controls are implemented
B. Risk transferred to an insurance provider
C. Risk existing before controls are considered
D. Risk created by the auditor

**Answer:** C

**Reason:** Inherent risk represents exposure before considering the effectiveness of controls.

---

### Question 3

Which activity should normally occur first when planning an IS audit?

A. Begin vulnerability scanning
B. Understand business objectives and relevant risks
C. Write the final audit report
D. Select random systems for testing

**Answer:** B

**Reason:** The auditor must understand the business context and relevant risks before determining appropriate audit procedures.

---

### Question 4

An organization has implemented controls, but some risk remains. What is the remaining risk called?

A. Inherent risk
B. Residual risk
C. Sampling risk
D. Detection risk

**Answer:** B

**Reason:** Residual risk remains after controls and risk treatments are applied.

---

### Question 5

An AI evaluator compares two cybersecurity responses. Response A is longer, while Response B is shorter but more accurate and fully follows the prompt. Which factor should receive more weight?

A. Response length
B. Technical vocabulary
C. Accuracy and instruction following
D. Writing complexity

**Answer:** C

**Reason:** Evaluation should focus on whether the response satisfies the defined criteria, not superficial characteristics such as length.

## Key Takeaway

> Good auditors and good AI evaluators prioritize what matters most: understand the objective, identify the highest risks, evaluate the evidence, and judge results against clear criteria rather than appearances.

## Resources

* ISACA CISA Exam Content Outline
* CISA Domain 1 — Information System Auditing Process
* ISACA audit and assurance guidance
* NIST Cybersecurity Framework
* NIST Risk Management Framework
* NIST AI Risk Management Framework

## Questions for Later

* How should an auditor determine materiality?
* What is the difference between audit risk and business risk?
* How should previous audit findings influence a new audit plan?
* When should an auditor expand the original audit scope?
* How should technical severity and business impact be balanced?
* How should an AI evaluator distinguish a minor error from a major error?
* What should happen when two AI responses have different strengths?
* When should grounding outweigh completeness in pairwise evaluation?
* How should evaluators handle answers that are correct but unnecessarily verbose?
