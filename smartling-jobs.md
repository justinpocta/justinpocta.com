---
title: Jobs Dashboard
hide_footer: true
layout: default
classes: page--jobs
toc: false
toc_sticky: true
toc_label: "Project Index"
toc_icon: "tasks"
galleryInitial:
  - url: ../assets/img/Smartling-Jobs-jobs-2018.png
    image_path: ../assets/img/Smartling-Jobs-jobs-2018.png
    alt: ""
    title: ""
  - url: ../assets/img/Smartling-Jobs-jobs+2019-05.png
    image_path: ../assets/img/Smartling-Jobs-jobs+2019-05.png
    alt: ""
    title: ""
galleryIterations:
  - url: /assets/img/Smartling-Jobs-Image.jpeg+2.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+2.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+4.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+4.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+9.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+9.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+10.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+10.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+11.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+11.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-toggle+Image.jpeg+5.png
    image_path: /assets/img/Smartling-Jobs-toggle+Image.jpeg+5.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+12.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+12.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-toggle+Image.jpeg+6.png
    image_path: /assets/img/Smartling-Jobs-toggle+Image.jpeg+6.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg+14.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg+14.png
    alt: " "
    title: " "
  - url: /assets/img/Smartling-Jobs-Image.jpeg.png
    image_path: /assets/img/Smartling-Jobs-Image.jpeg.png
    alt: " "
    title: " "
galleryFinal:
  - url: /assets/img/Smartling-Jobs-Progress+Overhaul.png
    image_path: /assets/img/Smartling-Jobs-Progress+Overhaul.png
    alt: " "
    title: " "
---
<div class="project-intro-grid">
<div class="project-intro-grid__content" markdown="1">

<span class="project-subheader">Jobs Dashboard, Extreme Makeover</span>
# Rebooting Jobs

Smartling use revolves around daily requests for original content to be translated, edited, reviewed and published.

It is fast paced and involves sophisticated workflow processes, with large teams and varying user permission levels, project structures, toolsets. Tracking these job requests is a critical piece of the day to day.

</div>
<aside class="project-intro-grid__sidebar">
  <img src="/assets/img/Smartling-Logo.png" alt="Smartling" class="sidebar-logo">
  <div class="sidebar-meta">
    <div class="sidebar-meta__item">
      <div class="sidebar-meta__label">My Role</div>
      <div class="sidebar-meta__value">Product Designer, Smartling</div>
    </div>
    <div class="sidebar-meta__item">
      <div class="sidebar-meta__label">Duration</div>
      <div class="sidebar-meta__value">Jan 2020&ndash;Aug 2020</div>
    </div>
    <div class="sidebar-meta__item">
      <div class="sidebar-meta__label">Contributions</div>
      <div class="sidebar-meta__value">
        <span class="contrib-tag">Discovery</span>
        <span class="contrib-tag">Research</span>
        <span class="contrib-tag">Design</span>
        <span class="contrib-tag">Launch</span>
      </div>
    </div>
    <div class="sidebar-meta__item">
      <div class="sidebar-meta__label">Teams</div>
      <div class="sidebar-meta__value">
        <span class="team-tag team-tooltip" data-tooltip="Justin Pocta">Design</span>
        <span class="meta-sep">&middot;</span>
        <span class="team-tag team-tooltip" data-tooltip="Sophia Lazare (PM)">Product</span>
        <span class="meta-sep">&middot;</span>
        <span class="team-tag team-tooltip" data-tooltip="Jeremy Shankle · Dmitry Masley · Oleksandr Tymchenko · Pavlo Myrotiuk · Valerii Linetskyi · Sergey Chichulin · Yurii Beiko · Xiaoyun Yang · Rich Tam · Dominic DeMarco">Engineering</span>
      </div>
    </div>
  </div>
</aside>
</div>

## Discovering Deep Roots

We had an array of challenges build up over 10 years of the company existence. Due to the varied nature of permissions, needs, and wishes between customers and translators, as well as internal effects like pricing models and different APIs, to our surprise, a large number of versions of the “Jobs” page existed, handled by multiple teams with different features and only floating further and further away from one another.

There were multiple smaller attempts in the past to improve the Jobs page, however in early 2020, I had begun to work with our new Product Manager, Sophia Lazare, who had joined us from the Language Services team. Her focus on the translation agency side of the business helped to give our team attention to a part of the platform that often was run outside of the focus on our customer-centric team. 

The initial goal was simply to help update the translator Jobs page—but after discussions with the tech team leads and with the CEO being brought into the conversation about the time wasted by splintered code, we had focus and support to improve problems we had all seen in portions. The mission was now to make life easier for everyone on our team as well as our user base, both customer and translators. It was time to unify the Jobs page.

---

## Differences in Roles, Permissions and unfortunately Codebases

Designs I inherited had many concerns. Learning about the 7 different sets of code helped me to realize that is was not a simple problem to fix, but caused a mess of an experience for our users. 

In this early screenshot before we started the project, you can observe below, basic data being displayed such as 1 or 2 Languages. A recent feature allowed visibility of the individual languages to be toggled. However, a visual status was lacking. 

Another minor but important element in scanning the list—a mixture of dates were posted onto the page while one was more of a backup reference rather than an important piece of information to be emphasized.

All in all, it was barebones and lacking in consideration for the needs of a Localization Manager or Agency Owner.

---

<div class="project-section" markdown="1">

## **Initial Design for Customers & Translators**

{% include gallery layout="half" id="galleryInitial" caption="" %}
</div>

## Listening In

Before getting too caught up in features, Sophia and I met with both translation agencies and customers. Sophia’s rapport with agencies having been on the Language Services and my focus on open conversation in user research helped us to give interviewees space to be comfortable to be brutally honest and share their frustrations, processes and needs.

We collected input that helped to shape incorrect assumptions and validate aspects we had observed but wanted to confirm. After initial conversations where we gathered insights, we began to show initial mockups. This allowed us to speak to functionality and understand what data or filters they found to be wasteful. Giving interviewees space to take part in an envisioning of their future created a space for dialogue, trust, and excitement. In some companies it might be risky to workshop ideas, but the investment our translators have in our platform makes them subject matter experts. Those are opinions we place a lot of value and were helpful in challenging us to consider any missteps we might be taking.

In this early iteration, we found that assignees were not valuable to users—general workflow status was critical. 

<div class="project-section" markdown="1">

## **Design Iterations**

{% include gallery layout="third" id="galleryIterations" caption="" %}
</div>

## Data Grid vs Table

A major internal debate through the definition process had to do with what this page actually would be categorized as, what it _should_ be. Would users want to edit data on this page like a Monday.com or would it just outline the most important data of a job and require the user to “click in” to handle it?

The user interviews definitely pushed us closer to the middle but did not point us to a total spreadsheet approach. The biggest pain we gathered from talking to our customers was clarity in status. Dynamic via filters to help reduce opening 15 browser tabs to learn about progress for a single language, but **not** editable. Intense daily conversations and debates amongst our team were incredibly helpful in making sure the vernacular we all used was actually describing the _same concept_, which led our developers down the right road for building a graphQL service to pull information in quickly and effectively and let us avoid refactors later on. I’m grateful for the dialogue and engagement our departments put into the project.

## Phase 1 Launch

After getting the critical pieces in place, we launched the first iteration of the project—the major enhancement of phase 1 focused on: **better filtering**, **dynamic data**, and **saved searches** (which many customers were _thrilled_ to have).

Future phases are planned to catch up the code to the UX vision where we intend to implement features like: custom column visibility, horizontal scrolling, and bulk selection to allow actions like assignment/unassignment to be incredibly fast and to save our localization managers **hours** in their week.

{% include gallery layout="" id="galleryFinal" caption="" %}

<div class="project-footer-nav">
  <a href="/opengov">← Previous</a>
  <a href="/smartling-workflows">Next →</a>
</div>
