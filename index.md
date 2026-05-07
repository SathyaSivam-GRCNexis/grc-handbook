---
layout: default
title: Overview
---

# Overview

A portfolio of fifteen non-technical Governance, Risk, and Compliance projects covering the frameworks, toolkits, methodologies, and templates an organisation needs to run a credible GRC programme alongside the technology platforms in the [companion repository](https://github.com/{{ site.companion_repo }}).

These are the documents, processes, and decision frameworks that a Head of GRC, CISO, Risk Manager, DPO, or Operational Resilience Lead would build, adopt, and operate. Together they make up the management-system layer that gives the technology layer its purpose and the audit layer its evidence.

This site also hosts a [six-month curriculum]({{ '/CURRICULUM/' | relative_url }}) covering every standard, regulation, technology, and concept referenced across both portfolios, with free learning resources for each.

<h1 id="projects">Projects</h1>

<div class="project-grid">
{% for p in site.projects %}
  <a class="project-card" href="{{ p.slug | append: '/' | relative_url }}">
    <div class="head"><span class="num">{{ p.num }}</span><span class="cat">{{ p.category }}</span></div>
    <h3>{{ p.title }}</h3>
    <p>{{ p.summary }}</p>
    <span class="open">Open project &rarr;</span>
  </a>
{% endfor %}
</div>

<h1 id="reading-order">Reading order</h1>

Read in this order if you want the cumulative view rather than dipping into one project.

**Foundations.**
1. [Enterprise Risk Management Framework](01-enterprise-risk-management-framework/)
2. [Information Security Policy Framework](05-information-security-policy-framework/)

**Standards adoption.**
3. [ISO 27001 Implementation Toolkit](02-iso27001-implementation-toolkit/)
4. [Control Mapping Matrix](06-control-mapping-matrix/)

**Risk operations.**
5. [Risk Register Templates](11-risk-register-templates/)
6. [Risk Scenario Library](07-risk-scenario-library-saas/)

**Audit and oversight.**
7. [Audit Readiness Playbook](03-audit-readiness-playbook/)
8. [Audit Finding Tracker Templates](12-audit-finding-tracker-templates/)
9. [Control Effectiveness Testing Templates](15-control-effectiveness-testing-templates/)
10. [Compliance Calendar](13-compliance-calendar/)

**Operational programmes.**
11. [Third-Party Risk Management Toolkit](04-third-party-risk-management-toolkit/)
12. [Vendor Due Diligence Tracker](14-vendor-due-diligence-tracker/)
13. [Incident Response Framework](09-incident-response-framework/)
14. [Business Continuity & DR Framework](10-business-continuity-dr-framework/)

**Visibility.**
15. [GRC Metrics & KPI Framework](08-grc-metrics-kpi-framework/)

# How each project is structured

Each project is a single comprehensive `README.md` covering:

- What the project is and what it produces
- The problem it solves and its symptoms
- Business impact when done well
- Framework alignment (every standard and regulation it touches)
- Components and deliverables in concrete detail
- Real-world cases and lessons that shape the design
- Common pitfalls
- Audit considerations
- Honest self-assessment of where the design is grounded vs aspirational
- Free further reading

# Voice and approach

Plain English. Present tense. Opinionated. Honest about trade-offs and limits. The aim is "this is how I would build it, here is why, here is what I have not yet learned from experience" rather than generic best-practice prose.

# Status

A working portfolio of frameworks, toolkits, and templates designed to be adapted by organisations rather than copied. Documents are detailed enough to start adoption work; they are not certified or pre-approved by any standards body.
