# GRC & Security Tech Curriculum

A six-month, week-by-week study plan covering every standard, regulation, framework, and technology referenced across the tech and non-tech projects in this portfolio. Designed to be done in two to three focused hours per evening or roughly ten to fifteen hours per week. Every resource is free unless explicitly marked.

The aim is for you to be able to defend any topic in this portfolio in conversation with a peer, recruiter, or interviewer. Not to make you a deep specialist in all of them; that is a multi-year journey. To make you fluent.

## How to use this curriculum

1. **Read top to bottom in order.** Topics build on each other. Skipping the foundations means re-doing them later.
2. **Take notes in your own words.** Reading is not learning. Writing is. After each major topic, write a one-paragraph summary in your own words. If you cannot, you have not understood it.
3. **Build the artefact at the end of each week.** Most weeks have a "do this" exercise. The exercise locks in the learning. Skip the exercises and the curriculum becomes information consumption.
4. **Test yourself weekly.** End-of-week self-check questions. Honest answers. Where you fail, re-read.
5. **Revisit your portfolio repos as you learn.** As topics become clear, you will spot things in your repos that look wrong or could be sharpened. Edit them. The repos become genuinely yours over time.
6. **Don't memorise. Understand.** Standards have thousands of details. Memorising them is pointless and impossible. Understanding what they exist for, what they require, and how to look up the rest is what you need.

## Time budget

| Effort level | Hours / week | Time to complete |
|---|---|---|
| Light (job + family) | 5-7 | 9-12 months |
| Standard | 10-15 | 6 months |
| Intensive (career change focus) | 20-25 | 3-4 months |

This document assumes the standard 6-month plan. Adjust accordingly.

---

# MONTH 1: FOUNDATIONS

You cannot understand any of the specific standards or technologies in your portfolio until you understand what risk, control, audit, and management systems are. Month 1 is the bedrock. Resist the temptation to skip ahead.

## Week 1: What is GRC actually?

**Concepts to learn**

- What governance, risk management, and compliance each mean and how they relate.
- The Three Lines model: who does what, who oversees what, who audits what.
- Why GRC exists: protecting value, enabling decisions, satisfying obligations.
- The difference between management systems and controls.
- The compliance fatigue problem and why it matters.

**Free resources**

- **The Institute of Internal Auditors: The Three Lines Model (2020).** Free PDF at theiia.org. 7 pages. Read it twice.
- **OCEG (Open Compliance and Ethics Group): GRC Capability Model "Red Book"** summary at oceg.org. Membership-walled but the executive summary is free and explains the principled-performance approach.
- **NIST SP 800-39: Managing Information Security Risk.** Free at csrc.nist.gov. Read chapters 1 and 2 only.
- **CISA's "Cybersecurity Risk Management" overview** at cisa.gov. Short, free, accurate.

**Do this**

In your own words, write a one-page note answering: "What is GRC and why does it exist in modern organisations?" Include the Three Lines model in your explanation. Aim for plain English, no jargon.

**Self-check questions**

- Can you explain the Three Lines model to a non-technical friend?
- What is the difference between governance and management?
- Why are second-line and third-line functions kept independent of first-line?
- What happens to a company that has no risk management function?

## Week 2: Risk fundamentals

**Concepts to learn**

- Inherent vs residual risk.
- Likelihood and impact, and why both must be defined precisely.
- Risk appetite and risk tolerance.
- Risk treatment options: mitigate, transfer, avoid, accept.
- The risk register: what it is, what it should not be.
- Quantitative vs qualitative risk approaches.

**Free resources**

- **NIST SP 800-30 Rev 1: Guide for Conducting Risk Assessments.** Free PDF at csrc.nist.gov. Read all of it; about 100 pages but readable.
- **ISO 31000:2018 overview** at iso.org/iso-31000-risk-management.html (free overview of the paid standard).
- **The IRM (Institute of Risk Management) free resources** at theirm.org, especially their "Risk appetite and tolerance" guidance paper.
- **The FAIR Institute's "Open FAIR" introduction** at fairinstitute.org. Free intro materials. Excellent on quantitative risk.
- **Hubbard Decision Research blog posts** at hubbardresearch.com. Free. Sceptical, intelligent.

**Do this**

Take ten things that worry you in your personal or professional life. Score them with a 1-5 likelihood and 1-5 impact. Reorder by score. Notice which scoring decisions felt arbitrary. That arbitrariness is exactly what risk methodologies attempt to constrain.

**Self-check questions**

- What does it mean for a residual risk to be "outside appetite"?
- Why are accepted risks reviewed periodically?
- When is qualitative scoring (low / medium / high) better than quantitative ($M loss expectancy)?
- Why do treatment plans need owners and dates?

## Week 3: Controls fundamentals

**Concepts to learn**

- What a control is. Preventive, detective, corrective, deterrent, compensating.
- Control objectives vs control activities.
- Control design vs control operation.
- Key controls vs supporting controls.
- Sampling and population testing.
- Why "control testing" exists.

**Free resources**

- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov. Don't read all 1000+ pages. Read the first 30 pages on structure and terminology. Then browse the AC, AU, CA, CM, IA, RA, SI families to see how controls are written.
- **NIST SP 800-53A Rev 5: Assessment Procedures.** Free PDF. Read the introduction to understand how controls are tested.
- **AICPA Trust Services Criteria and Description Criteria (DC 200) for SOC 2.** Free at aicpa-cima.com. Read the Common Criteria (CC1-CC9). About 50 pages of dense material; stay with it.
- **CIS Controls v8.1 documentation.** Free at cisecurity.org. Read the introduction and the first three controls in detail.

**Do this**

Pick one of your daily activities (e.g. logging into your laptop). Identify the controls involved. Categorise each as preventive, detective, or corrective. Identify the control owner. Then identify how an auditor would test that the control operates.

**Self-check questions**

- What is the difference between a control objective and a control activity?
- Why is design effectiveness tested separately from operating effectiveness?
- What is a key control?
- Why is a self-tested control weaker evidence than an independently tested control?

## Week 4: Audit fundamentals

**Concepts to learn**

- What an audit is and is not. Audit vs assessment vs review.
- First-party (internal), second-party (customer), third-party (independent) audits.
- The audit lifecycle: planning, fieldwork, reporting.
- Sampling.
- Findings: nonconformity, observation, opportunity for improvement.
- The Provided By Client (PBC) list.
- Materiality, professional scepticism, evidence sufficiency.

**Free resources**

- **ISO 19011:2018 overview** at iso.org. Paid in full, free overview. Read the overview.
- **AICPA's "What is a SOC 2 Report" overview** at aicpa-cima.com.
- **CISA Cybersecurity Audit Resources** at cisa.gov.
- **The IIA's "International Professional Practices Framework" overview** at theiia.org. Members-only in full, free at the descriptive level.
- **Big Four published methodology overviews:** PwC, KPMG, EY, Deloitte SOC 2 readiness guides. Search for them; treat as marketing-but-useful.

**Do this**

Read a publicly available SOC 2 Type 2 report from a SaaS company (many companies publish redacted versions to their trust centres). Identify the structure: management assertion, auditor opinion, control descriptions, test procedures, results. Note any exceptions. This is what your portfolio claims your future companies would deliver.

**Self-check questions**

- What is the difference between a SOC 2 Type 1 and Type 2?
- What does "in all material respects" mean in an audit opinion?
- Why are auditors required to be independent?
- What is professional scepticism and why does it matter?

---

# MONTH 2: CORE FRAMEWORKS

You now have the foundations. Time to learn the major frameworks your portfolio references repeatedly.

## Week 5: ISO 27001 and ISO 27002

**Concepts to learn**

- What ISO 27001 is and what certification means.
- The structure: clauses 4-10 (the management system) and Annex A (the controls).
- The 2022 revision: 93 controls in 4 themes (was 114 in 14 in 2013).
- The Statement of Applicability (SoA): the most important single document.
- Risk-based approach: clause 6.1.
- Continual improvement: clauses 9 and 10.
- The certification cycle: Stage 1, Stage 2, surveillance, recertification.

**Free resources**

- **ISO 27001:2022 official overview** at iso.org. Free.
- **BSI Group's free ISO 27001:2022 transition guides** at bsigroup.com. Excellent.
- **IT Governance UK blog posts on the 2022 revision** at itgovernance.co.uk. Free, accurate, opinionated.
- **The ISMS.online and Vanta blogs on ISO 27001.** Vendor content, but the explanatory parts are free and useful.
- **AdvisorPedia ISO 27001 free articles** at advisorpedia.com.
- **Annex A Controls Reference Card** (search "ISO 27001:2022 Annex A reference card pdf"). Free downloadable summaries from multiple consultancies.

**Paid but worth it (optional)**

- **The standard itself.** ISO 27001:2022 and ISO 27002:2022 from your national standards body (BSI in the UK). Around £150 each. If you can afford the investment, do it. The summaries are good but the standard is the source of truth.

**Do this**

Take your fictional portfolio company. Write a one-page Statement of Applicability covering 10 of the 93 Annex A controls: 5 included with one-line implementation reference, 5 excluded with one-line justification. This is the exact document an ISO 27001 auditor opens first.

**Self-check questions**

- What are the 4 themes of Annex A in ISO 27001:2022?
- Why is the SoA the most important document?
- What is the difference between a clause and a control?
- What does it mean for an organisation to be "certified to ISO 27001"? Who certifies?
- What is the difference between a major nonconformity and a minor nonconformity?

## Week 6: SOC 2 and the AICPA Trust Services Criteria

**Concepts to learn**

- What SOC 2 is, who issues it (AICPA, US-based), and how it differs from ISO 27001.
- SOC 1 vs SOC 2 vs SOC 3.
- Type 1 (point in time) vs Type 2 (period of operation).
- The Trust Services Criteria categories: Security (Common Criteria), Availability, Processing Integrity, Confidentiality, Privacy.
- The 2017 criteria revised in 2022 update.
- The SSAE 18 attestation standard underlying SOC 2.
- How auditor's opinions are written and what they mean.

**Free resources**

- **AICPA SOC 2 resource page** at aicpa-cima.com. Includes the Trust Services Criteria PDF for free.
- **AICPA "SOC 2 Reporting Resource Centre."** Free.
- **A real-world SOC 2 Type 2 report.** Search for any major SaaS company's trust centre (Datadog, Atlassian, Snowflake, Notion all publish or share on request).
- **"SOC 2 Compliance Handbook" content from Vanta and Drata.** Vendor content; treat with healthy scepticism but the explanatory parts are accurate.
- **Schellman, A-LIGN, Sensiba San Filippo** publish free SOC 2 readiness guides as marketing.

**Do this**

Map five Common Criteria (e.g. CC6.1, CC6.6, CC7.1, CC7.4, CC9.2) to specific real controls you would expect to find in a SaaS company. For each, note what evidence the auditor would expect.

**Self-check questions**

- What is the difference between SOC 2 Type 1 and Type 2?
- What are the five Trust Services categories?
- Which is mandatory? Which are optional?
- What does an "unqualified opinion" mean?
- What happens if a SOC 2 audit identifies an exception?

## Week 7: NIST CSF 2.0 and NIST 800-53

**Concepts to learn**

- NIST Cybersecurity Framework 2.0 (released February 2024). The new GOVERN function. The other five: IDENTIFY, PROTECT, DETECT, RESPOND, RECOVER.
- Functions, categories, subcategories.
- Implementation Tiers (1-4).
- Profiles (current vs target).
- NIST SP 800-53 Rev 5: control families, control enhancements, baselines.
- The relationship between CSF and 800-53 (CSF is outcome-oriented; 800-53 is control-oriented).
- Where 800-53 is mandatory (US federal systems) and where it is reference (everywhere else).

**Free resources**

- **NIST CSF 2.0 official site** at nist.gov/cyberframework. All resources free. Download the framework PDF, the Implementation Examples, the Quick Start Guides, and the informative references mapping CSF to 800-53.
- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov.
- **NIST SP 800-53B (control baselines).** Free PDF.
- **CISA's CSF 2.0 implementation resources** at cisa.gov.
- **NIST CSF 2.0 Reference Tool** at nist.gov/cyberframework/csf-tool. Excellent way to explore.

**Do this**

Pick five subcategories from NIST CSF 2.0 (one from each function except GOVERN; pick two from GOVERN). For each, write what your fictional company does today, what gaps exist, and what target state would look like. This is exactly how CSF Profiles are built.

**Self-check questions**

- What are the six NIST CSF 2.0 functions?
- Why was GOVERN added in 2.0?
- What is the difference between a Tier and a Profile?
- How does NIST CSF map to NIST 800-53?
- When would an organisation use CSF instead of 800-53 directly?

## Week 8: GDPR and privacy fundamentals

**Concepts to learn**

- The structure of GDPR: 99 articles plus 173 recitals.
- Key articles: 5 (principles), 6 (lawful basis), 7 (consent), 9 (special categories), 12-22 (data subject rights), 24-25 (controller responsibilities), 28 (processors), 30 (records), 32 (security), 33-34 (breach notification), 35 (DPIA).
- Controller vs processor.
- Lawful bases for processing.
- Data subject rights (access, rectification, erasure, restriction, portability, objection).
- The 72-hour notification clock.
- Cross-border transfers: SCCs, BCRs, adequacy decisions, the Schrems II saga.
- ICO (UK) vs EDPB (EU) and individual DPAs.
- Fines and enforcement.

**Free resources**

- **The full GDPR text** at gdpr-info.eu. Free, fully searchable, with recitals.
- **ICO Guide to GDPR** at ico.org.uk. Free, comprehensive, plain English.
- **EDPB Guidelines** at edpb.europa.eu. All guidelines free. Read at minimum: 9/2022 on breach notification, 7/2020 on processors, 4/2019 on Article 25 (data protection by design).
- **CNIL (France) guidance** at cnil.fr. Often clearer than the English-language equivalents.
- **Future of Privacy Forum** at fpf.org. Free analysis.
- **IAPP daily newsletter** at iapp.org. Free; sign up. The single best way to track privacy developments.

**Do this**

Pretend a customer has emailed asking for a copy of all their personal data, deletion of their account, and confirmation of all sub-processors. Walk through what your organisation would need to do for each, with timelines and evidence requirements. Write it as a one-page response.

**Self-check questions**

- Name the six lawful bases for processing under Article 6.
- What is the difference between controller and processor responsibilities?
- When does the 72-hour breach notification clock start?
- What is a DPIA and when is it required?
- What was Schrems II and why does it matter?
- What is the maximum GDPR fine?

---

# MONTH 3: REGULATIONS YOU MENTION

The portfolio references several specific regulations you flagged as unfamiliar. Time to learn them.

## Week 9: FedRAMP

**Concepts to learn**

- What FedRAMP is: the US federal cloud security authorisation programme.
- Why it exists: federal agencies cannot use cloud services without FedRAMP authorisation.
- Authorisation levels: Low, Moderate, High.
- The two authorisation paths: JAB (Joint Authorisation Board) Provisional ATO and Agency ATO.
- The 3PAO (Third Party Assessment Organisation) role.
- The POAM (Plan of Action and Milestones): a structured spreadsheet of open findings, owners, target dates, and compensating controls. Updated monthly.
- Continuous monitoring: monthly vulnerability scans, monthly POAM updates, annual assessments.
- StateRAMP (state-level equivalent).
- FedRAMP 20x (the 2024+ modernisation initiative).

**Free resources**

- **FedRAMP official site** at fedramp.gov. All templates and guides free.
- **The FedRAMP POAM template** at fedramp.gov/documents-templates. Download and look at it. It is just a structured spreadsheet.
- **The FedRAMP Continuous Monitoring Strategy Guide.** Free PDF.
- **FedRAMP Authorisation Boundary Guidance.** Free PDF.
- **NIST SP 800-37 Rev 2 (RMF).** Free PDF. FedRAMP is built on the RMF.
- **Schellman, A-LIGN, Coalfire** publish free FedRAMP overview content as marketing.

**Do this**

Download the FedRAMP POAM template. Populate three example rows for fictional findings (one Critical, one Moderate, one Low). Set a deadline based on FedRAMP's defined remediation timelines (Critical: 30 days, High: 30 days, Moderate: 90 days, Low: 180 days). This makes the POAM concrete.

**Self-check questions**

- What is a POAM?
- How often is the POAM updated?
- What are the three FedRAMP impact levels?
- What is the difference between JAB and Agency ATO?
- What is a 3PAO?
- Why does FedRAMP demand monthly continuous monitoring?

## Week 10: DORA (Digital Operational Resilience Act)

**Concepts to learn**

- What DORA is: EU regulation 2022/2554. Applies to financial entities and their critical ICT third parties from 17 January 2025.
- Five pillars: ICT risk management (Art 5-16), ICT-related incident management and reporting (Art 17-23), digital operational resilience testing (Art 24-27), ICT third-party risk management (Art 28-30), information sharing (Art 45).
- ICT incident classification and reporting: initial notification within 4 hours of classification, intermediate within 72 hours, final within one month.
- Threat-led penetration testing (TLPT) every 3 years for significant entities.
- The ICT third-party register of information.
- Critical ICT third-party providers (CTPPs) directly supervised by ESAs.
- Subcontracting transparency requirements.

**Free resources**

- **The full DORA text (Regulation EU 2022/2554)** at eur-lex.europa.eu. Free.
- **ESMA, EBA, EIOPA joint guidance and RTS** at esma.europa.eu, eba.europa.eu, eiopa.europa.eu. Free.
- **The Bank of England DORA implementation summary** at bankofengland.co.uk. Free.
- **ENISA DORA explainer materials** at enisa.europa.eu. Free.
- **TIBER-EU framework** (precursor to TLPT under DORA) at ecb.europa.eu. Free.
- **Numerous law firm explainers** (Linklaters, Clifford Chance, Hogan Lovells) all publish free DORA primers.

**Do this**

Take Article 17-23 of DORA. Write a one-page summary in plain English of what an ICT incident reporting workflow must do under DORA: who, what, when, to whom. This is a working brief you could hand to an engineer.

**Self-check questions**

- Who does DORA apply to?
- When did it become applicable?
- What is the timeline for incident reporting?
- What is TLPT and how often is it required?
- What is a CTPP and how is it supervised?

## Week 11: PCI DSS v4.0

**Concepts to learn**

- What PCI DSS is: a contractual standard issued by the PCI Security Standards Council, mandatory for any entity handling payment card data.
- The 12 requirements at the top level, and the ~400 detailed requirements beneath.
- Compliance vs validation: large merchants and service providers undergo annual QSA (Qualified Security Assessor) assessment; smaller merchants self-assess via SAQs.
- Cardholder data environment (CDE) and scope reduction techniques (tokenisation, network segmentation).
- The transition from v3.2.1 to v4.0 (March 2022) and the future-dated requirements that became mandatory 31 March 2025.
- Customised approach (new in v4.0): enables alternative implementations meeting the security objective.
- Specific requirements you mention in your portfolio: 6.3.3 (patching critical CVEs within one month), 11.4 (penetration testing), 11.5 (intrusion detection and change monitoring), 12.10 (incident response).

**Free resources**

- **PCI DSS v4.0.1 official document** at pcisecuritystandards.org. Free download. Read at minimum: introduction, Requirements 6, 8, 10, 11, 12.
- **PCI SSC FAQ database** at pcisecuritystandards.org. Free, searchable.
- **PCI DSS v4 Self-Assessment Questionnaires (SAQs)** at pcisecuritystandards.org. Free. The SAQ-D (full SAQ) is illuminating to skim.
- **TrustWave, Coalfire, A-LIGN, ControlScope** publish free PCI v4 transition guides.
- **PCI Compliance and Validation Tracker** posts on Reddit r/payments often have practical perspectives.

**Do this**

For Requirement 6.3.3 (patching critical CVEs within one month), describe what a SaaS company processing payments would actually need to do: vulnerability scanning, identification, prioritisation by CVSS, patch deployment, evidence retention. Map this to your existing canonical control set.

**Self-check questions**

- Who is required to comply with PCI DSS?
- What is the difference between Requirement 11.4.1 and 11.4.5?
- What does the customised approach enable?
- What is a QSA and when is one required?
- What evidence is required for Requirement 6.3.3 compliance?

## Week 12: HIPAA, NIS2, and other regimes worth knowing

**Concepts to learn**

- **HIPAA Privacy Rule** (45 CFR § 164.500): patient health information protections.
- **HIPAA Security Rule** (45 CFR §§ 164.302-318): administrative, physical, technical safeguards for PHI in electronic form.
- **HIPAA Breach Notification Rule** (45 CFR §§ 164.400-414): notification thresholds and timelines.
- **NIS2** (Directive (EU) 2022/2555): EU cybersecurity directive applying to "essential" and "important" entities. Article 21 cybersecurity risk management measures, Article 23 incident reporting.
- **The UK Cyber Resilience Bill** (in development) as the UK's NIS2 equivalent.
- **The SEC Cybersecurity Disclosure Rule** (17 CFR § 229.106): material cyber incidents at registrants must be disclosed within 4 business days.
- **Singapore IM8, Australia Essential Eight, India DPDP Act** as examples of national regimes practitioners encounter.

**Free resources**

- **HHS HIPAA resources** at hhs.gov/hipaa. Free, comprehensive.
- **NIS2 Directive text** at eur-lex.europa.eu. Free.
- **ENISA NIS2 guidance** at enisa.europa.eu. Free.
- **NCSC UK guidance on cyber resilience** at ncsc.gov.uk. Free.
- **SEC final rule release on cybersecurity disclosure** at sec.gov. Free PDF.
- **IAPP's regulator tracker.** Free portion of iapp.org.

**Do this**

Pick one regime you are unlikely to encounter (e.g. HIPAA if you are UK-based) and one you might (NIS2 if you are EU/UK-based). For each, write a one-paragraph summary of the basic obligations. Then for the regime you might encounter, identify three things your fictional SaaS company would need to do.

**Self-check questions**

- What is PHI?
- What is the difference between an essential entity and an important entity under NIS2?
- What is the SEC's 4-business-day disclosure rule?
- How are HIPAA breach notifications timed?

---

# MONTH 4: TECHNOLOGIES AND TOOLS

You now know the regulations. Time for the technologies you mention in your portfolio.

## Week 13: Open Policy Agent (OPA) and Rego

**Concepts to learn**

- What OPA is: a general-purpose policy engine. Used everywhere in cloud-native, Kubernetes, infrastructure, application authorisation, and CI/CD pipelines.
- Rego: OPA's declarative query language.
- Policy as Code: the principle that authorisation, compliance, and admission decisions should be expressed in version-controlled, testable code.
- OPA vs Gatekeeper (Gatekeeper is OPA wrapped for Kubernetes admission).
- OPA vs Cedar (AWS's policy language; different design choices).
- Decision logs and how OPA fits into a Policy Decision Point / Policy Enforcement Point architecture.

**Free resources**

- **OPA official documentation** at openpolicyagent.org/docs. Read the introduction and the Rego primer.
- **The OPA Playground** at play.openpolicyagent.org. Browser-based; write Rego without installing anything.
- **Styra Academy** at academy.styra.com. Free courses on OPA and Rego. Excellent.
- **The Rego language reference** at openpolicyagent.org/docs/policy-language.

**Do this**

Spend an afternoon writing five Rego policies in the Playground. Suggested:

1. Deny if a Kubernetes pod runs as root.
2. Allow if a user is in role X and the resource is owned by their team.
3. Require all S3 bucket Terraform definitions to disable public access.
4. Deny container images not from approved registries.
5. Require that all IAM policies grant least privilege (no wildcards in actions).

Each policy is small. The exercise is in writing them, not in their complexity.

**Self-check questions**

- What is the difference between OPA and Gatekeeper?
- Where does OPA fit in a PDP/PEP architecture?
- What is the difference between Rego and YAML-based policy languages like Kyverno's?
- What is a decision log and why is it useful?

## Week 14: Kyverno, Gatekeeper, and admission control

**Concepts to learn**

- Kubernetes admission controllers and the validating/mutating webhook pattern.
- Kyverno: Kubernetes-native policy engine using YAML policies.
- OPA Gatekeeper: OPA wrapped for Kubernetes admission, using Rego.
- The trade-off: YAML accessibility vs Rego expressive power.
- Policy enforcement modes: enforce (block) vs warn vs audit.
- Background and validation policies.
- Mutation: changing resources at admission time (e.g. injecting sidecars, applying defaults).

**Free resources**

- **Kyverno documentation** at kyverno.io. Read the introduction and policy-types pages.
- **Gatekeeper documentation** at open-policy-agent.github.io/gatekeeper.
- **CNCF (Cloud Native Computing Foundation) governance and policy resources** at cncf.io.
- **YouTube channels:** TechWorld with Nana on admission controllers; Rawkode Academy on policy.
- **Free kind clusters** for local Kubernetes practice via kind.sigs.k8s.io.

**Do this**

If you have a few hours and any Linux machine or Mac:
1. Install kind (`brew install kind` on Mac).
2. Create a kind cluster.
3. Install Kyverno via Helm.
4. Apply one Kyverno policy that requires every pod to have resource limits.
5. Try to create a pod without limits; observe the rejection.
6. Repeat with Gatekeeper and an equivalent ConstraintTemplate / Constraint pair.

This single afternoon makes the YAML-vs-Rego trade-off concrete.

**Self-check questions**

- What is an admission controller?
- What is the difference between mutating and validating webhooks?
- When would you choose Kyverno over Gatekeeper?
- What is the trade-off of enforcement vs audit mode?

## Week 15: Sigstore, SBOMs, and software supply-chain security

**Concepts to learn**

- The software supply-chain problem: SolarWinds, Codecov, NPM compromises, MOVEit, 3CX. Trust in your dependencies is the weak link.
- **SBOM (Software Bill of Materials):** a structured list of every component in a piece of software.
- **SPDX** and **CycloneDX:** the two standard SBOM formats. SPDX is ISO/IEC 5962:2021. CycloneDX is OWASP-led, more security-focused.
- **Sigstore:** open-source project providing keyless signing of software artefacts. Components: Cosign (CLI), Fulcio (CA), Rekor (transparency log).
- **SLSA (Supply-chain Levels for Software Artefacts):** a framework defining levels of supply-chain integrity (currently SLSA 1-4).
- **In-toto attestations:** structured statements about how an artefact was built.
- **Executive Order 14028:** US federal mandate that effectively required SBOMs from software suppliers.

**Free resources**

- **Sigstore documentation** at docs.sigstore.dev.
- **Cosign quickstart** at docs.sigstore.dev/cosign. Sign your first container image in 30 minutes.
- **SLSA framework** at slsa.dev. Free, well-written.
- **CycloneDX specification** at cyclonedx.org. Free.
- **SPDX specification** at spdx.dev. Free.
- **CISA SBOM resources** at cisa.gov/sbom.
- **The OpenSSF (Open Source Security Foundation) materials** at openssf.org. Free.

**Do this**

1. Install syft (`brew install syft`).
2. Generate an SPDX SBOM of any directory: `syft <dir> -o spdx-json > sbom.spdx.json`.
3. Generate a CycloneDX SBOM of the same: `syft <dir> -o cyclonedx-json > sbom.cdx.json`.
4. Look at both. Notice the structural differences.
5. Install cosign (`brew install cosign`).
6. Sign a container image you control: `cosign sign <image>`. Follow the keyless flow.
7. Verify the signature.

This exercise is the difference between knowing the words and using the tools.

**Self-check questions**

- What is an SBOM and why does it exist?
- What is the difference between SPDX and CycloneDX?
- What is keyless signing and why does it matter?
- What does SLSA Level 3 require?
- Why is the Rekor transparency log important?

## Week 16: CNAPP, CIEM, CSPM, and cloud security tooling

**Concepts to learn**

- **CSPM (Cloud Security Posture Management):** continuously assess cloud configurations against security best practice.
- **CWPP (Cloud Workload Protection Platform):** runtime protection for cloud workloads (containers, VMs, serverless).
- **CIEM (Cloud Infrastructure Entitlement Management):** identify and right-size excessive cloud permissions.
- **CNAPP (Cloud-Native Application Protection Platform):** the umbrella category combining CSPM + CWPP + CIEM + sometimes SAST + container scanning.
- Major vendors: Wiz, Orca Security, Palo Alto Prisma Cloud, Microsoft Defender for Cloud, AWS Security Hub, GCP Security Command Center.
- Cloud-native vs SIEM-extended approaches.
- Agent-based vs agentless approaches.
- Where the CNAPP space is going (consolidation, AI-driven prioritisation, runtime context).

**Free resources**

- **Wiz Academy** at academy.wiz.io. Free courses, vendor-flavoured but technically excellent.
- **Orca Security blog and resources** at orca.security.
- **Microsoft Defender for Cloud documentation** at learn.microsoft.com.
- **AWS Security Hub user guide** at docs.aws.amazon.com.
- **Cloud Security Alliance Cloud Controls Matrix** at cloudsecurityalliance.org. Free.
- **Gartner glossary entries on CSPM, CWPP, CIEM, CNAPP.** Free overviews, even though full reports are paid.
- **Marco Lancini's CloudSecList newsletter** at cloudseclist.com. Free, weekly, excellent.

**Do this**

Sign up for an AWS free-tier account if you don't have one. Enable AWS Security Hub. Within an hour you will see real findings against your account. Read three of them. Understand what they mean. This is exactly what CSPM tools deliver, just more.

**Self-check questions**

- What is the difference between CSPM and CWPP?
- What is CIEM and why is it a hot category?
- What is the difference between agent-based and agentless cloud security?
- What is the typical first finding a new CSPM deployment surfaces?

---

# MONTH 5: ARCHITECTURE AND DESIGN PATTERNS

You have the regulations and tools. Time for the design patterns that recur across modern security and GRC architecture.

## Week 17: Zero Trust and PDP/PEP

**Concepts to learn**

- The Zero Trust philosophy: never trust, always verify, assume breach.
- The shift from perimeter security to identity-and-context-driven access.
- NIST SP 800-207 Zero Trust Architecture: the canonical reference.
- **PDP (Policy Decision Point):** the centralised brain that says yes or no to access requests.
- **PEP (Policy Enforcement Point):** the gatekeeper at the resource that asks the PDP and enforces.
- The XACML reference architecture (largely superseded by simpler implementations like OPA, Cedar).
- Continuous verification: re-evaluating access during a session as context changes.
- Microsegmentation.
- Identity providers (IdPs), workload identity, attribute-based access control (ABAC), relationship-based access control (ReBAC).

**Free resources**

- **NIST SP 800-207 Zero Trust Architecture.** Free PDF at csrc.nist.gov. Read all of it.
- **NIST SP 800-207A and 207B** (subsequent zero-trust supplements). Free PDFs.
- **CISA Zero Trust Maturity Model 2.0** at cisa.gov/zero-trust-maturity-model. Free.
- **DoD Zero Trust Reference Architecture.** Free PDF, Google to find current version.
- **Google BeyondCorp papers** at cloud.google.com/beyondcorp. Foundational; free.
- **John Kindervag (Forrester) original zero-trust writings.** Find via Forrester or his current Numberline.

**Do this**

Diagram the access flow for one of your daily activities (e.g. logging into production at work). Identify the PDP, the PEP, the identity provider, the policy source, and the trust signals being evaluated. If you cannot identify one of these, that is a learning. Many organisations have implicit PDPs (the application itself).

**Self-check questions**

- What does "never trust, always verify" mean in practice?
- What is the difference between a PDP and a PEP?
- What is microsegmentation?
- What is the difference between ABAC and ReBAC?
- What is workload identity?

## Week 18: Knowledge graphs in GRC

**Concepts to learn**

- What a graph database is: nodes and relationships rather than tables and joins.
- Why GRC is naturally a graph: risks, controls, assets, frameworks, owners, evidence are densely interrelated.
- Major graph databases: Neo4j, Amazon Neptune, ArangoDB, Memgraph.
- Cypher query language (Neo4j's; widely understood).
- RDF and SPARQL (the alternative semantic-web stack).
- Common GRC graph patterns: control coverage analysis, risk impact propagation, evidence reachability.

**Free resources**

- **Neo4j "Graph Databases for Beginners" book.** Free PDF at neo4j.com.
- **Neo4j Sandbox** at neo4j.com/sandbox. Free hosted Neo4j. Run queries without installing.
- **Cypher query language manual** at neo4j.com/docs/cypher-manual.
- **The Apache Jena tutorial** at jena.apache.org for the RDF/SPARQL alternative.

**Do this**

In a Neo4j Sandbox, model a tiny GRC graph:
- 5 risks.
- 10 controls.
- 5 assets.
- 3 frameworks.
- Relationships: MITIGATES, AFFECTS, REQUIRES, OWNED_BY.

Then write Cypher queries:
- Which risks have no mitigating controls?
- Which controls satisfy multiple framework references?
- For a given asset, what are the risks?

**Self-check questions**

- What is a graph database and how does it differ from a relational database?
- What is Cypher?
- Why might a GRC platform be built on a graph database?
- What is the trade-off vs SQL?

## Week 19: SIEM, SOAR, and detection engineering

**Concepts to learn**

- **SIEM (Security Information and Event Management):** centralises logs, applies detection rules, alerts.
- **SOAR (Security Orchestration, Automation, and Response):** automates triage and response actions.
- Detection engineering: the discipline of writing, maintaining, and tuning detections.
- The MITRE ATT&CK framework: a knowledge base of adversary tactics, techniques, and procedures (TTPs).
- The Pyramid of Pain: hashes, IPs, domains, host artefacts, network artefacts, tools, TTPs.
- Sigma rules: vendor-agnostic detection format.
- Major SIEMs: Splunk, Elastic Security, Microsoft Sentinel, Sumo Logic, Datadog, Devo.
- The shift to data-lake security analytics and decoupling storage from analytics.

**Free resources**

- **MITRE ATT&CK** at attack.mitre.org. Free, comprehensive.
- **Sigma rule repository** at github.com/SigmaHQ/sigma.
- **The Detection Engineering Maturity Matrix** by Kyle Bailey (search GitHub).
- **Elastic Detection Rules repository** at github.com/elastic/detection-rules.
- **Splunk Security Content** at github.com/splunk/security_content.
- **SANS Reading Room** at sans.org/white-papers, free papers on detection.
- **Florian Roth's blog and Sigma rules** for practitioner-grade examples.

**Do this**

Browse five Sigma rules from the SigmaHQ repository. Pick one detection (e.g. for credential access) and walk through what each part does.

**Self-check questions**

- What is the difference between SIEM and SOAR?
- What does ATT&CK enumerate?
- What is the Pyramid of Pain?
- What is a Sigma rule?

## Week 20: AI/ML governance and AI risk

**Concepts to learn**

- **NIST AI Risk Management Framework (AI RMF 1.0)** released January 2023: GOVERN, MAP, MEASURE, MANAGE functions.
- **ISO/IEC 42001:2023** AI Management System (AIMS).
- **EU AI Act** (Regulation 2024/1689): risk-based regulation. Prohibited, high-risk, limited-risk, minimal-risk classifications. General-purpose AI models. Phased application 2024-2027.
- **OWASP LLM Top 10:** risks specific to large language models (prompt injection, sensitive information disclosure, training data poisoning, etc.).
- Model cards and datasheets for datasets.
- AI bias, fairness, explainability concepts.
- Differential privacy, federated learning, homomorphic encryption (privacy-preserving ML basics).

**Free resources**

- **NIST AI RMF 1.0** at nist.gov/ai-rmf. Free.
- **NIST AI RMF Playbook.** Free.
- **EU AI Act text** at eur-lex.europa.eu. Free.
- **EU AI Act explorer** at artificialintelligenceact.eu. Free, navigable.
- **OWASP LLM Top 10** at owasp.org. Free.
- **Google's Responsible AI Practices** at ai.google. Free.
- **Anthropic's published responsible scaling policy.** Free.
- **The Model Cards paper** by Mitchell et al. (2018). Search arXiv. Free.

**Do this**

For your fictional product, identify one AI use case. Apply the NIST AI RMF MAP function: what context, intended uses, foreseeable misuse, and impacts? Write half a page.

**Self-check questions**

- What are the four functions of NIST AI RMF?
- What is a "high-risk" AI system under the EU AI Act?
- What are three common LLM-specific risks?
- What is a model card and why does it matter?

---

# MONTH 6: SYSTEMS THINKING, ARCHITECTURE, AND CONSOLIDATION

You now have the breadth. Final month is about thinking like an architect and consolidating.

## Week 21: Systems thinking for GRC

**Concepts to learn**

- The difference between problems and symptoms.
- Feedback loops: balancing and reinforcing.
- Stocks and flows.
- Emergence: how system behaviour is not the sum of part behaviours.
- Why "more controls" is not always more security.
- Why optimising one metric often degrades others.
- The principle of subsidiarity: decisions made at the lowest competent level.

**Free resources**

- **"Thinking in Systems" by Donella Meadows.** Available free as PDF in many places (legitimately, the Sustainability Institute released excerpts). Read it. It will change how you think.
- **The Systems Thinker** at thesystemsthinker.com. Free articles.
- **John Sterman's MIT OpenCourseWare on system dynamics.** Free at ocw.mit.edu.
- **Cynefin Framework** by Dave Snowden. Free explainer videos on YouTube.

**Do this**

Pick one of your portfolio projects. Identify three feedback loops in the system it describes. Identify one place where local optimisation could harm the overall system.

**Self-check questions**

- What is the difference between a balancing and a reinforcing feedback loop?
- What is emergence?
- Why do controls accumulate even when they no longer add value?

## Week 22: Architecture decision records and trade-off thinking

**Concepts to learn**

- The ADR (Architecture Decision Record) pattern: capture decisions, alternatives, and rationale.
- The Michael Nygard ADR template.
- Trade-off analysis: cost / benefit / risk for each option.
- Why "we chose X" without saying what you rejected is half a decision.
- The "rejected alternatives" section as the most useful section.
- ADRs as living documents (superseded, not deleted).

**Free resources**

- **Michael Nygard's original ADR post** at cognitect.com/blog (search "Documenting Architecture Decisions"). Free.
- **The ADR GitHub repository** at github.com/joelparkerhenderson/architecture-decision-record. Many examples.
- **ThoughtWorks Tech Radar.** Free at thoughtworks.com/radar.

**Do this**

Re-read three ADRs from your existing portfolio. Pick one. Without re-reading what you wrote, list the alternatives you would consider and the trade-offs you would weigh. Then compare to what is in the ADR. Note the gap. That gap is your real architectural intuition vs the AI-generated text.

**Self-check questions**

- What is the difference between a context and a decision in an ADR?
- Why is the "rejected alternatives" section important?
- When is an ADR superseded vs deleted?

## Week 23: Threat modelling

**Concepts to learn**

- STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege).
- DREAD (legacy, less used).
- PASTA (Process for Attack Simulation and Threat Analysis).
- LINDDUN (privacy-focused).
- Attack trees.
- Microsoft's Threat Modelling Tool.
- The OWASP Threat Dragon free tool.
- The four-question framework (Adam Shostack): What are we working on? What can go wrong? What are we going to do about it? Did we do a good job?

**Free resources**

- **"Threat Modeling: Designing for Security" by Adam Shostack.** A book. Paid but the supporting materials and many of his free articles cover the core thinking.
- **OWASP Threat Modeling cheat sheet** at owasp.org.
- **OWASP Threat Dragon** at owasp.org/www-project-threat-dragon. Free tool.
- **Microsoft Threat Modeling Tool** at microsoft.com. Free.
- **LINDDUN** at linddun.org. Free privacy-focused threat modelling.
- **MITRE ATT&CK and D3FEND** at mitre.org. Free.

**Do this**

Threat-model one of the systems described in your portfolio using STRIDE. For each STRIDE category, identify one specific threat and one mitigation.

**Self-check questions**

- What does STRIDE stand for?
- When is LINDDUN preferred over STRIDE?
- What are Adam Shostack's four questions?

## Week 24: Bringing it together and the next steps

**Concepts to learn**

- Reading published incident reports critically.
- Reading published court decisions and regulatory orders.
- Building a habit of continuous learning.
- Where to go next.

**Free resources**

- **The DBIR (Verizon Data Breach Investigations Report).** Free annual report at verizon.com/dbir.
- **The Cyentia Information Risk Insights Study.** Free.
- **The CISA Known Exploited Vulnerabilities Catalog.** Free at cisa.gov.
- **ICO published enforcement actions** at ico.org.uk.
- **Public Big Tech post-mortems** (Google, AWS, Cloudflare, GitHub all publish).
- **Risky Business podcast** at risky.biz. Free, weekly.
- **Krebs on Security** at krebsonsecurity.com. Free.
- **SANS NewsBites** at sans.org. Free newsletter.
- **Phil Venables's blog and newsletter** at philvenables.com. Free, exceptional.
- **Ross Haleliuk newsletter** at ventureinsecurity.net. Free, sharp.

**Do this**

1. Read the most recent DBIR cover to cover.
2. Read three CISA advisories.
3. Read one full incident post-mortem (e.g. Cloudflare or GitHub).
4. Subscribe to two of the newsletters above for ongoing input.
5. Re-read one of your portfolio repos with the eyes you now have. Write a one-page reflection on what you would change.

**Self-check questions**

You should now be able to answer, without lookup:
- What is GRC?
- How does ISO 27001 differ from SOC 2?
- What is the difference between NIST CSF and NIST 800-53?
- What is FedRAMP and what is a POAM?
- What is DORA and when did it apply?
- What is OPA and where is it used?
- What is a CNAPP?
- What is zero trust and what is a PDP?
- What is an SBOM and which formats matter?
- What are the four functions of NIST AI RMF?

If you cannot answer any of these confidently, go back to that week and re-read.

---

# AFTER MONTH 6: WHERE NEXT

You now have foundational fluency. The journey to depth takes years and is best done through:

1. **Real work.** Apply for GRC, security, or compliance roles where you can practise. Theory locks in only through use.
2. **Specialisation.** Pick two areas you find genuinely interesting and go deep. Possibilities:
   - **Privacy:** add CIPP/E or CIPM (IAPP certifications, paid, ~£500 each, recognised globally).
   - **Cloud security:** add AWS Security Specialty or Microsoft SC-100 (paid).
   - **Audit:** add ISO 27001 Lead Auditor (paid, ~£2000 with a reputable provider).
   - **Risk management:** add CRISC or FAIR Foundational Analyst (paid).
3. **Build something real.** Pick one project from your portfolio and build a working prototype with code, tests, and CI. Even a small one. The conversation you can have about a working artefact is qualitatively different.
4. **Contribute.** Open issues, suggest improvements, write blog posts, answer questions on r/grc or r/cybersecurity.
5. **Find a mentor.** A senior GRC or security professional who has done the work. Most are willing to give an hour to someone clearly self-driven.

## Tracking your progress

A simple weekly journal answering three questions:

- What did I learn this week that I did not know last week?
- What can I now defend in conversation that I could not before?
- What still feels shaky?

Reviewed monthly. Adjusted accordingly.

## A note on certifications

The portfolio plus this curriculum gives you knowledge. Certifications give you a credential. Knowledge without a credential is invisible to many recruiters. A credential without knowledge is exposed in 10 minutes of conversation.

Pursue certifications when:
- You have the underlying knowledge.
- The certification is recognised in the roles you want.
- You can afford the time and money.

Skip certifications when:
- You are buying a credential to compensate for shaky knowledge.
- The certification is unrecognised or paywall-vendor-specific.
- The opportunity cost (the time spent) is better spent on real practice.

## A final honest note

This curriculum is six months of focused study. At the end, you will not be senior. You will be credibly junior-to-mid: someone who can hold a serious conversation, ask good questions, and learn fast on the job. That is enormous progress and exactly what employers in this field hire for at entry and intermediate levels.

Beyond that, mastery is years of real work, real incidents, real audits, real arguments, and real consequences. The curriculum starts you on the road; the road itself is the rest of your career.

Good luck. Take it one week at a time.
