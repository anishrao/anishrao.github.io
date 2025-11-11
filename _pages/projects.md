---
layout: page
title: projects
permalink: /projects/
description: A growing collection of our projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

**Fair warning: Work in progress!**

Please ignore most of the content below this paragraph while I get the house in order. For a quick glimpse into what actually interests me, check out the **selected publications** section on the main page instead.

The TL;DR: I am fascinated by self-assembly (especially in non-equilibrium systems), designing sensing protocols, developing principles for efficient catalysis, and more recently, using automation and AI to modernize scientific workflows.

**Why you might want to get in touch:**
- If any of this sounds interesting to you (or vice versa—maybe what you do could interest us!)
- If you need high-quality nanoparticles for nanoplasmonic applications (yes, we make them really well—pictures coming soon, I promise!)

Feel free to reach out. I hope you found what you came looking for! :)

---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
