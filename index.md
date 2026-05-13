---
layout: default
title: Overview
---

# Overview

Fifteen non-technical GRC projects covering the frameworks, toolkits, and templates an organisation actually uses to run a credible programme. Not theory. The documents you end up writing, arguing about, and handing to an auditor at 9pm the night before fieldwork starts.

These are the artefacts a Head of GRC, CISO, Risk Manager, DPO, or Operational Resilience Lead would build and operate. The management-system layer that sits underneath the technology layer and gives the audit layer something to evidence. None of it is glamorous. Most of it is unloved until the first audit cycle, at which point everyone suddenly cares.

There is also a [six-month curriculum]({{ '/CURRICULUM/' | relative_url }}) covering every standard, regulation, and concept referenced across the portfolio, with free resources for each.

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

If you want the cumulative view rather than dipping in, read in this order. The sequencing is deliberate. Most teams fail at audit readiness because they tried to do step 7 before step 2.

**Foundations.** Risk and policy come first. Without a working risk view and a policy hierarchy that someone actually owns, the rest is decoration.
1. [Enterprise Risk Management Framework](01-enterprise-risk-management-framework/)
2. [Information Security Policy Framework](05-information-security-policy-framework/)

**Standards adoption.** Pick the standard the business needs, not the one that sounds impressive. Usually ISO 27001 for international SaaS, SOC 2 if the buyers are US-heavy. The mapping matrix saves you from doing the same control three times for three frameworks.
3. [ISO 27001 Implementation Toolkit](02-iso27001-implementation-toolkit/)
4. [Control Mapping Matrix](06-control-mapping-matrix/)

**Risk operations.** A register without a scenario library is a spreadsheet. A scenario library without a register is a thought experiment.
5. [Risk Register Templates](11-risk-register-templates/)
6. [Risk Scenario Library](07-risk-scenario-library-saas/)

**Audit and oversight.** SOC 2 and ISO 27001 fail on evidence management more than control design. This section is mostly about not getting caught short.
7. [Audit Readiness Playbook](03-audit-readiness-playbook/)
8. [Audit Finding Tracker Templates](12-audit-finding-tracker-templates/)
9. [Control Effectiveness Testing Templates](15-control-effectiveness-testing-templates/)
10. [Compliance Calendar](13-compliance-calendar/)

**Operational programmes.** Third-party risk and incident response are where regulators look first when something goes wrong. Get them off the back foot.
11. [Third-Party Risk Management Toolkit](04-third-party-risk-management-toolkit/)
12. [Vendor Due Diligence Tracker](14-vendor-due-diligence-tracker/)
13. [Incident Response Framework](09-incident-response-framework/)
14. [Business Continuity & DR Framework](10-business-continuity-dr-framework/)

**Visibility.** Metrics last. You cannot measure what you have not yet built, and dashboards built too early just track the wrong things.
15. [GRC Metrics & KPI Framework](08-grc-metrics-kpi-framework/)

# How each project is structured

Every project is a single `README.md`. The structure is consistent so you can skim:

- What the project is and what it produces
- The problem it solves, and what the symptoms look like before you fix it
- Business impact when done properly
- Framework alignment (every standard and regulation it touches)
- Components and deliverables, in concrete detail
- Real-world patterns that shape the design
- Common pitfalls, including the ones I have walked into myself
- Audit considerations
- Honest self-assessment of where the design is grounded in experience vs aspirational
- Free further reading

# Status

A working portfolio meant to be adapted, not copied. The templates assume a mid-size SaaS context by default. If you are running an enterprise bank or a two-person startup, the shape changes and you will need to cut or stretch accordingly. None of this is certified or pre-approved by any standards body. Treat it as a starting point that has survived contact with real audits, not a guarantee of passing yours.
