---
layout: page
permalink: /research/
title: Research
type: [inetrav, forf_jours, indevac]
nav: true
publications: false
---

<div class="publications">

{% for y in page.type %}
  <!-- <h2 class="year">{{y}}</h2> -->
  {% bibliography -f ongoing -q @*[abbr={{y}}]* %}
  
  {% for entry in site.scholar.entries %}
    {% if entry.key == y %}
      <div class="publication">
        <h3>{{ entry.title }}</h3>
        <p>with {{ entry.author | replace: "Baptiste Roux,", "" | replace: ", Baptiste Roux", "" | replace: "Baptiste Roux", "" }}</p>
      </div>
    {% endif %}
  {% endfor %}
{% endfor %}

</div>
