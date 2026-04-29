# ISO 27001 Implementation Toolkit

## What this project is

A complete set of documents, templates, and workflows an organisation needs to design, implement, certify, and maintain an Information Security Management System (ISMS) compliant with ISO/IEC 27001:2022. This is what a Head of GRC, ISMS Manager, or external implementation consultant would hand to a company that has decided to pursue ISO 27001 certification for the first time.

The toolkit covers the full standard, both the management-system clauses (4 to 10) and Annex A controls (the 93 controls grouped into four themes in the 2022 revision). It is opinionated about what a real implementation looks like rather than a generic certification kit you can buy off the shelf.

## Problem this toolkit solves

Companies pursuing ISO 27001 for the first time usually fall into one of three traps.

1. **They buy a generic template pack from a consultancy.** It is comprehensive, polished, and bears no resemblance to how the company actually works. The auditor sees that immediately and the certification either fails or passes only after months of rework.
2. **They build everything from scratch.** Three to six months disappear into reinventing wheels. Energy is exhausted before the actual ISMS work begins.
3. **They under-scope the standard.** They treat it as a security project. ISO 27001 is a management-system standard. The clauses on context, leadership, planning, support, operation, performance evaluation, and improvement are at least as important as the technical Annex A controls. Companies that miss this fail Stage 1 audit because they have no Statement of Applicability, no risk treatment plan tied to a methodology, and no evidence of management review.

This toolkit gives an organisation a real, working ISMS structure that can be adapted rather than copied, and that maps cleanly to what a UKAS-accredited certification body will look for.

## Business impact

- Certification opens doors to enterprise customers who require ISO 27001 in procurement.
- Reduces sales cycle friction. Many security questionnaires have a single tick-box for ISO 27001 that replaces 50 detailed questions.
- Forces internal discipline that benefits the company beyond the certificate (defined ownership, change control, risk-based decisions).
- Establishes a baseline that other certifications (SOC 2, ISO 27701, ISO 27017, ISO 27018, TISAX) extend rather than duplicate.
- Generally non-negotiable for selling into UK and European public sector, financial services, healthcare, and any regulated industry.
- Material for cyber insurance underwriting, often resulting in better premiums.

## Framework alignment

- **ISO/IEC 27001:2022** is the certifiable standard.
- **ISO/IEC 27002:2022** is the implementation guidance for Annex A controls.
- **ISO/IEC 27005:2022** for the risk-management methodology.
- **ISO/IEC 27003:2017** for management-system implementation guidance.
- **ISO/IEC 27004:2016** for monitoring, measurement, analysis, and evaluation.
- **ISO/IEC 27007:2020** for guidelines on auditing ISMSs.
- The 2022 revision reduced Annex A from 114 controls in 14 categories down to **93 controls in 4 themes** (organisational, people, physical, technological). Existing implementations had until 31 October 2025 to transition; this toolkit assumes the 2022 revision throughout.

## Components and deliverables

The toolkit is organised around the structure ISO 27001 requires.

### Mandatory documented information (the "must have" list)

ISO 27001 explicitly requires the following documents to exist. An auditor will ask for each.

1. **Scope of the ISMS** (Clause 4.3)
2. **Information security policy** (Clause 5.2)
3. **Information security risk assessment process** (Clause 6.1.2)
4. **Information security risk treatment process** (Clause 6.1.3)
5. **Statement of Applicability (SoA)** (Clause 6.1.3 d)
6. **Information security objectives** (Clause 6.2)
7. **Evidence of competence** (Clause 7.2)
8. **Documented information determined as necessary for ISMS effectiveness** (Clause 7.5.1 b)
9. **Operational planning and control documentation** (Clause 8.1)
10. **Risk assessment results** (Clause 8.2)
11. **Risk treatment results** (Clause 8.3)
12. **Monitoring and measurement results** (Clause 9.1)
13. **Internal audit programme and results** (Clause 9.2)
14. **Management review results** (Clause 9.3)
15. **Nonconformities and corrective actions** (Clause 10.2)

### 1. Scope document

Defines the boundary of the ISMS. Includes which products, services, locations, business units, processes, technologies, and data flows are in scope, and explicit exclusions with justification.

A common mistake is to scope the certificate too narrowly to make it easier to pass and then discover the certificate is commercially useless because customers want the whole company covered. The toolkit pushes the conversation about scope into the first month so this is decided deliberately.

### 2. Information security policy

A short (3-5 page) board-approved policy that states the organisation's commitment to information security, the ISMS, the risk approach, the principal objectives, and the responsibilities. This is the umbrella under which all other policies sit.

### 3. Risk assessment methodology

Documents how risks will be identified, analysed, evaluated, and recorded. Includes the criteria for risk acceptance (linked to the risk appetite). Aligned with the ERM framework where one exists.

### 4. Risk treatment methodology and plan

For every risk above acceptance threshold, a treatment decision (modify, retain, avoid, share) and the plan to implement that decision. Links to specific Annex A controls being applied.

### 5. Statement of Applicability (SoA)

The single most important document in the entire toolkit. Lists every Annex A control, states whether it is included or excluded, the justification for that decision, the implementation status, and a reference to the document or evidence demonstrating implementation.

A working SoA is a living spreadsheet, not a static document. Auditors test the SoA against reality during Stage 2 audit. If the SoA says control 8.16 (Monitoring activities) is implemented and the auditor finds no monitoring evidence, that is a major nonconformity.

The 2022 SoA template covers all 93 controls across:
- **A.5 Organisational controls** (37 controls)
- **A.6 People controls** (8 controls)
- **A.7 Physical controls** (14 controls)
- **A.8 Technological controls** (34 controls)

### 6. Information security objectives

SMART objectives (specific, measurable, achievable, relevant, time-bound) at the ISMS level. Examples: "Reduce mean time to patch critical vulnerabilities to 7 days by Q4." Reviewed at management review. Tied to KPIs.

### 7. Internal audit programme

Schedule, scope, and methodology for internal ISMS audits. Coverage of every clause and every Annex A control over a defined cycle (typically annual). Audit findings tracked through to closure.

### 8. Management review template

Template and recurring meeting structure for management review (Clause 9.3). Required inputs: status of previous actions, changes in external and internal issues, feedback on ISMS performance (nonconformities, monitoring results, audit results, fulfilment of objectives), risk-assessment and risk-treatment results, opportunities for improvement. Outputs: decisions on continual improvement and resource needs.

Management review must happen at planned intervals, typically at least annually but often quarterly in maturing ISMSs.

### 9. Nonconformity and corrective action register

Template for recording nonconformities (whether from internal audit, external audit, incidents, or near-misses), root-cause analysis, corrective actions, and verification of effectiveness.

### 10. Annex A control implementation guidance

For each of the 93 controls, a one-page guide explaining what the control requires, what evidence demonstrates implementation, and common pitfalls. Selected examples:

- **A.5.7 Threat intelligence:** what counts (subscriptions, ISACs, vendor advisories), how to demonstrate use (decisions traceable to intelligence inputs).
- **A.5.23 Information security for use of cloud services:** cloud security policy, due diligence on providers, defined responsibilities under shared-responsibility models.
- **A.5.30 ICT readiness for business continuity:** alignment with BCDR programme, ICT-specific recovery plans, testing.
- **A.6.3 Information security awareness, education and training:** programme structure, frequency, role-specific training, evidence of completion, measurement of effectiveness.
- **A.8.9 Configuration management:** baseline definitions, change control, drift detection.
- **A.8.16 Monitoring activities:** what is monitored, how alerts are triaged, response times.
- **A.8.23 Web filtering** (new in 2022): technical control to reduce exposure to malicious web content.
- **A.8.28 Secure coding** (new in 2022): coding standards, training, code-review evidence, automated checks.

### 11. Internal audit checklist

A control-by-control audit checklist with evidence-collection prompts. Used by internal audit and as preparation for external audit.

### 12. Stage 1 and Stage 2 readiness assessments

Self-assessment templates that mirror what the certification body will examine.

- **Stage 1 (documentation review):** does the documented ISMS exist and is it complete? Run this 6-8 weeks before the real Stage 1.
- **Stage 2 (implementation review):** does the ISMS work in practice? Run this 4-6 weeks before the real Stage 2.

### 13. Communications plan

Stakeholder map, message templates for awareness campaigns, leadership talking points, customer communications when the certificate is awarded.

### 14. Continual improvement register

Living register of opportunities for improvement, separate from nonconformities. Required by Clause 10.1.

## How implementation actually unfolds

A realistic timeline for a 100-500 person SaaS company starting from scratch.

**Month 1: Foundation.**
- Define scope. Get board sponsorship. Run an executive briefing.
- Draft and approve the information security policy.
- Establish ISMS roles and the ISMS forum.

**Months 2-3: Risk and gap analysis.**
- Conduct full asset inventory.
- Run risk assessments (workshop-based, technology-supported).
- Perform Annex A gap analysis against current state.
- Draft the first Statement of Applicability.

**Months 4-7: Treatment and control implementation.**
- Build the risk treatment plan from the gap analysis.
- Implement missing controls. This is the largest chunk of work and budget.
- Develop or revise the supporting policies (acceptable use, access control, cryptography, supplier security, incident management, etc.).
- Roll out training programme.

**Months 8-9: Operate and evidence.**
- Operate the ISMS for at least three months to generate evidence (Clause 9.1 monitoring data, internal-audit findings, management-review minutes).
- Run first internal audit. Address findings.
- Run first management review. Generate minutes and actions.

**Month 10: Stage 1 audit.**
- Certification body reviews documentation.
- Address findings (typically minor: SoA tweaks, missing references, undocumented decisions).

**Month 12: Stage 2 audit.**
- Certification body tests implementation against documentation.
- Address findings (must close any majors before certification).
- **Certification awarded.**

**Year 2 onwards.**
- Surveillance audit annually for two years.
- Recertification audit at three years.
- Continual improvement, risk reviews, internal audits running on cadence.

## Real-world lessons baked into this toolkit

- **The SoA is the lever.** Every other document either drives or evidences SoA entries. Get the SoA right and the audit narrows enormously. Get it wrong and the audit becomes archaeology.
- **Documented information does not mean printed.** A wiki page, a JIRA ticket queue, a dashboard, or a Git-controlled markdown file can all be valid documented information provided you can produce them on request.
- **Internal audit is not a paperwork exercise.** Genuinely independent internal audit (not done by the people who wrote the controls) catches real problems and is what lets you fix them before the external auditor does.
- **Management review is a board ritual.** It is not the security team talking to itself. Senior management must actually attend, actually engage, actually make decisions. Auditors test this by reading minutes.
- **Excluding controls is fine if you justify it.** Excluding A.7.1 Physical security perimeters because the company is fully remote is a legitimate exclusion. Excluding A.8.28 Secure coding because the company says so is not.

## Common pitfalls

- **Documentation theatre.** Polished policies that nobody in operations has ever read.
- **Scope sandbagging.** Certifying only the GRC team and presenting the certificate as company-wide.
- **Risk theatre.** A risk assessment with 200 risks, all medium, no treatment plans, never reviewed.
- **Single point of knowledge.** ISMS dependent on one person; when they leave, the next surveillance audit is a disaster.
- **Tool obsession.** Buying a GRC platform and assuming it is the ISMS. The platform supports the ISMS. The ISMS is the people, decisions, and processes.
- **Ignoring Clause 4.** Skipping context-of-the-organisation work. Clause 4 is foundational and auditors notice when it has been done in five minutes.

## Audit considerations

A certification body will examine, at minimum:

- Scope statement and its alignment with the actual business.
- Approved information security policy and its currency.
- Risk assessment and treatment methodology and outputs.
- The SoA and evidence for every "included" control.
- Evidence of training, awareness, and competence.
- Internal audit reports for at least one full cycle.
- Management review minutes for at least one cycle.
- Nonconformity register and evidence of closure.
- Sample of risks traced to treatment plans and to operating controls.
- Sample of incidents and how they were managed.
- Performance evaluation: how is the ISMS measured?

## What I have done in this space and what I have not

I have studied ISO/IEC 27001:2022, ISO/IEC 27002:2022, and the related guidance standards in detail. I have built this toolkit as I would assemble it for a real implementation.

I have not personally led an organisation through Stage 1 and Stage 2 audits to certification. I have not negotiated audit findings with a UKAS lead auditor. Those experiences would refine the templates here, particularly around how aggressive auditors are about specific evidence forms.

This is a learning portfolio entry. It demonstrates understanding of every component of an ISO 27001 implementation, not operational delivery experience.

## Further reading

- **ISO/IEC 27001:2022** and **ISO/IEC 27002:2022.** Paid standards. Free overviews at iso.org.
- **BSI Group ISO 27001 implementation guidance** at bsigroup.com (free articles).
- **IT Governance UK** publishes useful blog content explaining the 2022 revision differences.
- **UKAS accreditation requirements** at ukas.com to understand what makes a certificate credible.
- **A Practical Guide to the New ISO 27001:2022** by Vivian Cracknell (book, paid, but excellent).
- **ENISA** publishes free guidance on risk management methodologies that complement ISO 27005.

## Status

Learning portfolio. Toolkit covers all mandatory documented information and all 93 Annex A controls. Templates ready for adaptation. Not used in a real certification engagement.
