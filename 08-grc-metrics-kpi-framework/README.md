# GRC Metrics & KPI Framework

## What this is

A framework for measuring the effectiveness, efficiency, and maturity of a Governance, Risk, and Compliance programme. It defines a set of KPIs (Key Performance Indicators), KRIs (Key Risk Indicators), KCIs (Key Control Indicators), the data sources behind each, measurement cadence, the audiences and forums where each is reported, and sample dashboards for executive, board, and operational use.

This is the document set a Head of GRC, CISO, or CRO would build to answer the question every executive eventually asks: "How do I know this is working?" In my experience that question arrives about six months after the first big budget conversation, and the answers had better be ready.

## Problem this framework solves

GRC programmes that cannot measure themselves cannot defend themselves at budget time and cannot detect their own failures.

- "We are improving" with no number behind the claim.
- Reports that count activity (number of policies updated) instead of outcome (whether controls actually work).
- Dashboards showing 47 metrics, all green, while the actual programme is on fire.
- Executives losing interest in GRC reporting because nothing ever changes from quarter to quarter.
- Boards unable to tell whether the programme is improving, declining, or flat.
- Teams gaming the metrics because the metrics are misaligned with what actually matters.
- No early warning when a control or risk is degrading.

A working metrics framework separates the dials people watch (KPIs and KRIs) from the gauges teams operate to (KCIs and operational metrics). Each metric is tied to a decision someone is going to make. The framework itself is reviewed periodically to weed out vanity metrics.

Strong opinion. Vanity metrics are the single biggest reason executives stop paying attention to GRC reporting. "Number of policies updated this quarter" tells nobody anything. "Median time to revoke leaver access" tells you whether your IAM actually works. The first is easy to produce; the second is what should be on the dashboard.

## Why it pays back

- Executives believe and use the data, so GRC reporting starts influencing decisions instead of decorating slide packs.
- Board confidence (or appropriate scepticism) calibrated to reality.
- Earlier detection of programme degradation. A metric trends adversely before an incident or finding.
- Budget conversations grounded in evidence. "We reduced this risk by this much; further reduction needs this investment."
- Better audit narratives because measurement evidence is structured rather than improvised.
- Cultural reinforcement. What gets measured gets attention.

## Framework alignment

- **ISO/IEC 27004:2016** Monitoring, measurement, analysis and evaluation for ISMS.
- **ISO 31000:2018** Clause 6.6 Monitoring and review.
- **NIST SP 800-55 Rev 2** Performance Measurement Guide for Information Security.
- **SOC 2 CC4.1 and CC4.2** monitoring activities.
- **ISO 27001 Clause 9.1** monitoring, measurement, analysis and evaluation; and **Clause 9.3** management review.
- **COBIT 2019** for the IT-governance angle (KGI, KPI, KRI definitions).
- **Institute of Risk Management** Risk Indicators guidance.
- **CIS Controls v8.1** measurement and metrics references.
- **FAIR Institute** for quantitative loss-based metrics.

## Categories of measurement

Different metrics serve different purposes. The framework keeps them separate on purpose.

### KPIs - Key Performance Indicators

How well the GRC function is delivering its services. Examples:
- Audit findings closed within SLA.
- Time to onboard a new vendor.
- Internal audit cycle completion.

KPIs are about activity quality.

### KRIs - Key Risk Indicators

Forward-looking measures of risk movement. Examples:
- Number of high-residual risks.
- Concentration index for Tier 1 vendors.
- Average age of accepted risks.

KRIs are about risk trajectory.

### KCIs - Key Control Indicators

Whether controls are operating as designed. Examples:
- Percentage of production access reviewed in the period.
- Mean time to revoke leaver access.
- Patch SLA compliance for critical vulnerabilities.

KCIs are about control health.

### KGIs - Key Goal Indicators (less common but useful)

Whether the programme is hitting its objectives. Examples:
- Customer-perceived security posture (proxy: contracts won where security was a stated factor).
- Zero in-period material incidents.
- Maturity score increase year-on-year.

The four-way split prevents the most common metrics-framework error: mixing activity, control, risk, and outcome metrics into one dashboard where the audience cannot tell what is signal and what is noise.

## A representative metrics catalogue

The framework defines around 50 metrics across the categories above. Below is a representative subset.

### Risk metrics (KRIs)

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| Number of high or critical residual risks | Count of risks scored 10+ on the residual matrix | Risk register | Monthly | ExCo, board |
| Risks breaching appetite | Count and list of risks scored above the appetite threshold | Risk register, appetite statement | Monthly | ExCo, board |
| Risks overdue treatment | Count of mitigation plans past target date | Risk register | Weekly | GRC, risk owners |
| Average age of accepted risks | Mean days since acceptance for currently-accepted risks | Risk register | Quarterly | ExCo |
| Risks reviewed within cycle | Percentage of risks reviewed within their defined cycle (annual or shorter) | Risk register | Monthly | GRC, ExCo |
| New risks identified per quarter | Count of risks added to register | Risk register | Quarterly | ExCo, board |
| Risks closed per quarter | Count closed (treatment complete or no-longer-applicable) | Risk register | Quarterly | ExCo |
| Concentration index (vendors) | Number of Tier 1 functions on top 3 vendors | Vendor inventory | Quarterly | ExCo |

### Control metrics (KCIs)

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| Patching SLA - critical | Percentage of critical CVE patches applied within 14 days | Vulnerability scanner, ticketing | Weekly | Engineering, CISO |
| Patching SLA - high | Percentage applied within 30 days | Same | Weekly | Same |
| Access review completion | Percentage of in-scope systems with completed quarterly review | IGA system | Quarterly | Engineering, CISO |
| Mean time to revoke leaver access | Median hours from leaver date to access removal across all systems | IAM, HR | Monthly | CISO, HR |
| MFA coverage on privileged accounts | Percentage of privileged accounts with phishing-resistant MFA enrolled | IAM | Monthly | CISO |
| Backup restoration test success | Pass/fail per restoration drill, plus elapsed time | Backup system | Quarterly | Engineering |
| Phishing simulation click rate | Percentage of staff clicking simulated phishing per quarter | Awareness platform | Quarterly | CISO |
| Phishing simulation report rate | Percentage who reported the simulation | Same | Quarterly | Same |
| Endpoint security agent coverage | Percentage of in-scope endpoints with EDR agent reporting | EDR console | Daily/Weekly | Engineering |
| Logging coverage | Percentage of in-scope systems forwarding to SIEM | SIEM | Monthly | CISO |
| Open security alerts past triage SLA | Count by severity past defined triage time | SIEM/SOAR | Daily | SOC |
| Vendors with current SOC 2 / ISO certificate | Percentage of Tier 1 + Tier 2 vendors | TPRM register | Monthly | GRC |

### Compliance and audit metrics (KPIs)

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| Audit findings open | Count by severity (major, minor, observation) | Findings register | Monthly | CISO, ExCo |
| Audit findings closed within SLA | Percentage of findings closed within their target date | Findings register | Monthly | CISO, ExCo |
| Mean time to close finding | By severity | Findings register | Quarterly | CISO |
| Repeat findings | Findings opened on the same control as a previously closed finding | Findings register | Per audit | CISO, board |
| Internal audit cycle coverage | Percentage of in-scope controls audited in the rolling cycle | Internal audit plan | Quarterly | CISO, audit committee |
| Policies overdue review | Count and list | Policy repository | Monthly | GRC |
| Policy acknowledgement | Percentage of staff acknowledged current policy set | HRIS, awareness platform | Monthly | GRC, HR |
| Awareness training completion | Percentage on time | Awareness platform | Quarterly | GRC, HR |
| Exception register | Open exceptions, expired exceptions, exceptions auto-extended | Exception register | Monthly | GRC, CISO |

### Incident metrics

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| Incidents in period by severity | Count of SEV-1 to SEV-4 | Incident management | Monthly | ExCo, board |
| Mean time to detect | Median minutes between event and detection | SIEM, IR | Quarterly | CISO |
| Mean time to contain | Median minutes from detection to containment | IR records | Quarterly | CISO |
| Mean time to resolve | Median hours from detection to closure | IR records | Quarterly | CISO |
| Customer-impacting minutes | Total minutes of customer impact attributable to security incidents | IR records | Quarterly | ExCo |
| Post-incident reviews completed | Percentage of qualifying incidents with PIR within 14 days | IR records | Monthly | CISO |
| PIR action item closure | Percentage of PIR actions closed within target | IR action register | Monthly | CISO |
| Near-miss reports | Count submitted; trend important | IR records | Quarterly | CISO |

### Privacy metrics

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| DSR volume by type | Access, deletion, portability, etc. | Privacy ops | Monthly | DPO |
| DSR SLA compliance | Percentage closed within 30 days | Privacy ops | Monthly | DPO |
| DPIAs initiated, in progress, closed | Counts | Privacy ops | Monthly | DPO |
| Personal data inventory currency | Percentage of inventory entries reviewed in cycle | Privacy ops | Quarterly | DPO |
| Sub-processor changes | Count of additions, removals, with customer notifications | Vendor inventory | Monthly | DPO |
| Privacy incidents notified to regulators | Count by jurisdiction | Privacy ops | Quarterly | DPO, board |

### Programme maturity (KGIs)

| Metric | Definition | Source | Cadence | Audience |
|---|---|---|---|---|
| Maturity self-assessment | Score against a defined maturity model (e.g. CMMI 1-5 per domain) | Annual self-assessment | Annual | Board |
| External maturity assessment | Independent review against the same model | External assessor | Biennial | Board |
| Customer-trust signal | Procurement deals where security was a positive factor | Sales CRM | Quarterly | ExCo |
| Time-to-yes on security questionnaires | Median business days to complete | Sales engineering | Quarterly | GRC |

## Components and deliverables

### 1. Metrics catalogue

The full catalogue document. Each metric: definition, source system, owner, cadence, audience, target, threshold for action. Reviewed annually.

### 2. Data architecture

For each metric: system of record, extraction method (manual, API, scheduled query), refresh frequency, data quality checks, transformation logic. Many programmes fail at exactly this step. Metrics calculated by hand once a quarter age into being calculated by nobody at all. Automation is the difference between maintainable and unmaintainable.

### 3. Dashboards

Three audiences, three content densities.

**Operational dashboard.** All KCIs and KPIs at high frequency. Owned by GRC ops. Used to catch issues early and drive action.

**Management dashboard.** Top 20 metrics across categories. Owned by CISO or Head of GRC. Weekly or monthly visibility for management decisions.

**Executive / board dashboard.** Top 10-12 metrics. Owned by CISO presenting to ExCo and board. Goal: confidence and judgement.

The board version usually includes:
- Top 5 risks with trajectory.
- Risks breaching appetite.
- Major audit findings open.
- Material incidents in period.
- Programme maturity trend.
- One forward-looking item.

### 4. Reporting cadence

| Forum | Cadence | Content |
|---|---|---|
| Operational standup | Daily/weekly | KCI alerts, open SOC actions |
| GRC team review | Weekly | All operational metrics |
| Engineering / GRC sync | Bi-weekly | KCIs related to engineering controls |
| Risk committee | Monthly | KRIs, top risks |
| Executive committee | Monthly or quarterly | Management dashboard |
| Audit committee / board | Quarterly | Board dashboard |
| Annual review | Annual | Full programme review, maturity, framework refresh |

### 5. Threshold and escalation rules

For each metric, define thresholds.
- **Green:** within target.
- **Amber:** trending adversely or near threshold.
- **Red:** threshold breached.

Define escalation per status. Red metrics escalate to the appropriate forum within a defined window. Common pattern is that "red" is the colour the executive committee sees, not the colour the dashboard discovers.

### 6. Metric narrative discipline

Numbers without narrative are noise. Every reporting cycle, the GRC lead writes a brief commentary covering:
- What changed since last period.
- What the change means.
- What is being done about it.
- What is not yet visible but could become so.

This is what executives actually read. The dashboard is the supporting evidence, not the headline.

### 7. Metric review process

Annually:
- Are metrics still aligned with risks and goals?
- Are metrics being used for decisions? If not, retire them.
- Are there decisions being made without metric support? If so, add metrics.
- Are metrics being gamed? If so, change the metric or the incentive.
- Is the cost of measurement justified?

Vanity metrics get retired ruthlessly. Nobody mourns them.

### 8. Maturity model

For each domain (risk, controls, audit, privacy, vendor, IR), a five-level model (initial, managed, defined, quantitatively managed, optimising) with explicit criteria per level. Self-assessed annually; externally assessed biennially.

## Sample executive dashboard (one-page)

```
GRC EXECUTIVE DASHBOARD - Q1 FY26

RISK
Top 5 risks: <list with residual scores>
Risks breaching appetite: 2 (Risk-039 supplier concentration; Risk-052 AI bias)
New high/critical risks this quarter: 1
Risks closed this quarter: 4

INCIDENTS (this quarter)
SEV-1: 0
SEV-2: 1 (vendor outage, 4 hours, customer impact, post-incident review complete)
SEV-3: 5
Mean time to contain: 38 minutes (target 60)

CONTROLS (in-period)
Patching SLA critical: 92% (target 95%)  AMBER
Access reviews completed: 100% (target 100%)  GREEN
Phishing click rate: 4.2% (target <5%)  GREEN
EDR coverage: 98.7% (target 99%)  AMBER

AUDIT AND COMPLIANCE
Open findings (major): 0
Open findings (minor): 7 (5 within SLA, 2 overdue)
Surveillance audit Q3: on track
SOC 2 Type 2 fieldwork: complete; report received clean

PRIVACY
DSR SLA compliance: 100%
Sub-processor changes notified: 2
Open DPIAs: 4

PROGRAMME
Maturity score: 3.6/5 (up from 3.4 last quarter)
Open exceptions: 14 (1 expired, escalated)

NARRATIVE
Patching SLA shortfall driven by major release window in March compressing patch cycle. Action plan agreed with engineering. Vendor outage exposed alternate-IDP gap; project initiated. AI bias risk recently identified, treatment plan pending; CTO owns. No incidents required regulatory notification.
```

## Lessons baked into this framework

- **Measure outcomes when you can; activity only when you must.** Activity metrics are easy and gameable. Outcome metrics are harder and matter.
- **Boards want trajectory, not snapshots.** "Worse than last quarter" beats "amber".
- **Targets must be defensible.** A 99 percent patching SLA target sounds good and is impossible during major release windows. Set targets that are achievable now and tighten them as investment grows. Targets that cannot be hit get quietly ignored by the team.
- **Aged metrics deteriorate.** A metric defined three years ago against a system that no longer exists silently produces meaningless data. Annual review is non-negotiable.
- **Granularity is a tool, not a goal.** Breaking patch SLA down by team is useful for accountability and useless to a board.
- **Forecast where you can.** "On current trajectory we will breach by Q3" is more useful than "we are amber".

## Common pitfalls

- **Metric soup.** 100 numbers, all green by default, audience tunes out.
- **Definition drift.** "Critical" CVE means CVSS 9+ in one team and "anything alarming" in another. Standardise definitions or the metric is meaningless.
- **Single-source dependency.** A metric pulled from one vendor system that breaks every other quarter.
- **Vanity averaging.** Mean time to close findings sounds impressive. Median exposes the outliers more honestly. Use both.
- **Cherry-picking.** Reporting only the metrics that look good. Auditors notice; so do executives, eventually.
- **No baseline.** Reporting current state without prior periods makes interpretation impossible.
- **Surprise red.** A red metric appearing on the board dashboard that the executive saw five hours earlier has been mismanaged.
- **Reporting what is easy to collect rather than what matters.** Common pattern. The fix is to start with the decision and work backwards to the metric.

## What auditors will ask

- Show me your KPIs, KRIs, and KCIs. How are they defined and where are they sourced?
- Walk me through one metric end to end: data, calculation, threshold, escalation, action.
- Show me a metric that breached threshold this year. What was done?
- Show me a metric that was retired this year. Why?
- Show me how the executive committee reviewed the programme last quarter.

## What I have done in this space and what I have not

I have studied ISO 27004, NIST 800-55, COBIT measurement guidance, and writing from CISOs and risk leaders on what executives actually use.

I have not personally presented quarterly GRC dashboards to a public-company board for multiple years. I have not had to defend a metric definition against a sceptical CFO. I have not had to retire a flagship metric I championed because it stopped being useful. Those experiences would refine the framework.

This is a learning portfolio entry.

## Further reading

- **NIST SP 800-55 Rev 2.** Free PDF at csrc.nist.gov.
- **ISO/IEC 27004:2016.** Paid; ENISA publishes complementary free guidance.
- **CIS Controls v8.1 Implementation Groups and Measures.** Free at cisecurity.org.
- **FAIR Institute** at fairinstitute.org for quantitative loss-based measures.
- **OWASP SAMM** for software-assurance maturity (an example of a published maturity model).
- **CMMI Cybermaturity Platform** for a commercial maturity reference (overview free).
- Various CISO blogs, including Phil Venables and Ross Haleliuk, for practitioner perspectives on metrics.

## Status

Learning portfolio. Framework, catalogue, dashboards, and cadences defined. Not running against live data.
