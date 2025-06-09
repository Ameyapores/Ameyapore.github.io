---
layout: page
title: Miscellaneous
permalink: /projects/
description: 
nav: true
nav_order: 5
display_categories: [fun]
horizontal: false
---

**Dance**

Trying to learn some technical Cuban Salsa and Bachata. Will post some updates soon.

**Music**

In my spare time, I like to create AI music. You can check my music on [Spotify](https://open.spotify.com/artist/6wWv9SWI07KvCb9YTNJFpa?si=QDW-VkW6QuKi_b2RUyxBxw) or [Apple music](https://music.apple.com/us/artist/uncle-pores/1719448357). I generally use open-source AI softwares to help me in the composition and the vocals.

Some of my representative albums are below.
<!-- projects_horizontal.html -->
<div class="col">
  <div class="project-card">
    <h3>{{ project.title }}</h3>
    <a href="{{ project.link }}">
      <img src="{{ project.image }}" alt="{{ project.title }}">
    </a>
    <p>{{ project.description }}</p>
  </div>
</div>


<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
