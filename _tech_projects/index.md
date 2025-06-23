---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
nav_exclude: true
---

# Tech projects

<ul>
{% for project in site.tech_projects %}
  {% assign rel = project.relative_path | remove_first: '_tech_projects/' %}
  {% assign rel_end = rel | slice: -9, 9 %}
  {% if rel != 'index.md' and rel_end == '/index.md' %}
    <li>
      <a href="{{ project.url }}">{{ project.title | default: project.path }}</a>
    </li>
  {% endif %}
{% endfor %}
</ul>