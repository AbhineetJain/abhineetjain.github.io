---
layout: page
permalink: /publications/
title: publications
description: publications by categories in reversed chronological order. 
years: []
nav: true
---

<div class="publications">
Coming soon!
{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
