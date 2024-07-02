---
layout: page
permalink: /research/
title: Research
type: [inetrav, forf_jours, indevac]
nav: true
publications: false
---


### work in progress
<div class="publications">

{% for y in page.type %}
  <!-- <h2 class="year">{{y}}</h2> -->
  {% bibliography -f ongoing -q @*[abbr={{y}}]* %}
{% endfor %}

</div>
