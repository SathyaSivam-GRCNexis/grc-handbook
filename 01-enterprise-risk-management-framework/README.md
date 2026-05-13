# Enterprise Risk Management (ERM) Framework

## What this is

A working set of documents, templates and workflows for running risk across a mid-sized SaaS organisation. Not a polished consulting deck. The kind of thing you actually open on a Monday morning to figure out who owns what and what is overdue.

It draws on ISO 31000, COSO ERM, ISO 27005 and NIST RMF, and is shaped for a SaaS company selling into the UK, EU and India. No software is produced. What you get is methodology, templates, decision rights and a reporting cadence that survives contact with engineering.

This is a learning portfolio entry. I have written it the way I would assemble it for a real rollout, with the bits that usually go wrong called out.

## What an ERM framework actually fixes

Organisations without one tend to look the same.

- Risk is whatever the loudest person in the room said it was last week.
- "High", "medium" and "low" mean different things in different teams. A high security risk and a high financial risk are not really comparable.
- The risk register is a spreadsheet someone updates the week before the audit, then forgets.
- The board hears about risk only after something has already gone wrong.
- Risks are accepted by silence, not by signed-off decision.
- Security risks are owned by the security team, which has no authority to fix half of them.
- Nobody can trace a control back to the risk it is supposed to address.

In my experience the fix is unglamorous. A shared scoring scale, named owners (people, not teams), a quarterly review that actually happens, an explicit risk appetite, and a clear route from "we found a risk" to "leadership has formally decided what to do about it."

A strong opinion to start with: in the first 12 months, a tidy Google Sheet with the right columns beats a fancy GRC tool. Tooling without ownership clarity just produces prettier confusion.

## What working well looks like

- Investment decisions can be expressed in terms of which risks they reduce, by how much, and for whom.
- Audit conversations get shorter. SOC 2 CC3 and ISO 27001 Clause 6.1.2 expect risk-based decision making and that is exactly what the register evidences.
- Issues are caught at quarterly review rather than during an incident.
- Cyber insurance underwriters stop sending follow-up questionnaires.
- The board gets consistent, comparable reporting instead of incident-driven panic.

## Framework alignment

The framework is not a clone of any single standard. It draws from several.

- **ISO 31000:2018** for the umbrella principles and process. This is the spine.
- **COSO ERM (2017)** for the link between risk and strategy, and the three lines model.
- **ISO 27005:2022** for the information security risk methodology specifically.
- **NIST SP 800-37 Rev 2 (RMF)** for the system-level six-step process where it is useful.
- **NIST SP 800-30 Rev 1** for the assessment mechanics, especially threat-source-event modelling.
- **ISO 27001:2022 Clauses 6.1.2 and 6.1.3** as the certifiable hooks.
- **NIST AI RMF 1.0** for AI-specific risks, scored on the same scale as everything else.
- **DORA Article 6** for any readers in financial services.
- **IRM guidance on risk appetite statements.**
- **The Three Lines Model (IIA, 2020)** for assurance roles.

## What sits in the framework

### 1. Risk management policy

Two or three pages signed by the CEO. States that the organisation runs ERM, who owns it, who approves the framework, how often it is reviewed, and what authority the risk function has. Without this, everything else is advisory. People learn to ignore advisory things.

### 2. Risk methodology

The working document, usually 15 to 25 pages. Scope, definitions, the risk universe, identification, scoring, treatment, review, roles and reporting. Long enough to be useful, short enough that someone might actually read it.

### 3. Risk taxonomy

Hierarchical categories so every risk has a home. Top level usually covers strategic, financial, operational, technology, security, privacy, regulatory and legal, third-party, people, reputational, environmental and social, and emerging. For SaaS, technology and security expand into more subcategories. Keep the tree shallow. Three levels is plenty. Five is where people stop using it.

### 4. Risk scoring criteria

A defined scale for likelihood and impact, with words and numbers tied together so "high" means the same thing to everyone. A 5x5 matrix is the usual choice.

Likelihood.
- 1 Rare, less than 5 percent chance in the next year.
- 2 Unlikely, 5 to 25 percent.
- 3 Possible, 25 to 50 percent.
- 4 Likely, 50 to 80 percent.
- 5 Almost certain, more than 80 percent.

Impact, anchored to multiple dimensions so non-financial impact can be scored honestly.

| Score | Financial | Operational | Customer / Reputation | Regulatory |
|---|---|---|---|---|
| 1 Negligible | < £10k | < 1 hour outage | No customer impact | No regulatory interest |
| 2 Minor | £10k to £100k | 1 to 4 hour outage on non-critical service | < 100 customers affected | Internal note only |
| 3 Moderate | £100k to £1m | 4 to 24 hour outage or critical service brief | 100 to 10,000 customers, single press story | Regulator notification within 72 hours |
| 4 Major | £1m to £10m | > 24 hour outage of critical service | > 10,000 customers, sustained press coverage | Formal regulatory action, fine likely |
| 5 Severe | > £10m or going-concern | Multi-day outage of all services | All customers, brand damage lasting > 1 year | Licence at risk, criminal liability |

Score is likelihood multiplied by impact. 1 to 4 low, 5 to 9 medium, 10 to 15 high, 16 to 25 critical.

A quiet truth: getting people to agree on impact bands is harder than the scoring itself. Expect to spend a workshop arguing whether a £200k loss is "moderate" or "major". That argument is the point. Once finance, legal and engineering agree, scoring becomes consistent.

### 5. Risk register template

The columns that matter.

- Risk ID (immutable, never reused)
- Risk title (one sentence)
- Risk description (cause, event, consequence)
- Risk category
- Inherent likelihood and impact
- Inherent score
- Existing controls (with control IDs)
- Residual likelihood and impact
- Residual score
- Risk owner (a named person, not a team)
- Treatment decision (mitigate, transfer, avoid, accept)
- Treatment plan and target date
- Residual-after-treatment score
- Risk appetite alignment (within or outside)
- Last review date
- Next review date
- Status (open, in treatment, accepted, closed)

Resist the temptation to add 20 more columns. Every extra column is a column someone will leave blank.

### 6. Risk treatment workflows

- **Mitigate.** Treatment plan, named owner, target date, link to controls, tracked to closure.
- **Transfer.** Document the mechanism (insurance, contract clause, outsourcing). Residual risk that remains is itself a risk, with a named owner.
- **Avoid.** Sign-off authority for stopping the activity, plan to wind down.
- **Accept.** Explicit sign-off at the appropriate level. Recorded. Reviewed annually. Acceptance without a date is just forgetting.

### 7. Risk appetite statement

A short, board-approved document on how much of each kind of risk the organisation is willing to take. Specific. Measurable. Not "we have low appetite for security risk."

Example.

- **No appetite** for any risk that could cause loss of customer data confidentiality at scale (more than 10,000 records).
- **Low appetite** for security risks rated high or above on residual basis. Any such risk needs CISO sign-off and a treatment plan within 30 days.
- **Moderate appetite** for operational risk in pursuit of growth. Up to four severity-2 incidents per quarter is tolerable.
- **High appetite** for product experimentation in non-customer-facing internal tooling.
- **No appetite** for regulatory non-compliance with GDPR, SOC 2 or ISO 27001 commitments.

The first version of the appetite statement is usually wrong. That is fine. It only becomes useful after you have tested it against two or three real decisions and adjusted.

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

### 9. Reporting cadence

- **Monthly.** Risk function reviews new risks, treatment progress, near-misses.
- **Quarterly.** Executive committee sees the dashboard, top ten risks, breach-of-appetite items.
- **Quarterly.** Board audit and risk committee sees the same plus emerging risks.
- **Annually.** Full risk universe refresh, appetite review, framework effectiveness review.
- **Trigger-based.** Material incidents, new markets, major product launches, significant vendor changes, regulatory changes.

### 10. Three lines

- **First line.** Business and technical teams that own the risk and operate the controls.
- **Second line.** The risk and compliance function. Designs the framework, challenges first-line assessments, provides oversight.
- **Third line.** Internal audit, independent of management. Tests both the controls and the second-line oversight.

Where teams get confused (often): security trying to be both first and second line, or internal audit being asked to do compliance work. Worth writing down explicitly which team is which line, for each major domain.

## Where teams stall

A few patterns that recur across SaaS environments I have seen or studied.

- **The 200-risk register.** Somebody tries to be exhaustive and lists every conceivable bad thing. Nothing is prioritised. Nothing gets treated. The register becomes wallpaper.
- **The CISO-as-owner problem.** Every security risk gets assigned to the CISO. The CISO cannot personally fix engineering practice, vendor selection or finance controls. Risks linger. Treatment plans drift.
- **Quarterly review becomes monthly cancellation.** First two quarters are reviewed properly, then the executive committee runs out of time and risk slides off the agenda. Usually returns only after an incident.
- **Acceptance by default.** No treatment plan agreed, so the risk silently becomes "accepted". A year later nobody can find the sign-off.
- **Heat maps that never change.** The same risks sit in the same quadrant for three years. Either the residual scoring is wrong or nothing is being done. Usually both.

In one SaaS environment I studied during ISO 27001 readiness, the register had 87 risks, no named owners other than the GRC manager, and the same five risks marked "in treatment" with target dates that had been pushed three times. The fix was not a better tool. It was a CEO email to the executive team naming owners and a hard rule that target dates can be moved once before escalation.

## Audit considerations

What an auditor will usually ask. Designing for the question makes the audit shorter.

- Is there a board-approved risk policy? Show me the date and the sign-off.
- Is there a documented methodology? When was it last reviewed?
- Show me the current risk register. Pick three risks and walk me through how they were identified, scored and treated.
- Show me a risk where the treatment plan was missed. What happened? Was it escalated?
- Show me a risk that breaches appetite. Is it visible to the board?
- Show me the minutes of the most recent board risk discussion. What decisions were taken?
- Pick a control listed against a risk. Test that the control operates as described.
- Pick a risk owner. Interview them. Do they know they own it? Do they know what the score means? Do they know what they are responsible for?
- Are risks actually closed when treatment is complete, or do they linger?
- Are accepted risks reviewed annually, or accepted-and-forgotten?

Most of the time the failure point is the last two questions.

## Common mistakes this framework tries to avoid

- **Register as inventory.** A list of every conceivable bad thing is not useful. Active register stays above a threshold. Trivial issues get aggregated.
- **Heat map without action.** Pretty quadrants do not change behaviour. Every risk above medium gets a treatment plan with a date.
- **Owners who cannot act.** The person closest to the decision owns it. Escalation paths exist for when they need authority.
- **Acceptance as default.** Acceptance requires explicit sign-off at a level matching the score.
- **Decoupled from strategy.** Risk reporting feeds into the same forums that approve strategy and budget. Otherwise it is a parallel universe.

## How a rollout actually goes

For a 200 to 1000 person SaaS company.

**Month 1.** Draft the policy, methodology, taxonomy, scoring criteria and register template. CEO signs the policy. Brief the executive team. Negotiate the first version of risk appetite.

**Month 2.** Top-down risk identification workshop with the executive team for the strategic register. Parallel workshops with engineering, product, sales, finance, people and security for operational risks. Score everything on the new scale. Expect at least one workshop to descend into an argument about what "moderate" means. That is healthy.

**Month 3.** First risk dashboard at the executive committee. Walk through the top ten. Discuss appetite breaches. Agree treatment plans and owners.

**Months 4 to 6.** Reporting cadence embedded. First quarterly board update. First trigger-based reviews on real events. First retrospective on a missed treatment date. This is usually where engineering pushback starts. The fix is showing them risks they care about (production stability, on-call burden) rather than only the ones GRC cares about.

**Months 7 to 9.** First independent challenge by internal audit. Findings adjust the framework.

**Months 10 to 12.** First annual refresh of the universe and appetite. Effectiveness review.

By month 12 the framework is not new any more. It is just how things get done.

## What I have done and what I have not

I have studied ISO 31000, COSO ERM, ISO 27005 and NIST SP 800-30 / 800-37 in detail. I have assembled this framework as I would design it.

I have not personally led an enterprise-wide ERM rollout in a 1000-person organisation. I have not negotiated a risk appetite statement with a sceptical CFO. I have not had to defend the framework in front of the Big Four during an annual audit. Those experiences would change parts of this document, particularly the bits about negotiation and authority.

This is a portfolio piece. It is intended to show that I understand what a real ERM framework needs to contain and why each part exists.

## Further reading

- **ISO 31000:2018 Risk management - Guidelines.** Paid; free overview at iso.org/iso-31000-risk-management.html.
- **COSO Enterprise Risk Management.** Executive summary is free at coso.org.
- **NIST SP 800-30 Rev 1 and SP 800-37 Rev 2.** Free PDFs at csrc.nist.gov.
- **ISO 27005:2022.** Paid. ENISA publishes free guidance that covers similar ground.
- **The Institute of Risk Management** at theirm.org, particularly the risk appetite guidance.
- **The IIA Three Lines Model (2020).** Free PDF at theiia.org.
- **Open FAIR.** Open standard at opengroup.org. Useful when stakeholders want quantitative risk in financial terms.

## Status

Learning portfolio. Framework is written end to end. Templates are populated with examples. Not in production use.
