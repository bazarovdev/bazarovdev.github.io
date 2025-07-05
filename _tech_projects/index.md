---
title: Tech Projects
layout: default
permalink: /tech_projects/
# nav_exclude: true
nav_order: 0
---

# Tech projects

<ul>
{% for project in site.tech_projects %}
  {% assign rel = project.relative_path | remove_first: '_tech_projects/' %}
  {% assign rel_end = rel | slice: -9, 9 %}
  {% assign slash_count = rel | split: '/' | size %}
  {% if rel != 'index.md' and rel_end == '/index.md' and slash_count <= 2 %}
    <li>
      <a href="{{ project.url }}">{{ project.title | default: project.path }}</a> - {{ project.short_description}}
    </li>
  {% endif %}
{% endfor %}
</ul>