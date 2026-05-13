# Information Security Policy Framework

## What this is

A hierarchical structure of policies, standards, procedures and guidelines covering the information security domain. The document architecture, the lifecycle (drafting, reviewing, approving, communicating, retiring), and a starter library of 25 to 30 policy and standard drafts ready for adaptation.

The kind of thing a Head of Information Security or GRC Lead builds to replace the usual chaos of "we have some policies but nobody is sure where they live, when they were last reviewed or whether they are still in force."

## What this framework is trying to fix

The familiar symptoms.

- Policies exist as Word documents emailed around years ago. No version control. No review history.
- Some policies contradict each other. The access policy says quarterly review, the access standard says monthly.
- New policies are written for audits and forgotten until the next audit.
- Employees never read them. Awareness training mentions them but does not link to them.
- Exceptions are granted verbally and never tracked.
- The CISO and the General Counsel disagree about what is policy and what is guidance.
- When an incident happens, the team cannot quickly find which policy applies.
- The board approves policies they have never read.
- New employees acknowledge "the policies" without having access to them.

A strong opinion to lead with: policies engineering cannot actually follow are worse than no policy at all. A document that says "all code must be peer-reviewed by a security engineer before merge" when there are two security engineers and a thousand pull requests a week is not a policy. It is a future audit finding. Write what you can enforce. Enforce what you write.

A working framework gives you a clear hierarchy, a defined lifecycle, version control, an exception process, an awareness mechanism and a single accessible location. Most of the value is in the second word of "policy framework", not the first.

## Why it matters

- Faster decisions. Authoritative answers exist for common questions.
- Clean audits. Evidence of policy currency, communication and acknowledgement is structured.
- Consistent enforcement. Policies enforce equally on everyone or they enforce on no one.
- Faster onboarding. New staff get a single coherent set of expectations.
- Legal defensibility. If termination follows a clear policy violation, the framework is the evidence chain.
- Foundation for ISO 27001. Clause 5.2 information security policy is mandatory documented information.

## Framework alignment

- **ISO/IEC 27001:2022 Clause 5.2** information security policy.
- **ISO/IEC 27001:2022 Annex A.5.1** policies for information security (topic-specific).
- **ISO/IEC 27002:2022** for guidance on the topics typically covered.
- **NIST SP 800-12 Rev 1** introduction to information security, including policy structure.
- **NIST SP 800-100** information security handbook.
- **SOC 2 CC1, CC2, CC5** internal control environment, policies and communication.
- **PCI DSS v4.0 Requirement 12** information security policy obligations.
- **GDPR Articles 24 and 32** controller responsibilities and security of processing.

## Document hierarchy

Four levels, with strict rules about what belongs where.

### Level 1: Policy

- One per topic.
- Short, two to five pages.
- States the **what** and the **why**.
- Approved at the appropriate authority. Board for the umbrella policy. Executive Committee or CISO for topic policies.
- Reviewed annually at minimum.
- Mandatory. Non-compliance is a disciplinary matter.

Example: "All access to information systems must be authorised, authenticated, accountable and reviewed regularly."

### Level 2: Standard

- Specifies the **how much** or the **what specifically**.
- Approved by CISO or the relevant function head.
- Reviewed at least annually.
- Mandatory. Non-compliance is a control failure subject to exception or remediation.

Example: "Privileged access to production systems must use phishing-resistant multi-factor authentication. Sessions must be limited to 4 hours. Access reviews must be performed quarterly."

### Level 3: Procedure

- Step-by-step **how**.
- Approved by the operational owner.
- Reviewed when changed or at least annually.
- Mandatory for the team executing the work.

Example: "Procedure for adding a new engineer to production access: requestor opens ticket, manager approves, CISO delegate reviews, IAM platform provisions, audit log retained."

### Level 4: Guideline

- Recommended practice. Not mandatory.
- Approved by the function head.
- Reviewed at least biennially.

Example: "When choosing a new password manager for personal accounts, consider the following criteria..."

The strict separation matters. A common failure mode is the 47-page policy that tries to do all four jobs at once: policy statements, technical standards, step-by-step procedures and tips. Auditors and employees both bounce off such documents. Engineering does not read them. The auditor finds the gap.

## What sits in the framework

### 1. Policy framework document

The meta-policy. Defines hierarchy, lifecycle, roles, exception process and document control standards. Itself a policy, approved by the board.

### 2. Policy lifecycle

```
Draft -> Review -> Approve -> Publish -> Communicate -> Operate -> Review -> Update or Retire
```

Each stage has defined inputs, outputs, owners and SLAs.

- **Draft.** Owner produces or updates using the template.
- **Review.** Defined reviewer set. Legal, security, operational, HR, technical. 10-business-day SLA.
- **Approve.** Defined approver per document level.
- **Publish.** Single source of truth (controlled wiki or DMS) with version, effective date, next review date, owner and approval record.
- **Communicate.** New or materially changed policies require active communication. All-hands mention, intranet announcement, email to affected groups, awareness module update.
- **Operate.** The policy is in force.
- **Review.** Scheduled review. Annual minimum. More frequent for fast-moving topics.
- **Update or retire.** Versioned update or formal retirement with rationale.

### 3. Document template

Every document at every level uses the same template.

- Document control header. ID, version, status, effective date, next review date, owner, approver.
- Purpose.
- Scope. Who, what, where it applies.
- Definitions.
- Policy statements (numbered).
- Roles and responsibilities.
- References. Other policies, standards, regulations.
- Compliance and exceptions.
- Document history.

Auditors and employees both recognise consistent structure as a maturity signal.

### 4. Roles and responsibilities

| Role | Responsibility |
|---|---|
| **Board / Executive sponsor** | Approves the umbrella information security policy. Holds management accountable. |
| **CISO** | Owns the policy framework. Approves topic policies. |
| **Policy owner** (function head) | Owns specific policies for their domain. |
| **Policy author** | Drafts and updates documents. |
| **Policy reviewer panel** | Reviews drafts within SLA. Legal, HR, IT, Security, Privacy, key business representatives. |
| **GRC team** | Manages lifecycle, tracks reviews, manages exceptions, runs awareness. |
| **All staff** | Read, acknowledge, comply. |
| **Internal audit** | Tests compliance and framework effectiveness. |

### 5. Starter library

Drafts for the topics any modern SaaS organisation needs. Starting points, not final documents for any specific company.

**Foundation policies (Level 1).**
- Information security policy (umbrella).
- Acceptable use policy.
- Privacy policy (internal facing).

**Topic policies (Level 1).**
- Access control policy.
- Asset management policy.
- Change management policy.
- Cryptography policy.
- Data classification and handling policy.
- Human resources security policy.
- Incident management policy.
- Information security in supplier relationships (TPRM linkage).
- Logging and monitoring policy.
- Mobile device and remote working policy.
- Network security policy.
- Operational security policy.
- Physical and environmental security policy.
- Secure development policy.
- Vulnerability management policy.
- Business continuity and disaster recovery policy.

**Topic standards (Level 2).**
- Authentication standard. MFA requirements, password requirements, federation.
- Encryption standard. Algorithms, key lengths, key management.
- Cloud security standard. Service-specific configurations.
- Endpoint security standard.
- Logging and monitoring standard. What is logged, where, retention.
- Vulnerability management standard. Scan frequency, remediation SLAs by severity.
- Backup standard. Frequency, encryption, testing.
- Secure coding standard. Language-specific where useful.
- Incident severity standard. Criteria for SEV-1 to SEV-4.
- Data retention and deletion standard.

**Procedures (Level 3).** Examples.
- Joiner / mover / leaver procedure.
- Production access request procedure.
- Incident triage procedure.
- Vulnerability remediation procedure.
- Change approval procedure.
- Vendor onboarding procedure.

**Guidelines (Level 4).** Examples.
- Working from public Wi-Fi.
- Travel security.
- Social media use.
- Choosing personal authenticators.

### 6. Exception management

Policies cannot be followed in every case. The framework provides a controlled exception path.

- **Request.** Documented business justification, scope, duration, compensating controls.
- **Risk assessment.** Risk of granting the exception evaluated by GRC.
- **Approval.** At the appropriate authority. Standard exception by CISO. High-risk exception by Executive Committee.
- **Recording.** Central exceptions register.
- **Time-bound.** Every exception has an expiry. No "permanent" exceptions.
- **Review at expiry.** Renew, remediate or accept as new policy norm.

A working exception register signals maturity. An empty register usually signals either an immature programme (nobody is asking) or a non-existent enforcement regime (nobody needs to ask).

### 7. Awareness and acknowledgement

- **Onboarding.** New joiners read and acknowledge the policy set within their first week. Training module covers the headlines.
- **Annual.** All staff complete annual security awareness training that references current policies.
- **On change.** Material changes communicated by email and in the next training cycle.
- **Role-specific.** Engineers for secure development. Finance for fraud awareness. HR for joiner / leaver discipline. Legal for privacy.
- **Acknowledgement records.** Retained for the duration of employment plus the limitation period.

A strong opinion: making engineers acknowledge a 47-page secure development policy is theatre. Build a one-page "what an engineer needs to know" version that maps to the full policy. That is what they will read. Keep the long version for audit traceability.

### 8. Version control and document repository

- Single source of truth. Confluence, controlled wiki or DMS.
- Every policy has an immutable URL that does not change between versions. URL points to "current". Older versions linked from history.
- Edit history retained.
- "Effective from" and "next review" dates always visible.
- Ownership and approval clearly displayed.
- Search across the entire repository.

### 9. Policy mapping to controls and frameworks

Each policy and standard maps to specific controls in ISO 27001 Annex A, SOC 2 Trust Services Criteria and any other framework relevant to the organisation. Mapping sits alongside the policy and is exposed to the SoA.

### 10. Metrics

The framework's effectiveness is measured.

- Percentage of policies reviewed within their cycle.
- Average age of current policy versions.
- Percentage of staff who have acknowledged the current set.
- Number of open exceptions.
- Percentage of exceptions reviewed at expiry rather than auto-extended.
- Number of policy violations recorded and trend.
- Internal audit findings on the framework.

## Where teams stall

Patterns I have seen.

- **The policy nobody reads.** Polished, thorough, signed by the CEO, last opened by an engineer in 2022. Awareness completion is 100 percent. Recall is zero. The fix is shorter policies, role-specific summaries and training that quotes the actual document.
- **Authority disputes.** Legal wants to own data classification. Security wants to own data classification. Privacy thinks they own it. Nothing gets published. Resolve at executive level once, in writing, before the first conflict.
- **Mass approval.** 30 policies approved in one board meeting that nobody read. Approval becomes ceremonial. Auditors notice when minutes are silent on discussion.
- **Silent revision.** Policy gets updated. Nobody is told. Staff are unknowingly out of compliance. Awareness completion is meaningless.
- **The 47-page document.** Trying to be both policy and procedure. Engineering treats it as documentation theatre and ignores it.

Common pattern during ISO 27001 readiness: the policy library exists, looks thorough, but the policies describe an idealised version of the company. Auditor walks an engineer through the secure development policy. The engineer has never read it. The auditor pulls a sample of merges. None match the documented process. Major nonconformity. The fix is not better policies. It is policies that match what engineering actually does, with the bits engineering should improve made explicit.

## Lessons baked in

- **Policy is what you enforce.** A document that says one thing while operations does another is worse than no document.
- **Length kills.** A 47-page policy is read by no one. Keep policies short. Push detail down to standards and procedures.
- **Authority matters.** A policy approved by the CISO carries weight only if the CISO has the authority to enforce it. Where authority is contested, escalate to executive approval.
- **Versioning matters more than people think.** When an audit asks "show me the policy that was in force on 15 March", reconstruction from email is humiliating.
- **Communication is part of the lifecycle.** Publishing is not communicating. Communicating is not understanding. Test understanding occasionally.
- **Acknowledgement is not a tick box.** It is a contractual expectation. HR processes must align so acknowledgement is enforced as part of employment.

## Common pitfalls

- **Hierarchy collapse.** Treating policy, standard and procedure as the same thing. Document becomes unmanageable.
- **One-author dependency.** Every policy written by one GRC person who becomes a bottleneck.
- **Silent revision.** Updating policy without communication.
- **Mass approval.** Approving 30 policies in one board meeting.
- **No exception path.** Either everything is an exception (overwhelm) or nothing is (quiet violation).
- **Policy and SoA drift.** SoA references controls. Controls reference policies. Policies update. SoA does not. Auditor finds the gap.
- **Legal asymmetry.** Legal owns some policies, security owns others, HR owns others, with no coherent framework. Conflicts are inevitable.

## What an auditor will ask

- Show me the policy framework document.
- Walk me through the lifecycle for a policy you recently revised.
- Show me a policy that is overdue for review. What is the plan?
- Show me a policy approved by the board with date and minutes.
- Show me an exception. Show me how you decided to grant it.
- Show me an exception that expired. What happened?
- Show me a new joiner's acknowledgement for the current set.
- Show me how a policy change was communicated.

## How a rollout actually goes

A 12-month rollout for a 200 to 500 person SaaS company starting from policy chaos.

**Month 1.** Inventory existing policies. Identify duplicates, conflicts, orphans and gaps. Define hierarchy. Get the framework document approved.

**Months 2 to 4.** Rewrite or write the umbrella policy and the highest-priority topic policies. Acceptable use, access control, incident management, data classification, change management. Approved. Communicated. Awareness module rebuilt.

**Months 5 to 7.** Standards aligned to policies. Procedures captured from operational reality, not invented. Single repository established. Exceptions register live.

**Months 8 to 9.** Remaining topic areas. Cryptography, supplier security, secure development, vulnerability management, BCDR.

**Months 10 to 12.** Guidelines, full mapping to ISO 27001 Annex A, internal audit on the framework, metrics dashboard.

By month 12 the framework is operating and the policy debt is paid down. Usually.

## What I have done and what I have not

I have studied ISO 27001 Annex A 5.1, ISO 27002 implementation guidance, SOC 2 CC1 to CC5 and practitioner writing on policy lifecycles. I have written this framework as I would design it.

I have not personally rebuilt a policy framework from chaos under a deadline. I have not had to defend contested policy authority in a senior leadership argument. I have not had to handle a staff disciplinary process that turned on the wording of a policy. Those experiences would refine the framework, particularly around enforcement and authority dynamics.

This is a learning portfolio entry.

## Further reading

- **ISO/IEC 27001:2022 Annex A.5.1** and the corresponding **ISO/IEC 27002:2022** guidance.
- **NIST SP 800-12 Rev 1.** Free PDF at csrc.nist.gov.
- **NIST SP 800-100.** Free PDF at csrc.nist.gov. Older but useful policy material.
- **SANS Information Security Policy Templates** at sans.org/information-security-policy. Free, widely used starting points.
- **CIS Controls Implementation Group resources** at cisecurity.org. Free, especially good for standards alongside policies.
- **AICPA Trust Services Criteria** for SOC 2 policy expectations.
- **PCI DSS v4.0 Requirement 12** for required policies in cardholder environments.

## Status

Learning portfolio. Framework defined, hierarchy clear, starter library outlined. Documents not deployed in a live organisation.
