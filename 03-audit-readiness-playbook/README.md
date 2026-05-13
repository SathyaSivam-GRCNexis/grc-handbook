# Audit Readiness Playbook (ISO 27001 / SOC 2)

## What this is

An operational playbook that takes an organisation from "we have policies and controls" to "we are ready to host an external auditor next week." It covers the six to eight weeks before an external audit (Stage 2 ISO 27001 or SOC 2 Type 2), the conduct of the audit itself and the post-audit remediation period.

The kind of document a Head of GRC writes after surviving their first audit and wishes they had had at the start. No software is delivered. The discipline it imposes is what separates audits that pass cleanly from audits that drag for months.

## What this playbook is trying to fix

Most audit problems are not control problems. They are evidence problems, owner problems and timing problems.

- The control exists. The evidence is in seven different systems and nobody can pull it together inside the auditor's three-day window.
- The control owner left the company two months ago. Nobody got reassigned.
- The auditor asks for a sample of 25 access reviews and the team can find 18.
- Policy says reviews happen quarterly. The last review was six months ago.
- The penetration test happened in the audit period but the report arrived after period end. It does not count.
- Management review minutes are missing for two of the four quarters.
- Risk register entries reference controls that have since been renumbered.

A strong opinion: the weeks before an audit are not about building new controls. They are about evidence freshness, ownership clarity and population completeness. If you are still writing new policy in week three, you are in trouble.

## Why it matters

- Audits complete on time and on budget instead of dragging into expensive overtime.
- Findings are minor observations, not nonconformities or qualifications.
- Customer trust because the SOC 2 report or ISO 27001 certificate arrives when promised.
- Team morale. Audit week is calm rather than chaotic.
- Reputation with the auditor. This compounds across years and influences how they sample.
- Lower audit cost. Efficient evidence delivery means fewer auditor hours billed.

## Framework alignment

- **ISO/IEC 27001:2022** for ISMS audits.
- **ISO/IEC 27007:2020** for ISMS auditing.
- **ISO 19011:2018** for management-system auditing in general.
- **AICPA SSAE 18** and **TSP Section 100** for SOC 2.
- **AICPA Trust Services Criteria 2017 (revised 2022)** for the SOC 2 control framework.
- **NIST SP 800-53A** for control assessment procedures. Useful reference even outside federal scope.
- **ISO/IEC 17021** for certification body requirements, helpful for understanding what a UKAS-accredited body must do.

## What sits in the playbook

### 1. Audit calendar and master timeline

A single source of truth listing every audit due in the next 18 months: period covered, audit firm, lead auditor, key dates (kickoff, fieldwork, draft report, final report) and the internal lead for each.

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

The most useful document in the playbook. A spreadsheet or database where every control is mapped to:

- Framework references (for example SOC 2 CC6.1, ISO 27001 A.8.3).
- Control description.
- Control owner (named individual).
- Evidence type (policy, log extract, screenshot, signed document, ticket export, configuration export).
- System or location where evidence lives.
- Frequency (continuous, daily, weekly, monthly, quarterly, annually, on event).
- Retention requirement.
- Link or path to the most recent evidence.
- Last evidence date.
- Next evidence due.

Auditors call this a "control matrix" and will ask for it. Maintaining it as a live document, not a pre-audit reconstruction, is the core discipline. In my experience this is the thing that most differentiates a mature programme from an immature one.

### 3. Evidence checklist (audit-period-specific)

Generated from the control matrix. The punch list for the upcoming audit. For each control, the specific evidence required for the audit period.

Example.

> **Control:** Access reviews of production systems are performed quarterly.
> **Framework refs:** SOC 2 CC6.1, ISO 27001 A.5.18, A.8.2.
> **Owner:** Engineering Manager, Platform.
> **Evidence required for FY26 audit:** Q1, Q2, Q3, Q4 access review reports including reviewers, reviewers' approval, removed users with date and exception sign-offs.
> **Location:** Confluence space ENG-ACCESS-REVIEWS, JIRA project ACR.
> **Status:** Q1, Q2, Q3 complete and uploaded. Q4 due 15 January, evidence due 30 January.
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

A defined, indexed location (Confluence, SharePoint or a controlled drive) where audit evidence lives. Folder structure mirrors the control matrix. Each evidence item uses a naming convention (`<control-id>_<period>_<evidence-type>_<date>.<ext>`).

Auditors notice the difference between an organised locker and a chaotic one. An organised locker reduces sampling because they trust the operational discipline behind it. The chaotic version invites a deeper look.

### 6. Pre-audit checklist (T-minus templates)

**T-minus 12 weeks**
- Confirm audit scope, period, fieldwork dates.
- Confirm auditor team and any rotations.
- Refresh the control matrix. Identify controls without evidence for the upcoming period.
- Schedule remediation work for any gaps.

**T-minus 8 weeks**
- Run mock audit. Internal team plays auditor against the matrix.
- Address mock-audit findings.
- Confirm logistics (NDAs, system access for auditors, meeting rooms or video calls).
- Brief control owners on what to expect.

**T-minus 4 weeks**
- Final evidence sweep. Every control matrix row has current evidence.
- Confirm all required reports (penetration test, vulnerability scans, awareness training completion) are dated within the audit period.
- Send the pre-audit information request response (PBC list, Provided By Client).

**T-minus 1 week**
- Confirm kickoff agenda.
- Brief executives on what auditors will ask of them in interviews.
- Calm and organised mode.

**Audit week**
- Daily stand-up with audit team and internal team.
- Sample requests handled within the agreed SLA (typically 24 to 48 hours).
- Findings discussed when raised, not at the end.

**T-plus 1 week**
- Receive draft report.
- Walk through findings. Agree language. Dispute or accept each.

**T-plus 4 weeks**
- Receive final report.
- Build remediation plan for any findings.
- Update control matrix to prevent recurrence.

### 7. Sample request handling protocol

Auditors request samples (for example "show me 25 access changes from the period"). The protocol covers:

- Sample size negotiation, within the auditor's methodology.
- Sample selection. Auditor selects from a complete population you supply.
- Evidence delivery format. PDF preferred. Screenshots in context. No raw API dumps without explanation.
- Response time. 24 hours for simple, 48 hours for complex, agreed in kickoff.
- Tracking. Sample log in a shared workspace.

### 8. Auditor interview prep

Control owners are interviewed by the auditor to test that they understand and operate the control. Briefing notes for each interviewed role cover:

- What the auditor will ask. Typical questions: walk me through, what would you do if X, when did you last do this, what was the outcome.
- What evidence the owner will be expected to bring.
- How to handle "I don't know" honestly. Escalate. Follow up. Never guess.
- What not to volunteer. Do not show the auditor your exception register unless asked. Do not speculate about other controls.

### 9. Findings register and remediation tracking

A simple register: finding ID, source (which audit), description, agreed management response, owner, target date, status, evidence of closure. Tracked through to closure. Reviewed at the next audit kickoff.

### 10. Continuous-readiness operating model

The thing that makes audits boring. Monthly or quarterly:

- Control matrix review. Any controls retired, new controls in scope, owner changes.
- Evidence freshness check. Controls operating, evidence current.
- Mock evidence pulls on a sample of controls.
- Control-owner check-ins.

## Where teams stall

A pattern I have seen across SaaS environments preparing for SOC 2 Type 2 or ISO 27001:

- **Hero-driven evidence collection.** One person knows where everything lives. They take leave during fieldwork. The audit goes sideways.
- **Reverse-engineered evidence.** Auditor asks for proof of a control. Team scrambles to generate something that looks like proof. Auditors recognise the pattern instantly. Sampling deepens.
- **Date-stamp blind spots.** A penetration test report dated three days after period end. Useless. Quarterly review dated the week before fieldwork rather than at the proper cadence. Useless.
- **Population gaps.** Auditor asks for all production access changes in the period. The team supplies 240. The actual count was 312. That is a complete-population failure that overrides whatever was in the 240. This single mistake produces more SOC 2 exceptions than any other.

In one SaaS environment, the team realised in week four that quarterly access reviews had been performed for three quarters of the period but the evidence for Q2 was a Slack thread that had since been deleted by retention policy. The fix took ten days of forensic reconstruction and a corrective action recorded with the auditor. Easier to log evidence to a controlled location at the time.

## Lessons baked in

- **The PBC list is half the work.** Auditors send a Provided By Client list before fieldwork. Responding well to the PBC dramatically reduces fieldwork friction.
- **Date stamping matters.** Evidence dated outside the audit period does not count. Plan vendor delivery dates carefully.
- **Sample populations must be complete.** Incomplete populations override the contents of the sample.
- **Auditors talk to each other.** A clean audit this year reduces sampling next year. A messy audit increases it. Treat audit conduct as a long-term relationship.
- **Walk the auditor through the wall, not over it.** When something is messy (an incident, a failed control test, a missed review), explain it, show what you did about it, provide the corrective-action evidence. Hiding it is much worse than disclosing it.
- **Have one voice.** All auditor communication goes through the GRC lead or designated alternates. Random Slack messages from engineers to auditors create contradictions.

## Common pitfalls

- **Evidence theatre.** Beautifully formatted PDFs that do not actually demonstrate the control operated.
- **Missing approvers.** Evidence shows the action but not the approval. Approval must be reviewable.
- **Stale screenshots.** Screenshots taken 18 months ago of dashboards that have since changed.
- **Surprise control changes.** Quietly changing how a control operates mid-period and not telling the auditor.
- **Defensive interviews.** Control owners argue with the auditor instead of showing how the control works.

## The meta-audit

A mature programme runs an internal audit-readiness assessment at least annually, ideally before each external audit. Self-test questions:

- Is the control matrix complete and accurate?
- Has every control been operated and evidenced in the period?
- Are control owners current and trained?
- Is the evidence locker organised and findable?
- Have we run a mock audit this cycle?
- Have we processed last audit's findings to closure?
- Have we updated the matrix for any control changes?
- Is leadership ready for their interviews?

## How this playbook gets used

A new Head of GRC arriving at a SaaS company two months before SOC 2 Type 2 fieldwork would, in my experience:

**Week 1.** Read the existing control matrix. Identify evidence gaps. Meet every control owner.
**Week 2.** Reorganise the evidence locker. Generate the audit-period evidence checklist. Identify high-risk gaps.
**Weeks 3 to 4.** Drive remediation of evidence gaps. Schedule mock audit.
**Week 5.** Run the mock audit. Document findings.
**Week 6.** Address mock-audit findings. Brief control owners and executives.
**Week 7.** Receive the PBC list. Respond in full.
**Week 8.** Audit kickoff. Daily standups. Sample handling. Findings discussion.

Eight stressful weeks, but survivable with the playbook. Without it, six months disappear into firefighting and the first audit cycle produces qualifications.

## What I have done and what I have not

I have studied ISO 19011, ISO 27007, AICPA audit guidance and SOC 2 reporting requirements in detail. I have written this playbook as I would design it.

I have not personally led an organisation through SOC 2 Type 2 fieldwork. I have not negotiated findings language with a Big Four lead auditor. I have not had to explain a missing quarter of management-review minutes. Those experiences would refine the playbook, particularly around findings negotiation and auditor relationship management.

This is a learning portfolio entry. It demonstrates understanding of what audit readiness requires, not lived audit-week experience.

## Further reading

- **AICPA SOC 2 Description Criteria DC 200 and the Trust Services Criteria.** Free at aicpa-cima.com.
- **ISO 19011:2018.** Paid. ISO publishes a free overview.
- **ISO/IEC 27007:2020.** Paid. Free overviews exist.
- **A2LA, ANAB, UKAS** accreditation body sites for what makes an auditor credible.
- **Practitioner SOC 2 handbooks** from established publishers.
- **AuditBoard, Drata, Vanta blog posts** on audit readiness. Vendor content but usable if read with a critical eye.
- **The Big Four firms' published methodologies** for SOC 2 audits, often available as marketing PDFs.

## Status

Learning portfolio. Playbook complete with templates and timelines. Not exercised in a live audit cycle.
