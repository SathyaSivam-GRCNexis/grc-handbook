# GRC Non-Tech Projects

Fifteen non-technical Governance, Risk, and Compliance projects covering the frameworks, toolkits, and templates an organisation needs to run a credible GRC programme alongside the technology platforms in the companion repository.

These are the documents and decision frameworks a Head of GRC, CISO, Risk Manager, DPO, or Operational Resilience Lead would actually build and operate. They form the management-system layer that gives the technology layer its purpose and the audit layer its evidence. In my experience most programmes fail here long before they fail at the technical layer. The policies exist, nobody reads them, ownership is fuzzy, and the auditor finds out in week one.

This repository also contains `CURRICULUM.md`, a six-month, week-by-week study plan covering every standard, regulation, and concept referenced across both the tech and non-tech portfolios. Every resource is free unless explicitly flagged otherwise.

## Projects

| # | Project | What it is |
|---|---|---|
| 1 | `01-enterprise-risk-management-framework` | ERM framework end to end: methodology, taxonomy, scoring, register, treatment workflows, appetite, governance, three-lines model |
| 2 | `02-iso27001-implementation-toolkit` | ISO 27001:2022 implementation set: scope, policy, SoA, risk methodology, all 93 Annex A controls, audit cycle, certification roadmap |
| 3 | `03-audit-readiness-playbook` | From "we have controls" to "auditor is here next Tuesday": calendar, evidence locker, sample handling, interview prep |
| 4 | `04-third-party-risk-management-toolkit` | Vendor classification, three-tier questionnaire suite, contractual clause library, onboarding workflow, monitoring, exit |
| 5 | `05-information-security-policy-framework` | Four-level hierarchy (policy, standard, procedure, guideline), lifecycle, exception register, awareness, starter library of 25+ documents |
| 6 | `06-control-mapping-matrix` | Cross-walk across ISO 27001, NIST CSF 2.0, NIST 800-53, SOC 2, CIS v8.1, PCI DSS v4, HIPAA, CCM, with mapping methodology |
| 7 | `07-risk-scenario-library-saas` | 40+ SaaS-focused risk scenarios with likelihood, impact, controls, real-world examples, and tabletop versions |
| 8 | `08-grc-metrics-kpi-framework` | KPIs, KRIs, KCIs, and KGIs catalogue with definitions, sources, dashboards, cadences, and audiences |
| 9 | `09-incident-response-framework` | NIST 800-61-aligned IR framework: severity model, lifecycle, playbook library, breach notification register across multiple jurisdictions |
| 10 | `10-business-continuity-dr-framework` | Operational resilience framework: BIA, impact tolerances, recovery strategies, DR plans, crisis management, testing programme |
| 11 | `11-risk-register-templates` | Five register variants from startup-minimal to enterprise-quantified (FAIR-aligned) with field models and sample populated entries |
| 12 | `12-audit-finding-tracker-templates` | Lightweight template-based finding tracker: intake, severity, lifecycle, validation discipline, repeat-finding management |
| 13 | `13-compliance-calendar` | Consolidated calendar of audits, certifications, regulatory submissions, contractual obligations, and operational compliance |
| 14 | `14-vendor-due-diligence-tracker` | Operational tracker for vendor pipeline, evidence locker, conditional approvals, reassessments, and incident log |
| 15 | `15-control-effectiveness-testing-templates` | Test plan templates, sampling guidance, evidence patterns, validator independence, continuous monitoring, reporting |

## Reading order

If you want the cumulative view rather than dipping in, read in this order. The sequencing is deliberate, not alphabetical. Most teams that stall in their first audit cycle stalled because they jumped to evidence collection before the risk view and the policy hierarchy were settled.

**Foundations.**
1. Enterprise Risk Management Framework (#1)
2. Information Security Policy Framework (#5)

**Standards adoption.**
3. ISO 27001 Implementation Toolkit (#2)
4. Control Mapping Matrix (#6)

**Risk operations.**
5. Risk Register Templates (#11)
6. Risk Scenario Library (#7)

**Audit and oversight.**
7. Audit Readiness Playbook (#3)
8. Audit Finding Tracker Templates (#12)
9. Control Effectiveness Testing Templates (#15)
10. Compliance Calendar (#13)

**Operational programmes.**
11. Third-Party Risk Management Toolkit (#4)
12. Vendor Due Diligence Tracker (#14)
13. Incident Response Framework (#9)
14. Business Continuity & DR Framework (#10)

**Visibility.**
15. GRC Metrics & KPI Framework (#8)

## How each project is structured

Every project is a single `README.md` covering:

- What the project is and what it produces
- The problem it solves, with the symptoms you can spot before you fix it
- Business impact when done properly
- Framework alignment (every standard and regulation it touches)
- Components and deliverables in concrete detail
- Real-world patterns and lessons that shape the design
- Common pitfalls, including ones I have walked into
- Audit considerations
- Honest self-assessment of where the design is grounded in experience vs aspirational
- Free further reading

## Voice and approach

Plain English. Present tense. Opinionated where it matters. Honest about trade-offs and limits. The aim is "this is how I would build it, here is why, here is what I have not yet had to live through" rather than vendor brochure prose.

A few standing opinions you will see repeated:

- Most SMBs do not need a GRC platform in year one. A shared drive and a disciplined owner beats a half-used tool.
- SOC 2 fails on evidence management more than on control design.
- Risk scoring models are usually overcooked at the start. A 5x5 grid that everyone uses beats a FAIR model that two people understand.
- Policies that nobody references are worse than no policies at all. They create false assurance.
- Third-party risk is where regulators look first after an incident. Treat the questionnaire process as a programme, not an inbox.

## Curriculum

`CURRICULUM.md` is a six-month, twenty-four-week study plan covering everything referenced across both portfolios. Every resource cited is free unless explicitly marked. The curriculum covers:

- Foundations: governance, risk, control, audit fundamentals
- Core frameworks: ISO 27001/27002, SOC 2, NIST CSF 2.0, NIST 800-53, GDPR
- Specific regulations: FedRAMP, DORA, PCI DSS v4, HIPAA, NIS2, DPDP Act 2023
- Technologies: OPA/Rego, Kyverno/Gatekeeper, Sigstore, SBOMs, CNAPP/CIEM, knowledge graphs, SIEM/SOAR
- Architecture and design patterns: Zero Trust, threat modelling, ADRs, AI governance
- Systems thinking and consolidation

The curriculum exists to make the portfolio defensible. Knowing what is in the documents is the starting line. Being able to argue them out with an auditor or a sceptical engineer is the goal.

## Companion materials

- The technology architecture portfolio sits in the companion repository `grc-tech-projects`, covering eleven platforms that operationalise the frameworks documented here.

## Status

A working portfolio meant to be adapted, not copied. The defaults assume a mid-size SaaS context. If you are at a two-person startup, you will cut hard. If you are at a regulated bank, you will need to extend. Documents are detailed enough to start adoption work. None of this is certified or pre-approved by any standards body, and nothing here guarantees you pass an audit. Treat it as a starting point that has survived contact with real audits.
