# Audit Readiness Playbook (ISO 27001 / SOC 2)

## What this project is

A practical operational playbook that takes an organisation from "we have policies and controls" to "we are ready to host an external auditor next week." It covers the six to eight week run-up to an external audit (Stage 2 ISO 27001 or SOC 2 Type 2), the conduct of the audit itself, and the post-audit remediation period.

This is the kind of document a Head of GRC writes after surviving their first audit and wishes they had had at the start. It is non-technical in that it produces no software, but the discipline it imposes is what separates audits that pass cleanly from audits that drag for months.

## Problem this playbook solves

Most audit failures are not control failures. They are evidence failures, owner failures, and timing failures.

- The control exists but the evidence is in seven different systems and nobody can pull it together within the auditor's three-day window.
- The control owner left the company two months ago and nobody has been re-assigned.
- The auditor asks for a sample of 25 access reviews and the company can only produce 18.
- The policy says reviews happen quarterly. The last review was six months ago.
- The penetration test happened in the audit period but the report was not received until after period end, so it does not count.
- Management review minutes are missing for two of the four quarters.
- Risk register entries reference controls that have since been renumbered.

A playbook fixes these by treating audit readiness as a continuous operating discipline, not a panic six weeks before the audit.

## Business impact

- Audits complete on time and on budget rather than dragging into expensive overtime.
- Findings are minor observations rather than nonconformities or qualifications.
- Customer trust because the audit report (SOC 2) or certificate (ISO 27001) arrives when promised.
- Internal team morale because audit week is calm rather than chaotic.
- Reputation with the auditor, which compounds across years and influences how they sample.
- Reduced cost of audits because efficient evidence delivery means fewer auditor hours billed.

## Framework alignment

- **ISO/IEC 27001:2022** for ISMS audits.
- **ISO/IEC 27007:2020** Guidelines for ISMS auditing.
- **ISO 19011:2018** Guidelines for auditing management systems (the meta-standard for how audits are conducted).
- **AICPA SSAE 18** and **TSP Section 100** for SOC 2 audits.
- **AICPA Trust Services Criteria 2017 (revised 2022)** for the SOC 2 control framework.
- **NIST SP 800-53A** for control assessment procedures (helpful reference even if not auditing federal systems).
- **ISO/IEC 17021** sets out the requirements for certification bodies, useful for understanding what a UKAS-accredited body must do.

## Components and deliverables

### 1. Audit calendar and master timeline

A single source of truth that lists every audit due in the next 18 months, the period covered, the audit firm, the lead auditor, key dates (kickoff, fieldwork, draft report, final report), and the internal lead for each.

Typical SaaS company calendar.

| Audit | Period | Fieldwork | Report due |
|---|---|---|---|
| SOC 2 Type 2 | 12 months ending 31 March | June (4 weeks) | August |
| ISO 27001 surveillance | n/a (point in time) | September | October |
| Customer-driven security questionnaires | continuous | continuous | n/a |
| Internal ISO 27001 audit | rolling | varies | quarterly reports |
| PCI DSS (if applicable) | annual | TBD | TBD |
| Cyber insurance assessment | annual | November | December |
| Penetration test (for evidence) | twice yearly | February and August | March and September |

### 2. Control-to-evidence mapping

The single most useful document in the playbook. A spreadsheet or database where every control is mapped to:

- The framework references (e.g. SOC 2 CC6.1, ISO 27001 A.8.3).
- The control description.
- The control owner (named individual).
- The evidence type (policy, log extract, screenshot, signed document, ticket export, configuration export).
- The system or location where evidence lives.
- The frequency of operation (continuous, daily, weekly, monthly, quarterly, annually, on event).
- The retention requirement.
- The link or path to the most recent evidence.
- Last evidence date.
- Next evidence due.

This is what auditors call a "control matrix" and they will ask for it. Maintaining it as a live document, not a pre-audit reconstruction, is the core discipline.

### 3. Evidence checklist (audit-period-specific)

Generated from the control-to-evidence map, this is the punch list for the upcoming audit. For each control, the specific evidence required for the audit period.

Example entry.

> **Control:** Access reviews of production systems are performed quarterly.
> **Framework refs:** SOC 2 CC6.1, ISO 27001 A.5.18, A.8.2.
> **Owner:** Engineering Manager, Platform.
> **Evidence required for FY26 audit:** Q1, Q2, Q3, Q4 access review reports including reviewers, reviewers' approval, removed users with date, and exception sign-offs.
> **Location:** Confluence space ENG-ACCESS-REVIEWS, JIRA project ACR.
> **Status:** Q1, Q2, Q3 complete and uploaded to evidence locker. Q4 due 15 January, evidence due 30 January.
> **Risk if missing:** SOC 2 exception. Likely qualified opinion.

### 4. Audit RACI

| Activity | GRC lead | Control owner | Engineering | Internal audit | Auditor |
|---|---|---|---|---|---|
| Maintain control matrix | A, R | C | I | C | I |
| Operate the control | C | A, R | R | I | I |
| Collect evidence | A | R | C | I | I |
| Quality-check evidence | A, R | C | I | C | I |
| Upload to evidence locker | A | R | I | I | I |
| Respond to auditor sample request | A, R | C | C | I | I |
| Negotiate findings | A, R | C | I | C | I |
| Track remediation | A, R | R | C | C | I |

### 5. Evidence locker structure

A defined, indexed location (typically a Confluence space, SharePoint, or a controlled drive) where audit evidence lives. Folder structure mirrors the control matrix. Each evidence item has a defined naming convention (`<control-id>_<period>_<evidence-type>_<date>.<ext>`).

Auditors notice the difference between an organised evidence locker and a chaotic one. An organised locker reduces auditor sampling because they trust your operational discipline.

### 6. Pre-audit checklist (T-minus templates)

A countdown of preparation activities.

**T-minus 12 weeks**
- Confirm audit scope, period, fieldwork dates.
- Confirm auditor team and any rotations.
- Refresh the control matrix; identify any controls without evidence for the upcoming period.
- Schedule remediation work for any gaps.

**T-minus 8 weeks**
- Run mock audit (internal team plays auditor against the matrix).
- Address mock-audit findings.
- Confirm logistics (NDAs, system access for auditors, meeting rooms or video calls).
- Brief control owners on what to expect.

**T-minus 4 weeks**
- Final evidence sweep. Every control matrix row has current evidence.
- Confirm all required reports (penetration test, vulnerability scans, awareness training completion) are dated within the audit period.
- Send pre-audit information request response (PBC list - Provided By Client).

**T-minus 1 week**
- Confirm kickoff meeting agenda.
- Brief executives on what auditors will ask of them in interviews.
- Calm-and-organised mode.

**Audit week**
- Daily stand-up with audit team and internal team.
- Sample requests handled within the agreed SLA (typically 24-48 hours).
- Findings discussed when raised, not at the end.

**T-plus 1 week**
- Receive draft report.
- Walk through findings, agree language, dispute or accept each.

**T-plus 4 weeks**
- Receive final report.
- Build remediation plan for any findings.
- Update control matrix to prevent recurrence.

### 7. Sample request handling protocol

Auditors request samples (e.g. "show me 25 access changes from the period"). The protocol covers:

- Sample size negotiation (defined by the auditor's methodology, but you can ask for justification).
- Sample selection (auditor selects from a complete population you supply).
- Evidence delivery format (PDF preferred, screenshots in context, no raw API dumps without explanation).
- Response time (24 hours for simple, 48 hours for complex, agreed in kickoff).
- Tracking (sample log in shared workspace).

### 8. Auditor interview prep

Control owners are interviewed by the auditor to test that they understand and operate the control. Briefing notes for each interviewed role cover:

- What the auditor will ask (typical questions: walk me through, what would you do if X, when did you last do this, what was the outcome).
- What evidence you will be expected to bring.
- How to handle "I don't know" honestly (escalate, follow up, never guess).
- What not to volunteer (do not show the auditor your exception register unless asked; do not speculate about other controls).

### 9. Findings register and remediation tracking

A simple register: finding ID, source (which audit), description, agreed management response, owner, target date, status, evidence of closure. Tracked through to closure. Reviewed at the next audit kickoff.

### 10. Continuous-readiness operating model

The thing that makes audits boring. Monthly or quarterly:

- Control matrix review (any controls retired, new controls in scope, owner changes).
- Evidence freshness check (controls operating and evidence current).
- Mock evidence pulls on a sample of controls.
- Control-owner check-ins.

## Real-world lessons baked into this playbook

- **The PBC list is half the work.** Auditors send a Provided By Client list of documents and evidence they want before fieldwork. Responding well to the PBC list dramatically reduces fieldwork friction.
- **Date stamping matters.** Evidence dated outside the audit period does not count. A penetration test report dated three days after period end is useless. Plan vendor delivery dates carefully.
- **Sample populations must be complete.** If the auditor asks for "all production access changes in the period" and you supply 240 records but the actual count was 312, that is a control failure (incomplete population) that overrides whatever was in the 240 you sent.
- **Auditors talk to each other.** A clean audit this year reduces sampling next year. A messy audit increases it. Treat audit conduct as a long-term relationship.
- **Walk the auditor through the wall, not over it.** When something is messy (an incident, a failed control test, a missed review), explain it, show what you did about it, and provide the corrective-action evidence. Hiding it is much worse than disclosing it.
- **Have one voice.** All auditor communication goes through the GRC lead or designated alternates. Random Slack messages from engineers to auditors create confusion and contradictions.

## Common pitfalls

- **Evidence theatre.** Beautifully formatted PDFs that do not actually demonstrate the control operated.
- **Reverse engineering.** Auditor asks for evidence; team scrambles to generate something. Mature programmes have evidence already; immature programmes manufacture it.
- **Missing approvers.** Evidence shows the action but not the approval. Approval must be reviewable.
- **Stale screenshots.** Screenshots taken 18 months ago of dashboards that have since changed.
- **Surprise control changes.** Quietly changing how a control operates mid-period and not telling the auditor.
- **Defensive posture in interviews.** Control owners argue with the auditor instead of showing how the control works.
- **Relying on heroes.** One person who knows where everything is. When they take leave during fieldwork, the audit collapses.

## Audit considerations (the meta-audit)

A mature programme runs an internal audit-readiness assessment at least annually, ideally before each external audit. Self-test questions include.

- Is the control matrix complete and accurate?
- Has every control been operated and evidenced in the period?
- Are control owners current and trained?
- Is the evidence locker organised and findable?
- Have we run a mock audit this cycle?
- Have we processed last audit's findings to closure?
- Have we updated the matrix for any control changes?
- Is leadership ready for their interviews?

## How this playbook would actually be used

A new Head of GRC arriving at a SaaS company two months before SOC 2 Type 2 fieldwork would:

**Week 1.** Read the existing control matrix. Identify gaps in evidence completeness. Meet every control owner.
**Week 2.** Reorganise the evidence locker to a defined structure. Generate the audit-period evidence checklist. Identify high-risk gaps.
**Week 3-4.** Drive remediation of evidence gaps. Schedule mock audit.
**Week 5.** Run mock audit. Document findings.
**Week 6.** Address mock-audit findings. Brief control owners and executives.
**Week 7.** Receive PBC list from auditor. Respond comprehensively.
**Week 8.** Audit kickoff. Daily standups. Sample handling. Findings discussion.

This is a stressful first eight weeks, but it is survivable with the playbook. Without it, six months disappear into firefighting.

## What I have done in this space and what I have not

I have studied ISO 19011, ISO 27007, AICPA audit guidance, and SOC 2 reporting requirements in detail. I have written the playbook as I would design it.

I have not personally led an organisation through SOC 2 Type 2 fieldwork. I have not negotiated findings language with a Big Four lead auditor. I have not had to explain a missing quarter of management-review minutes. Those experiences would refine the playbook in important ways, particularly around findings negotiation and auditor relationship management.

This is a learning portfolio entry. It demonstrates understanding of what audit readiness requires, not lived audit-week experience.

## Further reading

- **AICPA SOC 2 Description Criteria DC 200 and the Trust Services Criteria.** Free at aicpa-cima.com.
- **ISO 19011:2018 Guidelines for auditing management systems.** Paid; ISO publishes a free overview.
- **ISO/IEC 27007:2020 Guidelines for ISMS auditing.** Paid; free overviews exist.
- **A2LA, ANAB, UKAS** accreditation body sites for what makes an auditor credible.
- **"SOC 2 Compliance Handbook"** by Anetac (or similar practitioner handbooks).
- **AuditBoard, Drata, Vanta blog posts** on audit readiness (vendor content but practically useful, if read with critical eyes).
- **The Big Four firms' published methodologies** (KPMG, PwC, EY, Deloitte) for SOC 2 audits, often available as marketing PDFs.

## Status

Learning portfolio. Playbook complete with templates and timelines. Not exercised in a live audit cycle.
