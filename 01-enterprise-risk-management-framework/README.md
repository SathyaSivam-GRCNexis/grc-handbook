# Enterprise Risk Management (ERM) Framework

## What this project is

A complete, opinionated framework that an organisation can adopt to identify, assess, treat, monitor, and report on the risks it faces across security, privacy, operations, financial, regulatory, third-party, strategic, and emerging-technology categories. This is the document set and process that a Chief Risk Officer or Head of GRC would hand to the executive team and the board to say "this is how we run risk here."

It is non-technical in the sense that it produces no software. It produces methodology, templates, workflows, governance, and decision rights. Done well, an ERM framework changes how an organisation talks about risk and how it makes investment, hiring, vendor, product, and architecture decisions.

This portfolio entry is a learning study. It captures how I would assemble such a framework end to end, drawing on ISO 31000, COSO ERM, ISO 27005, and NIST RMF, and adapted for a mid-sized SaaS company.

## Problem this framework solves

Organisations without a real ERM framework usually have one or more of these symptoms.

- Risk is whatever the loudest person in the room said it was last week.
- Different teams use the words high, medium, and low to mean wildly different things, so a high security risk and a high financial risk are not actually comparable.
- The risk register is a spreadsheet someone updates the week before the audit and then forgets.
- The board hears about risk only when something has already gone wrong.
- Risk acceptance happens by silence rather than by signed-off decision.
- Risks are owned by the security team or the GRC team, not by the people who can actually do something about them.
- There is no link between risk, the controls that mitigate it, and the budget that funds the controls.

A working ERM framework fixes all of these by establishing a common language, a common scoring scale, named owners, scheduled reviews, an explicit risk appetite, and a route from "we identified a risk" to "the board agreed to accept, mitigate, transfer, or avoid it."

## Business impact when done well

- Faster, better-justified investment decisions because every project can be expressed in terms of which risks it reduces and by how much.
- Cleaner audits because evidence of risk-based decision-making is exactly what SOC 2 CC3, ISO 27001 Clause 6.1.2, and almost every other framework asks for.
- Earlier detection of emerging issues because risks are reviewed quarterly rather than discovered during incident response.
- Reduced insurance premiums and better cyber insurance terms when underwriters can see a real risk programme.
- Board confidence because they receive consistent, comparable risk reporting rather than incident-driven panic.
- Personal credibility for whoever runs it, because being able to articulate organisational risk is one of the rarest and most valued senior-leadership skills.

## Framework alignment

The framework draws on and aligns to the following standards. None is dominant. The strength of an ERM framework is that it integrates them.

- **ISO 31000:2018 Risk management** provides the umbrella principles, framework, and process. This is the spine.
- **COSO Enterprise Risk Management - Integrating with Strategy and Performance (2017)** provides the link between risk and strategy, and the governance structure of the three lines model.
- **ISO 27005:2022 Information security risk management** provides the detailed methodology specifically for information security risk.
- **NIST SP 800-37 Rev 2 Risk Management Framework (RMF)** provides the federal-style six-step process for system-level risk management.
- **NIST SP 800-30 Rev 1 Guide for Conducting Risk Assessments** provides the assessment-level mechanics, especially threat-source-event modelling.
- **ISO 27001:2022 Clause 6.1.2 Information security risk assessment and Clause 6.1.3 Information security risk treatment** are the certifiable hooks.
- **NIST AI RMF 1.0** is incorporated for AI-specific risks, mapped into the same scoring scheme.
- **DORA Article 6** for financial-sector readers, on ICT risk management framework.
- **The Institute of Risk Management Risk Appetite Statements guidance** for the risk appetite section.
- **The Three Lines Model (2020 update from the IIA)** for assurance roles and accountability.

## Components and deliverables

The framework consists of the following deliverables. Each is a separate document or template a real organisation would adopt.

### 1. Risk management policy

A two-to-three page policy signed by the CEO. States that the organisation runs ERM, who owns it, who approves the framework, how often it is reviewed, and what authority the risk function has. Without this, everything below is advisory only.

### 2. Risk methodology

The longer document (typically 15-25 pages) describing how risk is actually done. Sections cover scope, definitions, the risk universe (categories), how risks are identified, how they are scored, how they are treated, how they are reviewed, who has what role, and how risks are reported.

### 3. Risk taxonomy

A hierarchical list of risk categories so every risk has a home. Top-level categories typically include strategic, financial, operational, technology, security, privacy, regulatory and legal, third-party, people, reputational, environmental and social, and emerging. Each top-level category breaks into subcategories. A SaaS-focused taxonomy would expand technology and security significantly.

### 4. Risk scoring criteria

A defined scale for likelihood and impact, with words and numbers tied together so "high" means the same thing to everyone. A typical 5x5 matrix.

Likelihood scale example.
- 1 Rare, less than 5 percent chance in the next year.
- 2 Unlikely, 5-25 percent.
- 3 Possible, 25-50 percent.
- 4 Likely, 50-80 percent.
- 5 Almost certain, more than 80 percent.

Impact scale example, anchored to multiple dimensions so that you can score a non-financial impact too.

| Score | Financial | Operational | Customer / Reputation | Regulatory |
|---|---|---|---|---|
| 1 Negligible | < £10k | < 1 hour outage | No customer impact | No regulatory interest |
| 2 Minor | £10k - £100k | 1-4 hour outage on non-critical service | < 100 customers affected | Internal note only |
| 3 Moderate | £100k - £1m | 4-24 hour outage or critical service brief | 100-10,000 customers, single press story | Regulator notification within 72 hours |
| 4 Major | £1m - £10m | > 24 hour outage of critical service | > 10,000 customers, sustained press coverage | Formal regulatory action, fine likely |
| 5 Severe | > £10m or going-concern | Multi-day outage of all services | All customers, brand damage lasting > 1 year | Licence at risk, criminal liability |

The risk score is likelihood times impact, plotted on the matrix. Scores 1-4 are low, 5-9 medium, 10-15 high, 16-25 critical.

### 5. Risk register template

A structured template with the following columns at minimum.

- Risk ID (immutable, never reused)
- Risk title (one sentence)
- Risk description (what could happen, what would cause it, what the impact would be)
- Risk category (from the taxonomy)
- Inherent likelihood and impact
- Inherent score
- Existing controls (with control IDs)
- Residual likelihood and impact
- Residual score
- Risk owner (named individual, not team)
- Treatment decision (mitigate, transfer, avoid, accept)
- Treatment plan and target date
- Residual-after-treatment score
- Risk appetite alignment (within / outside)
- Last review date
- Next review date
- Status (open, in treatment, accepted, closed)

### 6. Risk treatment workflows

For each treatment decision, a defined workflow.

- **Mitigate:** create a treatment plan, assign an owner, set a target date, link to the controls being added or strengthened, track to closure.
- **Transfer:** identify the transfer mechanism (insurance, contract clause, outsourcing), document residual risk that remains, named owner for the residual.
- **Avoid:** document the decision to stop the activity, sign-off authority, plan to wind down.
- **Accept:** explicit sign-off at the appropriate authority level, recorded in the register, reviewed annually to check the acceptance is still valid.

### 7. Risk appetite statement

A short board-approved document expressing how much of each kind of risk the organisation is willing to take to pursue its strategy. Concrete and measurable, not "we have low appetite for security risk."

Example for a SaaS company.

- We have **no appetite** for any risk that would cause the loss of customer data confidentiality at scale (more than 10,000 records).
- We have **low appetite** for security risks rated high or above on residual basis. Any such risk requires CISO sign-off and a treatment plan within 30 days.
- We have **moderate appetite** for operational risk in pursuit of growth, accepting up to four severity-2 incidents per quarter.
- We have **high appetite** for product-experimentation risk in non-customer-facing internal tooling.
- We have **no appetite** for regulatory non-compliance with GDPR, SOC 2, or ISO 27001 commitments.

### 8. Roles and responsibilities (RACI)

| Role | Risk identification | Risk scoring | Risk treatment | Risk acceptance | Reporting |
|---|---|---|---|---|---|
| Risk owner (business) | A | A | R | R | C |
| Risk function | C | C | C | C | A |
| First-line teams | R | R | R | I | I |
| CISO / Head of GRC | C | C | C | A (security risks) | A |
| Executive committee | I | I | I | A (high risks) | I |
| Board / Audit committee | I | I | I | A (critical risks) | I |
| Internal audit | - | - | - | - | C |

### 9. Risk reporting cadence

- **Monthly:** risk function reviews new risks, treatment progress, near-misses.
- **Quarterly:** executive committee receives risk dashboard, top ten risks, breach-of-appetite items.
- **Quarterly:** board audit and risk committee receives same plus emerging risks.
- **Annually:** full risk universe refresh, risk appetite review, framework effectiveness review.
- **Trigger-based:** on material incidents, on entry into new markets, on major product launches, on significant vendor changes, on regulatory changes.

### 10. Three lines assurance model

- **First line:** business and technical teams that own the risk and operate the controls.
- **Second line:** the risk and compliance function that designs the framework, challenges first-line assessments, and provides oversight.
- **Third line:** internal audit (independent of management) that tests both the controls and the second-line oversight.

Defining who is which line removes a frequent source of confusion (the security team trying to be both first and second line, internal audit being asked to do compliance work).

## Real-world examples that shape this design

- **The 2020 Equifax post-breach reporting** showed what happens when risk identification exists but escalation pathways do not. Vulnerabilities were known months before exploitation. The framework here insists on time-bound treatment plans and breach-of-appetite escalation, not just register hygiene.
- **The 2023 SVB collapse** is a textbook case of strategic and concentration risk being treated as financial risk only, with no enterprise view. The taxonomy here forces a strategic-risk category that owns concentration and assumption risk explicitly.
- **The Maersk NotPetya 2017 incident** showed that operational and technology risk are inseparable. The framework links them through scenario libraries.
- **Boeing 737 MAX governance failures** showed that risk acceptance without explicit escalation authority is risk denial. The acceptance workflow here requires named sign-off at the appropriate level.

## Audit considerations

External and internal auditors looking at an ERM framework will typically test the following. Designing the framework with the test in mind makes audits much smoother.

- Is there a board-approved risk policy? Show me the date and the sign-off.
- Is there a documented methodology? When was it last reviewed?
- Show me the current risk register. Pick three risks and walk me through how they were identified, scored, and treated.
- Show me a risk where the treatment plan was missed. What happened? Was it escalated?
- Show me a risk that breaches appetite. Is it visible to the board?
- Show me the minutes of the most recent board risk discussion. What decisions were taken?
- Pick a control listed against a risk. Test that the control actually operates as described.
- Pick a risk owner. Interview them. Do they know they own it? Do they know what the score means? Do they know what action they are responsible for?
- Are risks actually closed when treatment is complete, or do they linger?
- Are accepted risks reviewed annually, or are they accepted-and-forgotten?

## Common mistakes this framework explicitly avoids

- **Risk register as inventory.** A list of every conceivable bad thing is not useful. The framework limits the active register to risks above a threshold and requires aggregation of trivial issues.
- **Heat map without action.** Pretty quadrants on a slide do not change behaviour. The framework requires every risk above medium to have a treatment plan with a date.
- **Owners who cannot act.** Assigning the CISO as owner of every security risk is a way of having no owner. The framework insists on the person closest to the decision, with escalation paths if they need authority.
- **Acceptance as default.** When nobody picks treatment, risks drift into acceptance. The framework requires explicit sign-off at a level appropriate to the score.
- **Decoupled from strategy.** An ERM framework that exists only for audits does not influence decisions. The framework links risk reporting into the same governance forums that approve strategy and budget.

## How this framework would actually be implemented

A reasonable rollout for a 200-1000 person SaaS company.

**Month 1.** Draft the policy, methodology, taxonomy, scoring criteria, and register template. Get the policy signed by the CEO. Brief the executive team. Define risk appetite jointly with them.

**Month 2.** Run a top-down risk identification workshop with the executive team to populate the first version of the strategic-risk register. Run parallel workshops with each function (engineering, product, sales, finance, people, security) to populate operational risks. Score everything against the new criteria.

**Month 3.** Land the first risk dashboard at the executive committee. Walk through the top ten risks. Discuss appetite breaches. Get treatment plans agreed and owners named.

**Months 4-6.** Embed reporting cadence. First quarterly board risk update. First trigger-based reviews (whatever real events have happened). First retrospective on a missed treatment date.

**Month 7-9.** First independent challenge by internal audit. Adjust framework based on findings.

**Month 10-12.** First annual refresh of the entire risk universe and appetite statement. Framework effectiveness review.

By month 12, the framework is no longer the new thing. It is just how the organisation runs.

## What I have done in this space and what I have not

I have studied ISO 31000, COSO ERM, ISO 27005, and NIST SP 800-30 / 800-37 in detail. I have written this framework as I would design it.

I have not personally led an enterprise-wide ERM rollout in a 1000-person organisation. I have not had to negotiate a risk appetite statement with a sceptical CFO. I have not had to defend a framework in front of the Big Four during an annual audit. Those experiences would change the document in ways I cannot fully predict.

This is a learning portfolio entry, not a claim of operational experience. It is intended to demonstrate that I understand what a real ERM framework needs to contain and why each part exists.

## Further reading

- **ISO 31000:2018 Risk management - Guidelines.** The standard itself is paid; ISO publishes a free overview at iso.org/iso-31000-risk-management.html.
- **COSO Enterprise Risk Management - Integrating with Strategy and Performance.** Executive summary is free at coso.org.
- **NIST SP 800-30 Rev 1 and SP 800-37 Rev 2.** Both free PDFs at csrc.nist.gov.
- **ISO 27005:2022 Information security risk management.** Paid; ENISA publishes free guidance covering similar ground at enisa.europa.eu.
- **The Institute of Risk Management resources at theirm.org**, particularly their risk-appetite guidance.
- **The IIA Three Lines Model (2020).** Free PDF at theiia.org.
- **Open FAIR (Factor Analysis of Information Risk).** Open standard at opengroup.org; useful when stakeholders want quantitative risk in financial terms.

## Status

Learning portfolio. Framework is written end to end. Templates are populated with examples. Not in production use.
