# Control Mapping Matrix

## What this project is

A comprehensive cross-walk between the major information security and privacy frameworks an organisation typically encounters: ISO/IEC 27001:2022 Annex A, NIST Cybersecurity Framework 2.0, NIST SP 800-53 Rev 5, SOC 2 Trust Services Criteria 2017 (revised 2022), CIS Controls v8.1, PCI DSS v4.0, GDPR (Article 32 and related), HIPAA Security Rule, Cloud Controls Matrix v4, and ISO/IEC 27701:2019.

The matrix lets a single control implementation be evidenced against multiple frameworks simultaneously. Done well, it is the difference between maintaining ten parallel control inventories (one per framework) and maintaining one canonical control set with framework labels.

## Problem this matrix solves

A growing SaaS company typically accumulates audit obligations.

- Year one: SOC 2 Type 1 because a customer asked.
- Year two: SOC 2 Type 2 because the customer asked again.
- Year three: ISO 27001 because European customers asked.
- Year four: HIPAA-aligned controls because healthcare customers arrived.
- Year five: PCI DSS because payments moved in-house.
- Year six: cyber insurance attestation, GDPR Art 32 evidence, vendor security questionnaires referencing CIS or NIST.

Without a mapping matrix, each framework runs as a separate workstream with separate evidence collection, separate dashboards, and separate audit fatigue. Engineers operating the same controls answer the same questions four times in different vocabularies.

A working matrix lets you say once: "We patch critical vulnerabilities within 14 days of vendor release. Here is the evidence." The matrix translates that single fact into:

- ISO 27001 A.8.8 Management of technical vulnerabilities.
- SOC 2 CC7.1.
- NIST CSF 2.0 PR.PS-02.
- NIST 800-53 SI-2 Flaw Remediation.
- CIS Control 7.4.
- PCI DSS 6.3.3.

One control. Six framework hits. One piece of evidence. One audit response.

## Business impact

- Sharply reduced cost of compliance: one control owner, one operating procedure, one piece of evidence answers many auditors.
- Faster sales cycles: customer security questionnaires (which mix vocabularies) are answered consistently from one source.
- Faster framework adoption: when a new framework arrives, the matrix shows what already exists and what is genuinely new.
- Cleaner gap analysis: gaps appear in a single dashboard rather than per-framework spreadsheets.
- Risk visibility: a control failure is visible against every framework it touches, not just one.
- Auditor confidence: a structured mapping signals operational maturity.

## Framework alignment

The matrix covers, at minimum, the following frameworks. Each is a column or row in the working spreadsheet.

- **ISO/IEC 27001:2022 Annex A** (93 controls in 4 themes).
- **ISO/IEC 27002:2022** implementation guidance is referenced but not mapped (it expands the same 93 controls).
- **NIST Cybersecurity Framework 2.0** (the 2024 revision: six functions including the new GOVERN, with ~106 subcategories).
- **NIST SP 800-53 Rev 5** (~1000+ controls in 20 families; this is the most granular).
- **SOC 2 Trust Services Criteria 2017 (revised 2022)** (Common Criteria + Availability + Processing Integrity + Confidentiality + Privacy categories; ~64 individual criteria).
- **CIS Controls v8.1** (18 controls and 153 safeguards, in three implementation groups).
- **PCI DSS v4.0** (12 requirements; ~400 detailed requirements).
- **HIPAA Security Rule** (Administrative, Physical, Technical Safeguards under 45 CFR 164.308-318).
- **Cloud Security Alliance Cloud Controls Matrix v4** (197 control specifications across 17 domains).
- **ISO/IEC 27701:2019** privacy extension (PII controllers and processors).
- **GDPR Article 32** (security of processing) and **Article 25** (data protection by design and default).
- Optional extensions for organisation context: **NIST SP 800-171** (CUI for federal contractors), **FedRAMP Moderate baseline**, **Australian Essential Eight**, **Singapore IM8**, **UK NCSC Cyber Essentials Plus**.

## How the matrix is structured

The matrix can be implemented as a spreadsheet, a database, or a feature in a GRC platform. The structure is the same regardless.

### Canonical control set

A single set of internal controls owned by the organisation. Each canonical control has:

- Internal control ID (e.g. CTRL-AC-001).
- Title.
- Description.
- Control type (preventive, detective, corrective, deterrent, compensating).
- Control owner.
- Operating frequency.
- Evidence source.
- Operating procedure reference.
- Linked policies and standards.

### Framework mappings

For each canonical control, mappings to one or more references in each framework. Mappings carry a strength indicator.

| Canonical control | ISO 27001 A | NIST CSF 2.0 | NIST 800-53 | SOC 2 | CIS v8.1 | PCI DSS v4 |
|---|---|---|---|---|---|---|
| CTRL-AC-001 Access reviews quarterly | A.5.18 (full), A.8.2 (full) | PR.AA-05 (full) | AC-2(j), AC-6(7) (full) | CC6.1, CC6.2, CC6.3 (full) | 6.1, 6.2, 6.7 (full) | 7.2.4 (full) |
| CTRL-VUL-002 Critical vulns patched within 14 days | A.8.8 (full) | PR.PS-02 (partial; CSF expects broader) | SI-2(2), SI-2(3) (partial) | CC7.1 (full) | 7.4 (full) | 6.3.3 (full, stricter timeframe than PCI requires) |
| CTRL-LOG-003 Centralised security event logging with 13-month retention | A.8.15, A.8.16 (full) | DE.CM-01, DE.AE-02 (full) | AU-2, AU-6, AU-11 (full) | CC7.2, CC7.3 (full) | 8.1, 8.2, 8.5 (full) | 10.5.1, 10.7 (full) |

### Mapping strength

- **Full:** the canonical control fully satisfies the framework reference.
- **Partial:** the canonical control satisfies most but not all of the framework reference; gap noted.
- **Compensating:** the canonical control compensates for a different framework requirement that is not directly met (typical for PCI compensating controls).
- **Not applicable:** the framework reference does not apply to this canonical control.

The matrix is **bidirectional**. Given a framework reference, you can find which canonical controls map to it and assess whether the reference is fully covered.

### Coverage gaps

The matrix surfaces gaps automatically.

- Framework references with no mapped canonical control = a gap.
- Canonical controls not mapped to any current framework = potential consolidation candidate or future-proofing control.
- Partial mappings = work to do to achieve full coverage.

A typical first-pass mapping for a SaaS company at SOC 2 + ISO 27001 maturity reveals 80-90 percent coverage when extended to NIST CSF; coverage of NIST 800-53 Moderate baseline often surprises people, sometimes higher than expected because many fine-grained 800-53 controls are picked up by the broader ISO controls.

## Example mappings (illustrative subset)

### Identity and access management

| Capability | ISO 27001 A | NIST CSF 2.0 | NIST 800-53 | SOC 2 | CIS v8.1 | PCI DSS v4 | HIPAA |
|---|---|---|---|---|---|---|---|
| Joiner/mover/leaver process | A.6.1, A.5.16, A.8.2 | PR.AA-01, PR.AA-04 | PS-3, PS-4, PS-5, AC-2 | CC6.2, CC6.3 | 6.1, 6.2 | 7.2.5, 8.2 | §164.308(a)(3), §164.308(a)(4) |
| MFA on all administrative access | A.8.5 | PR.AA-03 | IA-2(1), IA-2(2) | CC6.6 | 6.5 | 8.4.2, 8.4.3 | §164.308(a)(5)(ii)(D) |
| Least privilege | A.8.2 | PR.AA-05 | AC-6 | CC6.1 | 6.8 | 7.2.1 | §164.308(a)(4) |
| Privileged session recording | A.8.15 | DE.CM-03 | AC-2(11), AU-12 | CC6.1, CC7.2 | 8.5 | 10.2.1.5 | §164.312(b) |

### Vulnerability management

| Capability | ISO 27001 A | NIST CSF 2.0 | NIST 800-53 | SOC 2 | CIS v8.1 | PCI DSS v4 |
|---|---|---|---|---|---|---|
| Asset inventory current | A.5.9, A.5.12 | ID.AM-01, ID.AM-02 | CM-8, PM-5 | CC7.1 | 1.1, 2.1 | 12.5.1 |
| Vulnerability scanning | A.8.8 | DE.CM-09 | RA-5 | CC7.1 | 7.5 | 11.3.1 |
| Patching SLAs by severity | A.8.8 | PR.PS-02 | SI-2 | CC7.1 | 7.3, 7.4 | 6.3.3 |
| Penetration testing annual | A.8.8 | DE.AE-04, ID.RA-01 | CA-8 | CC4.1 | 18.1 | 11.4 |

### Incident response

| Capability | ISO 27001 A | NIST CSF 2.0 | NIST 800-53 | SOC 2 | CIS v8.1 | PCI DSS v4 |
|---|---|---|---|---|---|---|
| IR policy approved | A.5.24 | RS.MA-01 | IR-1 | CC7.4 | 17.1 | 12.10.1 |
| IR plan tested annually | A.5.27 | RS.MA-02 | IR-3 | CC7.4 | 17.6 | 12.10.2 |
| Severity classification | A.5.25 | RS.MA-03 | IR-4(2) | CC7.4 | 17.4 | 12.10.4 |
| Breach notification | A.6.8 | RS.CO-02, RS.CO-03 | IR-6 | CC7.5 | n/a | 12.10.5 |
| Post-incident review | A.5.27 | RC.IM-01 | IR-4(3) | CC7.5 | 17.8 | 12.10.6 |

## Components and deliverables

### 1. The mapping matrix itself

A spreadsheet (or database export) with the canonical control set and all framework mappings. Versioned and dated.

### 2. Mapping methodology document

Defines how mappings are made: who decides, what evidence supports a mapping, how partial mappings are handled, how the matrix is reviewed.

### 3. Per-framework coverage reports

For each framework, a report showing:
- Total framework references.
- Fully covered count.
- Partially covered count.
- Not covered count.
- List of gaps with proposed treatment.

### 4. Per-control framework profile

For each canonical control, a one-page summary showing every framework reference it supports. Useful for control owners who do not want to learn ten frameworks.

### 5. Change management process

When frameworks update (NIST CSF moved from 1.1 to 2.0 in 2024, ISO 27001 moved from 2013 to 2022), the matrix must be re-baselined. Documented process for:

- Tracking framework version changes.
- Diffing old to new.
- Updating mappings.
- Communicating changes to control owners.
- Republishing the matrix.

### 6. Customer-questionnaire response template

When customer security questionnaires arrive in mixed framework vocabulary ("how do you address NIST 800-53 AC-2 and CIS Control 6 and SOC 2 CC6.2?"), the matrix produces a single coherent answer.

### 7. SoA generator

For ISO 27001 specifically, the matrix generates the Statement of Applicability column "implementation reference" automatically, pointing to canonical controls.

## Real-world lessons baked into this design

- **Frameworks overlap heavily but not perfectly.** ISO 27001 A.8.5 (Secure authentication) and SOC 2 CC6.6 are very close but not identical. The "partial" strength flag is essential.
- **Granularity differs wildly.** NIST 800-53 SI-2 has multiple control enhancements; ISO 27001 A.8.8 is one bullet. A one-to-many mapping is normal.
- **Some frameworks are orthogonal.** NIST CSF is outcome-oriented; NIST 800-53 is control-oriented. Both reference the same underlying controls but cut differently. The matrix should cope.
- **Vocabulary matters.** "Information assets" (ISO) and "information system components" (NIST) and "in-scope systems" (SOC 2) and "system components" (PCI) all mean similar things in different contexts. The matrix uses canonical vocabulary internally.
- **Mappings published by standards bodies are useful but partial.** NIST publishes some CSF-to-800-53 mapping, and the AICPA publishes some SOC 2-to-NIST mapping. CIS publishes Controls-to-many mappings. None is complete; all are starting points.

## Common pitfalls

- **One-to-one obsession.** Forcing a single mapping where multiple are correct.
- **Mapping by name.** Mapping based on titles rather than reading the actual control text.
- **Stale mappings.** Failing to refresh when a framework version changes.
- **Implementation drift.** The control description changes in the canonical set but not in the mappings.
- **Treating mapping as compliance.** A mapping does not prove the control operates. The mapping says "if this control operates, it satisfies these references." Operating evidence is separate.
- **Auditor-only audience.** Building the matrix for audits only and not making it usable by control owners or sales teams.

## Audit considerations

Auditors increasingly expect mature organisations to maintain such a matrix.

- Show me your control library.
- For SOC 2 CC6.1, show me which of your internal controls map to it.
- For ISO 27001 A.8.5, walk me through the implementation.
- For a customer-facing claim of NIST CSF alignment, show me the basis.

The matrix is not itself audit evidence (operating evidence is). But it dramatically reduces the time auditors spend correlating answers across frameworks, and it improves their confidence that you operate one programme rather than ten parallel ones.

## How this matrix would actually be implemented

A 6-month rollout for a SaaS company that already has SOC 2 and is adding ISO 27001 and aligning to NIST CSF.

**Month 1.** Establish canonical control set by extracting from existing SOC 2 control matrix. Define mapping methodology.

**Month 2.** Map canonical controls to ISO 27001 Annex A 2022. Identify gaps. Draft remediation.

**Month 3.** Map canonical controls to NIST CSF 2.0. Identify gaps (CSF GOVERN function commonly reveals gaps in policy and supply-chain risk).

**Month 4.** Layer in CIS Controls and PCI DSS where applicable. Generate coverage reports.

**Month 5.** Build customer-questionnaire response template. Train security and sales engineering teams.

**Month 6.** First audit cycle uses the matrix. Refine based on findings.

## What I have done in this space and what I have not

I have studied the structure and content of every framework listed. I have built mapping logic from text rather than blindly copying others' published mappings.

I have not personally maintained a control matrix at scale through multiple framework revisions. I have not had to negotiate with an auditor over a "partial" mapping during fieldwork. I have not used the matrix to defeat a particularly bad customer questionnaire. Those experiences would shape the practical sections, especially around mapping strength definitions.

This is a learning portfolio entry.

## Further reading

- **NIST CSF 2.0 (2024).** Free at nist.gov/cyberframework. NIST publishes a CSF-to-800-53 informative reference and a CSF-to-CIS reference.
- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov.
- **AICPA SOC 2 mapping resources.** Free at aicpa-cima.com.
- **CIS Controls v8.1 mapping spreadsheets.** Free at cisecurity.org.
- **Cloud Security Alliance Cloud Controls Matrix.** Free at cloudsecurityalliance.org.
- **HITRUST CSF.** A commercial framework that includes a very large mapping; useful reference even without HITRUST certification.
- **ISO/IEC 27002:2022.** Paid, but BSI and IT Governance publish summaries with control numbering.
- **SCF (Secure Controls Framework)** at securecontrolsframework.com is a free, exhaustive multi-framework mapping resource.

## Status

Learning portfolio. Matrix structure defined, methodology documented, sample mappings populated. Not maintained as a live operational artefact.
