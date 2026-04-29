# Risk Register Templates (Multiple Variants)

## What this project is

A pack of risk register templates designed for different organisational contexts, sizes, and maturity levels. Includes the structural designs, field definitions, scoring conventions, sample populated entries, and guidance on when to use which variant.

The starting variant for most readers is the SaaS company at SOC 2 / ISO 27001 maturity. Variants extend or simplify from there.

## Why multiple variants

Risk registers are not one-size-fits-all. A 30-person startup needs something a single GRC person can maintain in a spreadsheet. A 500-person regulated SaaS needs something that supports multiple owners, sub-registers, and integration with audit evidence. A 10,000-person bank needs something that aggregates legal-entity registers, supports the Three Lines model formally, and feeds regulatory reporting.

Using the wrong variant fails predictably. Too simple: cannot record what regulators or auditors expect. Too complex: nobody updates it, it goes stale, and the actual risk conversations happen elsewhere.

## The variants

### Variant A: Startup minimal (recommended for <50 staff)

A spreadsheet a single GRC owner can maintain.

| Field | Notes |
|---|---|
| Risk ID | RSK-NNN, immutable |
| Risk title | One sentence |
| Description | Short paragraph |
| Category | From a small taxonomy (security, privacy, operational, financial, regulatory, people, third-party) |
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

Sufficient for early-stage risk visibility and SOC 2 Type 1 readiness.

### Variant B: SaaS standard (recommended for 50-1000 staff)

The most common starting point. Adds rigour without excessive overhead.

Additional fields beyond Variant A.

| Field | Notes |
|---|---|
| Sub-category | Detail within category (e.g. "third-party / sub-processor") |
| Threat source / actor | Where applicable (insider, external, accidental, environmental) |
| Asset(s) affected | Reference to asset inventory |
| Inherent impact dimensions | Financial, operational, reputational, regulatory, customer (each scored 1-5) |
| Linked controls | Reference to canonical control IDs in the control matrix |
| Residual impact dimensions | After controls |
| Risk appetite alignment | Within / outside / on-threshold |
| Treatment plan owner | If different from risk owner |
| Linked risk scenarios | Reference to scenario library |
| Linked incidents | Where the risk has manifested |
| Linked findings | Audit findings related |
| Approver of acceptance | Where treatment is accept |
| Acceptance review date | Annual |
| Confidence in scoring | High / medium / low |
| Trend | Improving / stable / worsening |

### Variant C: Multi-entity enterprise (recommended for 1000+ staff)

For organisations with multiple legal entities, business units, or regulated subsidiaries. Adds aggregation and lineage.

Additional fields beyond Variant B.

| Field | Notes |
|---|---|
| Legal entity | Where the risk sits |
| Business unit | Sub-divisional ownership |
| Geography | Where the risk applies |
| Aggregated parent risk | If this is a child of a group-level risk |
| Quantified loss expectation (FAIR) | Loss event frequency, loss magnitude (single or annualised) |
| Quantified loss after treatment | Same with controls |
| Risk velocity | How quickly this could escalate (slow, fast, immediate) |
| Indicators / KRIs | Linked early-warning metrics |
| Reporting line | Which board / committee oversees |
| Regulatory reportability | Yes / no, with regime |

### Variant D: Sub-registers

Sub-registers feed the master register. Use cases.

- **Project risk register** for individual programmes; closed at programme end with residuals migrated.
- **Vendor risk register** per Tier 1 vendor; aggregates into vendor concentration risks.
- **Product risk register** per major product line; rolls up into operational risk.
- **Privacy risk register** managed by DPO; aggregates into regulatory risk.
- **AI risk register** managed alongside MLOps; aggregates into emerging-tech risk.
- **Operational resilience register** of important business services; feeds BCDR programme.

Sub-registers use the same field model as the parent variant.

### Variant E: Quantified (FAIR-aligned)

For organisations adopting Open FAIR for security risks or financial-loss-based risk in general. Replaces ordinal L x I with frequency and magnitude distributions.

| Field | Notes |
|---|---|
| Loss event frequency (LEF) | Distribution: min, most likely, max times per year |
| Loss magnitude (LM) | Distribution: min, most likely, max in monetary terms |
| Annualised loss expectancy (ALE) | Computed |
| Confidence | High / medium / low on each parameter |
| Calibration source | Historical data / expert estimate / industry data |
| Treatment cost | Annualised |
| Risk reduction | Pre-treatment ALE - post-treatment ALE |
| Return on control investment | (Risk reduction - treatment cost) / treatment cost |

Best used for top-tier risks where the cost of quantitative analysis is justified by the size of the decision. Routine risks remain on ordinal scoring.

## Sample populated entries

### Sample (Variant B)

```
Risk ID: RSK-014
Title: Data exposure via misconfigured cloud storage bucket
Description: A development or production storage bucket is created or modified with permissions that allow unauthorised public access, exposing customer data such as PDFs, exports, or backups.
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
Treatment plan: Add organisation-wide deny-by-default SCP for public bucket creation; CSPM real-time alerting; quarterly drill of detection-to-remediation.
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
Annualised loss expectancy: £1.4m (median Monte Carlo estimate)
Confidence: Medium on frequency (industry-data-based), High on magnitude (internal modelling)
Treatment options considered:
A: Status quo (current controls). Residual ALE £1.4m.
B: Add immutable backups + tested cross-region restoration. Cost £350k/yr. Residual ALE £600k. ROI on control: 1.3x.
C: B plus phishing-resistant MFA + microsegmentation. Cost £950k/yr. Residual ALE £180k. ROI on control: 0.3x (B alone, then evaluate).
Recommendation: Option B; reassess C in 12 months with updated frequency data.
```

## Operating discipline

A register is only useful if maintained.

- **Cadence:** monthly review by GRC; quarterly review by risk owners; annual full refresh.
- **Quality:** every risk must have a named owner who is not the GRC team.
- **Aging:** any risk not reviewed in 90 days flags for attention; any over 180 escalates.
- **Aging acceptance:** any accepted risk over 12 months requires re-acceptance.
- **Closure:** risks closed when treatment complete OR no longer applicable; rationale recorded.
- **No silent edits:** changes are versioned; material changes are captured.
- **Accessibility:** the register is visible (with appropriate permissions) to risk owners, executive committee, and internal audit.

## Common pitfalls

- **Register as inventory.** A list of every conceivable bad thing is not a risk management tool.
- **Owner-less entries.** Risks without owners do not get treated.
- **Score inflation.** Everything is high so nothing is high.
- **Score deflation.** Risks scored low to avoid escalation.
- **Stale residuals.** Residual scores from years ago, controls changed since.
- **Treatment without dates.** Open mitigations indefinitely.
- **Acceptance as default.** Risks drift into acceptance because nobody decides anything.
- **Disconnected from controls.** The register references controls that no longer exist.
- **Disconnected from incidents.** A material incident occurs and no risk register entry was open.

## Audit considerations

- Show me your register.
- Show me a risk where the residual breaches appetite.
- Show me a risk that was closed in the past 12 months.
- Pick a risk and show me the linked controls actually operating.
- Show me a risk owner who is not the GRC team.
- Show me how risks are escalated.
- Show me changes to the register and approvals for material edits.

## What I have done in this space and what I have not

I have studied ISO 27005, ISO 31000, NIST 800-30, COSO ERM, and Open FAIR. I have built register templates as I would design them for organisations of different sizes.

I have not personally maintained a risk register through multiple SOC 2 audit cycles or a full ISO 27001 certification. I have not had to defend a residual score in front of an internal audit team. I have not had to design a sub-register integration that survives organisational restructuring.

This is a learning portfolio entry.

## Further reading

- **ISO 31000:2018** and **ISO/IEC 27005:2022.**
- **NIST SP 800-30 Rev 1.** Free PDF at csrc.nist.gov.
- **Open FAIR (The Open Group).** Standards free at opengroup.org; FAIR Institute provides community resources.
- **The Hubbard Decision Research book "How to Measure Anything in Cybersecurity Risk".**
- **CIS Risk Assessment Method.** Free at cisecurity.org.
- **ENISA risk-management resources.** Free at enisa.europa.eu.

## Status

Learning portfolio. Five variants designed with field models, samples, and operating guidance. Not maintained as live registers.
