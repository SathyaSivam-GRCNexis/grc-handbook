# Risk Scenario Library (SaaS Focused)

## What this project is

A library of 40+ realistic risk scenarios specific to mid-sized SaaS organisations, each scored for likelihood and impact, mapped to the controls that mitigate them, and grounded in actual incidents that have occurred in the industry. The library makes the risk register concrete by giving teams a vocabulary of scenarios rather than abstract risk titles.

This is the document a Head of Risk or CISO uses to seed risk workshops, train new joiners, brief boards, and ensure that the risk register is populated with risks that are real for the business rather than risks copied from generic templates.

## Problem this library solves

Risk registers in SaaS companies often share these symptoms.

- Generic entries copied from ISO 27005 examples, with no adaptation: "loss of confidentiality of information," "natural disaster."
- Owners assigned but not engaged because the risks feel theoretical.
- Workshops produce 200 risks of which 195 are duplicates or non-risks.
- Boards eye-glaze when presented with abstract categories.
- Treatment plans cannot be specific because the underlying scenario is too vague.
- Tabletop exercises and incident response training rest on scenarios invented on the spot, wasting facilitation time.

A risk scenario library fixes this. Each scenario describes a concrete situation: who, what, how, with what consequence. Workshops then run on "is this scenario relevant to us, what is the likelihood and impact for us specifically, what controls do we already have, what is missing." The conversation becomes operational rather than philosophical.

## Business impact

- Faster, sharper risk workshops that produce actionable output.
- Better board engagement because scenarios are storyable.
- Realistic tabletop exercises drawing from the same library.
- Continuity between risk identification, treatment, and incident-response readiness.
- New joiner onboarding accelerated by exposure to real scenarios.
- Insurance discussions improved because underwriters recognise scenario-based maturity.

## Framework alignment

- **ISO/IEC 27005:2022** scenario-based risk approach.
- **NIST SP 800-30 Rev 1** threat-source / threat-event / vulnerability modelling.
- **NIST SP 800-61 Rev 2** incident handling guide (scenarios feed IR exercises).
- **MITRE ATT&CK** for technique-level realism.
- **VERIS (Verizon Vocabulary for Event Recording and Incident Sharing)** for actor / action / asset / attribute taxonomy.
- **The DBIR (Verizon Data Breach Investigations Report)** for empirical likelihood weighting.
- **CISA Known Exploited Vulnerabilities catalogue** for currency.

## How scenarios are structured

Each scenario follows a consistent template.

```
Scenario ID: SC-NN
Title: <one sentence>
Category: <e.g. confidentiality / integrity / availability / privacy / regulatory / supply chain>
Description: <2-3 paragraph narrative>
Threat actor: <who would do this>
Threat vector: <how they would do it>
Affected assets: <what is at risk>
Likelihood (1-5): <inherent>
Impact dimensions: financial, operational, reputational, regulatory, customer
Inherent risk score: <L x I>
Existing controls: <list with control IDs>
Residual likelihood (1-5): <after current controls>
Residual impact (1-5):
Residual risk score:
Real-world examples: <named historical incidents>
Recommended additional controls:
Detection signals:
Tabletop exercise version:
```

## Selected scenarios (subset)

The full library contains 40+ scenarios. Below are the most representative across categories.

### Confidentiality scenarios

**SC-01 Customer database exfiltration via SQL injection in legacy admin tool**

A pre-migration internal admin web app has a SQL injection vulnerability in a search field used by support engineers. An external attacker who has obtained support credentials via phishing exploits the vulnerability to dump 800,000 customer records including emails, hashed passwords, and partial billing information. Detection occurs three weeks later when the dataset appears for sale on a dark-web forum.

- Inherent: L4 I5 (Major)
- Real-world reference: TalkTalk 2015 (157,000 records, similar pattern at much larger company).
- Existing controls: WAF (partial), code review (partial coverage of legacy systems), credential rotation (90-day).
- Residual: L3 I4 (with controls). Treatment: replace legacy admin, implement code-injection scanning in CI, dark-web monitoring.

**SC-02 Customer data leaked via misconfigured S3 bucket**

A new feature stores generated PDF reports in S3. The bucket is created with default settings by a junior engineer. ACL is left at "public-read" because that is the path-of-least-resistance default in some IaC examples. Six months later, a security researcher running a bucket scanner finds the bucket and discovers 4 million PDFs containing customer financial data.

- Inherent: L3 I5 (Severe).
- Real-world reference: Capital One 2019 (different mechanism but related cloud-misconfiguration pattern; many smaller publicised cases).
- Existing controls: cloud posture management (recently deployed), Terraform module (default-deny), code review.
- Residual: L2 I5. Treatment: enforce CSPM blocking deployment of public buckets, OPA policy in Terraform pipeline, S3 Block Public Access at account level.

**SC-03 Insider exfiltration by departing engineer**

A senior engineer who has accepted an offer at a competitor downloads a copy of the production data dictionary, internal architecture documents, and the customer pipeline-stage data, planning to take the material to their new role. Detection is via DLP triggering on bulk download, three days before their last day.

- Inherent: L3 I3.
- Real-world reference: Anthony Levandowski / Waymo / Uber 2017 (extreme version of the pattern); routine smaller versions occur frequently.
- Existing controls: DLP, HR-triggered access reduction on resignation, exit interview.
- Residual: L2 I3. Treatment: improve resignation-triggered access controls, formalise download-volume monitoring, contractual NDAs with bite.

**SC-04 Phishing of finance leading to wire fraud**

An attacker impersonating the CEO emails the FP&A team during a quiet period asking for an urgent confidential wire transfer to a "new acquisition target's escrow account." The team executes a £450,000 transfer that is unrecoverable.

- Inherent: L4 I3.
- Real-world reference: Persistent BEC pattern; FBI IC3 reports BEC as the highest-loss cybercrime category by total dollar value.
- Existing controls: dual approval for wires above £100k, training (annual).
- Residual: L3 I3. Treatment: callback verification on any new payee, just-in-time wire-fraud awareness, payment-system controls limiting first-time payees.

### Availability scenarios

**SC-05 Cloud-region outage takes down primary service for 8 hours**

The single AWS region (eu-west-1) where the production database resides experiences a multi-AZ outage lasting 8 hours due to network-fabric failure. Multi-AZ failover does not save the database. The standby region exists but quarterly DR drill failed; failover is untested in production.

- Inherent: L2 I5.
- Real-world reference: AWS us-east-1 outages 2021 December, 2017 February S3, multiple others; Azure 2024 incidents.
- Existing controls: multi-AZ database, monitoring, status page.
- Residual: L2 I5 unchanged. Treatment: complete cross-region failover testing, document RTO/RPO formally, customer SLA review.

**SC-06 Ransomware encrypts production via compromised admin endpoint**

An admin user clicks a phishing link, malware persists, escalates privileges, harvests credentials, lateral-moves to a build server, and via stored cloud credentials encrypts production storage. Encrypted data includes customer artefacts and internal databases. Ransom demand $5m.

- Inherent: L3 I5.
- Real-world reference: countless. MGM 2023, Change Healthcare 2024, many smaller cases.
- Existing controls: EDR, MFA on admin (but session-token theft possible), backups (untested restoration).
- Residual: L3 I5 unchanged. Treatment: phishing-resistant MFA, network segmentation between corporate and production, immutable backups with tested restoration, incident-response retainer.

**SC-07 Critical SaaS dependency outage**

The primary identity provider (Okta) is unavailable for 4 hours due to a security incident at their support vendor. SSO into all internal tools breaks. Customer-facing application using IdP-mediated authentication is unavailable for the same window.

- Inherent: L2 I4.
- Real-world reference: Okta support compromise October 2023; multiple SaaS outages affecting downstream.
- Existing controls: dependency monitoring, on-call.
- Residual: L2 I4. Treatment: emergency break-glass auth path, alternate IdP for critical paths, IdP failure runbook, customer comms template.

### Integrity scenarios

**SC-08 Data corruption from a bad release**

A schema migration in a release pipeline runs against the wrong database (staging credentials accidentally point to production). 3 hours of customer data is corrupted before the issue is detected. Restore from backup loses 3 hours of work for thousands of customers.

- Inherent: L3 I4.
- Real-world reference: GitLab 2017 production database deletion (extreme version of pattern).
- Existing controls: production / non-production credential separation (sometimes), change approval, backups (point-in-time).
- Residual: L2 I3. Treatment: schema migration tooling with explicit env-name confirmation, blue/green deployment for schema changes, point-in-time recovery validated.

**SC-09 Software supply-chain compromise via NPM package**

A widely used internal NPM dependency is compromised by an attacker who gained maintainer credentials. New version contains data-exfiltration code. Build pipeline picks it up automatically. Code reaches production for two days before discovery.

- Inherent: L2 I4.
- Real-world reference: event-stream 2018, ua-parser-js 2021, Tea/colors.js 2022, SolarWinds 2020 (compiled-binary version).
- Existing controls: dependency pinning (partial), SCA scanning.
- Residual: L2 I3. Treatment: SBOM generation, SCA gating in CI, signed dependencies where possible, dependency-update human review.

### Regulatory and privacy scenarios

**SC-10 GDPR data subject access request mishandled**

A data subject submits a comprehensive SAR via support email. Support team logs it as a normal ticket. It sits in queue for 6 weeks past the 30-day deadline. ICO complaint is lodged. ICO investigation reveals systemic deficiency in DSR handling.

- Inherent: L3 I3.
- Real-world reference: ICO has issued multiple fines for late DSR handling; not headline-making but routinely costly.
- Existing controls: privacy policy (mentions DSR), DPO appointed.
- Residual: L2 I2. Treatment: dedicated DSR intake channel, automated SLA tracking, training for support, monthly DPO review of DSR queue.

**SC-11 Cross-border data transfer compliance failure**

Following Schrems II, the company relied on Standard Contractual Clauses with a US sub-processor. A regulator in Germany determines the US sub-processor's surveillance exposure makes the transfer unlawful regardless of SCCs. Order to suspend transfers. Service disruption.

- Inherent: L2 I3.
- Real-world reference: ongoing Schrems II implications, Meta and Facebook fines, multiple DPAs taking divergent positions.
- Existing controls: SCC in place, TIA performed (Transfer Impact Assessment).
- Residual: L2 I3. Treatment: alternative EU-resident sub-processors mapped, technical safeguards documented, ongoing monitoring of TADPF-style mechanisms.

### Supply chain scenarios

**SC-12 Vendor breach exposes customer data the vendor processed**

A Tier 2 vendor (email-delivery provider) is breached. Attacker exfiltrates email metadata for the prior 18 months including from-to addresses, subject lines, and a sample of attachments. Notification arrives 14 days post-incident, well after the vendor first knew.

- Inherent: L3 I3.
- Real-world reference: Mailchimp 2022/2023, Twilio 2022, multiple SaaS-of-SaaS cascade events.
- Existing controls: vendor classification, contractual breach-notification clause (24-72 hours), CTO-approved vendor.
- Residual: L2 I3. Treatment: tighter contractual SLAs, alternative vendor mapped, customer-notification playbook.

**SC-13 Cloud provider control compromise**

A cloud provider experiences an internal breach where service-team credentials are compromised. Provider rotates all customer credentials and notifies. Limited customer-data exposure but operational disruption while rotating customer-side bindings.

- Inherent: L1 I4.
- Real-world reference: occasional Azure/AWS incidents; rare but high-magnitude. Closer pattern: Microsoft Storm-0558 2023.
- Existing controls: cloud governance, IAM hygiene.
- Residual: L1 I3. Treatment: workload identity rather than long-lived credentials, incident-response runbook for cloud-provider breach, dependency mapping.

### People and insider scenarios

**SC-14 Engineer error exposes secrets in public repository**

An engineer publishes a sample project to their personal public GitHub account containing copied-pasted code that includes a real API key and a database connection string. Bot scanners detect within 90 seconds; key is used to make API calls.

- Inherent: L4 I3.
- Real-world reference: routine; GitGuardian and others publish annual stats showing millions of detected secrets per year.
- Existing controls: pre-commit hooks (partial coverage), training.
- Residual: L3 I2. Treatment: organisation-wide secret scanning, automated secret rotation on detection, restrictions on personal-account use of company code.

**SC-15 Departing executive leaks strategic information**

A C-suite executive who leaves on bad terms gives a journalist details of an unannounced acquisition. Share-price impact follows; regulatory MAR (Market Abuse Regulation) inquiry begins.

- Inherent: L1 I4.
- Real-world reference: numerous high-profile cases.
- Existing controls: NDA, exit interview.
- Residual: L1 I4. Treatment: stricter exit access reduction, MAR-trained executive cohort, comms playbook.

### Emerging technology scenarios

**SC-16 LLM in product hallucinates regulated advice**

The customer-facing LLM-powered assistant gives a customer specific tax advice. Customer follows it; later receives a tax penalty. Class action follows.

- Inherent: L3 I3.
- Real-world reference: Air Canada chatbot 2024 (customer-refund liability); Avianca lawyer 2023 (fictional citations).
- Existing controls: model guardrails (basic), terms of service disclaimer.
- Residual: L2 I3. Treatment: domain-specific guardrails, intent classification, human-in-loop for regulated topics, output filtering.

**SC-17 LLM training data exfiltration via prompt injection**

A malicious customer prompt extracts portions of the training data including embedded internal documents that contain other customer information. Disclosure investigation determines training data segregation was inadequate.

- Inherent: L2 I3.
- Real-world reference: emerging; OWASP LLM Top 10 LLM01 (Prompt Injection) and LLM06 (Sensitive Information Disclosure).
- Existing controls: prompt sanitisation, output filtering.
- Residual: L2 I3. Treatment: training-data segmentation, differential-privacy techniques, prompt-injection red-teaming, customer-data exclusion from training.

### Reputation and brand scenarios

**SC-18 Founder social-media incident**

The founder posts a controversial opinion at 2am that goes viral. Customers cancel; staff resign; press coverage runs for two weeks. No security event but full crisis-response activated.

- Inherent: L3 I3.
- Real-world reference: countless.
- Existing controls: social-media policy.
- Residual: L3 I3. Treatment: founder-coaching, social-media policy enforcement at all levels, crisis-comms readiness.

### Regulatory enforcement scenarios

**SC-19 ICO investigation following customer complaint**

A pattern of complaints about deceptive subscription practices triggers an ICO investigation. Investigation expands to data protection practices generally. Fine and undertakings result.

- Inherent: L2 I3.
- Real-world reference: multiple ICO actions against SaaS companies on dark-pattern subscription flows.
- Existing controls: privacy programme, terms.
- Residual: L1 I3. Treatment: UX review for dark patterns, complaints-process visibility to executive, regulatory-monitoring capability.

**SC-20 Competition authority investigation following M&A**

A planned acquisition triggers extended CMA investigation. Regulatory hold on the transaction lasts 14 months. Strategic plans on hold.

- Inherent: L2 I4.
- Real-world reference: Microsoft / Activision 2022-2023, Adobe / Figma 2022-2023.
- Existing controls: M&A advisory.
- Residual: L2 I4. Treatment: pre-merger competition assessment as part of M&A due diligence.

(The full library contains 40+ scenarios covering security, privacy, operational, financial, AI, climate, geopolitical, and people categories.)

## Components and deliverables

### 1. The scenario library document

Master document containing all scenarios, indexed by category, by likelihood, by impact, and by primary asset. Cross-referenced to the canonical control set from the Control Mapping Matrix.

### 2. Scenario-to-control map

For each scenario, the list of controls that mitigate likelihood, impact, or both. Useful for justifying control investment.

### 3. Tabletop exercise pack

Each scenario has a tabletop version: facilitator guide, injects, expected discussion, success criteria. Used for half-day or full-day exercises.

### 4. Risk-workshop facilitation guide

How to use the library in a workshop: pre-read, scenario short-listing, scoring discipline, output capture.

### 5. Board-briefing extracts

For each high-impact scenario, a one-page board summary: what could happen, what we have done, what we are still doing, what we need.

### 6. New-joiner version

A simplified subset (15-20 scenarios) used for training new staff on what real risks look like.

### 7. Refresh cadence

Annual full review. Scenarios are added, updated, retired based on:
- Real incidents observed in the industry.
- Threat-intelligence changes.
- Regulatory changes.
- Internal incident learnings.
- Emerging-technology adoption.

## Real-world lessons baked into this design

- **Specificity beats generality.** "Phishing leading to compromise" is too vague to act on. "Phishing of finance staff leading to wire fraud" is actionable.
- **Real incidents make scenarios credible.** Citing the Equifax case grounds the scenario; a hypothetical does not.
- **Scenarios travel.** A SaaS-focused library ports cleanly across companies because the threat landscape is shared. The likelihoods change; the scenarios do not.
- **Likelihood is uncertain; rank is not.** Scoring scenarios precisely is harder than ranking them relative to each other. The library is most useful when teams compare and prioritise.
- **Tabletop pays back.** Running a tabletop on a scenario reveals gaps in playbooks, contact lists, decision rights, and language that paper review never finds.

## Common pitfalls

- **Scenario inflation.** 200 scenarios that no one ever uses. Cap at 40-50 actively maintained.
- **Library stagnation.** Built once, never refreshed. Threat landscape moves fast.
- **Disconnected from controls.** Scenarios that do not link to control investment are intellectually interesting but operationally inert.
- **Owner-less scenarios.** Each scenario should map to a function that owns the underlying risk. Otherwise mitigation is everyone's job and so no one's.
- **Overweighting headlines.** Spectacular scenarios crowd out routine risks that statistically cause more loss.

## Audit considerations

- Show me your risk register; show me which scenarios it draws from.
- For one high-residual scenario, show me the controls and the evidence they operate.
- Show me the most recent tabletop exercise output.
- How is the library refreshed? When was it last updated?

## What I have done in this space and what I have not

I have studied DBIR data, MITRE ATT&CK, OWASP, NIST 800-30 threat-event modelling, and reviewed many published incident post-mortems and regulatory enforcement actions in detail.

I have not personally facilitated a board-level tabletop exercise. I have not had to defend a likelihood score against a sceptical CFO. I have not led real-world response on any of the scenarios in the library.

This is a learning portfolio entry.

## Further reading

- **Verizon DBIR (Data Breach Investigations Report)** annual at verizon.com/dbir, free.
- **Verizon VIPDR (Verizon Insider Privacy Data Breach Report)** for insider scenarios.
- **VERIS framework** at veriscommunity.net.
- **MITRE ATT&CK** at attack.mitre.org.
- **CISA Known Exploited Vulnerabilities** at cisa.gov.
- **Black Kite, BitSight, SecurityScorecard** publish industry threat reports (vendor content but useful patterns).
- **OWASP LLM Top 10** at owasp.org for AI scenarios.
- **ENISA Threat Landscape report** (annual) at enisa.europa.eu.
- **NIST SP 800-30 Rev 1** for the threat-event modelling vocabulary.

## Status

Learning portfolio. Library structure complete. Sample scenarios populated; full 40+ scenarios drafted. Not exercised in live workshops or tabletops.
