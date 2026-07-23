---
title: Highlight — Recruiting
hide_footer: true
layout: default
toc: false
permalink: /highlight-recruiting
classes: page--project page--highlight-recruiting
---

<a href="/" style="font-size:0.8em; font-weight:400; color:#999; text-transform:uppercase; letter-spacing:0.08em; text-decoration:none; transition:color 0.2s ease;" onmouseover="this.style.color='#333'" onmouseout="this.style.color='#999'">← Back</a>

# Getting Recruiting on Rails
*From Manual Spreadsheets to Automated System*
{: .notice}

![Getting Recruiting on Rails — Highlight project overview](/assets/img/hl-rec-00-hero.jpg)

---

<div class="case-meta">
  <div class="case-meta__item">
    <div class="case-meta__label">Role</div>
    <div class="case-meta__value">UX Design &middot; Systems Design &middot; Research</div>
  </div>
  <div class="case-meta__item">
    <div class="case-meta__label">Scope</div>
    <div class="case-meta__value">
      <span class="scope-tag">Discovery</span>
      <span class="scope-tag">Research</span>
      <span class="scope-tag">Design</span>
      <span class="scope-tag">Launch</span>
    </div>
  </div>
  <div class="case-meta__item">
    <div class="case-meta__label">Duration</div>
    <div class="case-meta__value">Jan 2024&ndash;Present</div>
  </div>
  <div class="case-meta__item">
    <div class="case-meta__label">Team</div>
    <div class="case-meta__value">
      <span class="team-tooltip" data-tooltip="Justin Pocta">Design</span>
      <span class="meta-sep">&middot;</span>
      <span class="team-tooltip" data-tooltip="Andrew Shin, Emily Sutton (PM) · Deirdre Norris (VP Product)">Product</span>
      <span class="meta-sep">&middot;</span>
      <span class="team-tooltip" data-tooltip="Andrew Sidesinger · Brandon Reno · Matt Magnotta · Seth McCarthy · Sam Hanes · Russell Kennington · Sophie McGarity · Michael Funk">Engineering</span>
    </div>
  </div>
</div>

## Context

I joined **Highlight** in January 2024 during a pivotal shift — the company was evolving from a research services model toward a dedicated software product. I was brought on to help build the internal systems that would support that growth, starting with recruiting.

![Context: What Customer Brings → What Highlight Offers](/assets/img/hl-rec-01-context.jpg)

---

## The Problem

Highlight was wanting to scale fast, but their core recruiting operations were still running like a small agency—manual, disconnected, and unsustainable.

**Customers were not even using the app much yet** — Actual processes in the background involved so much PII that customers were only offered non-functional inputs, essentially a repeat of information gathered during the Sales kickoff process.

**Manual download and spreadsheet management** — User data had to be gathered for projects from multiple CSVs, which then became a challenge of juggling IDs and knowing who gets what.

**Criteria selection was frustrating and lacked clarity** — Poor labeling, a tedious multi-step process, and unclear options made targeting inefficient.

---

## My Process

- **Mapped internal workflows** — Gained understanding of how recruiting happens: CSV up/downloads, email address exports to send recruit emails, monitoring manual "dashboards"
- **Gathered stakeholder input** — Discussions with C-Level, Product, Customer Success, and Engineering on pain points and constraints, and to gather buy-in and support
- **Audited data collection** — Analyzed how recruit data was gathered and identified efficiency barriers
- **Diagrams to express concepts and mental models** — As words tend to get very muddled, I leverage simple visuals to confirm structures and flows
- **Iterative build-out** — Long collaborative process to layer in additional functionality and value

### Mapping Workflows

![Process: Mapping Workflows — FigJam workflow diagrams](/assets/img/hl-rec-04-mapping.jpg)

### Diagramming & Wireframing

![Process: Diagramming and Wireframing — quick wireframes with PM/Eng, confirming recruit structures with CE](/assets/img/hl-rec-05-wireframing.jpg)

---

## Before: Recruiting via Downloads

![Before: Recruiting via downloads — old CSM portal with Download Results and Export CSV](/assets/img/hl-rec-06-before.jpg)

The previous process required internal staff to run a query, download a CSV, manually manage IDs across spreadsheets, export email addresses, and send recruit emails entirely outside the platform. There was no visibility into status, no audit trail, and no scalable path forward.

---

## Early Explorations

![Early Explorations — Mad Libs audience builder and criteria sidebar](/assets/img/hl-rec-08-early-explorations.jpg)

Two early directions: a sentence-style audience builder that made the query logic legible, and a persistent sidebar for inserting criteria — the latter started to feel like the stronger foundation.

### Deeper Dive: Criteria & Answer Selection

![Exploration: Deeper dive on Criteria/Answer Selection](/assets/img/hl-rec-07-criteria-exploration.jpg)

Criteria selection was one of the most painful parts of the old experience. These explorations tested different models — from a card-based Global/Test Group structure with tag-style answers on the left, to a "Configure Dimensions" panel on the right that let users browse and select criteria by category. The sidebar approach won out: it gave users persistent visibility into what they'd configured without burying it in a modal flow.

---

## Developing Further: Layering in Test Groups

![Developing further: Layering in Test Groups](/assets/img/hl-rec-09-test-groups.jpg)

The sidebar evolved into the primary interaction surface — giving users at-a-glance visibility of all Test Groups and their criteria without disrupting the main flow. Language and labeling went through multiple rounds of internal and external usability testing before landing.

---

## Production

### Customer Version

![Production: Customer version — evolved from Admin App's UX](/assets/img/hl-rec-10-production-customer.jpg)

The customer-facing version evolved from the Admin App's UX patterns, adapted for customers building their own projects. With a clean "Qualifying Criteria" sidebar and Test Group management, customers could now actively configure their own recruiting instead of relying on internal handoffs.

### Admin Version

![Production: Admin version — full recruiting workflow](/assets/img/hl-rec-11-production-admin.jpg)

The admin app gives the internal team full control — Define and Finalize tabs, Test Group management with match counts, "Start Recruiting" / "Complete Recruit" actions, and the same criteria sidebar architecture refined through months of iteration.

---

## Results, So Far

**Strong team adoption** — Quick uptake due to clear value, though edge cases in project requirements continue to drive iterations and process refinement.

**Customer engagement increased** — With a functional app, alongside a huge update across all features, customers are able to actively build their own projects instead of relying on manual handoffs.*

**Downstream improvements unlocked** — QC tools, progress tracking, reduced human error, and streamlined CSV workflows.

**Next phase** — Automated project and survey completion tracking.

*\* this is a work in progress but we're closing in as these tools rely less on internal setup*

<div style="display:flex; justify-content:space-between; align-items:center; padding:1em 0 3em;">
  <span></span>
  <a href="/opengov" style="font-size:0.8em; font-weight:400; color:#999; text-transform:uppercase; letter-spacing:0.08em; text-decoration:none; transition:color 0.2s ease;" onmouseover="this.style.color='#333'" onmouseout="this.style.color='#999'">Next →</a>
</div>

<a href="/opengov" class="project-nav-arrow project-nav-arrow--right" aria-label="Next project"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg></a>
