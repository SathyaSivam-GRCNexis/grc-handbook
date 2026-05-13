# Audit Finding Tracker (Templates)

## What this is

A pack of templates and operating procedures for tracking audit findings and management responses across the organisation. It handles findings from external audits (SOC 2, ISO 27001 surveillance, regulatory examinations, customer security audits) and from internal sources (internal audit, self-assessments, incident post-mortems, pen tests, control effectiveness testing).

This is the template-based counterpart to the Audit Finding Tracker tech project elsewhere in the portfolio. It assumes a spreadsheet, a wiki, or a basic ticketing tool, not a custom platform. Suitable for organisations that have not yet justified investment in dedicated software, which is most of them honestly.

## Why this matters

Findings are the most visible piece of evidence about programme health. The way you handle them is itself observed in the next audit cycle. Auditors talk to each other across firms more than people think, and the prior year's open items are the first thing the next year's senior manager reads.

Teams with finding discipline:

- Close items inside the agreed window.
- Avoid repeat findings on the same control year after year.
- Have visible management response and root-cause learning.

Teams without it:

- Carry overdue findings into the next cycle.
- Repeat the same finding two or three times.
- Get worse opinions or qualified reports.
- Lose customer trust when reports surface in procurement.

Of all of these, the ageing buckets matter more than severity. A Minor finding open for 11 months reads worse to a regulator than a Critical closed inside two weeks. People forget this.

## Components

### 1. Intake and registration

One intake channel per source. Findings get registered the same day, not "when there's time."

| Source | Intake channel | Owner |
|---|---|---|
| External SOC 2 / ISO audit | Auditor draft and final report | GRC Lead |
| Customer audit | Customer questionnaire response with concerns flagged | Sales engineering + GRC |
| Regulatory examination | Examination report or MRA / MRIA letter | GRC Lead + Legal |
| Internal audit | Internal audit report | Internal Audit |
| Self-assessment / control testing | Control owner self-test outputs | Control owner |
| Pen test | Pen-test report | Security Lead |
| Incident root-cause | PIR action items | IR Lead |
| Bug bounty / vulnerability disclosure | Triage queue | Security Lead |

Every finding gets an immutable Finding ID at registration. No exceptions. I have seen too many cases where a finding was "tracked informally in Slack" and then could not be evidenced when asked.

### 2. The finding record

Each finding carries the following fields.

| Field | Notes |
|---|---|
| Finding ID | F-YYYY-NNNN |
| Source | From the table above |
| Source reference | Auditor reference number, page, or section |
| Title | One sentence summarising the issue |
| Description | What was observed; what the auditor concluded |
| Severity | Critical / Major / Moderate / Minor / Observation |
| Affected control(s) | Canonical control IDs |
| Affected systems / processes | |
| Date raised | |
| Date due (per source SLA) | |
| Owner | Single named individual |
| Remediation lead | If different from owner |
| Management response | Agreed response language for the auditor |
| Root cause | Process, design, knowledge, resource, supplier |
| Treatment plan | What will actually be done |
| Compensating controls | Where applied during remediation |
| Status | Open / In progress / Pending validation / Closed / Accepted |
| Acceptance approver | If status is Accepted |
| Validation method | How closure will be evidenced |
| Validator | Who validates closure (must not be the remediator) |
| Date closed | |
| Closure evidence reference | Link or path |
| Last update | |
| Next update due | |

The two fields that earn their place above the rest: **management response** (what you told the auditor) and **closure evidence reference** (what you actually did). Auditors compare them. So do customers reading SOC 2 reports.

### 3. Severity and SLA

| Severity | Definition | Default closure SLA |
|---|---|---|
| Critical | Material control failure with active risk; regulatory or customer notification likely | 14 days |
| Major | Significant control failure; remediation required for next audit cycle | 60 days |
| Moderate | Control weakness; remediation required within reporting cycle | 90 days |
| Minor | Observation requiring remediation but lower urgency | 180 days |
| Observation | Auditor suggestion or improvement opportunity | Tracked, not SLA-bound |

SLAs can be overridden by the source (regulator deadline, contract deadline, accepted-risk deferral). Override reasons are recorded.

### 4. Lifecycle

```
Identified -> Triaged -> Assigned -> In Progress -> Pending Validation -> Closed
                                                  |
                                                  +-> Accepted (with approval)
                                                  |
                                                  +-> Rejected (returned for further work)
```

Every state transition is logged with date and actor.

### 5. Validation discipline

Closure is not declared by the person who fixed it. Independent validation, every time.

- Control fixes: the validator repeats the control test with a fresh sample.
- Policy / process changes: validator reviews documentation and interviews affected staff.
- Technical changes: validator reviews configuration and test evidence.

Validators can sit in GRC, internal audit, or a peer team. The remediator cannot validate their own work. This is the discipline external auditors test for hardest. It is also the one most likely to get quietly skipped under deadline pressure.

### 6. Acceptance

When remediation is not feasible now.

- Business case for acceptance, including duration.
- Compensating controls in place and recorded.
- Approval at the right authority level (Major and above requires CISO; Critical requires an executive sponsor).
- Acceptance recorded with an expiry date.
- Re-evaluation at expiry: re-accept, remediate, or escalate.

Findings cannot quietly age out. Aged items either close or convert to formal acceptance. "Aged accepted" is not a state, it is a smell.

### 7. Reporting cadence

| Forum | Cadence | Content |
|---|---|---|
| GRC team review | Weekly | All open findings, status, blockers |
| Engineering / GRC sync | Bi-weekly | Findings affecting engineering controls |
| CISO review | Monthly | All Major+, all overdue, all aged accepted |
| Executive committee | Quarterly | Critical and Major, repeat findings, programme trends |
| Audit committee / board | Quarterly | Finding metrics, repeat findings, regulator outputs |
| External auditor | Per audit cycle | Status of prior-period findings |

### 8. Repeat findings

A repeat finding is an organisational signal, not just a control failure.

- Flag any new finding mapping to a closed historical one.
- Root-cause analysis specifically asking why the prior remediation failed.
- Escalation to CISO and ExCo at identification.
- Repeat-finding count reported to board.

Auditors specifically look for repeat findings. They erode credibility faster than almost anything else. In one SaaS environment, a single repeat finding on access reviews shifted the conversation with the customer-trust team from "renewal" to "remediation plan required." Two years of clean work undone.

### 9. Customer audit findings

When a customer audits you or escalates a questionnaire concern, the findings come into the same tracker. Same fields, same SLAs.

- Avoids parallel processes.
- Stops inconsistent handling across customers.
- Means the customer-visible work follows the same rigour as the SOC 2 report.

### 10. Metrics

- Open findings by severity.
- Closed-within-SLA percentage.
- Mean and median time to close, by severity.
- Aged findings (open beyond SLA). **This is the metric to lead with.** Ageing buckets are usually a better signal of programme health than severity counts.
- Aged accepted findings (accepted beyond 12 months).
- Repeat findings (count and trend).
- Findings by source.
- Findings by control area (where do issues cluster).
- Validator independence percentage.

### 11. Templates included

- Finding intake form (for self-raised findings).
- Finding record template (spreadsheet or wiki).
- Management response template (for external audit responses).
- Acceptance approval template.
- Validation evidence template.
- Closure notification template.
- Quarterly board finding report template.
- Repeat-finding RCA template.

## Lessons built into the design

- **Centralisation beats tooling.** One tracker for all findings, regardless of source, beats fancy tooling spread across silos.
- **Owners are individuals.** "The platform team owns it" produces no closure. Name a person.
- **Validation independence is non-negotiable.** Self-closure of own findings is the most common audit weakness I see written up.
- **Aged accepteds rot.** "Accepted with compensating control" becomes "forgotten" without a review cadence.
- **Auditors notice response quality.** "We will address this" gets pushed back. Specific, dated, owned responses pass.
- **Customer audits are first-class.** Treat them informally and you end up with inconsistent posture across customers.

## Where teams stall

- **Spreadsheet sprawl.** A register per audit, never consolidated.
- **Missing severities.** Recorded without a severity, so the SLA cannot apply.
- **Drifting owners.** People move teams, no reassignment.
- **Closure without evidence.** "Closed" with no link, no validator, no nothing.
- **Repeat findings ignored.** Same item back next year, no RCA.
- **Acceptance as escape hatch.** Anything inconvenient becomes "accepted" with a thin compensating control.
- **No board visibility.** Metrics never reach the board, so accountability never lands.

## What auditors actually ask for

- Show me your finding tracker.
- Show me every finding from the most recent SOC 2. Current status of each?
- Show me a finding closed in the past 90 days. Show me the validation evidence.
- Show me an accepted finding. Show me the approval and the compensating control.
- Show me a repeat finding from last year. What did you do differently this time?
- Show me how the board sees this.

## What I have done here and what I have not

I have worked through SOC 2 reporting expectations, ISO 27001 nonconformity processes (Clause 10.2), regulatory examination workflows (FedRAMP POAM, banking MRA/MRIA), and a few audit-software product designs.

I have not personally negotiated finding closure with a Big Four senior at 11pm before a deadline. I have not had to explain a repeat finding to an audit committee chair. I have not had to handle a regulator-imposed remediation deadline that was demonstrably impossible. These conversations shape real programmes more than any template.

This is a learning portfolio entry.

## Further reading

- **AICPA SSAE 18 and SOC 2 reporting standards.** Free at aicpa-cima.com.
- **ISO/IEC 27001:2022 Clause 10.** Paid; ISO and BSI summaries are useful.
- **FedRAMP POAM template and Continuous Monitoring Strategy Guide.** Free at fedramp.gov.
- **NIST SP 800-53A** assessment procedures. Free at csrc.nist.gov.
- **Bank of England, FCA, PRA examination guidance** on finding letters (s166, MRA, MRIA).
- **IIA Practice Guide series** on internal audit findings discipline. Members-only, summaries free.

## Status

Learning portfolio. Templates and procedures defined. Not used as a live finding tracker.
