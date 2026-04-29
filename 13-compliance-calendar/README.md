# Compliance Calendar

## What this project is

A consolidated calendar of every recurring compliance, audit, regulatory, contractual, and certification obligation an organisation must meet, with owners, lead times, dependencies, and reporting forums. Includes the calendar template itself, the operating procedure for maintaining it, and worked examples for a typical SaaS company at SOC 2 + ISO 27001 + GDPR maturity.

This is the document a Head of GRC builds in week one of a new role and refers to weekly. Without it, deadlines are missed, evidence is generated after the fact, and audits start in panic.

## Why this matters

Compliance work is overwhelmingly cyclical. The same activities recur monthly, quarterly, semi-annually, or annually. Most compliance "emergencies" are simply scheduled obligations that nobody scheduled.

A compliance calendar prevents this by making the cycle visible.

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
| Vulnerability scan (external) | Quarterly | n/a (auto) |
| Phishing simulation campaign | Quarterly | 2 weeks setup |
| Disaster recovery test | Annual or semi-annual | 4 weeks prep |
| Tabletop exercise | Quarterly | 2 weeks prep |

### Internal governance

| Item | Cadence | Lead time |
|---|---|---|
| ISMS Management Review (Clause 9.3) | Quarterly or annual | 2 weeks prep |
| Risk Committee | Monthly | 1 week prep |
| Audit Committee meetings | Quarterly | 2 weeks prep |
| Board ops resilience review | Annual | 4 weeks prep |
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
| Anti-money laundering refresher (where applicable) | Annual |
| Sanctions screening (where applicable) | Continuous + periodic review |

## Components and deliverables

### 1. Master calendar

A spreadsheet or calendar tool view of all obligations. Each entry has:
- Item.
- Cadence.
- Next due date.
- Owner.
- Lead time required.
- Dependencies (e.g. "requires last quarter's access review evidence").
- Forum where it is reported.
- Last completion date.
- Status.

### 2. Lead-time alerts

For each obligation, automated alerts at lead-time-out. A SOC 2 fieldwork in 12 weeks triggers preparation in week 1. A board meeting in 2 weeks triggers paper drafting now.

### 3. Quarterly view

A single view showing the next 90 days. Used in GRC weekly stand-ups. Items in "needs to start now" highlighted.

### 4. Annual roadmap

A 12-month view, by month. Used for resource planning, budgeting, and staffing.

### 5. Owner dashboards

Per-owner view of upcoming items they own. Reduces dependency on calendar lead chasing each owner.

### 6. Dependency graph

Some obligations depend on others. Pen test must complete before SOC 2 fieldwork. Access reviews must complete before SOC 2 evidence collection. Risk register must be current before management review. Visualising dependencies prevents cascade failures.

### 7. Operating procedure

- Maintainer: GRC Lead or designate.
- Update cadence: weekly stand-up to refresh statuses.
- Triggers: new contract signed (add obligations); new framework adopted (add cycle); regulator change (add or update); customer change (add or remove customer-driven items).
- Review: quarterly review of completeness with department heads.

### 8. Customer-portal alignment

Many SaaS companies maintain trust centres or customer portals showing audit cadences and certificate validity. Calendar feeds these so there is one truth.

### 9. Metrics

- Items completed on time vs total in period.
- Items completed late.
- Items missed entirely.
- Lead-time average vs planned.
- Owner load (items per owner per period).

## Real-world lessons baked into this design

- **Inherited calendars are usually wrong.** New GRC leaders should rebuild the calendar from contracts, regulations, and certifications rather than trust the spreadsheet they were handed.
- **Lead times are usually too short.** Twelve weeks for SOC 2 fieldwork prep is the floor, not the average.
- **Dependencies bite quietly.** A delayed pen test slips SOC 2 fieldwork; a slipped access review breaks SOC 2 evidence; the chain compounds.
- **Customer audits are unpredictable.** A reasonable buffer for inbound customer audits is required.
- **Regulatory clocks restart.** Updates to regulations create new obligations; the calendar must be reviewed against regulatory tracking.
- **Notification clocks are never on the calendar.** They are triggered by events. A separate event-triggered process is needed.

## Common pitfalls

- **Hidden obligations.** Items only one person knows about, never recorded.
- **Stale lead times.** Lead times not updated when systems or process change.
- **No owner.** Items in the calendar but no responsible person.
- **Status as theatre.** Everything green when actually nothing started.
- **Calendar as filing cabinet.** Items present but never reviewed.
- **Single-person dependency.** GRC Lead leaves; calendar memory leaves with them.

## Audit considerations

- Show me your compliance calendar.
- Show me the next 90 days.
- Show me an item completed in the past 90 days. Show evidence of completion.
- Show me an item missed or late. What was the response?

## What I have done in this space and what I have not

I have studied audit cycles, regulatory cadences across multiple regimes, and customer-audit patterns.

I have not personally maintained a compliance calendar through multiple full annual cycles, including the slippage events and recovery moves that calendar discipline produces. I have not had to negotiate a customer audit reschedule against a packed calendar.

This is a learning portfolio entry.

## Further reading

- **AICPA SSAE 18 timing guidance.**
- **ISO/IEC 27001:2022** for ISMS cadence requirements.
- **GDPR Articles 30, 33, 35** for cycle and event-trigger requirements.
- **ICO data protection fee guidance** at ico.org.uk.
- **Companies House** at gov.uk for statutory filings.
- **Calendar tooling guides** from Vanta, Drata, Tugboat Logic blogs (vendor content; useful patterns).

## Status

Learning portfolio. Calendar structure, categories, sample populated entries, and operating procedure defined. Not in live use.
