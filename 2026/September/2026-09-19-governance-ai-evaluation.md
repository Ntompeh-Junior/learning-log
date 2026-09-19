# Learning Note — 2026-09-19

**Focus area:** Cybersecurity / CISA / AI Evaluation

## What I learned
- Reviewed the purpose of Information Security Governance and how security activities should align with organizational objectives.
- Learned that governance establishes direction, accountability, policies, risk tolerance, and oversight, while management handles execution and day-to-day activities.
- Reviewed the relationship between governance, risk management, controls, and organizational objectives.
- Learned the importance of senior management and board oversight in information security governance.
- Reviewed the basic risk treatment options: mitigation, acceptance, transfer, and avoidance.
- Studied how CISA questions emphasize governance, business objectives, risk, audit evidence, control effectiveness, and management responsibility.
- Reviewed important AI evaluation dimensions including correctness, grounding, completeness, relevance, and instruction following.
- Learned that an AI response may sound confident and technically reasonable while still containing unsupported assumptions or hallucinations.

## What I practiced
- Compared information security governance with information security management.
- Reviewed how responsibility, accountability, and risk ownership differ between security teams, management, and internal audit.
- Analyzed a basic cybersecurity risk scenario and considered the appropriate risk treatment.
- Evaluated an AI-generated cybersecurity response for:
  - factual accuracy;
  - grounding;
  - instruction following;
  - unsupported assumptions;
  - completeness;
  - security implications.
- Practiced rewriting an AI response to remove unsupported assumptions and make the answer more precise and evidence-based.

## AI Evaluation Exercise

### Scenario
An AI was asked to summarize the risk of an internet-facing Windows web server with a critical remote code execution vulnerability, a CVSS score of 9.8, a public exploit, and an available vendor patch.

### Evaluation
The AI correctly identified remote exploitation as a major security risk.

However, an evaluator should flag any statement claiming that the server has already been compromised because no evidence of compromise was provided.

### Key evaluation principle
Public exploit availability increases the likelihood and urgency of exploitation, but it does not prove that exploitation has already occurred.

### Improved approach
A stronger response should describe the potential impact, recommend urgent patching and compensating controls where necessary, and recommend checking available security telemetry for indicators of exploitation without assuming compromise.

## Key takeaway
> Effective cybersecurity is not only about implementing technical controls; governance ensures that security decisions support business objectives, manage risk, and have clear accountability.

## Resources
- ISACA CISA Exam Content Outline
- CISA Domain 1: Information Systems Auditing Process
- CISA Domain 2: Governance and Management of IT
- NIST Cybersecurity Framework
- NIST AI Risk Management Framework

## Questions for later
- What is the difference between governance and management from a CISA examination perspective?
- Who ultimately owns information security risk?
- When should an information systems auditor escalate a finding?
- How does CISA distinguish the roles of management, information security, and internal audit?
- How should an AI evaluator distinguish between a hallucination, an unsupported assumption, and an incomplete answer?
- When should an AI evaluation issue be classified as minor versus major?
