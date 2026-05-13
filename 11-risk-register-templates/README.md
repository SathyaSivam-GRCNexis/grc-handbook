# Risk Register Templates (Multiple Variants)

## What this is

A set of risk register templates pitched at different organisation sizes, with field definitions, scoring conventions, sample entries, and notes on which one to actually pick up. Most readers will want Variant B (SaaS, SOC 2 / ISO 27001 maturity). The others extend or simplify from there.

Before anything else, the honest disclaimer about registers: they go stale faster than almost any other artefact in a GRC programme. The template is the easy part. Keeping it alive past quarter two is the real work.

## Why multiple variants

There is no universal register. A 30-person startup needs something one person can keep current in Sheets. A regulated SaaS in the 500-person range needs multiple owners, sub-registers, and links to audit evidence. A bank-scale organisation needs entity-level aggregation, Three Lines of Defence accountability, and outputs that survive a regulator's reading.

Pick wrong and it fails predictably. Too light, and you cannot answer what an auditor or regulator expects. Too heavy, and nobody updates it. The real risk conversations then happen in Slack, in incident channels, or in the CTO's notebook, and the register becomes a museum piece.

In my experience, most teams overshoot on the first attempt. Start one tier below where you think you need to be.

## The variants

### Variant A: Startup minimal (under ~50 staff)

One spreadsheet, one owner. Anything more is theatre at this size.

| Field | Notes |
|---|---|
| Risk ID | RSK-NNN, immutable |
| Risk title | One sentence |
| Description | Short paragraph |
| Category | Small taxonomy (security, privacy, operational, financial, regulatory, people, third-party) |
| Likelihood (1-5) | Inherent |
| Impact (1-5) | Inherent |
| Score | Inherent (auto from L x I) |
| Existing controls | Free text reference |
| Residual likelihood | After controls |
| Residual impact | After controls |
| Residual score | Auto |
| Treatment decision | Mitigate / transfer / avoid / accept |
| Owner | Named individual |
| Treatment plan | Short paragraph |
| Target date | |
| Status | Open / in treatment / accepted / closed |
| Last review | Date |
| Next review | Date |

Enough for early risk visibility and a SOC 2 Type 1. Not enough for a serious Type 2.

### Variant B: SaaS standard (50 to ~1000 staff)

The default. Adds rigour without burying the GRC team.

Extra fields on top of Variant A.

| Field | Notes |
|---|---|
| Sub-category | More detail (e.g. "third-party / sub-processor") |
| Threat source / actor | Where applicable (insider, external, accidental, environmental) |
| Asset(s) affected | Reference to asset inventory |
| Inherent impact dimensions | Financial, operational, reputational, regulatory, customer (each 1-5) |
| Linked controls | Canonical control IDs from the control matrix |
| Residual impact dimensions | After controls |
| Risk appetite alignment | Within / outside / on-threshold |
| Treatment plan owner | If different from risk owner |
| Linked risk scenarios | Reference to scenario library |
| Linked incidents | Where the risk has actually fired |
| Linked findings | Audit findings related |
| Approver of acceptance | Where treatment is accept |
| Acceptance review date | Annual at minimum |
| Confidence in scoring | High / medium / low |
| Trend | Improving / stable / worsening |

The "confidence in scoring" field looks soft but earns its place. It is the only honest way to flag a risk where the team genuinely does not know yet.

### Variant C: Multi-entity enterprise (1000+ staff)

For organisations with multiple legal entities, business units, or regulated subsidiaries. Adds aggregation and lineage.

Extra fields beyond Variant B.

| Field | Notes |
|---|---|
| Legal entity | Where the risk sits |
| Business unit | Sub-divisional ownership |
| Geography | Where the risk applies |
| Aggregated parent risk | If this is a child of a group-level risk |
| Quantified loss expectation (FAIR) | Loss event frequency, loss magnitude (single or annualised) |
| Quantified loss after treatment | Same with controls |
| Risk velocity | How fast this could escalate (slow, fast, immediate) |
| Indicators / KRIs | Linked early-warning metrics |
| Reporting line | Which board or committee oversees |
| Regulatory reportability | Yes / no, with regime |

### Variant D: Sub-registers

Sub-registers feed the master. The usual ones.

- **Project risk register** for individual programmes. Closed at programme end, residuals migrated up.
- **Vendor risk register** per Tier 1 vendor. Aggregates into vendor concentration risk.
- **Product risk register** per major product line. Rolls into operational risk.
- **Privacy risk register** owned by the DPO. Aggregates into regulatory risk. In an India context, this is also where DPDP-driven risks tend to land.
- **AI risk register** owned alongside MLOps. Aggregates into emerging-tech risk.
- **Operational resilience register** of important business services. Feeds BCDR.

Sub-registers reuse the parent's field model. Resist the urge to invent new schemas per sub-register; you will spend the rest of your career reconciling them.

### Variant E: Quantified (FAIR-aligned)

For top-tier risks where ordinal L x I is too coarse. Replaces it with frequency and magnitude distributions.

| Field | Notes |
|---|---|
| Loss event frequency (LEF) | Distribution: min, most likely, max times per year |
| Loss magnitude (LM) | Distribution: min, most likely, max in monetary terms |
| Annualised loss expectancy (ALE) | Computed |
| Confidence | High / medium / low per parameter |
| Calibration source | Historical / expert / industry |
| Treatment cost | Annualised |
| Risk reduction | Pre-treatment ALE minus post-treatment ALE |
| Return on control investment | (Risk reduction - treatment cost) / treatment cost |

Use this for the handful of risks where a quantitative answer is worth the modelling cost. Everything else stays on the ordinal scale. Trying to FAIR-quantify the whole register is a classic over-engineering trap.

## Sample populated entries

### Sample (Variant B)

```
Risk ID: RSK-014
Title: Data exposure via misconfigured cloud storage bucket
Description: A development or production bucket is created or modified with permissions allowing unauthorised public access, exposing customer data such as PDFs, exports, or backups.
Category: Security
Sub-category: Cloud configuration
Threat source: Internal accidental, opportunistic external scan
Assets affected: Customer-data buckets across product environments
Inherent likelihood: 4
Inherent impact: F4 O3 R4 G4 C5 (max 5)
Inherent score: 20 (Critical)
Existing controls:
- CTRL-CLD-002 (CSPM monitoring with daily scan)
- CTRL-CLD-005 (S3 Block Public Access at account level)
- CTRL-IAC-003 (Terraform module enforces private-only)
- CTRL-PIPE-007 (Pre-deployment policy check)
Residual likelihood: 2
Residual impact: F4 O3 R4 G4 C5
Residual score: 10 (High)
Risk appetite alignment: Within (security high requires CISO sign-off; in place)
Treatment decision: Mitigate (further reduction proposed)
Treatment plan: Add org-wide deny-by-default SCP for public bucket creation; CSPM real-time alerting; quarterly drill of detection-to-remediation.
Owner: VP Engineering
Treatment plan owner: Cloud Security Lead
Target date: 2026-09-30
Linked scenario: SC-02
Linked incidents: None
Linked findings: SOC2-FY25-OBS-003 (closed)
Confidence in scoring: High
Trend: Improving
Last review: 2026-04-01
Next review: 2026-07-01
Status: In treatment
```

### Sample (Variant E quantified)

```
Risk ID: RSK-021
Title: Successful ransomware encrypts production
Loss event frequency: 0.05 / 0.15 / 0.5 events per year
Loss magnitude: £2m / £8m / £25m per event
Annualised loss expectancy: £1.4m (median Monte Carlo)
Confidence: Medium on frequency (industry data), High on magnitude (internal modelling)
Treatment options considered:
A: Status quo. Residual ALE £1.4m.
B: Add immutable backups + tested cross-region restoration. Cost £350k/yr. Residual ALE £600k. ROI: 1.3x.
C: B plus phishing-resistant MFA + microsegmentation. Cost £950k/yr. Residual ALE £180k. ROI: 0.3x.
Recommendation: Option B; reassess C in 12 months with refreshed frequency data.
```

## Operating discipline (the part everyone underrates)

A register is only worth what it is worth at the end of each quarter, not the day you finalised the template.

- **Cadence.** Monthly GRC review, quarterly review by risk owners, annual full refresh. The quarterly refresh is non-negotiable. Slip it twice and the register is dead.
- **Quality.** Every risk has a named individual owner who is not in the GRC team. If GRC owns it, nobody owns it.
- **Ageing.** Any risk not reviewed in 90 days flags for attention. Over 180 days it escalates.
- **Ageing acceptance.** Any accepted risk older than 12 months goes back for re-acceptance. Acceptances drift.
- **Closure.** Risks close when treatment is done or when they are no longer applicable. The rationale gets written down.
- **No silent edits.** Changes are versioned. Material edits get captured with an actor and date.
- **Access.** Risk owners, ExCo, and internal audit see the register (with appropriate permissions). If it lives only on a GRC laptop, it does not exist.

## Where teams stall

- **Register as inventory.** Listing every conceivable bad thing is a hazard log, not a risk register.
- **Owner-less entries.** Without an owner, treatment never happens. Most common reason for stalled risks.
- **Score inflation.** Everything is High. Nothing is High.
- **Score deflation.** Risks scored low to avoid the escalation paperwork. I have seen this more than I would like.
- **Stale residuals.** Residual scores from two years ago. Controls have changed since, but the scoring has not been rerun.
- **Treatment without dates.** Open mitigations indefinitely. "Q3" written in Q1 of the previous year.
- **Acceptance as default.** Risks drift into "accepted" because nobody is willing to actually decide.
- **Disconnected from controls.** The register points at controls that were retired in the last refactor.
- **Disconnected from incidents.** A material incident happens and the relevant risk was never on the register. This one is the most embarrassing in an audit.

## What auditors actually ask for

- Show me your register.
- Show me a risk where the residual breaches appetite.
- Show me a risk that closed in the past 12 months.
- Pick a risk. Show me the linked controls actually operating.
- Show me a risk owner who is not in GRC.
- Show me how risks are escalated.
- Show me changes to the register and approvals for material edits.

The last one trips people up. Version history matters.

## What I have done here and what I have not

I have worked through ISO 31000, ISO/IEC 27005, NIST SP 800-30, COSO ERM, and Open FAIR. I have built the templates as I would design them across organisation sizes.

I have not personally maintained a register through multiple SOC 2 cycles or a full ISO 27001 certification. I have not defended a residual score to internal audit. I have not had to redesign sub-register integration after a reorg, which I am told is its own special pain.

This is a learning portfolio entry.

## Further reading

- **ISO 31000:2018** and **ISO/IEC 27005:2022.**
- **NIST SP 800-30 Rev 1.** Free PDF at csrc.nist.gov.
- **Open FAIR (The Open Group).** Standards free at opengroup.org; FAIR Institute has good community material.
- **"How to Measure Anything in Cybersecurity Risk"** (Hubbard and Seiersen).
- **CIS Risk Assessment Method.** Free at cisecurity.org.
- **ENISA risk management resources.** Free at enisa.europa.eu.

## Status

Learning portfolio. Five variants with field models, samples, and operating notes. Not maintained as live registers.
