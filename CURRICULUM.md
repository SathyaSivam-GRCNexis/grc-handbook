# GRC & Security Tech Curriculum

A six-month, week-by-week study plan covering every standard, regulation, framework, and technology referenced across the tech and non-tech projects in this portfolio. The shape assumes two to three focused hours an evening or roughly 10–15 hours a week. Every resource is free unless flagged otherwise.

The aim is fluency, not specialism. By the end you should be able to defend any topic in this portfolio in conversation with a peer, a recruiter, or an interviewer who knows the area. Deep specialism in any one of these takes years. Fluency takes months if you actually do the exercises.

## How to use this curriculum

1. **Read top to bottom.** The order matters. Skipping foundations means redoing them later in confusion. I have watched too many people jump straight to "ISO 27001 controls" before they understood what a control objective is.
2. **Take notes in your own words.** Reading is not learning. Writing is. After each major topic, write a one-paragraph summary in plain English. If you cannot, you have not understood it. Be honest with yourself about this.
3. **Build the artefact at the end of each week.** Most weeks have a "do this" exercise. The exercise is where the learning sticks. Skip the exercises and the curriculum becomes information consumption, which is comfortable but useless.
4. **Test yourself weekly.** End-of-week self-check questions. Answer them out loud. If you mumble, you do not know it.
5. **Revisit your portfolio repos as you learn.** As topics become clear, you will spot things in your repos that look wrong or thin. Edit them. The repos become genuinely yours over time.
6. **Do not memorise. Understand.** Standards have thousands of details. Memorising is pointless. Understanding what they exist for, what they require, and how to look up the rest is what you need on the job.

## Time budget

| Effort level | Hours / week | Time to complete |
|---|---|---|
| Light (job + family) | 5-7 | 9-12 months |
| Standard | 10-15 | 6 months |
| Intensive (career change focus) | 20-25 | 3-4 months |

This document assumes the standard six-month plan. Adjust accordingly. Do not pretend you are doing intensive if you are actually doing light. The plan only works if the hours are real.

---

# MONTH 1: FOUNDATIONS

You cannot understand any of the specific standards or technologies in this portfolio until you understand what risk, control, audit, and management systems actually are. Month 1 is the bedrock. Skip it and the rest will not stick. I have seen people with three years in the industry who still cannot explain the difference between a control objective and a control activity, and it shows in their work.

## Week 1: What is GRC actually?

**Concepts to learn**

- What governance, risk management, and compliance each mean, and how they relate.
- The Three Lines model: who does what, who oversees what, who audits what.
- Why GRC exists in the first place: protecting value, enabling decisions, satisfying obligations.
- The difference between management systems and controls.
- The compliance fatigue problem and why it matters. (This is real. Every audit cycle, people quietly stop caring. Knowing this shapes how you design programmes.)

**Free resources**

- **The Institute of Internal Auditors: The Three Lines Model (2020).** Free PDF at theiia.org. Seven pages. Read it twice.
- **OCEG GRC Capability Model "Red Book"** summary at oceg.org. Full model is membership-walled. The executive summary is free and explains the principled-performance approach.
- **NIST SP 800-39: Managing Information Security Risk.** Free at csrc.nist.gov. Read chapters 1 and 2 only. The rest can wait.
- **CISA's "Cybersecurity Risk Management" overview** at cisa.gov. Short, free, accurate.

**Do this**

Write a one-page note in your own words answering: "What is GRC and why does it exist in modern organisations?" Include the Three Lines model. Plain English, no jargon. If your note reads like a vendor blog, redo it.

**Self-check questions**

- Can you explain the Three Lines model to a non-technical friend without using the word "assurance"?
- What is the difference between governance and management?
- Why are second-line and third-line functions kept independent of first-line? What goes wrong when they are not?
- What practically happens to a company that has no risk management function? (Hint: usually nothing for a while, and then a lot all at once.)

## Week 2: Risk fundamentals

**Concepts to learn**

- Inherent vs residual risk.
- Likelihood and impact, and why both need precise definitions or you end up with five-point scales that nobody trusts.
- Risk appetite and risk tolerance.
- Risk treatment options: mitigate, transfer, avoid, accept.
- The risk register: what it is, what it should not be (it should not be a project log or a finding tracker).
- Quantitative vs qualitative approaches.

A standing opinion: most teams overcook their scoring model on day one. A simple 5x5 grid that everyone in the business actually uses is worth more than a FAIR-aligned model that lives in one analyst's head. You can graduate later. Start where the business is.

**Free resources**

- **NIST SP 800-30 Rev 1: Guide for Conducting Risk Assessments.** Free PDF at csrc.nist.gov. Around 100 pages, readable. Read all of it.
- **ISO 31000:2018 overview** at iso.org/iso-31000-risk-management.html (free overview of the paid standard).
- **The IRM (Institute of Risk Management) free resources** at theirm.org, especially the "Risk appetite and tolerance" guidance paper.
- **The FAIR Institute's "Open FAIR" introduction** at fairinstitute.org. Free intro materials. The best free starting point for quantitative risk.
- **Hubbard Decision Research blog posts** at hubbardresearch.com. Free. Sceptical and well-argued.

**Do this**

Take ten things that worry you in your personal or professional life. Score them 1-5 likelihood, 1-5 impact. Reorder by score. Notice which scoring decisions felt arbitrary. That arbitrariness is exactly what risk methodologies are trying to constrain, and the friction is the lesson.

**Self-check questions**

- What does it mean for a residual risk to be "outside appetite", and what should happen next?
- Why are accepted risks reviewed periodically? What changes?
- When is qualitative scoring (low / medium / high) actually better than quantitative ($M loss expectancy)?
- Why do treatment plans need owners and dates? What happens to the ones that do not?

## Week 3: Controls fundamentals

**Concepts to learn**

- What a control is. Preventive, detective, corrective, deterrent, compensating.
- Control objectives vs control activities. Confusing these is the single most common mistake I see in junior GRC work.
- Control design vs control operation.
- Key controls vs supporting controls.
- Sampling and population testing.
- Why "control testing" exists, and why self-attestation is not it.

**Free resources**

- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov. Do not read all 1000+ pages. Read the first 30 on structure and terminology. Then browse the AC, AU, CA, CM, IA, RA, SI families to see how controls are written.
- **NIST SP 800-53A Rev 5: Assessment Procedures.** Free PDF. Read the introduction to see how controls are actually tested.
- **AICPA Trust Services Criteria and Description Criteria (DC 200) for SOC 2.** Free at aicpa-cima.com. Read the Common Criteria (CC1-CC9). Around 50 pages of dense material. Stay with it.
- **CIS Controls v8.1 documentation.** Free at cisecurity.org. Read the introduction and the first three controls in detail.

**Do this**

Pick one daily activity (logging into your laptop is a good one). Identify every control involved. Categorise each as preventive, detective, or corrective. Identify the owner. Then describe how an auditor would test that the control operates over a period, not just at a point in time. The last bit is where most people get stuck the first time.

**Self-check questions**

- What is the difference between a control objective and a control activity? Give an example of each for password management.
- Why is design effectiveness tested separately from operating effectiveness?
- What is a key control? How do you decide?
- Why is a self-tested control weaker evidence than an independently tested one?

## Week 4: Audit fundamentals

**Concepts to learn**

- What an audit is and is not. Audit vs assessment vs review. People use these interchangeably and it causes real confusion in vendor RFPs.
- First-party (internal), second-party (customer), third-party (independent) audits.
- The audit lifecycle: planning, fieldwork, reporting.
- Sampling. The auditor does not test everything. They sample. The maths matters.
- Findings: nonconformity, observation, opportunity for improvement.
- The Provided By Client (PBC) list. This will be your life during fieldwork.
- Materiality, professional scepticism, evidence sufficiency.

**Free resources**

- **ISO 19011:2018 overview** at iso.org. Paid in full. Free overview is enough at this stage.
- **AICPA's "What is a SOC 2 Report" overview** at aicpa-cima.com.
- **CISA Cybersecurity Audit Resources** at cisa.gov.
- **The IIA's "International Professional Practices Framework" overview** at theiia.org. Members-only in full, free at the descriptive level.
- **Big Four published methodology overviews:** PwC, KPMG, EY, Deloitte SOC 2 readiness guides. Marketing, but useful as long as you read them critically.

**Do this**

Read a publicly available SOC 2 Type 2 report from a SaaS company. Many publish redacted versions on their trust centres. Identify the structure: management assertion, auditor opinion, control descriptions, test procedures, results. Note any exceptions. This is exactly what your future employers will deliver to their customers, and what your customers will deliver to you.

**Self-check questions**

- What is the difference between a SOC 2 Type 1 and Type 2? Which one actually means something?
- What does "in all material respects" mean in an audit opinion? Why is that phrase chosen?
- Why are auditors required to be independent? What happens when independence is compromised in practice?
- What is professional scepticism, and why is it the thing that distinguishes an audit from a friendly review?

---

# MONTH 2: CORE FRAMEWORKS

You have the foundations. Now learn the frameworks this portfolio references repeatedly. Be honest about which one your target market actually needs. ISO 27001 dominates outside North America. SOC 2 dominates inside it. NIST is the reference everyone points at. GDPR has the longest reach.

## Week 5: ISO 27001 and ISO 27002

**Concepts to learn**

- What ISO 27001 is and what certification actually means (and does not mean).
- The structure: clauses 4-10 (the management system) and Annex A (the controls).
- The 2022 revision: 93 controls in 4 themes (was 114 in 14 in 2013).
- The Statement of Applicability (SoA): the single most important document. An auditor opens this first. If yours is sloppy, the rest of the audit gets harder.
- Risk-based approach: clause 6.1.
- Continual improvement: clauses 9 and 10.
- The certification cycle: Stage 1, Stage 2, surveillance, recertification.

A common pattern during ISO 27001 readiness: teams obsess over Annex A and underinvest in clauses 4-10. The auditor will spend more time on the management system clauses than on most individual controls. Plan accordingly.

**Free resources**

- **ISO 27001:2022 official overview** at iso.org. Free.
- **BSI Group's free ISO 27001:2022 transition guides** at bsigroup.com.
- **IT Governance UK blog posts on the 2022 revision** at itgovernance.co.uk. Free, accurate, opinionated.
- **The ISMS.online and Vanta blogs on ISO 27001.** Vendor content, but the explanatory parts are useful.
- **AdvisorPedia ISO 27001 free articles** at advisorpedia.com.
- **Annex A Controls Reference Card** (search "ISO 27001:2022 Annex A reference card pdf"). Free downloadable summaries from multiple consultancies.

**Paid but worth it (optional)**

- **The standard itself.** ISO 27001:2022 and ISO 27002:2022 from your national standards body (BSI in the UK). Around £150 each. If you can afford it, do it. Summaries are good but the standard is the source of truth, and you will eventually need to quote clause numbers.

**Do this**

Take your fictional portfolio company. Write a one-page Statement of Applicability covering 10 of the 93 Annex A controls: 5 included with a one-line implementation reference, 5 excluded with a one-line justification. The justifications are where most SoAs go wrong. "Not applicable" is not a justification. "We do not develop software, so A.8.25 secure development lifecycle is excluded" is.

**Self-check questions**

- What are the four themes of Annex A in ISO 27001:2022?
- Why is the SoA the most important document?
- What is the difference between a clause and a control?
- What does it mean for an organisation to be "certified to ISO 27001"? Who certifies, and who accredits the certifier?
- What is the difference between a major nonconformity and a minor nonconformity, and how does each affect the certification outcome?

## Week 6: SOC 2 and the AICPA Trust Services Criteria

**Concepts to learn**

- What SOC 2 is, who issues it (AICPA, US-based), and how it differs from ISO 27001. The short version: ISO 27001 is a management system certification, SOC 2 is an attestation report. Different beasts. Different audiences.
- SOC 1 vs SOC 2 vs SOC 3.
- Type 1 (point in time) vs Type 2 (period of operation). Type 1 is not impressive to buyers and most procurement teams know it.
- The Trust Services Criteria categories: Security (Common Criteria), Availability, Processing Integrity, Confidentiality, Privacy.
- The 2017 criteria with the 2022 update.
- The SSAE 18 attestation standard underlying SOC 2.
- How auditor opinions are written and what they mean.

A standing opinion: SOC 2 fails on evidence management more than on control design. Almost every exception I have seen in a Type 2 report was traceable to a missing ticket, a missed quarterly review, or a control owner who left and was not replaced. Build the evidence rhythm first. The control design is the easy part.

**Free resources**

- **AICPA SOC 2 resource page** at aicpa-cima.com. Includes the Trust Services Criteria PDF for free.
- **AICPA "SOC 2 Reporting Resource Centre."** Free.
- **A real-world SOC 2 Type 2 report.** Search for any major SaaS company's trust centre (Datadog, Atlassian, Snowflake, Notion all publish or share on request).
- **"SOC 2 Compliance Handbook" content from Vanta and Drata.** Vendor content. The explanatory parts are accurate. Treat the product pitches with healthy scepticism.
- **Schellman, A-LIGN, Sensiba San Filippo** publish free SOC 2 readiness guides as marketing.

**Do this**

Map five Common Criteria (e.g. CC6.1, CC6.6, CC7.1, CC7.4, CC9.2) to specific controls you would expect to find in a SaaS company. For each, note what evidence the auditor would expect, and where in the business that evidence actually lives day to day. The "where it lives" question is the one that separates real readiness from theatre.

**Self-check questions**

- What is the difference between SOC 2 Type 1 and Type 2, and why does it matter to a buyer?
- What are the five Trust Services categories?
- Which is mandatory? Which are optional? When would you scope in Availability or Confidentiality?
- What does an "unqualified opinion" mean?
- What happens if a SOC 2 audit identifies an exception? Does the company "fail"? (No, but the report carries it for the period.)

## Week 7: NIST CSF 2.0 and NIST 800-53

**Concepts to learn**

- NIST Cybersecurity Framework 2.0 (released February 2024). The new GOVERN function. The other five: IDENTIFY, PROTECT, DETECT, RESPOND, RECOVER.
- Functions, categories, subcategories.
- Implementation Tiers (1-4).
- Profiles (current vs target).
- NIST SP 800-53 Rev 5: control families, control enhancements, baselines.
- The relationship between CSF and 800-53 (CSF is outcome-oriented; 800-53 is control-oriented). They are not alternatives. They are different tools for different jobs.
- Where 800-53 is mandatory (US federal systems) and where it is a reference (everywhere else).

**Free resources**

- **NIST CSF 2.0 official site** at nist.gov/cyberframework. All resources free. Download the framework PDF, the Implementation Examples, the Quick Start Guides, and the informative references mapping CSF to 800-53.
- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov.
- **NIST SP 800-53B (control baselines).** Free PDF.
- **CISA's CSF 2.0 implementation resources** at cisa.gov.
- **NIST CSF 2.0 Reference Tool** at nist.gov/cyberframework/csf-tool. Use it.

**Do this**

Pick five subcategories from NIST CSF 2.0 (one from each function except GOVERN; pick two from GOVERN since it is the new and most-asked-about function). For each, write what your fictional company does today, what gaps exist, and what target state would look like. This is exactly how CSF Profiles are built in practice.

**Self-check questions**

- What are the six NIST CSF 2.0 functions?
- Why was GOVERN added in 2.0? What was missing before?
- What is the difference between a Tier and a Profile?
- How does NIST CSF map to NIST 800-53?
- When would an organisation use CSF instead of 800-53 directly?

## Week 8: GDPR and privacy fundamentals

**Concepts to learn**

- The structure of GDPR: 99 articles plus 173 recitals.
- Key articles: 5 (principles), 6 (lawful basis), 7 (consent), 9 (special categories), 12-22 (data subject rights), 24-25 (controller responsibilities), 28 (processors), 30 (records), 32 (security), 33-34 (breach notification), 35 (DPIA).
- Controller vs processor. People confuse this constantly. It matters because the obligations differ.
- Lawful bases for processing.
- Data subject rights (access, rectification, erasure, restriction, portability, objection).
- The 72-hour notification clock. When does it start? Not when you find out. When you become aware of a personal data breach as defined. Read that definition carefully.
- Cross-border transfers: SCCs, BCRs, adequacy decisions, the Schrems II saga.
- ICO (UK) vs EDPB (EU) and individual DPAs.
- Fines and enforcement.

If you work in India, also skim the **DPDP Act 2023** alongside this. The vocabulary differs (data fiduciary, data principal, consent manager) but the underlying logic borrows heavily from GDPR. Where it diverges, it diverges meaningfully.

**Free resources**

- **The full GDPR text** at gdpr-info.eu. Free, fully searchable, with recitals.
- **ICO Guide to GDPR** at ico.org.uk. Free, comprehensive, plain English. The best single resource.
- **EDPB Guidelines** at edpb.europa.eu. All free. At minimum read: 9/2022 on breach notification, 7/2020 on processors, 4/2019 on Article 25 (data protection by design).
- **CNIL (France) guidance** at cnil.fr. Often clearer than the English-language equivalents.
- **Future of Privacy Forum** at fpf.org. Free analysis.
- **IAPP daily newsletter** at iapp.org. Free. Sign up. The single best way to track privacy developments.
- **DPDP Act 2023** text at meity.gov.in. Free.

**Do this**

Pretend a customer has emailed asking for a copy of all their personal data, deletion of their account, and confirmation of all sub-processors. Walk through what your organisation would need to do for each, with timelines and evidence requirements. Write it as a one-page response. The interesting part is usually deletion, because most engineering teams have not actually built it and the operational answer is messy.

**Self-check questions**

- Name the six lawful bases for processing under Article 6.
- What is the difference between controller and processor responsibilities?
- When does the 72-hour breach notification clock start? (Trickier than it sounds.)
- What is a DPIA and when is it actually required?
- What was Schrems II and why does it still matter?
- What is the maximum GDPR fine, and when have regulators actually approached it?

---

# MONTH 3: REGULATIONS YOU MENTION

The portfolio references several regulations flagged as unfamiliar. Time to fix that. None of these are obscure. They come up in customer questionnaires, RFPs, and audits routinely.

## Week 9: FedRAMP

**Concepts to learn**

- What FedRAMP is: the US federal cloud security authorisation programme.
- Why it exists: federal agencies cannot use cloud services without FedRAMP authorisation.
- Authorisation levels: Low, Moderate, High.
- The two paths: JAB (Joint Authorisation Board) Provisional ATO and Agency ATO.
- The 3PAO (Third Party Assessment Organisation) role.
- The POAM (Plan of Action and Milestones): a structured spreadsheet of open findings, owners, target dates, and compensating controls. Updated monthly. The POAM is the single artefact you will live with longest.
- Continuous monitoring: monthly vulnerability scans, monthly POAM updates, annual assessments.
- StateRAMP (state-level equivalent).
- FedRAMP 20x (the 2024+ modernisation initiative).

Honest framing: FedRAMP is genuinely heavy. If your buyers are not US federal, this is reference reading, not adoption reading. If they are, plan for 12–24 months and significant cost.

**Free resources**

- **FedRAMP official site** at fedramp.gov. All templates and guides free.
- **The FedRAMP POAM template** at fedramp.gov/documents-templates. Download and open it. It is just a structured spreadsheet, and a lot of FedRAMP mystique dissolves once you have actually looked at it.
- **The FedRAMP Continuous Monitoring Strategy Guide.** Free PDF.
- **FedRAMP Authorisation Boundary Guidance.** Free PDF.
- **NIST SP 800-37 Rev 2 (RMF).** Free PDF. FedRAMP sits on top of the RMF.
- **Schellman, A-LIGN, Coalfire** publish free FedRAMP overview content as marketing.

**Do this**

Download the FedRAMP POAM template. Populate three example rows for fictional findings (one Critical, one Moderate, one Low). Set deadlines based on FedRAMP's defined remediation timelines (Critical: 30 days, High: 30 days, Moderate: 90 days, Low: 180 days). This makes the POAM concrete in a way that no amount of reading does.

**Self-check questions**

- What is a POAM, and why is it updated monthly rather than quarterly?
- What are the three FedRAMP impact levels?
- What is the difference between JAB and Agency ATO?
- What is a 3PAO?
- Why does FedRAMP demand monthly continuous monitoring rather than annual?

## Week 10: DORA (Digital Operational Resilience Act)

**Concepts to learn**

- What DORA is: EU regulation 2022/2554. Applies to financial entities and their critical ICT third parties from 17 January 2025.
- Five pillars: ICT risk management (Art 5-16), ICT-related incident management and reporting (Art 17-23), digital operational resilience testing (Art 24-27), ICT third-party risk management (Art 28-30), information sharing (Art 45).
- ICT incident classification and reporting: initial notification within 4 hours of classification, intermediate within 72 hours, final within one month.
- Threat-led penetration testing (TLPT) every three years for significant entities.
- The ICT third-party register of information.
- Critical ICT third-party providers (CTPPs) directly supervised by ESAs.
- Subcontracting transparency requirements.

If you sell SaaS to EU banks, insurers, or asset managers, DORA is now table stakes. Expect their procurement teams to ask for a DORA register of information mapping before contract.

**Free resources**

- **The full DORA text (Regulation EU 2022/2554)** at eur-lex.europa.eu. Free.
- **ESMA, EBA, EIOPA joint guidance and RTS** at esma.europa.eu, eba.europa.eu, eiopa.europa.eu. Free.
- **The Bank of England DORA implementation summary** at bankofengland.co.uk. Free.
- **ENISA DORA explainer materials** at enisa.europa.eu. Free.
- **TIBER-EU framework** (precursor to TLPT under DORA) at ecb.europa.eu. Free.
- **Law firm explainers** (Linklaters, Clifford Chance, Hogan Lovells) all publish free DORA primers.

**Do this**

Take Articles 17-23 of DORA. Write a one-page summary in plain English of what an ICT incident reporting workflow must do under DORA: who, what, when, to whom. Write it as a working brief you could hand to an engineer who has not read the regulation. If the engineer still needs to read the regulation after your brief, rewrite it.

**Self-check questions**

- Who does DORA apply to? Who is excluded?
- When did it become applicable?
- What is the timeline for incident reporting?
- What is TLPT and how often is it required?
- What is a CTPP and how is it supervised?

## Week 11: PCI DSS v4.0

**Concepts to learn**

- What PCI DSS is: a contractual standard issued by the PCI Security Standards Council, mandatory for any entity handling payment card data.
- The 12 requirements at the top level, and the ~400 detailed requirements beneath.
- Compliance vs validation: large merchants and service providers undergo annual QSA (Qualified Security Assessor) assessment; smaller merchants self-assess via SAQs.
- Cardholder data environment (CDE) and scope reduction techniques (tokenisation, network segmentation). Scope reduction is where the real money is saved.
- The transition from v3.2.1 to v4.0 (March 2022) and the future-dated requirements that became mandatory 31 March 2025.
- Customised approach (new in v4.0): enables alternative implementations that meet the security objective. Sounds liberating. Carries an evidence overhead most teams underestimate.
- Specific requirements worth knowing: 6.3.3 (patching critical CVEs within one month), 11.4 (penetration testing), 11.5 (intrusion detection and change monitoring), 12.10 (incident response).

**Free resources**

- **PCI DSS v4.0.1 official document** at pcisecuritystandards.org. Free download. Read at minimum: introduction, Requirements 6, 8, 10, 11, 12.
- **PCI SSC FAQ database** at pcisecuritystandards.org. Free, searchable.
- **PCI DSS v4 Self-Assessment Questionnaires (SAQs)** at pcisecuritystandards.org. Free. Skim SAQ-D (full SAQ); it shows what a small merchant attests to and clarifies the structure of the standard.
- **TrustWave, Coalfire, A-LIGN, ControlScope** publish free PCI v4 transition guides.
- **PCI subreddits and r/payments** often have practical perspectives that the official documentation does not.

**Do this**

For Requirement 6.3.3 (patching critical CVEs within one month), describe what a SaaS company processing payments would actually need to do end to end: vulnerability scanning, identification, prioritisation by CVSS, patch deployment, evidence retention. Map this to your existing canonical control set. The honest part of the exercise is noticing where your set is thin.

**Self-check questions**

- Who is required to comply with PCI DSS? (Hint: it is contractual, not regulatory.)
- What is the difference between Requirement 11.4.1 and 11.4.5?
- What does the customised approach enable, and what does it cost you in evidence?
- What is a QSA and when is one required?
- What evidence is required for Requirement 6.3.3 compliance?

## Week 12: HIPAA, NIS2, and other regimes worth knowing

**Concepts to learn**

- **HIPAA Privacy Rule** (45 CFR § 164.500): patient health information protections.
- **HIPAA Security Rule** (45 CFR §§ 164.302-318): administrative, physical, technical safeguards for PHI in electronic form.
- **HIPAA Breach Notification Rule** (45 CFR §§ 164.400-414): notification thresholds and timelines.
- **NIS2** (Directive (EU) 2022/2555): EU cybersecurity directive applying to "essential" and "important" entities. Article 21 cybersecurity risk management measures, Article 23 incident reporting.
- **The UK Cyber Resilience Bill** (in development) as the UK's NIS2 equivalent.
- **The SEC Cybersecurity Disclosure Rule** (17 CFR § 229.106): material cyber incidents at registrants must be disclosed within four business days.
- **Singapore IM8, Australia Essential Eight, India DPDP Act 2023** as examples of national regimes practitioners encounter.

You are not expected to be an expert in any of these. You are expected to know they exist, what shape they have, and where to look when a customer questionnaire asks.

**Free resources**

- **HHS HIPAA resources** at hhs.gov/hipaa. Free, comprehensive.
- **NIS2 Directive text** at eur-lex.europa.eu. Free.
- **ENISA NIS2 guidance** at enisa.europa.eu. Free.
- **NCSC UK guidance on cyber resilience** at ncsc.gov.uk. Free.
- **SEC final rule release on cybersecurity disclosure** at sec.gov. Free PDF.
- **IAPP's regulator tracker.** Free portion of iapp.org.
- **MeitY DPDP Act materials** at meity.gov.in. Free.

**Do this**

Pick one regime you are unlikely to encounter (HIPAA if you are UK-based, for example) and one you might (NIS2 if you are EU/UK-based; DPDP if you are India-based). For each, write a one-paragraph summary of the basic obligations. Then for the regime you might encounter, identify three things your fictional SaaS company would actually need to do.

**Self-check questions**

- What is PHI?
- What is the difference between an essential entity and an important entity under NIS2?
- What is the SEC's four-business-day disclosure rule? When does the clock start, and on what?
- How are HIPAA breach notifications timed by the size of the affected population?
- Under DPDP Act 2023, who is the data fiduciary and what is a significant data fiduciary?

---

# MONTH 4: TECHNOLOGIES AND TOOLS

You know the regulations. Now the technologies referenced in the portfolio. The aim here is not to make you an engineer. The aim is for you to be able to sit in a design review and contribute. Most GRC people cannot. The ones who can are the ones that get promoted.

## Week 13: Open Policy Agent (OPA) and Rego

**Concepts to learn**

- What OPA is: a general-purpose policy engine used across cloud-native, Kubernetes, infrastructure, application authorisation, and CI/CD pipelines.
- Rego: OPA's declarative query language.
- Policy as Code: the principle that authorisation, compliance, and admission decisions should be expressed in version-controlled, testable code.
- OPA vs Gatekeeper (Gatekeeper is OPA wrapped for Kubernetes admission).
- OPA vs Cedar (AWS's policy language; different design choices).
- Decision logs and how OPA fits into a Policy Decision Point / Policy Enforcement Point architecture.

**Free resources**

- **OPA official documentation** at openpolicyagent.org/docs. Read the introduction and the Rego primer.
- **The OPA Playground** at play.openpolicyagent.org. Browser-based. Write Rego without installing anything.
- **Styra Academy** at academy.styra.com. Free courses on OPA and Rego. Genuinely well done.
- **The Rego language reference** at openpolicyagent.org/docs/policy-language.

**Do this**

Spend an afternoon writing five Rego policies in the Playground:

1. Deny if a Kubernetes pod runs as root.
2. Allow if a user is in role X and the resource is owned by their team.
3. Require all S3 bucket Terraform definitions to disable public access.
4. Deny container images not from approved registries.
5. Require that all IAM policies grant least privilege (no wildcards in actions).

Each policy is small. The exercise is in writing them, not in their complexity.

**Self-check questions**

- What is the difference between OPA and Gatekeeper?
- Where does OPA sit in a PDP/PEP architecture?
- What is the difference between Rego and YAML-based policy languages like Kyverno's?
- What is a decision log and why is it useful in an audit?

## Week 14: Kyverno, Gatekeeper, and admission control

**Concepts to learn**

- Kubernetes admission controllers and the validating/mutating webhook pattern.
- Kyverno: Kubernetes-native policy engine using YAML policies.
- OPA Gatekeeper: OPA wrapped for Kubernetes admission, using Rego.
- The trade-off: YAML accessibility vs Rego expressive power.
- Policy enforcement modes: enforce (block), warn, audit. Most teams start in audit, which is correct, and never graduate, which is not.
- Background and validation policies.
- Mutation: changing resources at admission time (e.g. injecting sidecars, applying defaults).

**Free resources**

- **Kyverno documentation** at kyverno.io. Read the introduction and policy-types pages.
- **Gatekeeper documentation** at open-policy-agent.github.io/gatekeeper.
- **CNCF (Cloud Native Computing Foundation) governance and policy resources** at cncf.io.
- **YouTube channels:** TechWorld with Nana on admission controllers; Rawkode Academy on policy.
- **Local Kubernetes practice** via kind.sigs.k8s.io.

**Do this**

If you have a few hours and any Linux machine or Mac:
1. Install kind (`brew install kind` on Mac).
2. Create a kind cluster.
3. Install Kyverno via Helm.
4. Apply one Kyverno policy that requires every pod to have resource limits.
5. Try to create a pod without limits; observe the rejection.
6. Repeat with Gatekeeper and an equivalent ConstraintTemplate / Constraint pair.

This one afternoon makes the YAML-vs-Rego trade-off concrete in a way no diagram does.

**Self-check questions**

- What is an admission controller?
- What is the difference between mutating and validating webhooks?
- When would you choose Kyverno over Gatekeeper?
- What is the trade-off of enforcement vs audit mode in production?

## Week 15: Sigstore, SBOMs, and software supply-chain security

**Concepts to learn**

- The software supply-chain problem. SolarWinds, Codecov, NPM compromises, MOVEit, 3CX. Trust in your dependencies is the weak link, and every quarter there is a fresh reminder.
- **SBOM (Software Bill of Materials):** a structured list of every component in a piece of software.
- **SPDX** and **CycloneDX:** the two standard SBOM formats. SPDX is ISO/IEC 5962:2021. CycloneDX is OWASP-led and more security-focused.
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
4. Open both. Notice the structural differences.
5. Install cosign (`brew install cosign`).
6. Sign a container image you control: `cosign sign <image>`. Follow the keyless flow.
7. Verify the signature.

This is the difference between knowing the words and using the tools. Recruiters can tell.

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
- **CIEM (Cloud Infrastructure Entitlement Management):** identify and right-size excessive cloud permissions. In most cloud accounts I have looked at, identities are the weakest link, not configuration.
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
- **Gartner glossary entries on CSPM, CWPP, CIEM, CNAPP.** Free overviews, full reports paid.
- **Marco Lancini's CloudSecList newsletter** at cloudseclist.com. Free, weekly, sharp.

**Do this**

Sign up for an AWS free-tier account if you do not have one. Enable AWS Security Hub. Within an hour you will see real findings against your account. Read three of them. Understand what they mean. This is exactly what CSPM tools deliver, just at more scale.

**Self-check questions**

- What is the difference between CSPM and CWPP?
- What is CIEM and why is it a hot category?
- What is the difference between agent-based and agentless cloud security?
- What is the typical first finding a new CSPM deployment surfaces? (Usually public S3 buckets, exposed databases, or wildcards in IAM. Boring. That is the point.)

---

# MONTH 5: ARCHITECTURE AND DESIGN PATTERNS

You have the regulations and tools. Now the design patterns that recur across modern security and GRC architecture. These are what let you talk to architects without nodding through it.

## Week 17: Zero Trust and PDP/PEP

**Concepts to learn**

- The Zero Trust philosophy: never trust, always verify, assume breach. Yes, every vendor abuses the term. Learn it from the source.
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
- **DoD Zero Trust Reference Architecture.** Free PDF; search for the current version.
- **Google BeyondCorp papers** at cloud.google.com/beyondcorp. Foundational. Free.
- **John Kindervag (Forrester) original zero-trust writings.** Find via Forrester or his current outlet.

**Do this**

Diagram the access flow for one of your daily activities (logging into production at work is a good one). Identify the PDP, the PEP, the identity provider, the policy source, and the trust signals being evaluated. If you cannot identify one of these, that is a learning. In one SaaS environment I worked in the PDP was the application itself, which made the whole zero-trust diagram theoretical.

**Self-check questions**

- What does "never trust, always verify" mean in practice, not in slides?
- What is the difference between a PDP and a PEP?
- What is microsegmentation, and why is it hard in real networks?
- What is the difference between ABAC and ReBAC?
- What is workload identity?

## Week 18: Knowledge graphs in GRC

**Concepts to learn**

- What a graph database is: nodes and relationships rather than tables and joins.
- Why GRC is naturally a graph: risks, controls, assets, frameworks, owners, evidence are densely interrelated.
- Major graph databases: Neo4j, Amazon Neptune, ArangoDB, Memgraph.
- Cypher query language (Neo4j's, widely understood).
- RDF and SPARQL (the alternative semantic-web stack).
- Common GRC graph patterns: control coverage analysis, risk impact propagation, evidence reachability.

In my experience, most GRC platforms quietly run on a relational schema and present a graph view in the UI. That is fine. You do not need a graph database to think in graphs.

**Free resources**

- **Neo4j "Graph Databases for Beginners" book.** Free PDF at neo4j.com.
- **Neo4j Sandbox** at neo4j.com/sandbox. Free hosted Neo4j. Run queries without installing.
- **Cypher query language manual** at neo4j.com/docs/cypher-manual.
- **The Apache Jena tutorial** at jena.apache.org for the RDF/SPARQL alternative.

**Do this**

In a Neo4j Sandbox, model a tiny GRC graph:
- 5 risks
- 10 controls
- 5 assets
- 3 frameworks
- Relationships: MITIGATES, AFFECTS, REQUIRES, OWNED_BY

Then write Cypher queries:
- Which risks have no mitigating controls?
- Which controls satisfy multiple framework references?
- For a given asset, what are the risks?

**Self-check questions**

- What is a graph database and how does it differ from a relational database?
- What is Cypher?
- Why might a GRC platform be built on a graph database? Why might it not be worth the migration cost?

## Week 19: SIEM, SOAR, and detection engineering

**Concepts to learn**

- **SIEM (Security Information and Event Management):** centralises logs, applies detection rules, alerts.
- **SOAR (Security Orchestration, Automation, and Response):** automates triage and response actions.
- Detection engineering: the discipline of writing, maintaining, and tuning detections. The "maintaining" part is where most teams drown.
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
- **SANS Reading Room** at sans.org/white-papers. Free papers on detection.
- **Florian Roth's blog and Sigma rules** for practitioner-grade examples.

**Do this**

Browse five Sigma rules from the SigmaHQ repository. Pick one detection (e.g. for credential access) and walk through what each part does. Then ask yourself: how would this rule get noisy in a real environment, and what would you tune?

**Self-check questions**

- What is the difference between SIEM and SOAR?
- What does ATT&CK enumerate?
- What is the Pyramid of Pain, and what does climbing it cost an attacker?
- What is a Sigma rule?

## Week 20: AI/ML governance and AI risk

**Concepts to learn**

- **NIST AI Risk Management Framework (AI RMF 1.0)** released January 2023: GOVERN, MAP, MEASURE, MANAGE functions.
- **ISO/IEC 42001:2023** AI Management System (AIMS).
- **EU AI Act** (Regulation 2024/1689): risk-based regulation. Prohibited, high-risk, limited-risk, minimal-risk classifications. General-purpose AI models. Phased application 2024-2027.
- **OWASP LLM Top 10:** risks specific to large language models (prompt injection, sensitive information disclosure, training data poisoning, and so on).
- Model cards and datasheets for datasets.
- AI bias, fairness, explainability concepts.
- Differential privacy, federated learning, homomorphic encryption (privacy-preserving ML basics).

AI governance is the area where the gap between guidance and operational reality is widest right now. Most teams have a policy. Few have working evidence. If you can build the evidence layer you will be unusually valuable for the next two to three years.

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

For your fictional product, identify one AI use case. Apply the NIST AI RMF MAP function: what context, intended uses, foreseeable misuse, and impacts? Write half a page. Be specific about misuse. "Could be used badly" is not a misuse case.

**Self-check questions**

- What are the four functions of NIST AI RMF?
- What is a "high-risk" AI system under the EU AI Act?
- What are three common LLM-specific risks?
- What is a model card and why does it matter to a procurement team?

---

# MONTH 6: SYSTEMS THINKING, ARCHITECTURE, AND CONSOLIDATION

You have the breadth. The last month is about thinking like an architect rather than a checklist-filler, and consolidating what you know into something you can defend.

## Week 21: Systems thinking for GRC

**Concepts to learn**

- The difference between problems and symptoms.
- Feedback loops: balancing and reinforcing.
- Stocks and flows.
- Emergence: how system behaviour is not the sum of part behaviours.
- Why "more controls" is not always more security. In one SaaS environment I worked in, the team added controls every quarter for two years and ended up with a 200-line register that nobody read and an audit posture worse than when they started.
- Why optimising one metric often degrades others.
- The principle of subsidiarity: decisions made at the lowest competent level.

**Free resources**

- **"Thinking in Systems" by Donella Meadows.** Available free as PDF in many legitimate places (the Sustainability Institute released excerpts). Read it. It will change how you think about programmes.
- **The Systems Thinker** at thesystemsthinker.com. Free articles.
- **John Sterman's MIT OpenCourseWare on system dynamics.** Free at ocw.mit.edu.
- **Cynefin Framework** by Dave Snowden. Free explainer videos on YouTube.

**Do this**

Pick one of your portfolio projects. Identify three feedback loops in the system it describes. Identify one place where local optimisation could harm the overall system. Most GRC programmes have at least one obvious example. Find yours.

**Self-check questions**

- What is the difference between a balancing and a reinforcing feedback loop?
- What is emergence?
- Why do controls accumulate even when they no longer add value? (Hint: removing a control is politically expensive.)

## Week 22: Architecture decision records and trade-off thinking

**Concepts to learn**

- The ADR (Architecture Decision Record) pattern: capture decisions, alternatives, and rationale.
- The Michael Nygard ADR template.
- Trade-off analysis: cost / benefit / risk for each option.
- Why "we chose X" without saying what you rejected is half a decision.
- The "rejected alternatives" section as the most useful section, which is exactly why most ADRs skimp on it.
- ADRs as living documents (superseded, not deleted).

**Free resources**

- **Michael Nygard's original ADR post** at cognitect.com/blog (search "Documenting Architecture Decisions"). Free.
- **The ADR GitHub repository** at github.com/joelparkerhenderson/architecture-decision-record. Many examples.
- **ThoughtWorks Tech Radar.** Free at thoughtworks.com/radar.

**Do this**

Re-read three ADRs from your existing portfolio. Pick one. Without re-reading what you wrote, list the alternatives you would consider and the trade-offs you would weigh. Then compare. The gap between your fresh thinking and what is on the page is your real architectural intuition.

**Self-check questions**

- What is the difference between a context and a decision in an ADR?
- Why is the "rejected alternatives" section the one people skip and the one auditors and new engineers care most about?
- When is an ADR superseded vs deleted?

## Week 23: Threat modelling

**Concepts to learn**

- STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege).
- DREAD (legacy, less used; know it exists).
- PASTA (Process for Attack Simulation and Threat Analysis).
- LINDDUN (privacy-focused).
- Attack trees.
- Microsoft's Threat Modelling Tool.
- The OWASP Threat Dragon free tool.
- The four-question framework (Adam Shostack): What are we working on? What can go wrong? What are we going to do about it? Did we do a good job?

In my experience threat modelling is the engineering practice GRC people most often talk about and least often sit through. Sit through one. Bring snacks.

**Free resources**

- **"Threat Modeling: Designing for Security" by Adam Shostack.** Paid book. His free articles cover the core thinking.
- **OWASP Threat Modeling cheat sheet** at owasp.org.
- **OWASP Threat Dragon** at owasp.org/www-project-threat-dragon. Free tool.
- **Microsoft Threat Modeling Tool** at microsoft.com. Free.
- **LINDDUN** at linddun.org. Free privacy-focused threat modelling.
- **MITRE ATT&CK and D3FEND** at mitre.org. Free.

**Do this**

Threat-model one of the systems described in your portfolio using STRIDE. For each STRIDE category, identify one specific threat and one mitigation. Then ask: which of these would actually get prioritised in a real engineering backlog, and which would sit there for two years?

**Self-check questions**

- What does STRIDE stand for?
- When is LINDDUN preferred over STRIDE?
- What are Adam Shostack's four questions?

## Week 24: Bringing it together and the next steps

**Concepts to learn**

- Reading published incident reports critically.
- Reading published court decisions and regulatory orders.
- Building a habit of continuous learning. The field moves. The people who stop learning stop being useful within two years.
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
3. Read one full incident post-mortem (Cloudflare or GitHub are good starts).
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

If you cannot answer any of these confidently, go back to the relevant week. No shame. The point is to be honest.

---

# AFTER MONTH 6: WHERE NEXT

You now have foundational fluency. Depth takes years and is best built through:

1. **Real work.** Apply for GRC, security, or compliance roles where you can practise. Theory locks in only through use. The first audit you actually sit through will teach you more than three months of reading.
2. **Specialisation.** Pick two areas you genuinely find interesting and go deep. Possibilities:
   - **Privacy:** add CIPP/E or CIPM (IAPP certifications, paid, ~£500 each, recognised globally).
   - **Cloud security:** add AWS Security Specialty or Microsoft SC-100 (paid).
   - **Audit:** add ISO 27001 Lead Auditor (paid, ~£2000 with a reputable provider).
   - **Risk management:** add CRISC or FAIR Foundational Analyst (paid).
3. **Build something real.** Pick one project from your portfolio and build a working prototype with code, tests, and CI. Even a small one. The conversation you can have about a working artefact is qualitatively different from the conversation about a document.
4. **Contribute.** Open issues, suggest improvements, write blog posts, answer questions on r/grc or r/cybersecurity.
5. **Find a mentor.** A senior GRC or security professional who has done the work. Most are willing to give an hour to someone clearly self-driven. Be specific about what you want from the conversation.

## Tracking your progress

A simple weekly journal answering three questions:

- What did I learn this week that I did not know last week?
- What can I now defend in conversation that I could not before?
- What still feels shaky?

Reviewed monthly. Adjusted accordingly.

## A note on certifications

The portfolio plus this curriculum gives you knowledge. Certifications give you a credential. Knowledge without a credential is invisible to many recruiters. A credential without knowledge gets exposed in ten minutes of conversation.

Pursue certifications when:
- You have the underlying knowledge.
- The certification is recognised in the roles you want.
- You can afford the time and money.

Skip certifications when:
- You are buying a credential to paper over shaky knowledge.
- The certification is unrecognised or vendor-paywalled.
- The opportunity cost (time spent) is better spent on real practice.

## A final honest note

This curriculum is six months of focused study. At the end you will not be senior. You will be credibly junior-to-mid: someone who can hold a serious conversation, ask good questions, and learn fast on the job. That is what employers at entry and intermediate levels actually hire for.

Beyond that, mastery is years of real work, real incidents, real audits, real arguments, and real consequences. The curriculum starts you on the road. The road itself is the rest of your career. Most of it is unglamorous. The interesting bits make up for it.

Good luck. Take it one week at a time.
