# Vendor Due Diligence Tracker

## What this project is

A focused operational tracker that records every vendor due diligence assessment underway or completed, the stage each vendor is at, the evidence collected, the questions outstanding, the risk decisions made, and the renewal or reassessment dates. This is the day-to-day operational layer that sits beneath the broader Third-Party Risk Management Toolkit, designed for use by procurement, GRC, and security engineering teams who need to see at a glance "what is in the pipeline."

## Why a separate tracker

The TPRM toolkit defines policy, classification, questionnaires, and contracts. The tracker is the live operational state: who is being assessed right now, who is overdue for reassessment, who is blocked on what evidence. Without this, due diligence work disappears into individual mailboxes, vendors' onboarding stalls, and reassessment cycles silently lapse.

## Components and deliverables

### 1. Vendor pipeline view

| Vendor | Tier | Stage | Initiated | Due | Owner | Status | Blockers |
|---|---|---|---|---|---|---|---|
| Acme Auth Inc. | 1 | Risk decision | 2026-03-12 | 2026-04-30 | GRC + CISO | Pending pen-test summary | Vendor delay |
| BetaSign Ltd | 2 | Questionnaire returned | 2026-04-01 | 2026-04-15 | GRC | Reviewing | None |
| Catnip CRM | 3 | Lite questionnaire issued | 2026-04-22 | 2026-05-13 | GRC | Awaiting response | None |

### 2. Stage definitions

```
Sourcing -> Triage -> Classification -> Questionnaire issued -> Questionnaire returned -> Evidence review -> Risk decision -> Contract negotiation -> Approved -> Onboarded -> Operating
                                                                                                              |
                                                                                                              +-> Conditionally approved (with conditions)
                                                                                                              |
                                                                                                              +-> Rejected (with rationale)
```

Each transition is timestamped with the actor.

### 3. Evidence locker

Per vendor, a structured folder of:
- Questionnaire response (latest version).
- Certifications (SOC 2 Type 2 report, ISO 27001 certificate + SoA, PCI AoC where relevant).
- Pen-test summary or attestation.
- Insurance certificate (cyber, professional indemnity).
- Financial information (audited accounts or D&B).
- Sub-processor list (latest).
- Reference call notes.
- Risk decision record.
- Approved contract (signed PDF).
- Communications history.

### 4. Risk decision record

For each vendor, a one-page record:
- Risk classification justification.
- Material findings from due diligence.
- Risks identified and treatment.
- Conditions of approval (if any).
- Approver and date.
- Review date.
- Linked contract.

### 5. Reassessment scheduler

For approved vendors, the reassessment cadence:
- Tier 1: annual.
- Tier 2: annual.
- Tier 3: biennial.
- Tier 4: triennial.
- Trigger-based: on material event (vendor breach, change of control, regulatory action, scope change).

Tracker shows next reassessment date and lead time. Alerts at lead-time-out.

### 6. Outstanding-evidence tracker

For vendors mid-assessment, the gaps:
- Questionnaire questions awaiting clarification.
- Evidence requested and not received.
- Reference calls pending.
- Internal approvals pending.

Visible to procurement so they can chase appropriately.

### 7. Decision log

Approvals, rejections, and conditional approvals logged with date, actor, and rationale. Useful for audit and for pattern analysis (e.g. why are Tier 2 vendors rejected most often).

### 8. Conditional approvals tracker

Vendors approved with conditions (e.g. "approved subject to delivery of pen-test summary within 60 days"). Conditions tracked to closure. Failure to close converts to rejection or escalation.

### 9. Vendor incident log

When vendors report incidents or breaches affecting our data or services:
- Date received.
- Vendor and contact.
- Incident description.
- Impact on us.
- Actions taken (information request, customer notification, contractual remedy).
- Closure date.
- Lessons.

Linked to incident-management process.

### 10. Metrics

- Vendors in pipeline by stage.
- Average days from initiation to approval, by tier.
- Vendors overdue at any stage.
- Reassessments overdue.
- Conditional approvals open.
- Rejections (count and rationale).
- Tier 1 / Tier 2 vendors with current SOC 2 / ISO certificate.
- Vendor incidents reported in period.

### 11. Templates

- Initial sourcing intake form.
- Tier classification worksheet.
- Risk decision record template.
- Conditional approval letter template.
- Rejection letter template.
- Reassessment kickoff template.
- Vendor incident intake template.

## Operating cadence

- Daily: GRC ops review of pipeline status.
- Weekly: GRC + procurement sync to clear blockers.
- Monthly: CISO review of Tier 1 / Tier 2 status, risk decisions, conditional approvals.
- Quarterly: ExCo concentration risk view; vendor incident summary.
- Annual: full vendor inventory reconciliation; programme effectiveness review.

## Real-world lessons baked into this design

- **The pipeline is the heartbeat.** A clear pipeline view turns vendor management from reactive to proactive.
- **Conditional approvals are a trap.** Without tracking, conditions are forgotten and vendors operate at unmanaged risk.
- **Reassessment is where programmes fail.** Initial onboarding gets attention; year three reassessments quietly slip.
- **Evidence freshness matters.** A SOC 2 Type 2 report from 2022 is not a current attestation in 2026.
- **Decision rationale aids future reuse.** When a similar vendor appears next year, the prior decision record saves weeks of work.

## Common pitfalls

- **Tracker as filing cabinet.** Updated only when someone has time.
- **Stages skipped.** Approval recorded without evidence review.
- **Reassessments dropped.** Vendors approved years ago, never revisited.
- **Conditions forgotten.** Conditional approvals become permanent without conditions met.
- **Pipeline blindness.** Procurement does not see what is stuck in GRC and vice versa.
- **Vendor incident silence.** Vendors notify, GRC notes, nothing else happens.

## Audit considerations

- Show me the vendor pipeline.
- Show me a Tier 1 vendor's full due diligence file.
- Show me the most recent reassessment for a Tier 1 vendor.
- Show me a conditional approval. Has the condition been met?
- Show me a rejected vendor and the rationale.
- Show me a vendor incident and the response.

## What I have done in this space and what I have not

I have studied vendor risk patterns, due diligence methodologies, and contractual mechanics in detail.

I have not personally pushed back a Tier 1 vendor approval that the business desperately wanted to close. I have not had to chase a vendor for evidence that simply does not exist. I have not had to close a Tier 1 contract under deadline with significant unresolved findings.

This is a learning portfolio entry.

## Further reading

- **Shared Assessments SIG / SIG Lite** at sharedassessments.org.
- **Cloud Security Alliance CAIQ** at cloudsecurityalliance.org.
- **ICO processor due diligence** at ico.org.uk.
- **NIST SP 800-161 Rev 1.** Free at csrc.nist.gov.
- **Vendor risk product blogs** (Bitsight, Prevalent, OneTrust, Vanta) for operational patterns.

## Status

Learning portfolio. Tracker structure, stages, templates, and operating cadence defined. Not in live operation.
