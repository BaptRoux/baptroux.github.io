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

  {% for publication in site.data.publications %}
    {% if publication.abbr == y %}
      <div class="publication">
        <h3>{{ publication.title }}</h3>
        <p>with {{ publication.authors | replace: "Your Name,", "" | replace: ", Your Name", "" | replace: "Your Name", "" }}</p>
      </div>
    {% endif %}
  {% endfor %}
{% endfor %}

</div>
