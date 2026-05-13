# ISO 27001 Implementation Toolkit

## What this is

A working set of documents, templates and workflows for designing, implementing, certifying and maintaining an ISMS compliant with ISO/IEC 27001:2022. The kind of thing a Head of GRC, ISMS Manager or implementation consultant would actually use, not the glossy template pack sold off the shelf.

It covers the full standard. The management-system clauses (4 to 10) and the 93 Annex A controls grouped into the four 2022 themes. It is opinionated about what real implementation looks like, because generic kits are exactly why most first audits go badly.

## What this toolkit is trying to fix

First-time ISO 27001 attempts tend to fall into one of three traps.

1. **The off-the-shelf template pack.** Polished, exhaustive, and obviously not related to how the company works. Auditors spot this in the first hour. The Stage 2 either fails or passes only after months of rework.
2. **Writing everything from scratch.** Three to six months disappear into reinventing wheels. Energy is spent before the ISMS work actually starts.
3. **Treating it as a security project.** ISO 27001 is a management-system standard. Clauses 4 through 10 (context, leadership, planning, support, operation, performance evaluation, improvement) matter at least as much as the technical Annex A controls. Most Stage 1 failures I have seen are management-system failures, not control failures. No proper Statement of Applicability, no risk treatment plan tied to a methodology, no evidence of management review.

This toolkit gives an organisation a real working ISMS structure to adapt rather than copy, and one that maps to what a UKAS-accredited certification body actually examines.

## Why organisations bother

- Certification opens doors into enterprise procurement. Many security questionnaires collapse to a single tick-box for ISO 27001.
- Forces internal discipline that the company benefits from beyond the certificate. Defined ownership, change control, risk-based decisions.
- Establishes a baseline that SOC 2, ISO 27701, ISO 27017, ISO 27018 and TISAX extend rather than duplicate.
- Effectively a precondition for selling into UK and European public sector, financial services, healthcare and most regulated industries.
- Material for cyber insurance underwriting and usually translates into better premiums.

## Framework alignment

- **ISO/IEC 27001:2022** is the certifiable standard.
- **ISO/IEC 27002:2022** is the implementation guidance for Annex A.
- **ISO/IEC 27005:2022** for the risk methodology.
- **ISO/IEC 27003:2017** for management-system implementation guidance.
- **ISO/IEC 27004:2016** for monitoring, measurement and evaluation.
- **ISO/IEC 27007:2020** for ISMS auditing guidance.
- The 2022 revision moved Annex A from 114 controls in 14 categories to **93 controls in 4 themes** (organisational, people, physical, technological). Existing implementations had until 31 October 2025 to transition. This toolkit assumes the 2022 revision throughout.

## What sits in the toolkit

### Mandatory documented information

ISO 27001 explicitly requires the following. An auditor will ask for each.

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

Defines the ISMS boundary. Products, services, locations, business units, processes, technologies, data flows. Explicit exclusions with justification.

A pattern I have seen during ISO 27001 readiness: scope gets drawn narrowly to make the certificate easier to pass. Then sales discovers customers want the whole company covered and the certificate is commercially useless. The toolkit forces the scope conversation in the first month so it is decided deliberately, not by drift.

### 2. Information security policy

Short, three to five pages, board-approved. States the organisation's commitment, the ISMS, the risk approach, principal objectives and responsibilities. The umbrella under which the topic policies sit.

### 3. Risk assessment methodology

How risks are identified, analysed, evaluated and recorded. Includes the criteria for risk acceptance, tied to risk appetite. Aligned with the ERM framework where one exists.

### 4. Risk treatment methodology and plan

For every risk above acceptance threshold, a treatment decision (modify, retain, avoid, share) and the plan to implement it. Links to the specific Annex A controls being applied.

### 5. Statement of Applicability (SoA)

The single most important document in the toolkit. Lists every Annex A control, whether it is included or excluded, the justification, the implementation status, and a reference to the evidence demonstrating implementation.

A strong opinion: the SoA is not a document, it is a live spreadsheet. Auditors care about consistent operation, not pretty PDFs. During Stage 2 they will pull a sample of "included" controls and test them against reality. If the SoA says control 8.16 (Monitoring activities) is implemented and the auditor cannot find evidence that monitoring actually happens, that is a major nonconformity. Polished wording does not save you.

The 2022 SoA covers all 93 controls across:
- **A.5 Organisational** (37 controls)
- **A.6 People** (8 controls)
- **A.7 Physical** (14 controls)
- **A.8 Technological** (34 controls)

### 6. Information security objectives

SMART objectives at ISMS level. For example: "Reduce mean time to patch critical vulnerabilities to 7 days by Q4." Reviewed at management review. Tied to KPIs.

### 7. Internal audit programme

Schedule, scope and methodology for internal ISMS audits. Coverage of every clause and every Annex A control over a defined cycle, typically annual. Findings tracked to closure.

### 8. Management review template

Template and recurring meeting structure for management review (Clause 9.3). Required inputs: previous-action status, changes in external and internal issues, ISMS performance (nonconformities, monitoring results, audit results, fulfilment of objectives), risk results, opportunities for improvement. Outputs: decisions on improvement and resourcing.

Management review must happen at planned intervals. Annually is the floor. Quarterly is more realistic for a maturing ISMS.

### 9. Nonconformity and corrective action register

For nonconformities from internal audit, external audit, incidents or near-misses. Root-cause analysis, corrective action, verification of effectiveness.

### 10. Annex A control implementation guidance

For each of the 93 controls, a one-page note on what the control requires, what evidence demonstrates implementation and common pitfalls. Selected examples:

- **A.5.7 Threat intelligence.** What counts as evidence (subscriptions, ISACs, vendor advisories) and how to demonstrate use (decisions traceable to inputs).
- **A.5.23 Information security for use of cloud services.** Cloud security policy, provider due diligence, defined responsibilities under shared-responsibility models.
- **A.5.30 ICT readiness for business continuity.** Alignment with BCDR, ICT-specific recovery plans, testing.
- **A.6.3 Information security awareness, education and training.** Programme structure, frequency, role-specific training, completion evidence, effectiveness measurement.
- **A.8.9 Configuration management.** Baseline definitions, change control, drift detection.
- **A.8.16 Monitoring activities.** What is monitored, alert triage, response times.
- **A.8.23 Web filtering** (new in 2022). Technical control to reduce exposure to malicious web content.
- **A.8.28 Secure coding** (new in 2022). Coding standards, training, code-review evidence, automated checks.

### 11. Internal audit checklist

Control-by-control checklist with evidence prompts. Used by internal audit and as preparation for external audit.

### 12. Stage 1 and Stage 2 readiness assessments

Self-assessment templates that mirror what the certification body will examine.

- **Stage 1 (documentation review).** Does the documented ISMS exist and is it complete? Run 6 to 8 weeks before the real Stage 1.
- **Stage 2 (implementation review).** Does the ISMS actually work? Run 4 to 6 weeks before the real Stage 2.

### 13. Communications plan

Stakeholder map, message templates for awareness campaigns, leadership talking points, customer communications when the certificate is awarded.

### 14. Continual improvement register

A separate register for opportunities for improvement, distinct from nonconformities. Required by Clause 10.1.

## How implementation actually unfolds

A realistic timeline for a 100 to 500 person SaaS company starting from scratch.

**Month 1. Foundation.**
- Define scope. Get board sponsorship. Run an executive briefing.
- Draft and approve the information security policy.
- Establish ISMS roles and the ISMS forum.

**Months 2 to 3. Risk and gap analysis.**
- Asset inventory.
- Risk assessments (workshop-based, technology-supported).
- Annex A gap analysis.
- First draft SoA.

**Months 4 to 7. Treatment and control implementation.**
- Treatment plan built from the gap analysis.
- Implement missing controls. This is the largest chunk of work and budget, and where engineering pushback usually appears. Most of the time the resistance is about how the control is implemented, not whether it should exist. Be ready to negotiate technical specifics.
- Develop or revise supporting policies (acceptable use, access control, cryptography, supplier security, incident management).
- Roll out training programme.

**Months 8 to 9. Operate and evidence.**
- Operate the ISMS for at least three months to generate evidence (monitoring data, internal-audit findings, management-review minutes). This is non-negotiable. Auditors look for evidence over time, not a snapshot taken the week before.
- Run first internal audit. Address findings.
- Run first management review.

**Month 10. Stage 1.**
- Certification body reviews documentation. Findings are usually minor (SoA tweaks, missing references, undocumented decisions).

**Month 12. Stage 2.**
- Certification body tests implementation against documentation. Close any majors before certification.
- **Certificate issued.**

**Year 2 onwards.** Surveillance audits annually for two years. Recertification at three years. Continual improvement, risk reviews and internal audits on cadence.

## Where teams stall

In my experience the same problems recur.

- **Evidence freshness.** Controls operate, but evidence is scattered across Notion, Jira, Slack, screenshots on someone's laptop. The week before the auditor visits, the GRC team is hunting for artefacts. The fix is a control-to-evidence map maintained continuously, not a pre-audit scramble.
- **The SoA drifts.** Controls get renumbered, owners change, policies are updated. The SoA stays the same. The auditor finds the gap in under an hour.
- **Management review by email.** No real attendance, no real decisions, minutes constructed retrospectively. Auditors test this by reading minutes and interviewing attendees. They will spot it.
- **Heroes problem.** One person knows where everything is. They take leave during surveillance. Audit goes sideways.
- **Awareness training as click-through.** Completion is 100 percent, retention is zero. A.6.3 asks for effectiveness, not just completion.

Common pattern during ISO 27001 readiness: the controls are mostly there, but the documentation does not describe what is actually being done. Engineering implements something sensible. Policy says something different. Auditor catches it in 10 minutes. Easier to update the policy to match reality, where reality is sound, than to wedge engineering into the policy.

## Lessons baked into the toolkit

- **The SoA is the lever.** Every other document either drives or evidences SoA entries. Get the SoA right and the audit narrows. Get it wrong and the audit becomes archaeology.
- **Documented information does not mean printed.** A wiki page, a Jira queue, a dashboard or a Git-controlled markdown file can all be valid documented information provided you can produce them on request.
- **Internal audit is not paperwork.** Genuinely independent internal audit, not done by the people who wrote the controls, catches real problems and lets you fix them before the external auditor does.
- **Management review is a board ritual.** Not the security team talking to itself. Senior management must actually attend, engage and decide. Auditors test this by reading minutes.
- **Excluding controls is fine if you justify it.** Excluding A.7.1 Physical security perimeters because the company is fully remote is legitimate. Excluding A.8.28 Secure coding because the company says so is not.

## Common pitfalls

- **Documentation theatre.** Polished policies nobody in operations has read.
- **Scope sandbagging.** Certifying only the GRC team and selling the certificate as company-wide.
- **Risk theatre.** A risk assessment with 200 risks, all medium, no treatment plans, never reviewed.
- **Single point of knowledge.** ISMS dependent on one person.
- **Tool obsession.** Buying a GRC platform and assuming it is the ISMS. The platform supports the ISMS. The ISMS is the people, decisions and processes.
- **Ignoring Clause 4.** Skipping context-of-the-organisation work. Auditors notice when it was done in five minutes.

## What an auditor will look at

- Scope statement and how it lines up with the actual business.
- Approved information security policy and its currency.
- Risk methodology and outputs.
- The SoA and evidence for every "included" control.
- Evidence of training, awareness and competence.
- Internal audit reports for at least one full cycle.
- Management review minutes for at least one cycle.
- Nonconformity register and evidence of closure.
- A sample of risks traced to treatment plans and to operating controls.
- A sample of incidents and how they were managed.
- How the ISMS is measured.

## What I have done and what I have not

I have studied ISO/IEC 27001:2022, ISO/IEC 27002:2022 and the related guidance in detail. I have assembled this toolkit the way I would assemble it for a real implementation.

I have not personally led an organisation through Stage 1 and Stage 2 to certification. I have not negotiated audit findings with a UKAS lead auditor. Those experiences would refine the templates, particularly around how aggressive auditors are about specific evidence forms.

This is a learning portfolio entry. It demonstrates understanding of every component of an ISO 27001 implementation, not operational delivery experience.

## Further reading

- **ISO/IEC 27001:2022** and **ISO/IEC 27002:2022.** Paid standards. Free overviews at iso.org.
- **BSI Group ISO 27001 implementation guidance** at bsigroup.com.
- **IT Governance UK** for blog content on the 2022 revision differences.
- **UKAS accreditation requirements** at ukas.com to understand what makes a certificate credible.
- **A Practical Guide to the New ISO 27001:2022** by Vivian Cracknell (book, paid, but worth it).
- **ENISA** for free guidance on risk methodologies that complement ISO 27005.

## Status

Learning portfolio. Toolkit covers all mandatory documented information and all 93 Annex A controls. Templates ready for adaptation. Not used in a real certification engagement.
