# Third-Party Risk Management (TPRM) Toolkit

## What this is

A framework and template set for managing the security, privacy, operational, financial and regulatory risks introduced by suppliers, vendors, contractors, sub-processors and any external party that processes data on the organisation's behalf or supplies critical services. Full lifecycle from sourcing through onboarding, ongoing monitoring, performance reviews, contract renewals and offboarding.

The kind of document set a Head of Procurement, CISO or Vendor Management lead would use to stand up or rebuild a TPRM programme. No software is delivered. What you get is the classification model, due-diligence depths, contractual safeguards, workflows and ongoing oversight a real programme needs.

## What this toolkit is trying to fix

Most organisations have a familiar set of TPRM failure modes.

- Procurement signs vendors before security or legal sees the contract.
- Every vendor gets the same 200-question security questionnaire regardless of risk.
- Critical vendors and the office coffee supplier are treated identically.
- Vendor approval is a one-time event. Nothing happens between then and contract renewal three years later.
- Sub-processors of sub-processors are unknown.
- Nobody can quickly say which vendors have access to which data.
- When a vendor has a breach, the company finds out from the news.
- The inventory is a spreadsheet last updated 18 months ago.
- Contracts have no security clauses, no audit rights, no breach notification requirements, no exit obligations.
- Concentration risk (multiple critical functions on one vendor) is invisible.

A strong opinion: questionnaire fatigue kills TPRM programmes faster than any other single thing. If every vendor receives a 250-question SIG and the security team is the one chasing responses, you will get poor data, slow procurement, and procurement quietly routing around you within six months. Tier first. Question second.

Another opinion: somebody has to own the vendor inbox. If "vendor risk" is everyone's job, due diligence happens by accident. Usually it should sit with GRC, with procurement holding the contract relationship and security holding veto rights on high-risk vendors.

## Why it matters

- Reduces supply-chain exposure. The SolarWinds, Kaseya, MOVEit and 3CX patterns all flowed through trusted vendors.
- Regulatory compliance with GDPR Art 28 (processors), DORA (ICT third parties), NIS2 (essential and important entities and their suppliers), PRA SS2/21 (UK financial services), ISO 27001 A.5.19 to A.5.23, SOC 2 CC9.2.
- Faster procurement for low-risk vendors. The slow security review only happens where it is actually needed.
- Concentration risk visibility for the board.
- Cleaner audits because TPRM evidence is in one programme rather than scattered.
- Lower likelihood of being the case study in next year's supply-chain breach report.

## Framework alignment

- **GDPR Articles 28 and 32** for processors, sub-processors and security of processing.
- **ISO/IEC 27001:2022 Annex A.5.19 to A.5.23** on supplier relationships, supplier agreements, service delivery, monitoring and cloud services.
- **ISO/IEC 27036** series for information security in supplier relationships.
- **NIST SP 800-161 Rev 1** for cybersecurity supply chain risk management.
- **SOC 2 CC9.2** for monitoring of third parties.
- **DORA Articles 28 to 30** for ICT third-party risk and the register of information.
- **NIS2 Article 21(2)(d)** for supply-chain security.
- **PRA SS2/21** Outsourcing and third-party risk management (UK financial services).
- **EBA Guidelines on Outsourcing Arrangements EBA/GL/2019/02** (EU financial services).
- **Shared Assessments SIG and SIG Lite** as widely adopted questionnaire templates.
- **Cloud Security Alliance CAIQ** for cloud-vendor due diligence.

## What sits in the toolkit

### 1. Vendor inventory

The single source of truth. Fields: vendor name, primary contact, services provided, data accessed, systems integrated with, contract owner, contract dates, classification tier, last review date, next review date.

A real inventory for a mid-sized SaaS company runs 200 to 2,000 entries. Most organisations underestimate by an order of magnitude until they actually look. Pull from procurement records, expense data, system integration lists and DPIA records. Then cross-check. There will be surprises.

### 2. Vendor classification model

Diligence has to scale to risk. A defensible classification model is the only way to keep the programme alive.

| Tier | Description | Examples | Diligence required |
|---|---|---|---|
| **Tier 1 - Critical** | Vendor whose failure would cause material business disruption, regulatory breach or significant data exposure | AWS, Stripe, primary identity provider, primary database hosting | Full SOC 2 + ISO 27001 review, on-site or video due diligence, financial review, contract with full clauses, quarterly reviews, annual reassessment, documented exit plan |
| **Tier 2 - High** | Vendor with privileged access or significant data | Email security, SIEM provider, payroll, HR system | Full questionnaire, SOC 2 review, contract with key clauses, semi-annual review |
| **Tier 3 - Moderate** | Vendor with limited data access | Marketing automation, internal collaboration tools | Lite questionnaire, evidence of certifications, standard contract, annual review |
| **Tier 4 - Low** | Vendor with no data access | Office supplies, catering, training | Basic background check, standard terms, biennial review |

Classification criteria.

- Volume and sensitivity of data processed.
- Privileges granted (admin, root, network access).
- Criticality to operations (RTO impact).
- Regulatory implications (personal data, financial data, health data).
- Substitutability. If they fail tomorrow, how fast can we replace them.
- Concentration. This vendor plus what else.

In my experience the tiering itself is the most contested part. Engineering wants critical infrastructure as Tier 2 because Tier 1 due diligence "slows them down". Hold the line. Get the criteria written and approved before the first contested vendor, so it is not a judgement call in the moment.

### 3. Risk assessment questionnaire suite

Three tiers of questionnaire matched to classification.

**Full questionnaire (Tier 1 to 2).** 150 to 250 questions covering governance, security policies, asset management, access control, encryption, vulnerability management, incident response, business continuity, physical security, personnel security, secure development, sub-processors, certifications, regulatory compliance.

Use the **Shared Assessments SIG** or **CAIQ** as the base. Add organisation-specific questions for AI, regulated data, country-specific requirements (in an Indian SaaS context, DPDP Act and sectoral rules; for EU customers, GDPR specifics).

**Lite questionnaire (Tier 3).** 30 to 50 questions. Certifications, encryption, access control, breach notification, sub-processors, basic governance.

**Minimal questionnaire (Tier 4).** 10 to 15 questions. Certifications and breach notification.

### 4. Risk scoring methodology

Translate responses into a numerical score so vendors can be ranked and tracked.

- Weight questions by importance. Encryption at rest is heavier than office cleanliness.
- Score responses. Yes / no / partial / N/A with multipliers.
- Calculate inherent risk (questionnaire plus classification).
- Calculate residual risk. Factor in certifications, audit reports, references.
- Thresholds for approval, conditional approval, rejection.
- Document exceptions where the business accepts risk.

### 5. Due diligence procedures

For each tier, defined diligence steps.

**Tier 1 Critical.**
- Read the SOC 2 Type 2 report end to end, not just the opinion page.
- Review ISO 27001 certificate and SoA where available.
- Review penetration test summary.
- Review business continuity and disaster recovery testing evidence.
- Review insurance certificates.
- Review financial stability. Audited accounts, D&B report.
- Reference checks with two or more existing customers.
- Site visit or detailed video diligence.
- Sub-processor list reviewed.
- Concentration check. Other vendors in the same datacentre, region or parent company.

**Tier 2 to 3.** Scaled down. SOC 2 review, certification verification, lite reference checks.

**Tier 4.** Basic checks. Trust but verify on certifications.

### 6. Contractual clauses library

Standard clauses for vendor contracts with negotiation guidance for each.

Core clauses for any data-processing or systems-access vendor.

- **Data protection / processor terms.** GDPR Art 28 compliant. Processing instructions, confidentiality, security measures, sub-processors, assistance to data subjects, breach notification, return or deletion of data, audit rights.
- **Information security minimum standards.** Referencing the customer's security standard.
- **Sub-processor consent.** Right to know, right to object, list maintained current.
- **Breach notification.** Typically 24 to 72 hours from awareness, with required minimum content.
- **Audit rights.** Annual with reasonable notice, or equivalent attestation.
- **Right to receive SOC 2 / ISO 27001** reports on request.
- **Insurance requirements.** Cyber liability, professional indemnity, with named coverage minimums.
- **Service levels.** RTO, RPO, availability, response time. Credits for breach.
- **Exit obligations.** Data return in agreed format, secure deletion confirmed in writing, transition assistance.
- **Indemnities.** Data breach, IP infringement, regulatory penalties.
- **Limitation of liability.** Carve-outs for data breach, gross negligence, wilful misconduct.
- **Governing law and dispute resolution.**
- **Subcontracting restrictions.** Consent for material change of control, geography.

### 7. Onboarding workflow

Sequenced from sourcing decision to operational vendor.

1. Business case and sourcing decision recorded.
2. Initial classification by procurement, advisory by GRC.
3. Questionnaire issued.
4. Due diligence performed at the depth set by tier.
5. Risk assessment completed and approved by the appropriate authority. Tier 1 needs CISO plus Procurement Director. Tier 4 needs the Procurement Manager.
6. Contract negotiation including security clauses.
7. Final approval and PO issued.
8. Onboarding. System access, integrations, data sharing, training of internal users.
9. Vendor entered into inventory with metadata.
10. First review scheduled.

### 8. Ongoing monitoring

Vendor risk is not a point-in-time check.

**Continuous, where automation supports it.**
- Security ratings monitoring (Bitsight, SecurityScorecard, RiskRecon) for Tier 1 to 2.
- Breach disclosure monitoring. News, threat intelligence, regulatory notices.
- Certification status monitoring. SOC 2, ISO 27001 expiry, lapses.

**Periodic.**
- Annual reassessment for Tier 1 to 2.
- Biennial for Tier 3.
- Triennial for Tier 4.
- Trigger-based for any tier on material event. Vendor breach, change of control, regulatory action, change in data scope.

**Performance review.**
- SLA performance tracked monthly for Tier 1.
- Issue tickets logged against vendor.
- Vendor scorecard maintained.
- Quarterly business review meetings with Tier 1 vendors.

### 9. Sub-processor management

For data processors: maintained list of sub-processors, customer notification on change with right to object where contractually agreed, assessment of new sub-processors before use, contractual flow-down of obligations.

### 10. Concentration risk register

Where multiple critical functions depend on one vendor, one region, one datacentre, one network provider, one identity provider or one parent company.

Example concentration findings.
- Three Tier 1 vendors all hosted in AWS eu-west-1. A regional outage affects all.
- Both primary and backup payroll providers acquired by the same private equity firm last year.
- Primary CDN and primary DDoS protection from the same vendor.

Reported quarterly to the executive committee.

### 11. Exit and offboarding playbook

When a vendor is replaced or fired.

- Contractual exit clauses invoked.
- Data return in agreed format.
- Secure deletion certified in writing.
- Access revocation across all systems.
- Integrations decommissioned.
- Vendor removed from inventory.
- Lessons learned documented.
- Concentration risk reassessed.

### 12. Vendor incident response

When a vendor reports a breach or security incident.

- Initial notification logged. Date, time, source.
- Severity classification. Impact on us, our customers, our data.
- Internal escalation. CISO, Legal, comms.
- Information request to vendor. What data, what users, what timeframe.
- Customer notification decision. Legal advice, regulatory clocks.
- Remediation tracking.
- Post-incident review including the relationship itself.

## Where teams stall

Patterns that recur.

- **The inbox nobody owns.** Vendor questionnaire responses, SOC 2 reports and sub-processor notifications pile up in a shared mailbox. Nothing gets reviewed until renewal. The fix is naming a single owner with calendar time for it.
- **Questionnaire response inflation.** Every vendor gets the 250-question SIG. Response quality is poor. Review backlog grows. Procurement learns to route around the process.
- **Onboarding without offboarding.** Vendors get added efficiently. Removal is informal. Twelve months later the inventory has 30 vendors with active integrations that nobody is paying for and nobody is monitoring.
- **Sub-processor blindness.** Tier 1 vendor lists their sub-processors. Nobody reviews the list. A change appears in version 14 of the data processing addendum. It is six months before anyone notices.
- **Certificate theatre.** "We have ISO 27001" is accepted without seeing the certificate, the scope, or the expiry. Then it turns out the certificate covered the parent entity's HR systems in another country.

In one SaaS environment during ISO 27001 readiness, the auditor pulled a sample of five Tier 1 vendors and asked for current SOC 2 reports. Two were over 18 months old. One vendor had moved to a different audit firm and the new report was held up by a sales process. The fix was a quarterly evidence-freshness sweep on Tier 1 vendors, not a heroic effort the week before audit.

## Real-world cases shaping the design

- **SolarWinds Orion.** Trusted update mechanism compromised. The toolkit emphasises supply-chain integrity questions and out-of-band breach intelligence monitoring.
- **Kaseya VSA.** MSP tool exploited to push ransomware to MSP customers' customers. The toolkit emphasises sub-processor mapping and concentration awareness.
- **MOVEit.** File-transfer vendor zero-day used to extract data from many organisations. The toolkit emphasises the difference between SaaS data exposure and infrastructure compromise.
- **Okta support compromise.** Identity vendor support system compromise exposed customer session tokens. The toolkit treats support-system access reviews as their own question category.
- **3CX.** Software supply-chain compromise via earlier compromise of a different vendor. The toolkit treats software supply chain as its own assessment dimension.
- **Snowflake-related customer breaches.** Stolen credentials used against customer instances without MFA. The toolkit pushes on customer-side configuration controls within vendor environments.

## Audit considerations

Auditors will usually test:

- Is the vendor inventory complete?
- Is the classification model documented and applied consistently?
- Pick five vendors and walk through their due diligence files.
- Show me a Tier 1 vendor without a SOC 2 report. What is the compensating control?
- Show me the most recent annual reassessments for three Tier 1 vendors.
- Show me a vendor breach in the past 12 months. Walk me through the response.
- How is sub-processor change handled? Show evidence.
- How is concentration risk reported? To whom? When?
- Show me a contract with full security clauses. Show me one with weakened clauses and the risk acceptance.

## Common pitfalls

- **Questionnaires as the whole programme.** Issuing questionnaires and filing responses without analysis or follow-up.
- **Onboarding as one-time.** Vendor approval treated as the end of risk management rather than the start.
- **No reciprocal evidence.** Accepting "we have ISO 27001" without seeing certificate, scope or expiry.
- **Sub-processor blindness.** Not knowing the supply chain beneath the supply chain.
- **Concentration ignorance.** Treating each vendor in isolation.
- **Contract surrender.** Accepting vendor master agreements without negotiating security and exit terms.
- **Programme as procurement only.** TPRM owned solely by procurement with security as advisory. Nobody enforces security positions.
- **No off-ramp.** Critical vendors with no documented exit plan. The organisation is hostage at renewal.

## How a rollout actually goes

For a 500-person SaaS company.

**Months 1 to 2.** Build the inventory. Procurement records, expense data, system integrations and DPIA records. Classify by tier. Tier 1 vendors identified urgently.

**Month 3.** Roll out the questionnaire process for new vendors. Start Tier 1 reassessments using the new questionnaire.

**Months 4 to 6.** Reassess all Tier 1 vendors. Update contracts at next renewal. Address gaps. First concentration risk report.

**Months 7 to 9.** Tier 2 reassessments. Implement security ratings monitoring for Tier 1 to 2. Build vendor incident playbook.

**Months 10 to 12.** First annual cycle complete. Tier 3 and Tier 4 sweeps. Vendor scorecard live.

**Year 2.** Refine, automate where possible. Questionnaire portal, evidence collection, ratings integration.

Most of the time, the second year is when the programme stops feeling like a permanent backlog.

## What I have done and what I have not

I have studied GDPR Art 28, NIST 800-161, ISO 27036, DORA Chapter V and the Shared Assessments SIG framework in detail.

I have not personally negotiated a major Tier 1 vendor contract with hostile counsel on the other side. I have not led a vendor incident response across legal, comms and customer notification in real time. I have not managed a TPRM programme through a regulatory examination on outsourcing arrangements. Those experiences would shape the practical sections, especially the contractual negotiation tactics.

This is a learning portfolio entry.

## Further reading

- **ENISA Supply Chain Security guidance** at enisa.europa.eu.
- **NIST SP 800-161 Rev 1.** Free PDF at csrc.nist.gov.
- **Shared Assessments SIG.** Membership-based with a free overview. SIG Core has 1,500+ questions. SIG Lite is the abridged 100-question version.
- **Cloud Security Alliance CAIQ.** Free at cloudsecurityalliance.org.
- **DORA Chapter V (Articles 28 to 30) and the EBA Outsourcing Guidelines.** Free at eur-lex.europa.eu and eba.europa.eu.
- **ICO guidance on processor contracts** at ico.org.uk.
- **PRA SS2/21** at bankofengland.co.uk.
- **OneTrust, Vanta, Drata blog content** on TPRM. Vendor content but useful patterns.

## Status

Learning portfolio. Toolkit complete with classification model, three-tier questionnaire suite, contractual library, workflows and templates. Not used in a live TPRM operation.
