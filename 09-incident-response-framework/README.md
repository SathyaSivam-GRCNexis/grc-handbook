# Incident Response & Breach Management Framework

## What this project is

A complete framework an organisation can adopt to detect, triage, contain, eradicate, recover from, and learn from cyber-security incidents and personal-data breaches. Includes severity classification, the incident response (IR) lifecycle, role definitions, communication and escalation paths, breach-notification workflows for multiple jurisdictions, post-incident review process, and a library of IR playbooks for common scenario classes.

This is what a CISO, IR lead, or DPO would build to replace ad-hoc "we will figure it out when it happens" with structured, practised, defensible response.

## Problem this framework solves

Organisations without a real IR framework typically learn the hard way.

- The first major incident is the one where everyone discovers there is no defined SEV-1 process.
- The on-call engineer who detected the issue does not know who has authority to take production offline.
- Three hours into the incident, someone realises they should have called Legal.
- Customers find out from social media before official communication.
- The 72-hour GDPR notification clock has been running since the incident started, and nobody is tracking it.
- Six months later, the same kind of incident happens again because no post-incident review captured the lessons.
- The board hears about the incident two weeks after it concludes, and they hear it from the press.

A working framework fixes these by establishing roles, processes, decision authority, communications, and learning loops in advance.

## Business impact

- Faster containment, reducing material loss.
- Defensible record of decisions and actions, critical for regulator and litigant scrutiny.
- Compliance with notification clocks (GDPR Art 33/34, NIS2, DORA, US state breach laws, sector-specific).
- Customer trust preserved through prompt and accurate communication.
- Insurance claim integrity (insurers require evidence of process).
- Board confidence in management's ability to handle the next event.
- Cyclic improvement: each incident improves controls and processes.

## Framework alignment

- **NIST SP 800-61 Rev 2** Computer Security Incident Handling Guide.
- **ISO/IEC 27035:2023** Information security incident management (parts 1, 2, 3, 4).
- **ISO/IEC 27001:2022 Annex A.5.24-A.5.30** information security incident management controls.
- **NIST CSF 2.0** RESPOND (RS) and RECOVER (RC) functions.
- **GDPR Articles 33 and 34** breach notification to supervisory authority and data subjects.
- **NIS2 Article 23** incident reporting to national CSIRT/competent authority.
- **DORA Articles 17-23** ICT incident classification and reporting (financial sector).
- **PCI DSS v4.0 Requirement 12.10** incident response.
- **HIPAA Breach Notification Rule** (45 CFR §§ 164.400-414).
- **SEC Cybersecurity Disclosure Rule** (17 CFR § 229.106) for material incidents at registrants.
- **UK NCSC CIRP guidance** at ncsc.gov.uk.
- **State-level US breach notification laws** (50+ jurisdictions).

## Lifecycle phases

The framework follows the NIST 800-61 four-phase model with explicit hooks for privacy and regulatory dimensions.

### 1. Preparation

Everything done before an incident.
- Defined IR team and on-call rota.
- Tools (SIEM, EDR, forensics, ticketing).
- Playbooks (per scenario class).
- Communications templates (customer, regulator, internal).
- Tabletop exercises and live drills.
- Vendor relationships (forensics retainer, legal, PR).
- Documented decision authority for severe actions.

### 2. Detection and analysis

- Detection sources: SIEM alerts, EDR alerts, vendor notifications, customer reports, internal reports, threat intelligence.
- Initial triage by SOC analyst or on-call.
- Severity classification (SEV-1 to SEV-4) using defined criteria.
- Activation of appropriate playbook.
- IR team assembly proportional to severity.

### 3. Containment, eradication, recovery

- **Short-term containment:** stop the bleeding. Disconnect, block, quarantine.
- **Long-term containment:** stable state while eradication proceeds (e.g. forensic snapshot before re-imaging).
- **Eradication:** remove the cause (malware, compromised credentials, vulnerable software).
- **Recovery:** restore systems and validate normal operation; monitor for recurrence.

### 4. Post-incident activity

- Post-incident review (PIR) within 14 days for significant incidents.
- Action items captured and tracked to closure.
- Lessons fed into controls, training, playbooks.
- Metrics updated.
- Insurance and regulatory follow-ups closed.

## Severity classification

Defined and consistent severity is the spine of the framework.

| Severity | Criteria | Response posture |
|---|---|---|
| **SEV-1 Critical** | Active material customer-data exposure or active material service outage; or any confirmed breach with regulatory notification trigger; or any incident requiring board-level disclosure | Full IR team activated within 30 minutes. Executive and CISO bridge. Continuous coverage. CFO + Legal + Comms + DPO required. |
| **SEV-2 High** | Significant potential customer impact or active limited customer-facing impact; significant control failure; suspected breach pending confirmation | IR team activated within 1 hour. CISO informed. Sub-team handles. Hourly updates to leadership. |
| **SEV-3 Medium** | Internal impact only; controlled events with manageable scope (e.g. single compromised endpoint) | IR team handles in business hours. CISO informed in next standup. |
| **SEV-4 Low** | Routine events with no business impact (e.g. blocked phishing) | Tracked for trend; no special handling. |

Criteria are explicit because hand-wave severity definitions get gamed downward when the implication is escalation cost.

## Roles and responsibilities

| Role | Responsibility |
|---|---|
| **Incident Commander** | Single point of authority. Coordinates response. Makes operational decisions. Typically a senior IR engineer or duty CISO. |
| **Technical Lead** | Drives investigation and remediation. |
| **Communications Lead** | All internal and external messaging. Liaises with comms team. |
| **Legal Lead** | Regulatory clocks, evidence preservation, third-party communications. |
| **Privacy Lead (DPO or designate)** | Personal-data assessment, regulatory notification, data-subject communication. |
| **Engineering Lead** | Service stability, recovery actions, customer-facing changes. |
| **Executive Sponsor** | Authority for severe actions (taking service offline, customer notifications, ransom decisions). For SEV-1 typically the CISO; for board-disclosable, the CEO. |
| **Scribe** | Maintains running incident log with timestamps and decisions. |
| **Customer Success Liaison** | Manages customer relationship during impact. |
| **External Counsel / Forensics Retainer** | Engaged at SEV-1; provides legal privilege framework where applicable. |

## Components and deliverables

### 1. Incident management policy

Approved by the board or CISO. Defines what is an incident, the severity model, the roles, the basic process, and the authority structure.

### 2. Severity classification standard

Detailed criteria and decision tree. Includes worked examples.

### 3. Incident response plan

The operational document. Lifecycle phases, role responsibilities, communications, escalation paths. Reviewed annually.

### 4. Playbook library

Scenario-specific runbooks. Each playbook has:
- Trigger conditions.
- Severity guidance.
- Investigation steps.
- Containment actions.
- Eradication actions.
- Recovery validation.
- Communication templates.
- Required notifications.
- Common pitfalls.

Core playbooks include:
- Phishing leading to credential compromise.
- Malware on user endpoint.
- Ransomware (full enterprise).
- Insider data exfiltration.
- Cloud account compromise.
- Vendor breach affecting our data.
- Web application attack (SQLi, RCE, account takeover at scale).
- Distributed denial of service.
- Lost or stolen device with sensitive data.
- Misconfiguration leading to data exposure (S3 etc.).
- Regulatory data subject complaint indicating breach.
- AI-system incident (model exfiltration, prompt-injection at scale).
- Physical security breach affecting data.
- Source code or IP leak.

### 5. Communications templates

Pre-drafted templates approved by Legal and Comms.
- Initial customer notification.
- Customer status updates.
- Regulator notification (jurisdiction-specific).
- Data-subject notification (GDPR Art 34).
- Press statement.
- Internal all-staff notification.
- Status page update.
- Specific-customer breach notification (named accounts).

Templates are blank-fill. Drafting in the heat of the incident is too slow and prone to error.

### 6. Notification register

A live register tracking all required notifications for the incident.

| Recipient | Trigger criterion | Clock | Status |
|---|---|---|---|
| ICO (UK) | Personal-data breach with risk to individuals | 72 hours from awareness | Drafted, sent at HH:MM |
| EDPB-relevant DPAs | Cross-border DPA | 72 hours | Lead authority identified |
| Affected data subjects | High risk to individuals | Without undue delay | Pending decision |
| NCSC (UK) | NIS2 essential entity, significant incident | Initial 24h, intermediate 72h, final 1 month | n/a |
| Customers (contractual) | Per individual contract | Per contract (24-72h typical) | List building |
| SEC (US) | Material incident at registrant | 4 business days | n/a |
| State AGs (US) | Per individual statute | Varies | n/a |
| HHS OCR (US, HIPAA) | PHI breach | 60 days (or annual for <500) | n/a |
| Cyber insurer | Per policy | Per policy (often 24-48h) | Notified at HH:MM |

### 7. Decision authority matrix

Specific high-impact actions need pre-defined authority.

| Action | Authority |
|---|---|
| Take customer-facing service offline | CISO + Engineering VP, or CEO during board hours |
| Pay ransomware demand | CEO + Board chair + Legal advice; never by IR team alone |
| Issue press statement | CEO or CMO |
| Notify regulator | DPO + Legal |
| Notify affected customers | CEO sign-off for material incident |
| Engage external forensics | CISO |
| Engage external counsel | Legal |
| Notify law enforcement | CEO + Legal |

### 8. Evidence preservation

- Forensic snapshots before any remediation.
- Chain of custody documentation.
- Log retention preservation (extended retention activated for incident period).
- Memory captures where appropriate.
- All decisions and actions logged contemporaneously.

### 9. Tabletop exercise programme

- Quarterly scenarios drawn from the risk scenario library.
- Annual full-scale exercise involving executive team.
- Biennial supplier-led red-team or purple-team exercise.
- Exercises rotate across scenario classes (ransomware, BEC, DDoS, supply chain, insider).
- Documented outcomes; action items tracked.

### 10. Post-incident review

Within 14 days of resolution.
- What happened (timeline of facts).
- What we did (timeline of actions).
- What worked.
- What did not work.
- What systemic improvements are needed (people, process, technology).
- Action items with owners and dates.

PIRs are blameless. The aim is learning, not punishment. Findings are shared internally to maximise organisational learning.

### 11. Customer breach communication patterns

- **Soonest possible accurate communication** beats fast incorrect communication.
- Include what we know, what we do not know, what we are doing, what customers can do, when we will update.
- Direct from the company; not from PR firm.
- Consistent across channels.
- Updates on a stated cadence.

### 12. Metrics

- Time to detect, contain, recover (per incident).
- Notification clock compliance.
- Action items closure rate from PIRs.
- Tabletop exercise frequency and learnings closed.
- Incident volume and severity distribution.

## Real-world lessons baked into this framework

- **The first hour is decisive.** Most damage occurs and most evidence is created in the first hour. A pre-defined process beats improvisation.
- **Single Incident Commander discipline.** Multiple "leaders" produce contradictory actions. One IC at a time.
- **Communications under-promise / over-deliver.** "Within 24 hours" you can hit; "in the next hour" you usually cannot.
- **Notification clocks start at awareness, not confirmation.** GDPR's 72 hours starts when the controller becomes aware that a breach has occurred, even with limited information. Wait for full confidence and you have already missed the clock.
- **Lawyers and engineers speak different languages.** Get them in the same room early so they translate in real time.
- **Tabletop early, tabletop often.** Most organisations discover process gaps during their first real incident. Tabletops surface gaps cheaply.
- **Vendor breach is your incident.** Customers do not care that the data was at a sub-processor; they care that you held it.
- **Don't pay ransoms, except sometimes.** Position is policy, not in-the-moment decision. Resolve in advance with executive and legal.
- **The PIR is the deliverable.** An incident without a PIR is an incident that will recur.

## Common pitfalls

- **No defined IC.** Three engineers each doing what they think best.
- **Severity inflation.** Every incident is SEV-1. Real SEV-1 capacity is exhausted.
- **Severity deflation.** SEV-2 incidents handled as SEV-3 to avoid waking executives.
- **Comms paralysis.** Waiting for "complete information" before saying anything; customers learn from press first.
- **Heroics dependence.** One specific person knows the systems; without them, response collapses.
- **Forgotten clocks.** Regulatory deadlines missed because no one tracked them.
- **No PIR.** "We will write it next week." It never happens.
- **PIR theatre.** A PIR full of action items, none ever closed.
- **Compromise of the responder communications.** Discussing the incident on the same compromised systems being used by the attacker. Use out-of-band channels for IR comms.

## Audit considerations

- Show me your incident management policy and IR plan.
- Walk me through your most recent SEV-2 or SEV-1 incident.
- Show me the notification register for that incident.
- Show me the PIR. Show me action item closure.
- Show me your most recent tabletop exercise.
- Show me your IR team rota and on-call coverage.
- Show me your decision authority matrix.

## How this framework would actually be implemented

A 6-month rollout for a 200-500 person SaaS company starting with informal IR.

**Month 1.** Approve policy and severity classification. Establish IR team and on-call. Build notification register template.

**Month 2.** Write the IR plan. Build top 5 playbooks (phishing, ransomware, cloud-account compromise, vendor breach, DDoS).

**Month 3.** Communications templates with Legal and Comms approval. Decision authority matrix with executive sign-off.

**Month 4.** First tabletop exercise. Address gaps.

**Month 5.** Remaining playbooks. Build 24/7 on-call coverage if not already.

**Month 6.** Second tabletop. Insurance and external counsel relationships in place. PIR template tested on a SEV-3.

By month 6, the next real incident is met by structure rather than panic.

## What I have done in this space and what I have not

I have studied NIST 800-61, ISO 27035, GDPR Articles 33-34, NIS2 incident reporting, DORA Articles 17-23, and many published incident reports.

I have not personally been Incident Commander on a SEV-1 with regulator and customer notifications running concurrently. I have not had to brief a board mid-incident. I have not made the call to take a customer-facing service offline. Those experiences shape practical framework details (especially comms cadence and decision authority) in ways I cannot fully anticipate.

This is a learning portfolio entry.

## Further reading

- **NIST SP 800-61 Rev 2.** Free at csrc.nist.gov. Rev 3 in development as of 2026.
- **ISO/IEC 27035 series.** Paid; ENISA publishes complementary free guidance.
- **NCSC Cyber Security Incident Response Plan template.** Free at ncsc.gov.uk.
- **CISA Incident Response Playbooks for Federal Civilian Executive Branch.** Free at cisa.gov; valuable patterns.
- **ICO Personal Data Breach guidance.** Free at ico.org.uk.
- **EDPB Guidelines 9/2022 on personal data breach notification.** Free at edpb.europa.eu.
- **MITRE ATT&CK and D3FEND** for technique-level investigation patterns.
- **Verizon DBIR** for empirical incident patterns.
- **The Code of Practice for Crisis Management ISO 22301.** Adjacent but useful.

## Status

Learning portfolio. Framework, severity model, role definitions, playbook outlines, communication templates, and notification register all defined. Not exercised in a real incident.
