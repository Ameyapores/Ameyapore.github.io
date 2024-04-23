---
layout: page
permalink: /publications/
title: Publications
description: 
years: [2024, 2023, 2022, 2021, 2020]
nav: true
nav_order: 1
---

<p>Peer-reviewed or pre-print publications. Check my <a href="https://scholar.google.com/citations?user=Ewe4vSsAAAAJ&hl=en">Google scholar</a> for the complete list. <br>(* indicates equal contribution)<br/></p>
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
