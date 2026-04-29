# Business Continuity & Disaster Recovery Framework

## What this project is

A complete framework for ensuring an organisation can continue critical operations through disruption (business continuity) and restore IT services and data following destructive incidents (disaster recovery). Includes Business Impact Analysis (BIA) methodology, recovery objectives, plans, testing, governance, and integration with incident response and crisis management.

This is the framework a Head of Operational Resilience, CISO with BCDR remit, or Head of GRC would build to satisfy regulators (DORA, PRA SS1/21 / SS2/21, NIS2), certifications (ISO 22301, ISO 27001 Annex A.5.29-A.5.30), and the basic business requirement that customers continue to be served when something breaks.

## Problem this framework solves

Organisations without a real BCDR programme tend to share these symptoms.

- BCDR documents exist as a 200-page binder updated for the last audit, not opened since.
- Recovery time objectives (RTOs) are wishful (the documented RTO is 4 hours; nobody has ever tested under 24).
- Backups exist but restoration has never been tested end to end.
- Critical functions are concentrated on single individuals; when they are unavailable, the function stops.
- Cloud-region failover is documented but untested; the standby region has stale configuration.
- Crisis communication assumes the office is reachable; pandemic and remote-working caught everyone out.
- The IT recovery team and the business continuity team plan in separate spreadsheets that never meet.
- Suppliers' continuity is unknown.
- The board last engaged with BCDR seven years ago.

A working framework fixes these by tying recovery objectives to business impact, testing actual recovery rather than reading documents, and linking IT, business, suppliers, people, premises, and crisis management into one programme.

## Business impact

- Reduced downtime and faster service recovery, directly preserving revenue and customer trust.
- Regulatory compliance with operational-resilience expectations (UK PRA SS1/21 and SS2/21, EU DORA, NIS2, sector-specific).
- ISO 22301 certifiability where commercially relevant.
- Insurance: BCDR maturity is increasingly a condition of cyber and business-interruption coverage.
- Customer assurance through tested recovery commitments.
- Supplier conversations that are evidence-based, not aspirational.
- Reduced cost of incidents because recovery is structured rather than improvised.

## Framework alignment

- **ISO 22301:2019** Security and resilience - Business continuity management systems.
- **ISO 22313:2020** Guidance on the use of ISO 22301.
- **ISO 22317:2021** BIA guidelines.
- **ISO/IEC 27031:2011** ICT readiness for business continuity (under revision).
- **ISO/IEC 27001:2022 Annex A.5.29 and A.5.30** information security during disruption and ICT readiness for business continuity.
- **NIST SP 800-34 Rev 1** Contingency Planning Guide for Federal Information Systems.
- **NIST CSF 2.0** RECOVER (RC) function.
- **UK PRA Supervisory Statement SS1/21 Operational resilience: impact tolerances for important business services.**
- **UK PRA SS2/21 Outsourcing and third party risk management** for supplier-resilience expectations.
- **DORA (Regulation (EU) 2022/2554) Articles 11-14** ICT business continuity policy, response and recovery plans, and testing.
- **NIS2 Article 21(2)(c)** business continuity management.
- **Basel Committee Principles for Operational Resilience (BCBS 239 + 2021 Principles).**
- **Bank of England, FCA, PRA Operational Resilience Policy Statements (2021).**

## Core concepts

The framework rests on a small set of definitions that must be applied consistently.

### Critical business services

The customer-facing services whose disruption causes intolerable harm to customers, the firm, market integrity, or financial stability. The PRA term is **Important Business Services**. DORA refers to **critical or important functions**.

Examples for a SaaS company: customer authentication, customer-data access, transaction processing, support contact, billing.

### Impact tolerance

The maximum tolerable disruption (in time, in volume, in monetary terms) for each critical business service before harm becomes intolerable. Distinct from RTO (an internal recovery target). Impact tolerance is a board-set commitment to customers and regulators.

Example: "Customer authentication impact tolerance is 4 hours of unavailability in any rolling 12-hour window."

### Recovery time objective (RTO)

How quickly a process or service must be restored after disruption.

### Recovery point objective (RPO)

How much data loss is tolerable, measured as the time between the last good backup or replica and the disruption.

### Maximum tolerable period of disruption (MTPD)

The point beyond which the survival of the organisation is at risk. RTO must be substantially shorter than MTPD.

### Resources required to recover (RRR)

People, systems, premises, suppliers, data, working capital required to restore service to its minimum acceptable level.

### Minimum business continuity objective (MBCO)

The minimum level of service that must be maintained or restored quickly, even if full service takes longer.

## Components and deliverables

### 1. BCDR policy

Board-approved policy stating commitment, scope, governance, and basic principles. Reviewed annually.

### 2. Business Impact Analysis (BIA) methodology and outputs

The BIA is the most important single document. It identifies critical processes and services, quantifies the impact of their disruption over time, and drives recovery objectives.

BIA per critical service captures:
- Description.
- Owner.
- Customer-facing impact at 1 hour, 4 hours, 24 hours, 72 hours, 1 week.
- Financial impact at the same time points.
- Regulatory impact at the same time points.
- Reputational impact.
- Dependencies (people, systems, suppliers, premises, data).
- MTPD.
- Recommended RTO and RPO.
- Recommended impact tolerance.
- Minimum acceptable level of service.

BIA is refreshed annually and on material change.

### 3. Recovery strategies

For each critical service, a defined strategy.

- **People:** cross-training, succession planning, third-party coverage.
- **Systems:** redundancy, multi-region failover, manual workaround.
- **Data:** backup strategy, replication, point-in-time recovery.
- **Premises:** alternate site, remote-working capability, hot site.
- **Suppliers:** alternate vendors, contractual continuity obligations.
- **Communications:** alternate channels, customer notification mechanisms.

### 4. Disaster recovery plans (technical)

For each critical IT system, a documented recovery procedure.

- Trigger criteria.
- Roles and responsibilities.
- Step-by-step recovery procedure.
- Required resources.
- Validation criteria.
- Estimated recovery time.
- Communications during recovery.
- Roll-back procedures if recovery fails.

DR plans are owned by the IT/engineering teams that run the systems. The BC programme integrates them but does not write them.

### 5. Business continuity plans (operational)

For each critical business function, a documented continuity plan.

- Activation criteria.
- Responsibilities.
- Manual workarounds.
- Reduced-service operating procedures.
- Communication to internal teams and customers.
- Resource requirements (additional people, third-party support).
- Restoration to normal operations.

### 6. Crisis management plan

The umbrella response when an event exceeds normal incident management. Includes crisis team composition, decision authorities, war room (physical or virtual), executive briefing cadence, board notification, regulatory engagement, and customer and media communications.

Triggered by SEV-1 incidents, regulatory crises, severe physical incidents, or extended disruption.

### 7. Communications plans

- Internal: staff status, instructions, reassurance.
- Customer: status page, direct communications, support messaging.
- Supplier: invoking continuity clauses, requesting heightened service.
- Regulator: notification per applicable regimes.
- Media: holding statements, planned briefings.
- Investor / shareholder where applicable.

Templates pre-approved.

### 8. Testing programme

The BCDR programme is only credible to the extent it has been tested.

| Test type | Frequency | Scope |
|---|---|---|
| **Plan walk-through** | Annual | Read through and validate plans for each critical service |
| **Tabletop exercise** | Semi-annual | Discussion-based simulation of a scenario |
| **Component test** | Quarterly | Test individual components (single backup restoration, single failover) |
| **Functional test** | Annual | End-to-end recovery of a single critical service in a controlled environment |
| **Full simulation** | Biennial | Simulate full disruption with multiple services failing |
| **Live failover** | Annual where feasible | Real failover of a real service in production |
| **Crisis exercise** | Annual | Executive team exercises crisis response |

Each test produces a report. Findings tracked to closure.

DORA, PRA, and NIS2 increasingly demand evidence of meaningful testing including scenarios approaching severe-but-plausible.

### 9. Supplier continuity

Critical suppliers (Tier 1 from TPRM) must have:
- Documented continuity plans seen and assessed.
- Contractual continuity obligations.
- Alternate-supplier mapping.
- Inclusion in our own scenario testing where they would be involved.

### 10. Roles and responsibilities

| Role | Responsibility |
|---|---|
| **Board** | Approves policy and impact tolerances. Receives annual report on resilience. |
| **CEO / Crisis Director** | Leads crisis response. Final decision authority during major events. |
| **Head of Operational Resilience / BCDR Lead** | Owns the framework and programme. |
| **Service owners** | Own BIA and recovery plans for their services. |
| **IT / Engineering** | Owns DR plans. Operates technical recovery. |
| **Communications** | Owns external messaging. |
| **HR** | Owns people aspects (welfare, alternate working arrangements). |
| **Facilities** | Owns premises continuity. |
| **Procurement** | Owns supplier continuity. |
| **Internal audit** | Independent assurance. |

### 11. Governance

- Operational resilience committee meets quarterly. Membership: BCDR Lead, CISO, Head of Engineering, Head of Operations, Head of People, Legal.
- BCDR forum meets monthly. Membership: BCDR Lead, service owners, key technical leads.
- Board operational resilience review annually.
- Regulatory submissions on cycle.

### 12. Metrics

- Coverage: percentage of critical services with current BIA and tested plan.
- Testing: tests planned vs completed; findings closed within target.
- Recovery: actual RTO performance during real incidents and tests vs documented RTO.
- Impact tolerance breaches: count and details.
- Action item closure from tests.
- Supplier continuity coverage.

## Real-world lessons baked into this framework

- **Documented does not equal recoverable.** A polished plan that has never been exercised is theatre. Testing is the test.
- **People assumptions break first.** Plans assume specific individuals will be available. Pandemics, severe weather, and family emergencies disprove the assumption regularly.
- **Cloud is not magic resilience.** Multi-AZ does not save you from regional outages. Multi-region is hard and expensive and most teams have not tested it under real production load.
- **Backups must restore.** Untested backups are not backups; they are encrypted unknowns.
- **Suppliers cascade.** Vendor concentration and lack of alternate-vendor relationships turn a single supplier failure into your outage.
- **Crisis comms are practised, not improvised.** Statements drafted at 2am in panic embarrass the company.
- **Operational resilience > business continuity > disaster recovery.** Modern regulatory framing centres on the customer-facing service, not internal IT systems. Frameworks built top-down from BCDR rarely meet operational-resilience expectations.
- **Severe-but-plausible scenarios.** Testing only "easy" scenarios proves only that you can recover from "easy" scenarios. Regulators want hard tests.

## Common pitfalls

- **BIA inflation.** Every service is "critical." Recovery investment is impossible to prioritise.
- **RTO fantasy.** RTOs that have never been tested. The documented RTO becomes the customer commitment until the first real disruption.
- **Backup blindness.** Backups configured but restoration never tested. Restoration that takes 18 hours but RTO claims 4.
- **Plan without people.** Detailed technical recovery plans, no consideration of who is actually available to execute them.
- **Single point of failure: the document author.** The BCDR Lead leaves; nobody else understands the framework.
- **Test theatre.** Tests run with maximum prep and notice; success is foregone. Real disruption is unannounced.
- **Supplier trust without verification.** Vendor SOC 2 mentions BCP; we never check the testing evidence.
- **Crisis decisions made in panic.** Authority not pre-defined; senior people argue over who can decide what.

## Audit considerations

- Show me your BCDR policy.
- Show me your BIA. Pick a critical service and walk me through it.
- Show me the recovery plan for that service.
- Show me the most recent test for that service. What were the findings? Have they been closed?
- Show me your impact tolerances. How were they set?
- Show me a service whose actual recovery time exceeded RTO. What was the response?
- Show me your supplier continuity assessments for Tier 1 suppliers.
- Show me your last crisis exercise. Show me the action items.
- How does the board engage with this programme?

## How this framework would actually be implemented

A 12-month rollout for a 200-500 person SaaS company.

**Months 1-2.** Identify critical business services with executive team. Approve policy. Form operational resilience committee.

**Months 3-4.** Conduct BIA across critical services. Set initial impact tolerances and RTO/RPOs. Identify critical resource dependencies.

**Months 5-7.** Build recovery strategies. Write or update DR plans for technical systems. Write BC plans for business processes.

**Month 8.** Crisis management plan with executive team. Communications templates approved.

**Month 9.** First component tests (backup restoration, single failover). Findings addressed.

**Month 10.** First functional test of a critical service. Findings addressed.

**Month 11.** Tabletop exercise with executive team.

**Month 12.** Full annual report to board. Programme effectiveness review. Plan year 2 enhancements (live failover, multi-region testing, severe-but-plausible scenarios).

## What I have done in this space and what I have not

I have studied ISO 22301, ISO 22313, ISO 27031, NIST 800-34, PRA SS1/21 and SS2/21, DORA Chapter II, and writings on operational resilience.

I have not personally led an organisation through PRA operational-resilience self-assessment. I have not been part of an executive crisis-response team in a real major event. I have not led a multi-region cloud failover under real customer-impact pressure. Those experiences would refine the framework's testing and crisis sections substantially.

This is a learning portfolio entry.

## Further reading

- **ISO 22301:2019** and **ISO 22313:2020.** Paid standards.
- **NIST SP 800-34 Rev 1.** Free PDF at csrc.nist.gov.
- **UK PRA SS1/21 and SS2/21.** Free at bankofengland.co.uk.
- **DORA Regulation (EU) 2022/2554.** Free at eur-lex.europa.eu.
- **Basel Committee Principles for Operational Resilience.** Free at bis.org.
- **The BCI (Business Continuity Institute) Good Practice Guidelines.** Members-only but BCI publishes free overviews.
- **Continuity Central** (continuitycentral.com) for free practitioner content.
- **Resilience First** (resiliencefirst.org) for free thought leadership.
- **ENISA business continuity guidance.** Free at enisa.europa.eu.

## Status

Learning portfolio. Framework, BIA methodology, recovery and crisis plans, testing programme, governance all defined. Not operated against real disruption.
