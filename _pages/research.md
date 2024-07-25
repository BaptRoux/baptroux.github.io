---
layout: page
permalink: /research/
title: Research
type: [inetrav, forf_jours, indevac]
nav: true
---

### Work in Progress
<div class="publications">
  {% for entry in site.data.ongoing.entries %}
    {% if entry.key in page.type %}
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
        {% if entry.abstract %}
          <p>{{ entry.abstract }}</p>
        {% endif %}
      </div>
    {% endif %}
  {% endfor %}
</div>
