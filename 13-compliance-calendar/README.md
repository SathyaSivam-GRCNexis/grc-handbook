# Compliance Calendar

## What this is

A consolidated calendar of every recurring compliance, audit, regulatory, contractual, and certification obligation an organisation has to meet. Owners, lead times, dependencies, reporting forums. Includes the calendar template, the operating procedure, and worked examples for a SaaS company at SOC 2 + ISO 27001 + GDPR / DPDP maturity.

This is the document a Head of GRC builds in week one and refers to weekly afterwards. Without it, deadlines slip, evidence gets generated after the fact, and audit prep starts in panic.

## Why this matters

Compliance work is overwhelmingly cyclical. The same activities recur monthly, quarterly, semi-annually, or annually. Most "compliance emergencies" are scheduled obligations that nobody actually scheduled.

A calendar prevents that. It also surfaces the failure mode I see most often: ownership confusion. Two teams assume the other is filing the return. Nobody is. The calendar's main job is to make ownership unambiguous, more than to track dates. Dates are easy. Ownership is the hard problem.

## Categories of obligation

### Audit and certification

| Item | Cadence | Lead time |
|---|---|---|
| SOC 2 Type 2 fieldwork | Annual | 12 weeks prep |
| SOC 2 Type 2 report delivery | Annual (~8 weeks post-fieldwork) | n/a |
| ISO 27001 surveillance audit | Annual | 6 weeks prep |
| ISO 27001 recertification audit | Triennial | 12 weeks prep |
| PCI DSS QSA assessment | Annual (where applicable) | 8 weeks prep |
| Customer-driven audits | Per contract, varies | Per contract |
| Internal ISMS audits | Continuous, by control coverage | 4 weeks prep per cycle |
| Cyber insurance assessment | Annual | 4 weeks prep |
| Penetration test | Semi-annual or annual | 4 weeks prep, 4 weeks remediation |
| External vulnerability scan | Quarterly | n/a (auto) |
| Phishing simulation | Quarterly | 2 weeks setup |
| DR test | Annual or semi-annual | 4 weeks prep |
| Tabletop exercise | Quarterly | 2 weeks prep |

### Internal governance

| Item | Cadence | Lead time |
|---|---|---|
| ISMS Management Review (Clause 9.3) | Quarterly or annual | 2 weeks prep |
| Risk Committee | Monthly | 1 week prep |
| Audit Committee | Quarterly | 2 weeks prep |
| Board operational resilience review | Annual | 4 weeks prep |
| Operational Resilience Committee | Quarterly | 2 weeks prep |
| Privacy Programme Review | Quarterly | 2 weeks prep |
| Vendor Risk Review (Tier 1) | Quarterly per vendor | 1 week prep |
| Policy review cycle | Annual per policy | Per policy |
| Access reviews | Quarterly | 1 week per system |

### Regulatory submissions and notifications

| Item | Cadence | Trigger |
|---|---|---|
| ICO data protection registration renewal | Annual | Calendar |
| ICO breach notifications | On event | 72 hours from awareness |
| EDPB / DPA notifications | On event | 72 hours from awareness |
| DPDP breach notification (India) | On event | As prescribed by the Data Protection Board |
| RBI cyber incident reporting (if regulated entity in India) | On event | 6 hours from detection |
| SEBI CSCRF reporting (regulated entities) | Per circular | Per regime |
| Companies House annual confirmation | Annual | Calendar |
| Pension regulator returns | Per regulator | Calendar |
| HMRC submissions (PAYE etc.) | Per scheme | Calendar |
| FCA / PRA submissions (if regulated) | Per regulator | Calendar |
| DORA register of information update | Quarterly (financial) | Calendar |
| NIS2 incident reporting | On event | 24h initial / 72h intermediate / 1 month final |
| US state breach notifications | On event | Per state statute |
| SEC 8-K cyber disclosures (if registrant) | On event | 4 business days |
| GDPR Art 30 ROPA refresh | At least annual; on change | Calendar |
| Sub-processor change notifications | On change | Per contract |

Regulator clocks drift. DPDP rules and CSCRF circulars in India have moved more than once in their early life; the EU side keeps shipping new instruments. Treat this table as live, not settled. Quarterly review of the regulatory items against actual gazette / regulator updates is the discipline that saves you.

### Contractual obligations

| Item | Cadence | Source |
|---|---|---|
| Customer contract renewals | Per contract | CRM |
| Customer security questionnaires | On request | Sales |
| MSA-required SOC reports | Per customer | Contract |
| MSA-required pentest summaries | Per customer | Contract |
| Vendor contract renewals | Per contract | Procurement |
| Insurance policy renewals | Annual | Finance |

### Operational compliance

| Item | Cadence | Owner |
|---|---|---|
| Backup restoration tests | Per system | Engineering |
| Change advisory board | Weekly | Engineering |
| User access reviews | Quarterly | IT / Engineering |
| Privileged access reviews | Monthly | Security |
| Vendor reassessments | Per tier | GRC |
| Awareness training cycle | Annual + on join | HR / GRC |
| Code of conduct re-acknowledgement | Annual | HR |
| Phishing simulation | Quarterly | Security |

### Financial and regulatory periodic

| Item | Cadence |
|---|---|
| Year-end financial audit | Annual |
| Tax filings | Per regime |
| AML refresher (where applicable) | Annual |
| Sanctions screening (where applicable) | Continuous + periodic review |

## Components

### 1. Master calendar

A spreadsheet or calendar tool view. Each entry has:

- Item.
- Cadence.
- Next due date.
- Owner (a person, not a team).
- Lead time required.
- Dependencies (e.g. "requires last quarter's access review evidence").
- Forum where it is reported.
- Last completion date.
- Status.

### 2. Lead-time alerts

Automated alerts at lead-time-out. SOC 2 fieldwork in 12 weeks fires the prep alert in week 1. Board meeting in 2 weeks fires the paper-drafting alert now.

### 3. Quarterly view

A rolling 90-day view used in the GRC weekly stand-up. Items in "needs to start now" highlighted. This is the view I actually look at. The full calendar is reference; the 90-day view is the working tool.

### 4. Annual roadmap

A 12-month view, by month. Used for resource planning, budget, and staffing. Useful when arguing for headcount.

### 5. Owner dashboards

A per-owner view of upcoming items. Reduces dependency on the GRC team chasing each owner individually. In one SaaS environment, switching from "GRC chases everyone" to "each owner sees their own list" cut missed deadlines noticeably inside two quarters.

### 6. Dependency graph

Some obligations depend on others. Pen test must finish before SOC 2 fieldwork starts. Access reviews must close before SOC 2 evidence collection. Risk register must be current before management review. The chain compounds. Visualising it stops cascade failures.

### 7. Operating procedure

- Maintainer: GRC Lead or designate.
- Update cadence: weekly stand-up to refresh statuses.
- Triggers for adding items: new contract signed; new framework adopted; regulator change; customer change.
- Review: quarterly review of completeness with department heads.

### 8. Customer-portal alignment

Many SaaS companies maintain trust centres showing audit cadences and certificate validity. The calendar feeds those so there is one source of truth, not two that disagree at the worst moment.

### 9. Metrics

- Items completed on time vs total in period.
- Items completed late.
- Items missed entirely.
- Lead-time average vs planned.
- Owner load (items per owner per period). Worth tracking; one or two owners usually carry too much.

## Lessons built into the design

- **Inherited calendars are usually wrong.** New GRC leaders should rebuild from contracts, regulations, and certifications rather than trust the spreadsheet they were handed.
- **Lead times are usually too short.** 12 weeks for SOC 2 fieldwork prep is the floor, not the average. If a customer audit lands in the middle, double it.
- **Dependencies bite quietly.** A slipped pen test slips SOC 2 fieldwork; a slipped access review breaks SOC 2 evidence; the chain compounds and no single person sees it coming.
- **Customer audits are unpredictable.** Hold a buffer for inbound customer audits or they will eat planned work.
- **Regulatory clocks restart.** Updates to regulations create new obligations. The calendar needs a regulatory-tracking input, not just date entries.
- **Notification clocks are never on the calendar.** They are event-triggered. They need their own runbook, not a calendar entry.

## Where teams stall

- **Hidden obligations.** Items only one person knows about, recorded nowhere. Discovered when that person leaves.
- **Stale lead times.** Lead times not updated when systems or processes changed underneath.
- **No owner.** Item in the calendar, no responsible person.
- **Ownership confusion.** Two teams each think the other is filing. Nobody is. This is the failure mode I see most often.
- **Status as theatre.** Everything green when nothing has actually started.
- **Calendar as filing cabinet.** Items present, never reviewed.
- **Single-person dependency.** GRC Lead leaves. Calendar memory goes too.

## What auditors actually ask for

- Show me your compliance calendar.
- Show me the next 90 days.
- Show me an item completed in the past 90 days. Show me the evidence.
- Show me an item missed or late. What was the response?

## What I have done here and what I have not

I have worked through audit cycles, regulatory cadences across multiple regimes (UK, EU, India), and customer-audit patterns in SaaS contexts.

I have not personally run a compliance calendar through multiple full annual cycles with the slippage events and recovery moves that produce the actual discipline. I have not had to negotiate a customer audit reschedule against a packed quarter.

This is a learning portfolio entry.

## Further reading

- **AICPA SSAE 18 timing guidance.**
- **ISO/IEC 27001:2022** for ISMS cadence requirements.
- **GDPR Articles 30, 33, 35** for cycle and event-trigger requirements.
- **DPDP Act 2023 and Rules** (India), as published by MeitY.
- **RBI Master Direction on Cyber Security** for regulated entities in India.
- **SEBI CSCRF circulars** for regulated entities.
- **ICO data protection fee guidance** at ico.org.uk.
- **Companies House** at gov.uk for statutory filings.
- **Vendor calendar guides** (Vanta, Drata, Tugboat Logic blogs). Vendor content, but useful patterns.

## Status

Learning portfolio. Calendar structure, categories, sample entries, and operating procedure defined. Not in live use.
