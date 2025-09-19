---
layout: default
title: Progetti
---

# Projects

## Actual progects

{% assign current_projects = site.progetti | where: "status", "attivo" %}
{% for project in current_projects %}
<div class="project-item current">
  <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tecnologie:</strong> {{ project.technologies | join: ", " }}</p>
  <p><strong>Stato:</strong> <span class="status-active">{{ project.status }}</span></p>
  {% if project.github_url %}
  <p><a href="{{ project.github_url }}" target="_blank">Vedi su GitHub →</a></p>
  {% endif %}
</div>
{% endfor %}

## Archived projects

{% assign archived_projects = site.progetti | where: "status", "archiviato" %}
{% for project in archived_projects %}
<div class="project-item archived">
  <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tecnologie:</strong> {{ project.technologies | join: ", " }}</p>
  <p><strong>Stato:</strong> <span class="status-archived">{{ project.status }}</span></p>
  {% if project.github_url %}
  <p><a href="{{ project.github_url }}" target="_blank">Vedi su GitHub →</a></p>
  {% endif %}
</div>
{% endfor %}