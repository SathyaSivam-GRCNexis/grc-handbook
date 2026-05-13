# Control Mapping Matrix

## What this is

A cross-walk between the major security and privacy frameworks a SaaS organisation ends up dealing with: ISO/IEC 27001:2022 Annex A, NIST Cybersecurity Framework 2.0, NIST SP 800-53 Rev 5, SOC 2 Trust Services Criteria 2017 (revised 2022), CIS Controls v8.1, PCI DSS v4.0, GDPR (Article 32 and friends), HIPAA Security Rule, Cloud Controls Matrix v4, and ISO/IEC 27701:2019. India teams will also bump into DPDP and SEBI/RBI overlays sitting on top of these.

The point of the matrix is simple. One control, mapped against many frameworks, evidenced once. Without it, you end up running ten parallel control inventories with ten sets of evidence and ten sets of audit fatigue. I have watched teams do exactly that, and it is a slow waste of everyone's time.

## Problem this matrix solves

A growing SaaS company picks up audit obligations on a fairly predictable schedule.

- Year one: SOC 2 Type 1 because a customer asked.
- Year two: SOC 2 Type 2 because the customer asked again.
- Year three: ISO 27001 because European customers asked.
- Year four: HIPAA-aligned controls because healthcare customers arrived.
- Year five: PCI DSS because payments moved in-house.
- Year six: cyber insurance attestation, GDPR Art 32 evidence, vendor security questionnaires written in CIS or NIST vocabulary.

Without a mapping matrix, each framework runs as its own workstream. Separate evidence collection. Separate dashboards. Engineers operating the same controls answer the same questions four times in four different vocabularies. By the time the fourth auditor turns up asking about patching, the engineering lead is short-tempered and the evidence pack is inconsistent across frameworks.

A working matrix lets you say once: "We patch critical vulnerabilities within 14 days of vendor release. Here is the ticket data and the scanner export." The matrix then translates that single fact into:

- ISO 27001 A.8.8 Management of technical vulnerabilities.
- SOC 2 CC7.1.
- NIST CSF 2.0 PR.PS-02.
- NIST 800-53 SI-2 Flaw Remediation.
- CIS Control 7.4.
- PCI DSS 6.3.3.

One control. Six framework hits. One piece of evidence. One audit response. That is the prize.

## Why it actually pays back

- Cost of compliance drops. One control owner, one operating procedure, one piece of evidence answers many auditors.
- Sales cycles get faster. Customer security questionnaires are written in mixed vocabularies, and the matrix lets sales engineering answer them consistently from a single source.
- New framework adoption is quicker. When a customer demands HITRUST or a regulator publishes a new guideline, the matrix shows what is already covered and what is genuinely new.
- Gaps appear in one place rather than scattered across spreadsheets.
- A control failure surfaces against every framework it touches, not just the one whose audit is next.
- Auditors notice. A structured mapping signals that you operate one programme, not ten.

## Framework alignment

The matrix covers, at minimum, the following. Each is a column or row in the working sheet.

- **ISO/IEC 27001:2022 Annex A** (93 controls across 4 themes).
- **ISO/IEC 27002:2022** implementation guidance is referenced but not mapped separately (same 93 controls, just expanded).
- **NIST Cybersecurity Framework 2.0** (the 2024 revision: six functions including the new GOVERN, about 106 subcategories).
- **NIST SP 800-53 Rev 5** (over a thousand controls across 20 families; the most granular of the lot).
- **SOC 2 Trust Services Criteria 2017 (revised 2022)** (Common Criteria plus Availability, Processing Integrity, Confidentiality, Privacy; around 64 individual criteria).
- **CIS Controls v8.1** (18 controls and 153 safeguards, across three implementation groups).
- **PCI DSS v4.0** (12 requirements that expand to around 400 detailed sub-requirements).
- **HIPAA Security Rule** (Administrative, Physical, Technical Safeguards under 45 CFR 164.308-318).
- **Cloud Security Alliance Cloud Controls Matrix v4** (197 control specifications across 17 domains).
- **ISO/IEC 27701:2019** privacy extension (PII controllers and processors).
- **GDPR Article 32** (security of processing) and **Article 25** (data protection by design and default).
- Optional overlays depending on context: **NIST SP 800-171** (CUI for federal contractors), **FedRAMP Moderate baseline**, **Australia Essential Eight**, **Singapore IM8**, **UK NCSC Cyber Essentials Plus**, **DPDP Act 2023** for India.

## How the matrix is built

Spreadsheet, database, or feature in a GRC tool. The structure is the same.

### Canonical control set

One internal control set, owned by the organisation. Each canonical control carries:

- Internal control ID (for example CTRL-AC-001).
- Title.
- Description.
- Control type (preventive, detective, corrective, deterrent, compensating).
- Control owner. Named individual, not a team mailbox.
- Operating frequency.
- Evidence source.
- Operating procedure reference.
- Linked policies and standards.

The owner field is where most matrices rot. If it points at a generic "Engineering" or "Security Team", nobody updates it when the team reshuffles, and twelve months later nobody knows who runs the control.

### Framework mappings

For each canonical control, mappings to one or more references in each framework. Each mapping carries a strength flag.

| Canonical control | ISO 27001 A | NIST CSF 2.0 | NIST 800-53 | SOC 2 | CIS v8.1 | PCI DSS v4 |
|---|---|---|---|---|---|---|
| CTRL-AC-001 Access reviews quarterly | A.5.18 (full), A.8.2 (full) | PR.AA-05 (full) | AC-2(j), AC-6(7) (full) | CC6.1, CC6.2, CC6.3 (full) | 6.1, 6.2, 6.7 (full) | 7.2.4 (full) |
| CTRL-VUL-002 Critical vulns patched within 14 days | A.8.8 (full) | PR.PS-02 (partial; CSF expects broader) | SI-2(2), SI-2(3) (partial) | CC7.1 (full) | 7.4 (full) | 6.3.3 (full, stricter than PCI requires) |
| CTRL-LOG-003 Centralised security event logging with 13-month retention | A.8.15, A.8.16 (full) | DE.CM-01, DE.AE-02 (full) | AU-2, AU-6, AU-11 (full) | CC7.2, CC7.3 (full) | 8.1, 8.2, 8.5 (full) | 10.5.1, 10.7 (full) |

### Mapping strength

- **Full:** the canonical control fully satisfies the framework reference.
- **Partial:** satisfies most of it; the gap is noted explicitly.
- **Compensating:** answers a different framework requirement that is not directly met. PCI lives here often.
- **Not applicable:** the reference does not apply to this control.

The matrix is **bidirectional**. Given a framework reference, you should be able to ask "which of our canonical controls cover this, and is it fully covered" and get an answer in seconds.

### Coverage gaps

Gaps surface automatically once the structure is right.

- Framework references with no mapped canonical control. That is a gap.
- Canonical controls not mapped to any current framework. Consolidation candidate, or future-proofing.
- Partial mappings. Work outstanding to reach full coverage.

A first-pass mapping for a SaaS company already at SOC 2 plus ISO 27001 maturity usually shows 80 to 90 percent coverage when extended to NIST CSF. NIST 800-53 Moderate often surprises people in a good way, because many fine-grained 800-53 controls get picked up by the broader ISO controls.

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

A spreadsheet or database export with the canonical control set and all framework mappings. Versioned and dated. Never trust an undated copy.

### 2. Mapping methodology document

Who decides a mapping is valid. What evidence supports it. How partials are handled. How often the matrix gets reviewed. Without this, two people will map the same control differently next quarter.

### 3. Per-framework coverage reports

For each framework, a short report showing total references, fully covered, partially covered, not covered, and gaps with proposed treatment.

### 4. Per-control framework profile

A one-page summary per canonical control listing every framework reference it supports. Control owners do not want to learn ten frameworks. This sheet gives them a reason not to.

### 5. Change management process

When a framework moves, the matrix needs re-baselining. NIST CSF went from 1.1 to 2.0 in 2024. ISO 27001 jumped from 2013 to 2022 and re-themed Annex A. Document how to:

- Track framework version changes.
- Diff old to new.
- Update mappings.
- Tell control owners what changed.
- Republish.

The 2022 ISO transition caught a lot of teams out. The new theme structure plus the renumbering meant matrices built against 2013 looked tidy but pointed at nothing useful.

### 6. Customer-questionnaire response template

Questionnaires arrive in mixed vocabulary. "How do you address NIST 800-53 AC-2 and CIS Control 6 and SOC 2 CC6.2?" The matrix produces a single coherent answer instead of three slightly different ones.

### 7. SoA generator

For ISO 27001, the matrix generates the Statement of Applicability "implementation reference" column automatically by pointing at canonical controls. Saves a week of copy-paste at audit time.

## Lessons baked into this design

- **Frameworks overlap heavily but never perfectly.** ISO 27001 A.8.5 (Secure authentication) and SOC 2 CC6.6 are close but not identical. The "partial" flag exists for a reason.
- **Granularity differs wildly.** NIST 800-53 SI-2 has multiple control enhancements; ISO 27001 A.8.8 is one bullet. One-to-many is normal.
- **Some frameworks are orthogonal.** NIST CSF is outcome-oriented. NIST 800-53 is control-oriented. They reference the same underlying controls but cut differently. The matrix has to cope.
- **Vocabulary matters.** "Information assets" (ISO), "information system components" (NIST), "in-scope systems" (SOC 2), "system components" (PCI). Same idea, different words. Pick one internally and stick to it.
- **Mappings published by standards bodies are useful starting points, no more.** NIST publishes CSF-to-800-53. AICPA publishes SOC 2-to-NIST. CIS publishes Controls-to-many. None is complete. All need reading and adjustment.

## Common pitfalls

- **One-to-one obsession.** Forcing a single mapping where multiple references are correct. Usually a sign someone is mapping by control title rather than by reading the actual text.
- **Mapping by name.** The classic. "Both say 'access control', they must match." They often do not.
- **Stale mappings.** A framework version moves and the matrix does not. Six months later, half the references point at withdrawn controls.
- **Implementation drift.** The canonical control description changes; the mappings do not get re-checked.
- **Treating mapping as compliance.** A mapping does not prove a control operates. It says "if it operates, it satisfies these references." Operating evidence is a separate problem.
- **Auditor-only audience.** Building the matrix purely for audits, then ignoring the fact that sales engineering and control owners need to use it too.
- **No owner for the matrix itself.** Cross-walks rot fast without an owner. In my experience, this is the single most reliable way to kill an otherwise good matrix. Assign a named person, review quarterly.

## What auditors will ask

- Show me your control library.
- For SOC 2 CC6.1, show me which internal controls map to it.
- For ISO 27001 A.8.5, walk me through implementation.
- For a customer-facing claim of NIST CSF alignment, show me the basis.

The matrix is not audit evidence in itself. Operating evidence is. But a good matrix dramatically cuts the time auditors spend correlating answers, and it shifts their default mood from suspicious to cooperative.

## How a rollout actually goes

A 6-month plan for a SaaS company that already has SOC 2 and is adding ISO 27001 plus NIST CSF alignment.

**Month 1.** Extract canonical control set from the existing SOC 2 matrix. Write the mapping methodology. This sets the language for everything else.

**Month 2.** Map canonical controls to ISO 27001 Annex A 2022. Identify gaps. Draft remediation. Expect surprises in supplier and supply-chain controls.

**Month 3.** Map to NIST CSF 2.0. The new GOVERN function commonly reveals gaps in policy and supply-chain risk, even at mature organisations.

**Month 4.** Layer in CIS Controls and PCI DSS where applicable. Generate coverage reports.

**Month 5.** Build the customer-questionnaire response template. Train sales engineering. This is where the matrix earns its keep commercially.

**Month 6.** First audit cycle uses the matrix. Refine based on findings.

## What I have done in this space and what I have not

I have studied the structure and content of every framework listed. I have built mapping logic from the actual control text rather than copying others' published mappings.

I have not personally maintained a control matrix at scale through multiple framework revisions. I have not had to negotiate with an auditor over a "partial" mapping during fieldwork. Those experiences would shape the practical sections, especially around mapping strength definitions.

This is a learning portfolio entry.

## Further reading

- **NIST CSF 2.0 (2024).** Free at nist.gov/cyberframework. NIST also publishes a CSF-to-800-53 informative reference and a CSF-to-CIS reference.
- **NIST SP 800-53 Rev 5.** Free PDF at csrc.nist.gov.
- **AICPA SOC 2 mapping resources.** Free at aicpa-cima.com.
- **CIS Controls v8.1 mapping spreadsheets.** Free at cisecurity.org.
- **Cloud Security Alliance Cloud Controls Matrix.** Free at cloudsecurityalliance.org.
- **HITRUST CSF.** Commercial framework with a very large built-in mapping; useful reference even without HITRUST certification.
- **ISO/IEC 27002:2022.** Paid, but BSI and IT Governance publish summaries with control numbering.
- **SCF (Secure Controls Framework)** at securecontrolsframework.com. Free, exhaustive multi-framework mapping resource. Worth knowing about before reinventing.

## Status

Learning portfolio. Matrix structure defined, methodology documented, sample mappings populated. Not maintained as a live operational artefact.
