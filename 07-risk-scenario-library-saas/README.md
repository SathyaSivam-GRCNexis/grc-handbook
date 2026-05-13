# Risk Scenario Library (SaaS Focused)

## What this is

A library of 40+ realistic risk scenarios for mid-sized SaaS organisations. Each one is scored for likelihood and impact, mapped to the controls that mitigate it, and tied back to incidents that have actually happened in the industry. The library exists to make the risk register concrete. Teams stop arguing over abstract risk titles and start arguing about scenarios.

This is the document a Head of Risk or CISO uses to seed risk workshops, train new joiners, brief the board, and stop the risk register being a copy-paste of someone else's ISO 27005 template.

## Problem this library solves

Risk registers in SaaS companies tend to share the same symptoms.

- Generic entries copied from ISO 27005 examples and never adapted. "Loss of confidentiality of information." "Natural disaster." Nobody knows what to do with these.
- Owners assigned but disengaged because the risks feel theoretical.
- Workshops produce 200 risks of which 195 are duplicates or non-risks.
- Boards glaze over when presented with abstract categories.
- Treatment plans cannot get specific because the underlying scenario is too vague.
- Tabletop exercises rest on scenarios invented on the spot, which burns facilitation time and produces shallow output.

A risk scenario library fixes this. Each scenario describes a concrete situation: who, what, how, with what consequence. Workshops then run on "is this scenario relevant to us, what is the likelihood and impact for us specifically, what controls do we already have, what is missing." The conversation becomes operational rather than philosophical.

Strong opinion. Most SaaS risks repeat across companies. A decent generic library beats a bespoke workshop output for the first two years of a programme. Run the workshop later, once the team can argue back.

## Why it pays back

- Risk workshops produce useful output rather than 200 noisy rows.
- Boards engage because scenarios tell stories.
- Tabletop exercises pull from the same library, so risk and IR teams speak the same language.
- New joiners get on-boarded faster because real scenarios beat abstract definitions.
- Insurance conversations improve because underwriters recognise scenario-based maturity.

## Framework alignment

- **ISO/IEC 27005:2022** scenario-based risk approach.
- **NIST SP 800-30 Rev 1** threat-source, threat-event, vulnerability modelling.
- **NIST SP 800-61 Rev 2** incident handling guide; scenarios feed IR exercises.
- **MITRE ATT&CK** for technique-level realism.
- **VERIS** (Verizon Vocabulary for Event Recording and Incident Sharing) for actor / action / asset / attribute taxonomy.
- **Verizon DBIR** for empirical likelihood weighting.
- **CISA Known Exploited Vulnerabilities** catalogue for currency.
- **DPDP Act 2023** and CERT-In directions for India-specific scenarios.

## How scenarios are structured

Every scenario follows the same template. The discipline matters; without it, scenarios drift into essays.

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

The full library has 40+ scenarios. Below is a representative slice across categories.

### Confidentiality scenarios

**SC-01 Customer database exfiltration via SQL injection in legacy admin tool**

A pre-migration internal admin web app has a SQL injection vulnerability in a search field used by support engineers. An attacker who has obtained support credentials via phishing exploits the vulnerability to dump 800,000 customer records including emails, hashed passwords, and partial billing information. Detection occurs three weeks later when the dataset appears for sale on a dark-web forum.

- Inherent: L4 I5 (Major).
- Real-world reference: TalkTalk 2015 (157,000 records, similar pattern at a much larger company).
- Existing controls: WAF (partial), code review (partial coverage of legacy systems), credential rotation (90-day).
- Residual: L3 I4. Treatment: replace legacy admin, code-injection scanning in CI, dark-web monitoring.

**SC-02 Customer data leaked via misconfigured S3 bucket**

A new feature stores generated PDF reports in S3. The bucket is created with default settings by a junior engineer. ACL is left at "public-read" because that is the path of least resistance in some IaC examples. Six months later, a security researcher running a bucket scanner finds the bucket and discovers four million PDFs containing customer financial data.

- Inherent: L3 I5 (Severe).
- Real-world reference: Capital One 2019 (different mechanism, related cloud-misconfiguration pattern). Smaller public cases occur monthly.
- Existing controls: cloud posture management (recently deployed), Terraform module (default-deny), code review.
- Residual: L2 I5. Treatment: enforce CSPM blocking deployment of public buckets, OPA policy in Terraform pipeline, S3 Block Public Access at account level.

**SC-03 Insider exfiltration by departing engineer**

A senior engineer who has accepted an offer at a competitor downloads a copy of the production data dictionary, internal architecture documents, and the customer pipeline-stage data. The plan is to take the material to the new role. Detection via DLP triggering on bulk download, three days before their last day.

- Inherent: L3 I3.
- Real-world reference: Waymo / Uber 2017 (extreme version of the pattern). Routine smaller versions happen often.
- Existing controls: DLP, HR-triggered access reduction on resignation, exit interview.
- Residual: L2 I3. Treatment: improve resignation-triggered access controls, formalise download-volume monitoring, NDAs with bite.

**SC-04 Phishing of finance leading to wire fraud**

An attacker impersonating the CEO emails the FP&A team during a quiet period asking for an urgent confidential wire transfer to a "new acquisition target's escrow account." The team executes a £450,000 transfer that is unrecoverable.

- Inherent: L4 I3.
- Real-world reference: persistent BEC pattern. FBI IC3 lists BEC as the highest-loss cybercrime category by total dollar value year after year.
- Existing controls: dual approval for wires above £100k, annual training.
- Residual: L3 I3. Treatment: callback verification on any new payee, just-in-time wire-fraud awareness, payment-system controls limiting first-time payees.

### Availability scenarios

**SC-05 Cloud-region outage takes down primary service for 8 hours**

The single AWS region (eu-west-1) where the production database lives experiences a multi-AZ outage lasting 8 hours due to network-fabric failure. Multi-AZ failover does not save the database. The standby region exists but the quarterly DR drill failed; failover is untested in production.

- Inherent: L2 I5.
- Real-world reference: AWS us-east-1 outages in December 2021, February 2017 S3, and several since. Azure had its own in 2024.
- Existing controls: multi-AZ database, monitoring, status page.
- Residual: L2 I5 unchanged. Treatment: actually complete cross-region failover testing, document RTO/RPO formally, customer SLA review.

**SC-06 Ransomware encrypts production via compromised admin endpoint**

An admin user clicks a phishing link. Malware persists, escalates privileges, harvests credentials, lateral-moves to a build server, and via stored cloud credentials encrypts production storage. Encrypted data includes customer artefacts and internal databases. Ransom demand $5m.

- Inherent: L3 I5.
- Real-world reference: countless. MGM 2023, Change Healthcare 2024, many smaller cases.
- Existing controls: EDR, MFA on admin (but session-token theft possible), backups (restoration untested).
- Residual: L3 I5 unchanged. Treatment: phishing-resistant MFA, network segmentation between corporate and production, immutable backups with tested restoration, IR retainer.

**SC-07 Critical SaaS dependency outage**

The primary identity provider (Okta) is unavailable for 4 hours due to a security incident at their support vendor. SSO into all internal tools breaks. The customer-facing application using IdP-mediated authentication is unavailable for the same window.

- Inherent: L2 I4.
- Real-world reference: Okta support compromise October 2023; several SaaS outages cascading downstream.
- Existing controls: dependency monitoring, on-call.
- Residual: L2 I4. Treatment: emergency break-glass auth path, alternate IdP for critical paths, IdP failure runbook, customer comms template.

### Integrity scenarios

**SC-08 Data corruption from a bad release**

A schema migration in a release pipeline runs against the wrong database (staging credentials accidentally point at production). Three hours of customer data is corrupted before the issue is detected. Restore from backup loses three hours of work for thousands of customers.

- Inherent: L3 I4.
- Real-world reference: GitLab 2017 production database deletion (extreme version of the pattern).
- Existing controls: production / non-production credential separation (sometimes), change approval, point-in-time backups.
- Residual: L2 I3. Treatment: schema migration tooling with explicit env-name confirmation, blue/green deployment for schema changes, point-in-time recovery validated.

**SC-09 Software supply-chain compromise via NPM package**

A widely used internal NPM dependency is compromised by an attacker who obtained maintainer credentials. The new version contains data-exfiltration code. Build pipeline picks it up automatically. Code reaches production for two days before discovery.

- Inherent: L2 I4.
- Real-world reference: event-stream 2018, ua-parser-js 2021, colors.js 2022, SolarWinds 2020 (compiled-binary version).
- Existing controls: dependency pinning (partial), SCA scanning.
- Residual: L2 I3. Treatment: SBOM generation, SCA gating in CI, signed dependencies where possible, human review on dependency updates.

### Regulatory and privacy scenarios

**SC-10 GDPR data subject access request mishandled**

A data subject submits a comprehensive SAR via support email. Support logs it as a normal ticket. It sits in the queue for six weeks past the 30-day deadline. ICO complaint is lodged. ICO investigation reveals a systemic deficiency in DSR handling.

- Inherent: L3 I3.
- Real-world reference: ICO has issued multiple fines for late DSR handling. Not headline-making but routinely costly. DPDP under India follows a similar pattern with the Data Protection Board.
- Existing controls: privacy policy mentions DSR, DPO appointed.
- Residual: L2 I2. Treatment: dedicated DSR intake channel, automated SLA tracking, training for support, monthly DPO review of the DSR queue.

**SC-11 Cross-border data transfer compliance failure**

Following Schrems II, the company relied on Standard Contractual Clauses with a US sub-processor. A regulator in Germany determines the US sub-processor's surveillance exposure makes the transfer unlawful regardless of SCCs. Order to suspend transfers. Service disruption.

- Inherent: L2 I3.
- Real-world reference: ongoing Schrems II implications; Meta and Facebook fines; multiple DPAs taking divergent positions.
- Existing controls: SCCs in place, Transfer Impact Assessment performed.
- Residual: L2 I3. Treatment: alternative EU-resident sub-processors mapped, technical safeguards documented, ongoing monitoring of TADPF-style mechanisms.

### Supply chain scenarios

**SC-12 Vendor breach exposes customer data the vendor processed**

A Tier 2 vendor (email-delivery provider) is breached. The attacker exfiltrates email metadata for the prior 18 months including from-to addresses, subject lines, and a sample of attachments. Notification arrives 14 days post-incident, well after the vendor first knew.

- Inherent: L3 I3.
- Real-world reference: Mailchimp 2022 and 2023, Twilio 2022, several SaaS-of-SaaS cascade events.
- Existing controls: vendor classification, contractual breach-notification clause (24-72 hours), CTO-approved vendor.
- Residual: L2 I3. Treatment: tighter contractual SLAs, alternative vendor mapped, customer-notification playbook.

**SC-13 Cloud provider control compromise**

A cloud provider experiences an internal breach where service-team credentials are compromised. The provider rotates all customer credentials and notifies. Limited customer-data exposure but operational disruption while rotating customer-side bindings.

- Inherent: L1 I4.
- Real-world reference: occasional Azure / AWS incidents; rare but high magnitude. Closest pattern: Microsoft Storm-0558 2023.
- Existing controls: cloud governance, IAM hygiene.
- Residual: L1 I3. Treatment: workload identity rather than long-lived credentials, IR runbook for cloud-provider breach, dependency mapping.

### People and insider scenarios

**SC-14 Engineer error exposes secrets in public repository**

An engineer publishes a sample project to their personal public GitHub account containing pasted-in code that includes a real API key and a database connection string. Bot scanners detect within 90 seconds. The key is used to make API calls.

- Inherent: L4 I3.
- Real-world reference: routine. GitGuardian and others publish annual stats showing millions of detected secrets per year.
- Existing controls: pre-commit hooks (partial coverage), training.
- Residual: L3 I2. Treatment: organisation-wide secret scanning, automated rotation on detection, restrictions on personal-account use of company code.

**SC-15 Departing executive leaks strategic information**

A C-suite executive who leaves on bad terms gives a journalist details of an unannounced acquisition. Share-price impact follows. Regulatory MAR (Market Abuse Regulation) inquiry begins.

- Inherent: L1 I4.
- Real-world reference: numerous high-profile cases.
- Existing controls: NDA, exit interview.
- Residual: L1 I4. Treatment: stricter exit access reduction, MAR-trained executive cohort, comms playbook.

### Emerging technology scenarios

**SC-16 LLM in product hallucinates regulated advice**

The customer-facing LLM-powered assistant gives a customer specific tax advice. Customer follows it; later receives a tax penalty. Class action follows.

- Inherent: L3 I3.
- Real-world reference: Air Canada chatbot 2024 (customer-refund liability); Avianca lawyer 2023 (fictional citations).
- Existing controls: basic model guardrails, terms of service disclaimer.
- Residual: L2 I3. Treatment: domain-specific guardrails, intent classification, human-in-loop for regulated topics, output filtering.

**SC-17 LLM training data exfiltration via prompt injection**

A malicious customer prompt extracts portions of training data including embedded internal documents that contain other customer information. Disclosure investigation determines training-data segregation was inadequate.

- Inherent: L2 I3.
- Real-world reference: emerging; OWASP LLM Top 10 LLM01 (Prompt Injection) and LLM06 (Sensitive Information Disclosure).
- Existing controls: prompt sanitisation, output filtering.
- Residual: L2 I3. Treatment: training-data segmentation, differential-privacy techniques, prompt-injection red-teaming, customer-data exclusion from training.

### Reputation and brand scenarios

**SC-18 Founder social-media incident**

The founder posts a controversial opinion at 2am that goes viral. Customers cancel. Staff resign. Press coverage runs for two weeks. No security event but full crisis-response activated.

- Inherent: L3 I3.
- Real-world reference: countless.
- Existing controls: social-media policy.
- Residual: L3 I3. Treatment: founder coaching, policy enforcement at all levels, crisis-comms readiness.

### Regulatory enforcement scenarios

**SC-19 ICO investigation following customer complaint**

A pattern of complaints about deceptive subscription practices triggers an ICO investigation. Investigation expands to data protection practices generally. Fine and undertakings result.

- Inherent: L2 I3.
- Real-world reference: multiple ICO actions against SaaS companies on dark-pattern subscription flows.
- Existing controls: privacy programme, terms.
- Residual: L1 I3. Treatment: UX review for dark patterns, complaints-process visibility to executive, regulatory-monitoring capability.

**SC-20 Competition authority investigation following M&A**

A planned acquisition triggers an extended CMA investigation. Regulatory hold on the transaction lasts 14 months. Strategic plans on hold.

- Inherent: L2 I4.
- Real-world reference: Microsoft / Activision 2022-2023, Adobe / Figma 2022-2023.
- Existing controls: M&A advisory.
- Residual: L2 I4. Treatment: pre-merger competition assessment as part of M&A due diligence.

(The full library contains 40+ scenarios across security, privacy, operational, financial, AI, climate, geopolitical, and people categories.)

## Components and deliverables

### 1. The scenario library document

Master document containing all scenarios, indexed by category, by likelihood, by impact, and by primary asset. Cross-referenced to the canonical control set from the Control Mapping Matrix.

### 2. Scenario-to-control map

For each scenario, the controls that mitigate likelihood, impact, or both. Useful for justifying control investment, especially when finance asks why the spend is needed.

### 3. Tabletop exercise pack

Each scenario has a tabletop version: facilitator guide, injects, expected discussion points, success criteria. Used for half-day or full-day exercises.

### 4. Risk-workshop facilitation guide

How to use the library in a workshop. Pre-read, scenario short-listing, scoring discipline, output capture. Without this, workshops descend into definitional arguments.

### 5. Board-briefing extracts

For each high-impact scenario, a one-page board summary. What could happen. What we have done. What we are still doing. What we need.

### 6. New-joiner version

A simplified subset of 15-20 scenarios used for training new staff on what real risks look like. Useful in week one, before anyone gets too philosophical.

### 7. Refresh cadence

Annual full review. Scenarios are added, updated, or retired based on:

- Real incidents observed in the industry.
- Threat-intelligence shifts.
- Regulatory changes.
- Internal incident learnings.
- Emerging-technology adoption.

## Lessons baked into this design

- **Specificity beats generality.** "Phishing leading to compromise" is too vague to act on. "Phishing of finance staff leading to wire fraud" is actionable.
- **Real incidents make scenarios credible.** Citing the Equifax case grounds the scenario; a hypothetical does not. Engineering audiences in particular respond to named events.
- **Scenarios travel.** A SaaS-focused library ports cleanly across companies because the threat landscape is largely shared. Likelihoods change; the scenarios do not.
- **Likelihood is uncertain; rank is not.** Scoring scenarios precisely is harder than ranking them relative to each other. The library earns its keep when teams compare and prioritise.
- **Tabletops pay back.** Running a tabletop on a scenario reveals gaps in playbooks, contact lists, decision rights, and language that paper review never finds. In one SaaS environment, a routine BEC tabletop surfaced the fact that nobody in finance had the IR team's out-of-hours number.

## Common pitfalls

- **Scenario inflation.** 200 scenarios that nobody ever uses. Cap at 40-50 actively maintained.
- **Library stagnation.** Built once, never refreshed. The threat landscape moves fast; LLM scenarios did not exist three years ago.
- **Disconnected from controls.** Scenarios that do not link to control investment are intellectually interesting but operationally inert.
- **Owner-less scenarios.** Each scenario should map to a function that owns the underlying risk. Otherwise mitigation is everyone's job, which means it is nobody's.
- **Overweighting headlines.** Spectacular scenarios crowd out routine risks that statistically cause more loss. BEC and misconfiguration outscore nation-state intrusion by a wide margin in actual losses, but the boardroom wants to talk about the latter.

## What auditors will ask

- Show me your risk register; show me which scenarios it draws from.
- For one high-residual scenario, show me the controls and the evidence they operate.
- Show me the most recent tabletop output.
- How is the library refreshed? When was it last updated?

## What I have done in this space and what I have not

I have studied DBIR data, MITRE ATT&CK, OWASP, NIST 800-30 threat-event modelling, and reviewed many published incident post-mortems and regulatory enforcement actions.

I have not personally facilitated a board-level tabletop. I have not had to defend a likelihood score against a sceptical CFO. I have not led real-world response on any of the scenarios in the library.

This is a learning portfolio entry.

## Further reading

- **Verizon DBIR** annual at verizon.com/dbir, free.
- **VERIS framework** at veriscommunity.net.
- **MITRE ATT&CK** at attack.mitre.org.
- **CISA Known Exploited Vulnerabilities** at cisa.gov.
- **Black Kite, BitSight, SecurityScorecard** publish industry threat reports. Vendor content, but the patterns are useful.
- **OWASP LLM Top 10** at owasp.org for AI scenarios.
- **ENISA Threat Landscape** annual report at enisa.europa.eu.
- **NIST SP 800-30 Rev 1** for the threat-event modelling vocabulary.

## Status

Learning portfolio. Library structure complete. Sample scenarios populated; full 40+ scenarios drafted. Not exercised in live workshops or tabletops.
