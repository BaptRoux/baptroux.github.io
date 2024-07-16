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
        <p>with 
          {% assign authors = entry.author | split: " and " %}
          {% assign filtered_authors = "" %}
          {% for author in authors %}
            {% if author != "Baptiste Roux" %}
              {% if filtered_authors != "" %}
                {% assign filtered_authors = filtered_authors | append: ", " %}
              {% endif %}
              {% assign filtered_authors = filtered_authors | append: author %}
            {% endif %}
          {% endfor %}
          {{ filtered_authors }}
        </p>
      </div>
    {% endif %}
  {% endfor %}
{% endfor %}

</div>
