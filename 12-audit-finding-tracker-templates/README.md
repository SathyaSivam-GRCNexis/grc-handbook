# Audit Finding Tracker (Templates)

## What this project is

A pack of templates and operating procedures for tracking audit findings and management responses across the organisation, from external audits (SOC 2, ISO 27001 surveillance, regulatory examinations, customer security audits) and internal sources (internal audit, self-assessments, incident root-cause analyses, penetration tests, control effectiveness testing).

This is the non-technical, template-based counterpart to the Audit Finding Tracker tech project elsewhere in the portfolio. It assumes a spreadsheet, a wiki, or a basic ticketing tool rather than a custom platform, and is suitable for organisations that have not yet justified investment in dedicated software.

## Why this matters

Audit findings are the most concrete, externally visible evidence of programme weakness. How the organisation handles findings is itself observed in the next audit cycle. Companies with disciplined finding management:

- Close findings within agreed timelines.
- Avoid repeat findings on the same control year over year.
- Have visible evidence of management response and root-cause learning.

Companies without it:

- Carry overdue findings into the next audit.
- Repeat the same finding two or three times.
- Receive worse opinions or qualified reports.
- Lose customer trust when audit reports are shared in procurement.

## Components and deliverables

### 1. Finding intake and registration

A defined intake channel for findings from each source.

| Source | Intake channel | Owner |
|---|---|---|
| External SOC 2 / ISO audit | Auditor's draft and final report | GRC Lead |
| Customer audit | Customer questionnaire response with concerns flagged | Sales engineering + GRC |
| Regulatory examination | Examination report or MRA / MRIA letter | GRC Lead + Legal |
| Internal audit | Internal audit report | Internal Audit |
| Self-assessment / control testing | Control owner self-test outputs | Control owner |
| Penetration test | Pen-test report | Security Lead |
| Incident root-cause | PIR action items | IR Lead |
| Bug bounty / vulnerability disclosure | Triage queue | Security Lead |

Every finding receives an immutable Finding ID at registration.

### 2. Standard finding record

Each finding is recorded with the following fields.

| Field | Notes |
|---|---|
| Finding ID | F-YYYY-NNNN |
| Source | From the table above |
| Source reference | Auditor's reference number, page, or section |
| Title | One sentence summarising the issue |
| Description | What was observed; what the auditor concluded |
| Severity | Critical / Major / Moderate / Minor / Observation |
| Affected control(s) | Reference to canonical control IDs |
| Affected systems / processes | |
| Date raised | |
| Date due (per source SLA) | |
| Owner | Single named individual responsible for closure |
| Remediation lead | If different from owner |
| Management response | Agreed response language for the auditor |
| Root cause | Why this happened (process, design, knowledge, resource, supplier) |
| Treatment plan | What will be done |
| Compensating controls | Where applied during remediation |
| Status | Open / In progress / Pending validation / Closed / Accepted |
| Acceptance approver | If status is Accepted |
| Validation method | How closure will be evidenced |
| Validator | Who validates closure (must not be remediator) |
| Date closed | |
| Closure evidence reference | Link or path |
| Last update | |
| Next update due | |

### 3. Severity and SLA standard

| Severity | Definition | Default closure SLA |
|---|---|---|
| Critical | Material control failure with active risk; regulatory or customer notification likely | 14 days |
| Major | Significant control failure; remediation required for next audit cycle | 60 days |
| Moderate | Control weakness; remediation required within reporting cycle | 90 days |
| Minor | Observation requiring remediation but lower urgency | 180 days |
| Observation | Auditor suggestion or improvement opportunity | Tracked, not SLA-bound |

SLAs may be overridden by the source (regulator-imposed deadline, contractual customer-audit deadline, accepted-risk deferral).

### 4. Finding lifecycle

```
Identified -> Triaged -> Assigned -> In Progress -> Pending Validation -> Closed
                                                  |
                                                  +-> Accepted (with approval)
                                                  |
                                                  +-> Rejected (returned for further work)
```

State transitions logged with date and actor.

### 5. Validation discipline

Closure is not declared by the remediator. Independent validation is required.

- For control fixes: control test repeated by validator with sample.
- For policy / process changes: validator reviews documentation and interviews affected staff.
- For technical changes: validator reviews configuration and test evidence.

Validators may be GRC team, internal audit, or peer team. The remediator cannot validate their own work.

### 6. Acceptance process

When immediate remediation is not possible.

- Business case for acceptance, including duration.
- Compensating controls in place.
- Approval at appropriate authority level (Major+ requires CISO; Critical requires Executive sponsor).
- Acceptance recorded with expiry date.
- Re-evaluation at expiry: re-accept, remediate, or escalate.

Findings cannot be silently aged out. Aged findings either close or convert to accepted.

### 7. Reporting cadence

| Forum | Cadence | Content |
|---|---|---|
| GRC team review | Weekly | All open findings, status, blockers |
| Engineering / GRC sync | Bi-weekly | Findings affecting engineering controls |
| CISO review | Monthly | All Major+, all overdue, all aged accepted |
| Executive committee | Quarterly | Critical and Major findings, repeat findings, programme trends |
| Audit committee / board | Quarterly | Finding metrics, repeat findings, regulatory examination outputs |
| External auditor | Per audit cycle | Status of prior-period findings |

### 8. Repeat finding management

Repeat findings are an organisational signal. The framework requires:

- Identification of any new finding that maps to a closed historical finding.
- Root-cause analysis specifically asking why prior remediation failed.
- Escalation to CISO and ExCo on identification.
- Reporting of repeat-finding count to board.

Auditors specifically test for repeat findings. They are credibility-eroding.

### 9. Customer audit findings

When customers conduct audits or escalate questionnaire concerns, findings flow into the same tracker. This:

- Avoids parallel processes.
- Prevents inconsistent handling.
- Ensures customer-visible findings are managed with the same discipline.

### 10. Metrics

- Open findings by severity.
- Findings closed within SLA (percentage).
- Mean and median time to close, by severity.
- Aged findings (open > SLA).
- Aged accepted findings (accepted > 12 months).
- Repeat findings (count and trend).
- Findings by source (external, internal, customer, regulator, pentest, incident).
- Findings by affected control area (where do issues cluster).
- Validator independence (percentage closed by independent validator).

### 11. Templates

The pack includes:

- Finding intake form (for self-raised findings).
- Finding record template (spreadsheet or wiki).
- Management response template (for external audit responses).
- Acceptance approval template.
- Validation evidence template.
- Closure notification template.
- Quarterly board finding report template.
- Repeat-finding root cause analysis template.

## Real-world lessons baked into this design

- **Centralisation matters more than tooling.** Every finding in one tracker, regardless of source, beats sophisticated tooling distributed across silos.
- **Owners are individuals, not teams.** "The platform team owns it" produces no closure.
- **Validation independence is non-negotiable.** Self-closure of own findings is the most common audit weakness.
- **Aged accepteds rot.** "Accepted with compensating control" becomes "forgotten" if there is no review cadence.
- **Auditors notice management response quality.** Hand-wave responses ("we will address this") get pushed back; specific, dated, owned responses pass.
- **Customer audits are first-class.** Treating them informally leads to inconsistent posture across customers.

## Common pitfalls

- **Spreadsheet sprawl.** Multiple finding registers per audit, no consolidation.
- **Missing severities.** Findings recorded without severity, so SLA cannot apply.
- **Owners drifting.** Owners rotate without re-assignment.
- **Closure without evidence.** "Closed" with no record of what was done or who validated.
- **Repeat findings ignored.** No systemic root-cause analysis when the same finding returns.
- **Acceptance as escape hatch.** Anything inconvenient becomes accepted with weak compensating controls.
- **No board visibility.** Finding metrics never reach the board, so management is never held accountable.

## Audit considerations

- Show me your finding tracker.
- Show me all findings from your most recent SOC 2 audit. What is the status of each?
- Show me a finding closed in the past 90 days. Show me the validation evidence.
- Show me an accepted finding. Show me the approval and the compensating control.
- Show me a repeat finding from last year. What did you do differently?
- Show me how the board sees finding metrics.

## What I have done in this space and what I have not

I have studied SOC 2 reporting expectations, ISO 27001 nonconformity processes (Clause 10.2), regulatory examination workflows (FedRAMP POAM, banking MRA/MRIA), and audit-software product designs.

I have not personally negotiated a finding closure with a Big Four senior audit manager at 11pm before a deadline. I have not had to explain a repeat finding to an audit committee chair. I have not had to handle a regulator-imposed remediation deadline that was demonstrably impossible.

This is a learning portfolio entry.

## Further reading

- **AICPA SSAE 18 and SOC 2 reporting standards.** Free at aicpa-cima.com.
- **ISO/IEC 27001:2022 Clause 10.** Paid; ISO and BSI summarise.
- **FedRAMP POAM template and Continuous Monitoring Strategy Guide.** Free at fedramp.gov.
- **NIST SP 800-53A** assessment procedures. Free at csrc.nist.gov.
- **Bank of England, FCA, PRA examination guidance** for finding-letter formats (s166, MRA, MRIA).
- **The IIA's Practice Guide series** for internal audit findings discipline. Members-only but summaries free.

## Status

Learning portfolio. Templates and procedures defined. Not used as live finding tracker.
