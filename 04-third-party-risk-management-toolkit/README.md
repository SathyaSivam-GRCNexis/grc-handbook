# Third-Party Risk Management (TPRM) Toolkit

## What this project is

A complete framework and template set for managing the security, privacy, operational, financial, and regulatory risks introduced by suppliers, vendors, contractors, sub-processors, and any external party that processes data on the organisation's behalf or supplies critical services. It covers the full lifecycle from sourcing through onboarding, ongoing monitoring, performance reviews, contract renewals, and offboarding.

This is the document set a Head of Procurement, CISO, or Head of Vendor Management would use to stand up or rebuild a TPRM programme. It is non-technical in that no software is delivered, but it defines the workflows, classifications, due-diligence depth, contractual safeguards, and ongoing oversight that a real programme requires.

## Problem this toolkit solves

Most organisations have one or more of these failure modes around third parties.

- Procurement signs vendors before security or legal sees the contract.
- Every vendor gets the same 200-question security questionnaire regardless of risk.
- Critical vendors and the company canteen are treated identically.
- Vendor approval is a one-time event; nothing happens between then and contract renewal three years later.
- Sub-processors of sub-processors are unknown.
- No one knows which vendors have access to which data.
- When a vendor has a breach, the company finds out from the news.
- The vendor inventory is a spreadsheet last updated 18 months ago.
- Contracts have no security clauses, no audit rights, no breach notification requirements, no exit obligations.
- Concentration risk (multiple critical functions on one vendor) is invisible.

A working TPRM programme fixes these by classifying vendors by risk, scaling diligence to that risk, contracting appropriately, monitoring continuously, and exiting cleanly.

## Business impact

- Reduced supply-chain risk exposure (the SolarWinds, Kaseya, MOVEit, and 3CX breaches all flowed through trusted vendors).
- Regulatory compliance with GDPR Art 28 (processors), DORA (ICT third parties), NIS2 (essential and important entities and their suppliers), PRA SS2/21 (UK financial services), ISO 27001 A.5.19-A.5.23, SOC 2 CC9.2.
- Faster procurement for low-risk vendors (the slow security review goes away when the vendor is genuinely low risk).
- Concentration-risk visibility for the board.
- Cleaner audits because TPRM evidence is concentrated in one programme rather than scattered.
- Lower likelihood of being the case study in next year's supply-chain breach report.

## Framework alignment

- **GDPR Articles 28 and 32** for data processors, sub-processors, and security of processing.
- **ISO/IEC 27001:2022 Annex A controls 5.19-5.23** (supplier relationships, addressing security in supplier agreements, managing supplier service delivery, monitoring services, information security in cloud services).
- **ISO/IEC 27036 series** Information security for supplier relationships.
- **NIST SP 800-161 Rev 1** Cybersecurity Supply Chain Risk Management Practices.
- **SOC 2 CC9.2** for monitoring of third parties.
- **DORA Articles 28-30** for ICT third-party risk management and the register of information.
- **NIS2 Article 21(2)(d)** for supply-chain security.
- **PRA Supervisory Statement SS2/21** Outsourcing and third-party risk management (UK financial services).
- **EBA Guidelines on Outsourcing Arrangements EBA/GL/2019/02** (EU financial services).
- **Shared Assessments SIG and SIG Lite** as widely adopted questionnaire templates.
- **Cloud Security Alliance CAIQ** for cloud-vendor due diligence.

## Components and deliverables

### 1. Vendor inventory

The single source of truth for every external party. Fields include vendor name, primary point of contact, services provided, data accessed, systems integrated with, contract owner, contract dates, classification tier, last review date, next review date.

A real inventory has 200-2000 entries for a mid-sized SaaS company. Most organisations underestimate by an order of magnitude until they look properly.

### 2. Vendor classification model

Scaling diligence to risk requires a defensible classification.

| Tier | Description | Examples | Diligence required |
|---|---|---|---|
| **Tier 1 - Critical** | Vendor whose failure would cause material business disruption, regulatory breach, or significant data exposure | AWS, Stripe, primary identity provider, primary database hosting | Full SOC 2 + ISO 27001 review, on-site or video due diligence, financial review, contract with full clauses, quarterly reviews, annual reassessment, exit plan documented |
| **Tier 2 - High** | Vendor with privileged access or significant data | Email security, SIEM provider, payroll, HR system | Full questionnaire, SOC 2 review, contract with key clauses, semi-annual review |
| **Tier 3 - Moderate** | Vendor with limited data access | Marketing automation, internal collaboration tools | Lite questionnaire, evidence of certifications, standard contract, annual review |
| **Tier 4 - Low** | Vendor with no data access | Office supplies, catering, training | Basic background check, standard terms, biennial review |

Classification criteria.

- Volume and sensitivity of data processed.
- Privileges granted (admin, root, network access).
- Criticality to operations (RTO impact).
- Regulatory implications (handles personal data, financial data, health data).
- Substitutability (if they fail tomorrow, how fast can we replace them).
- Concentration (this vendor plus what else).

### 3. Risk assessment questionnaire suite

Three tiers of questionnaire to match the classification.

**Full questionnaire (Tier 1-2):** 150-250 questions covering governance, security policies, asset management, access control, encryption, vulnerability management, incident response, business continuity, physical security, personnel security, secure development, sub-processors, certifications, regulatory compliance.

Use the **Shared Assessments SIG (Standardised Information Gathering)** or **CAIQ** as the base. Add organisation-specific questions for AI, regulated data, country-specific requirements.

**Lite questionnaire (Tier 3):** 30-50 questions covering certifications, encryption, access control, breach notification, sub-processors, basic governance.

**Minimal questionnaire (Tier 4):** 10-15 questions on certifications and breach notification.

### 4. Risk scoring methodology

Translate questionnaire responses into a numerical risk score so vendors can be ranked and tracked.

- Weight questions by importance (encryption at rest is heavier than office cleanliness).
- Score responses (yes/no/partial/N/A with multipliers).
- Calculate inherent risk (questionnaire + classification).
- Calculate residual risk (factor in evidence of certifications, audit reports, references).
- Threshold for approval, conditional approval, rejection.
- Document exceptions where the business accepts risk.

### 5. Due diligence procedures

For each tier, defined diligence steps.

**Tier 1 Critical.**
- Review SOC 2 Type 2 report (full read, not just opinion page).
- Review ISO 27001 certificate and SoA where available.
- Review penetration test summary.
- Review business continuity and disaster recovery testing evidence.
- Review insurance certificates.
- Review financial stability (audited accounts, D&B report).
- Reference checks with two or more existing customers.
- Site visit or detailed video diligence.
- Sub-processor list reviewed.
- Concentration check (other vendors in same datacentre, same region, same parent company).

**Tier 2-3.** Scaled down: SOC 2 review, certification verification, lite reference checks.

**Tier 4.** Basic checks; trust but verify on certifications.

### 6. Contractual clauses library

Standard clauses for inclusion in vendor contracts. Negotiation guidance for each.

Core clauses for any data-processing or systems-access vendor.

- **Data protection / processor terms** (GDPR Art 28 compliant: processing instructions, confidentiality, security measures, sub-processors, assistance to data subjects, breach notification, return or deletion of data, audit rights).
- **Information security minimum standards** (referencing the customer's security standard).
- **Sub-processor consent** (right to know, right to object, list maintained current).
- **Breach notification** (typically 24-72 hours from awareness, with required minimum content).
- **Audit rights** (right to audit annually with reasonable notice, or to receive equivalent attestation).
- **Right to receive SOC 2 / ISO 27001** reports on request.
- **Insurance requirements** (cyber liability, professional indemnity, with named coverage minimums).
- **Service levels** (RTO, RPO, availability, response time, with credits for breach).
- **Exit obligations** (data return in agreed format, secure deletion confirmed in writing, transition assistance).
- **Indemnities** (data breach, IP infringement, regulatory penalties).
- **Limitation of liability** (carve-outs for data breach, gross negligence, wilful misconduct).
- **Governing law and dispute resolution.**
- **Subcontracting restrictions** (consent for material change of control, geography).

### 7. Onboarding workflow

Sequenced steps from sourcing decision to operational vendor.

1. Business case and sourcing decision recorded.
2. Initial classification by procurement (advisory by GRC).
3. Questionnaire issued.
4. Due diligence performed (depth by tier).
5. Risk assessment completed and approved by appropriate authority (Tier 1 = CISO + Procurement Director; Tier 4 = Procurement Manager).
6. Contract negotiation including security clauses.
7. Final approval and PO issued.
8. Onboarding (system access, integrations, data sharing, training of internal users).
9. Vendor entered into inventory with metadata.
10. First review scheduled.

### 8. Ongoing monitoring

Vendor risk is not a point-in-time check.

**Continuous (where automation supports it).**
- Security ratings monitoring (Bitsight, SecurityScorecard, RiskRecon) for Tier 1-2.
- Breach disclosure monitoring (news, threat intelligence, regulatory notices).
- Certification status monitoring (SOC 2, ISO 27001 expiry, lapses).

**Periodic.**
- Annual reassessment for Tier 1-2 (questionnaire refresh, evidence refresh, contract review).
- Biennial for Tier 3.
- Triennial for Tier 4.
- Trigger-based for any tier on material event (vendor breach, change of control, regulatory action, change in data scope).

**Performance review.**
- SLA performance tracked monthly for Tier 1.
- Issue tickets logged against vendor.
- Vendor scorecard maintained.
- Quarterly business review meetings with Tier 1 vendors.

### 9. Sub-processor management

For data processors: maintained list of sub-processors, customer notification on change (with right to object where contractually agreed), assessment of new sub-processors before use, contractual flow-down of obligations.

### 10. Concentration risk register

Visibility into where multiple critical functions depend on one vendor, one region, one datacentre, one network provider, one identity provider, or one parent company.

Example concentration findings.
- Three Tier 1 vendors all hosted in AWS eu-west-1; regional outage affects all.
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

- Initial notification logged (date, time, source).
- Severity classification (impact on us, our customers, our data).
- Internal escalation (CISO, Legal, comms).
- Information request to vendor (what data, what users, what timeframe).
- Customer notification decision (legal advice, regulatory clocks).
- Remediation tracking with vendor.
- Post-incident review including the relationship.

## Real-world cases shaping this design

- **SolarWinds Orion (December 2020).** Trusted update mechanism compromised, malicious code distributed to thousands of customers including US government agencies. The toolkit emphasises supply-chain integrity questions and out-of-band breach intelligence monitoring.
- **Kaseya VSA (July 2021).** Managed service provider tool exploited to ransomware-distribute to MSP customers' customers. The toolkit emphasises sub-processor mapping and concentration-risk awareness.
- **MOVEit (May-June 2023).** File-transfer vendor zero-day exploited to mass-extract data from hundreds of organisations including BBC, BA, and others. The toolkit emphasises the difference between SaaS data exposure and infrastructure compromise.
- **Okta support compromise (October 2023).** Identity vendor support system compromise exposed customer session tokens. The toolkit emphasises support-system access reviews as a category of question.
- **3CX (March 2023).** Software supply-chain compromise via earlier compromise of a different vendor (X_TRADER). The toolkit treats software supply chain as its own assessment dimension.
- **Snowflake-related customer breaches (2024).** Stolen credentials used against vendor instances without MFA. The toolkit pushes hard on customer-side configuration controls within vendor environments.

## Audit considerations

External and internal auditors will test:

- Is the vendor inventory complete?
- Is the classification model documented and applied consistently?
- Pick five vendors and walk through their due diligence files.
- Show me a Tier 1 vendor without a SOC 2 report. What is the compensating control?
- Show me the most recent annual reassessments for three Tier 1 vendors.
- Show me a vendor breach in the past 12 months. Walk through the response.
- How is sub-processor change handled? Show evidence.
- How is concentration risk reported? To whom? When?
- Show me a contract with full security clauses; show me a contract with weakened clauses and the risk acceptance.

## Common pitfalls

- **Questionnaires as the whole programme.** Issuing questionnaires and filing responses without analysis or follow-up.
- **Onboarding as one-time.** Treating vendor approval as the end rather than the start of risk management.
- **No reciprocal evidence.** Accepting "we have ISO 27001" without seeing the certificate, scope, or expiry date.
- **Sub-processor blindness.** Not knowing the supply chain beneath the supply chain.
- **Concentration ignorance.** Treating each vendor in isolation.
- **Contract surrender.** Accepting vendor master agreements without negotiating security and exit terms.
- **Programme as procurement department.** TPRM owned solely by procurement with security as advisory; nobody enforces security positions.
- **No off-ramp.** Critical vendors with no documented exit plan, so the organisation is hostage at renewal.

## How this toolkit would actually be implemented

A new TPRM programme rollout for a 500-person SaaS company.

**Months 1-2.** Build inventory by combining procurement records, expense data, system integration lists, and DPIA records. Classify by tier. Identify Tier 1 vendors urgently.

**Month 3.** Roll out questionnaire process for new vendors. Begin Tier 1 reassessments using the new questionnaire.

**Months 4-6.** Reassess all Tier 1 vendors. Update contracts at next renewal. Address gaps. First concentration risk report.

**Months 7-9.** Tier 2 reassessments. Implement security ratings monitoring for Tier 1-2. Build vendor incident playbook.

**Months 10-12.** First annual cycle complete. Tier 3 and Tier 4 sweeps. Vendor scorecard live.

**Year 2.** Refine, optimise, automate where possible (questionnaire portal, evidence collection, ratings integration).

## What I have done in this space and what I have not

I have studied GDPR Art 28, NIST 800-161, ISO 27036, DORA Chapter V, and the Shared Assessments SIG framework in detail.

I have not personally negotiated a major Tier 1 vendor contract with hostile counsel on the other side. I have not led a vendor incident response across legal, comms, and customer-notification dimensions in real time. I have not managed a TPRM programme through a regulatory examination on outsourcing arrangements. Those experiences would shape the practical sections, especially contractual negotiation tactics.

This is a learning portfolio entry.

## Further reading

- **ENISA Supply Chain Security guidance** at enisa.europa.eu (free).
- **NIST SP 800-161 Rev 1.** Free PDF at csrc.nist.gov.
- **Shared Assessments SIG.** Membership-based but a free overview is available; SIG Core has 1500+ questions, SIG Lite is the abridged 100-question version.
- **Cloud Security Alliance CAIQ.** Free at cloudsecurityalliance.org.
- **DORA Chapter V (Articles 28-30) and the EBA Outsourcing Guidelines.** Free at eur-lex.europa.eu and eba.europa.eu.
- **ICO guidance on processor contracts** at ico.org.uk.
- **PRA SS2/21** at bankofengland.co.uk.
- **OneTrust, Vanta, Drata blog content** on TPRM (vendor content but useful patterns).

## Status

Learning portfolio. Toolkit complete with classification model, three-tier questionnaire suite, contractual library, workflows, and templates. Not used in a live TPRM operation.
