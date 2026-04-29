# Information Security Policy Framework

## What this project is

A complete hierarchical structure of policies, standards, procedures, and guidelines covering the full information security domain. This includes the document architecture, the lifecycle for creating, reviewing, approving, communicating, and retiring policy documents, and a starter library of 25-30 actual policy and standard drafts ready for adaptation.

This is what a Head of Information Security or GRC Lead would build to replace the typical chaos of "we have some policies but no one is sure where they live, when they were last reviewed, or whether they are still in force."

## Problem this framework solves

Most organisations have one or more of these symptoms.

- Policies exist as Word documents emailed around years ago, no version control, no review history.
- Some policies contradict each other (the access policy says quarterly review, the access standard says monthly).
- New policies are written for audits and forgotten until the next audit.
- Employees never read them; awareness training mentions them but does not link to them.
- Exceptions are granted verbally and never tracked.
- The CISO and the General Counsel disagree on what is policy and what is guidance.
- When an incident happens, the team cannot quickly find which policy applies.
- The board approves policies they have never read.
- New employees acknowledge "the policies" without having access to them.

A working framework fixes these by establishing a clear hierarchy, a defined lifecycle, version control, an exception process, an awareness mechanism, and a single accessible location.

## Business impact

- Faster decisions because authoritative answers exist for common questions.
- Clean audits because evidence of policy currency, communication, and acknowledgement is structured.
- Reduced risk of inconsistent enforcement (policies enforce equally on everyone or they enforce on no one).
- Faster onboarding because new staff have a single coherent set of expectations.
- Legal defensibility (if termination follows a clear policy violation, the framework is the evidence chain).
- Foundation for ISO 27001 (Clause 5.2 information security policy is mandatory documented information).

## Framework alignment

- **ISO/IEC 27001:2022 Clause 5.2** information security policy.
- **ISO/IEC 27001:2022 Annex A.5.1** policies for information security (topic-specific policies).
- **ISO/IEC 27002:2022** for guidance on the topics typically covered.
- **NIST SP 800-12 Rev 1** an introduction to information security including policy structure.
- **NIST SP 800-100** information security handbook (chapter on policy).
- **SOC 2 CC1, CC2, CC5** internal control environment, policies, and communication.
- **PCI DSS v4.0 Requirement 12** information security policy obligations.
- **GDPR Article 24 and 32** controller responsibilities and security of processing.

## Document hierarchy

The framework defines a four-level hierarchy with strict rules about what belongs at each level.

### Level 1: Policy

- One per topic.
- Short (2-5 pages).
- States the **what** and the **why**.
- Approved by the appropriate authority (Board for the umbrella policy, Executive Committee or CISO for topic policies).
- Reviewed annually at minimum.
- Mandatory; non-compliance is a disciplinary matter.

Example: "All access to information systems must be authorised, authenticated, accountable, and reviewed regularly."

### Level 2: Standard

- Specifies the **how much** or the **what specifically**.
- Approved by CISO or relevant function head.
- Reviewed at least annually.
- Mandatory; non-compliance is a control failure subject to exception or remediation.

Example: "Privileged access to production systems must use phishing-resistant multi-factor authentication. Sessions must be limited to 4 hours. Access reviews must be performed quarterly."

### Level 3: Procedure

- Step-by-step **how**.
- Approved by the operational owner.
- Reviewed when changed or at least annually.
- Mandatory for the team executing the work.

Example: "Procedure for adding a new engineer to production access: requestor opens ticket, manager approves, CISO delegate reviews, IAM platform provisions, audit log retained."

### Level 4: Guideline

- Recommended practice, not mandatory.
- Approved by the function head.
- Reviewed at least biennially.

Example: "When choosing a new password manager for personal accounts, consider the following criteria..."

The strict separation matters. A common failure is policy documents that try to do all four jobs at once: a 47-page policy with policy statements, technical standards, step-by-step procedures, and tips. Auditors and employees both bounce off such documents.

## Components and deliverables

### 1. Policy framework document

The meta-policy. Defines the hierarchy, the lifecycle, the roles and responsibilities, the exception process, and the document control standards. This is itself a policy and is approved by the board or the equivalent.

### 2. Policy lifecycle

```
Draft -> Review -> Approve -> Publish -> Communicate -> Operate -> Review -> Update or Retire
```

Each stage has defined inputs, outputs, owners, and SLAs.

- **Draft.** Owner produces or updates document using the template.
- **Review.** Defined reviewer set (legal, security, operational, HR, technical). 10-business-day SLA.
- **Approve.** Defined approver per document level.
- **Publish.** Single source of truth (typically a controlled wiki or document management system) with version, effective date, next review date, owner, and approval record.
- **Communicate.** New or materially changed policies require active communication: all-hands mention, intranet announcement, email to affected groups, awareness module update.
- **Operate.** The policy is in force.
- **Review.** Scheduled review (annual minimum, more frequent for fast-moving topics).
- **Update or retire.** Versioned update or formal retirement with rationale.

### 3. Document template

Every policy at every level uses the same template.

- Document control header (ID, version, status, effective date, next review date, owner, approver).
- Purpose.
- Scope (who, what, where it applies).
- Definitions.
- Policy statements (numbered).
- Roles and responsibilities.
- References (other policies, standards, regulations).
- Compliance and exceptions.
- Document history.

Auditors and employees alike recognise consistent structure as a maturity signal.

### 4. Roles and responsibilities

| Role | Responsibility |
|---|---|
| **Board / Executive sponsor** | Approves the umbrella information security policy. Holds management accountable. |
| **CISO** | Owns the policy framework. Approves topic policies. |
| **Policy owner** (function head) | Owns specific policies for their domain. |
| **Policy author** | Drafts and updates documents. |
| **Policy reviewer panel** | Reviews drafts within SLA. Includes Legal, HR, IT, Security, Privacy, key business representatives. |
| **GRC team** | Manages the lifecycle, tracks reviews, manages exceptions register, runs awareness. |
| **All staff** | Read, acknowledge, comply. |
| **Internal audit** | Tests compliance and framework effectiveness. |

### 5. Starter library of policies and standards

The framework includes drafts for the topics any modern organisation needs. Each is a structured starting point, not a final document for any specific company.

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
- Information security in supplier relationships policy (TPRM linkage).
- Logging and monitoring policy.
- Mobile device and remote working policy.
- Network security policy.
- Operational security policy.
- Physical and environmental security policy.
- Secure development policy.
- Vulnerability management policy.
- Business continuity and disaster recovery policy.

**Topic standards (Level 2).**
- Authentication standard (MFA requirements, password requirements, federation).
- Encryption standard (algorithms, key lengths, key management).
- Cloud security standard (service-specific configurations).
- Endpoint security standard.
- Logging and monitoring standard (what is logged, where, retention).
- Vulnerability management standard (scan frequency, remediation SLAs by severity).
- Backup standard (frequency, encryption, testing).
- Secure coding standard (language-specific where useful).
- Incident severity standard (criteria for SEV-1 to SEV-4).
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

### 6. Exception management process

Reality is that policies cannot be followed in every case. The framework provides a controlled exception path.

- **Request:** documented business justification, scope, duration, compensating controls.
- **Risk assessment:** the risk of granting the exception evaluated by GRC.
- **Approval:** by appropriate authority. Standard exception by CISO. High-risk exception by Executive Committee.
- **Recording:** in a central exceptions register.
- **Time-bound:** every exception has an expiry. No "permanent" exceptions.
- **Review:** at expiry, either renew, remediate, or accept as new policy norm.

A working exception register signals maturity. An empty exception register usually signals either an immature programme (no one is asking) or a non-existent enforcement regime (no one needs to ask).

### 7. Awareness and acknowledgement

- **Onboarding:** new joiners read and acknowledge the policy set within their first week. Training module covers the headlines.
- **Annual:** all staff complete annual security awareness training that references current policies.
- **On change:** material policy changes are communicated by email and the next training cycle.
- **Topic-specific:** role-specific training for engineers (secure development), finance (fraud awareness), HR (joiner/leaver discipline), legal (privacy).
- **Acknowledgement records:** retained for the duration of employment plus the limitation period.

### 8. Version control and document repository

- Single source of truth (typically a controlled wiki, Confluence space, or document management system).
- All policies have an immutable URL that does not change between versions (the URL points to "current"; older versions are linked from history).
- Edit history retained.
- "Effective from" and "next review" dates always visible.
- Ownership and approval clearly displayed.
- Search across the entire repository.

### 9. Policy mapping to controls and frameworks

Each policy and standard maps to specific controls in ISO 27001 Annex A, SOC 2 Trust Services Criteria, and any other framework relevant to the organisation. This mapping lives alongside the policy and is exposed to the SoA.

### 10. Metrics

The framework's effectiveness is measured. Examples.

- Percentage of policies reviewed within their cycle.
- Average age of policies (current versions).
- Percentage of staff who have acknowledged the current policy set.
- Number of open exceptions.
- Percentage of exceptions reviewed at expiry rather than auto-extended.
- Number of policy violations recorded (and trend).
- Internal-audit findings on policy framework.

## Real-world lessons baked into this framework

- **Policy is what you enforce.** A document that says one thing while operations does another is worse than no document because it creates legal and audit liability without security benefit.
- **Length kills.** A 47-page policy is read by no one. Keep policies short; push detail down to standards and procedures.
- **Authority matters.** A policy approved by the CISO carries weight only if the CISO has the organisational authority to enforce it. Where authority is contested, escalate to executive approval.
- **Versioning matters more than people think.** When an audit asks "show me the policy that was in force on 15 March," reconstruction from email is humiliating.
- **Communication is part of the lifecycle.** Publishing is not the same as communicating. Communication is not the same as understanding. Periodically test understanding.
- **Acknowledgement is not a tick box.** It is a contractual expectation. HR processes must align so that acknowledgement is enforced as part of employment.

## Common pitfalls

- **Hierarchy collapse.** Treating policy and standard and procedure as the same thing. Document becomes unmanageable.
- **One-author dependency.** Every policy written by one GRC person who becomes a bottleneck.
- **Silent revision.** Updating policy without communication. Staff unknowingly out of compliance.
- **Mass approval.** Approving 30 policies in one board meeting nobody actually read. Approval becomes ceremonial.
- **No exception path.** Either everything is an exception (overwhelm) or nothing is (people quietly violate).
- **Policy and SoA drift.** SoA references controls; controls reference policies; policies update; SoA does not. Auditor finds the gap.
- **Legal asymmetry.** Legal owns some policies, security owns others, HR owns others, with no coherent framework. Conflicts are inevitable.

## Audit considerations

- Show me the policy framework document.
- Walk me through the lifecycle for a policy you recently revised.
- Show me a policy that is overdue for review. What is the plan?
- Show me a policy approved by the board with date and minutes.
- Show me an exception. Show me how you decided to grant it.
- Show me an exception that expired. What happened?
- Show me a new joiner's acknowledgement for the current policy set.
- Show me how a policy change was communicated.

## How this framework would actually be implemented

A 12-month rollout for a 200-500 person SaaS company starting from policy chaos.

**Month 1.** Inventory existing policies. Identify duplicates, conflicts, orphans, and gaps. Define hierarchy. Get framework document approved.

**Months 2-4.** Rewrite or write the umbrella policy and the highest-priority topic policies (acceptable use, access control, incident management, data classification, change management). Get approved. Communicate. Awareness module rebuilt.

**Months 5-7.** Standards aligned to policies. Procedures captured from operational reality. Single repository established. Exceptions register live.

**Months 8-9.** Coverage of remaining topic areas (cryptography, supplier security, secure development, vulnerability management, BCDR).

**Months 10-12.** Guidelines, full mapping to ISO 27001 Annex A, internal audit on the framework, metrics dashboard.

By month 12 the framework is operating and the policy debt is paid down.

## What I have done in this space and what I have not

I have studied ISO 27001 Annex A 5.1, ISO 27002 implementation guidance, SOC 2 CC1-CC5, and academic and practitioner writing on policy lifecycles. I have written this framework as I would design it.

I have not personally rebuilt a policy framework from chaos under a deadline. I have not had to defend a contested policy authority in a senior leadership argument. I have not had to handle a staff disciplinary process that turned on the wording of a policy. Those experiences would refine the framework in important ways, especially around enforcement and authority dynamics.

This is a learning portfolio entry.

## Further reading

- **ISO/IEC 27001:2022 Annex A.5.1** and the corresponding **ISO/IEC 27002:2022** guidance.
- **NIST SP 800-12 Rev 1.** Free PDF at csrc.nist.gov.
- **NIST SP 800-100.** Free PDF at csrc.nist.gov (older but useful policy material).
- **SANS Information Security Policy Templates** at sans.org/information-security-policy (free, widely used starting points).
- **CIS Controls Implementation Group resources** at cisecurity.org (free, especially good for standards alongside policies).
- **AICPA Trust Services Criteria** for SOC 2 policy expectations.
- **PCI DSS v4.0 Requirement 12** for required policies in cardholder environments.

## Status

Learning portfolio. Framework defined, hierarchy clear, starter library outlined. Documents not deployed in a live organisation.
