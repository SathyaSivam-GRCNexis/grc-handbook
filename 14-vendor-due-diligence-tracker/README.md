# Vendor Due Diligence Tracker

## What this is

An operational tracker that records every vendor due diligence assessment underway or completed: the stage each vendor is at, the evidence collected, the questions still outstanding, the risk decisions made, and the next reassessment date. It sits beneath the broader Third-Party Risk Management Toolkit and exists so procurement, GRC, and security engineering can all see, at a glance, what is in the pipeline and what is stuck.

## Why a separate tracker

The TPRM toolkit defines policy, classification, questionnaires, and contracts. The tracker is the live operational state. Who is being assessed right now. Who is overdue for reassessment. Who is blocked on what piece of evidence. Without it, due diligence work disappears into individual mailboxes, vendor onboarding stalls, and reassessment cycles quietly lapse.

Two opinions up front, because they shape everything below.

First, questionnaire-only assessments lie. A vendor with a well-written SIG and a glossy trust page can still be a mess inside. Tiering plus actual evidence review plus reference calls is the minimum bar for anything Tier 1 or Tier 2.

Second, the reassessment cycle is where most programmes fail. Initial onboarding gets attention. Year three quietly slips. The whole tracker is designed around that failure mode.

## Components

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

Every transition is timestamped with the actor. Yes, it is tedious. Yes, you will be glad of it when the auditor asks who approved what.

### 3. Evidence locker

A structured folder per vendor:

- Questionnaire response (latest version).
- Certifications (SOC 2 Type 2, ISO 27001 certificate plus SoA, PCI AoC where relevant).
- Pen-test summary or attestation.
- Insurance certificate (cyber, professional indemnity).
- Financial information (audited accounts or D&B).
- Sub-processor list (latest).
- Reference call notes.
- Risk decision record.
- Approved contract (signed PDF).
- Communications history.

Check certificate dates. A SOC 2 Type 2 from two years ago is not a current attestation, no matter how nicely the trust page presents it.

### 4. Risk decision record

A one-pager per vendor:

- Tier classification justification.
- Material findings from due diligence.
- Risks identified and treatment.
- Conditions of approval (if any).
- Approver and date.
- Review date.
- Linked contract.

### 5. Reassessment scheduler

Reassessment cadence for approved vendors:

- Tier 1: annual.
- Tier 2: annual.
- Tier 3: biennial.
- Tier 4: triennial.
- Trigger-based: on material event (vendor breach, change of control, regulatory action, scope change).

Tracker shows next reassessment date and lead time. Alerts at lead-time-out. The trigger-based row is the one most teams forget to operationalise; usually it works for a year, then somebody changes role and the trigger never fires again.

### 6. Outstanding-evidence tracker

For vendors mid-assessment, the gaps:

- Questionnaire questions awaiting clarification.
- Evidence requested and not received.
- Reference calls pending.
- Internal approvals pending.

Visible to procurement so they can chase. If only GRC can see the blockers, procurement assumes silence means progress.

### 7. Decision log

Approvals, rejections, conditional approvals. Each logged with date, actor, and rationale. Useful for audit. Also useful for pattern analysis: in one SaaS environment, six months of decision-log review showed that almost every Tier 2 rejection was on the same issue (no sub-processor flow-downs). That fed back into how the team scoped early questions and saved time on both sides.

### 8. Conditional approvals tracker

Vendors approved with conditions ("approved subject to delivery of pen-test summary within 60 days"). Conditions tracked to closure. Missed conditions convert to rejection or escalation.

Conditional approvals are a useful tool and a recurring trap. They get attention on day one. Day sixty, nobody remembers. Make the close-out date a calendar entry, not a footnote.

### 9. Vendor incident log

When a vendor reports an incident affecting our data or services:

- Date received.
- Vendor and contact.
- Incident description.
- Impact on us.
- Actions taken (information request, customer notification, contractual remedy).
- Closure date.
- Lessons.

Linked to the incident-management process. Vendor incidents are often the first signal a tier classification was wrong.

### 10. Metrics

- Vendors in pipeline by stage.
- Average days from initiation to approval, by tier.
- Vendors overdue at any stage.
- Reassessments overdue. **This is the metric to lead with.** It is the truest indicator of programme health.
- Conditional approvals open.
- Rejections (count and rationale).
- Tier 1 / Tier 2 vendors with current SOC 2 / ISO certificate.
- Vendor incidents reported in period.

### 11. Templates

- Initial sourcing intake form.
- Tier classification worksheet.
- Risk decision record template.
- Conditional approval letter.
- Rejection letter.
- Reassessment kickoff template.
- Vendor incident intake template.

## Operating cadence

- Daily: GRC ops scan of pipeline status.
- Weekly: GRC and procurement sync to clear blockers.
- Monthly: CISO review of Tier 1 / Tier 2 status, risk decisions, conditional approvals.
- Quarterly: ExCo concentration risk view; vendor incident summary.
- Annual: full vendor inventory reconciliation; programme effectiveness review.

The annual reconciliation matters more than it sounds. Shadow vendors keep appearing, usually on engineering's credit cards.

## Lessons built into the design

- **The pipeline is the heartbeat.** A clear pipeline view turns vendor management from chase-mode into something teams can plan around.
- **Conditional approvals are a trap.** Without active tracking, conditions are forgotten and the vendor runs at unmanaged risk.
- **Reassessment is where programmes fail.** Onboarding gets attention. Year three quietly slips.
- **Evidence freshness matters.** A 2022 SOC 2 Type 2 is not a 2026 attestation.
- **Decision rationale aids reuse.** A similar vendor next year is half the work if last year's decision record is intact.
- **Questionnaire-only does not cut it for Tier 1.** Treat the questionnaire as a starting point, not the assessment.

## Where teams stall

- **Tracker as filing cabinet.** Updated when somebody has time, which is never.
- **Stages skipped.** Approval recorded with evidence review missing.
- **Reassessments dropped.** Vendors approved years ago, never revisited. The single most common audit finding I have seen in this space.
- **Conditions forgotten.** Conditional approvals quietly become permanent.
- **Pipeline blindness.** Procurement does not see what is stuck in GRC, and vice versa.
- **Vendor incident silence.** Vendor notifies, GRC notes the email, nothing else happens.

## What auditors actually ask for

- Show me the vendor pipeline.
- Show me a Tier 1 vendor's full due diligence file.
- Show me the most recent reassessment for a Tier 1 vendor.
- Show me a conditional approval. Has the condition been met?
- Show me a rejected vendor and the rationale.
- Show me a vendor incident and the response.

The reassessment question is the one that bites.

## What I have done here and what I have not

I have worked through vendor risk patterns, due diligence methodologies, and contractual mechanics in detail.

I have not personally pushed back a Tier 1 vendor approval that the business desperately wanted closed. I have not had to chase a vendor for evidence that simply does not exist. I have not had to close a Tier 1 contract under deadline with significant unresolved findings. Those conversations shape real programmes more than the templates do.

This is a learning portfolio entry.

## Further reading

- **Shared Assessments SIG / SIG Lite** at sharedassessments.org.
- **Cloud Security Alliance CAIQ** at cloudsecurityalliance.org.
- **ICO processor due diligence guidance** at ico.org.uk.
- **NIST SP 800-161 Rev 1.** Free at csrc.nist.gov.
- **DPDP processor obligations** (India) and **RBI outsourcing guidelines** for regulated entities.
- **Vendor risk product blogs** (Bitsight, Prevalent, OneTrust, Vanta). Vendor content, useful operational patterns.

## Status

Learning portfolio. Tracker structure, stages, templates, and operating cadence defined. Not in live operation.
