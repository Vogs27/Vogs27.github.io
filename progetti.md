---
layout: default
title: Projects
permalink: /progetti/
---

# Projects pages

## Actual projects

{% assign current_projects = site.progetti | where: "status", "attivo" %}
{% if current_projects.size > 0 %}
{% for project in current_projects %}
<div class="project-item current">
  <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tags:</strong> {{ project.technologies | join: ", " }}</p>
  <p><strong>Status:</strong> <span class="status-active">{{ project.status }}</span></p>
  {% if project.github_url %}
  <p><a href="{{ project.github_url }}" target="_blank">View in GitHub →</a></p>
  {% endif %}
</div>
{% endfor %}
{% else %}
<p>Great things take time to build, come back soon!</p>
{% endif %}

## Past projects

{% assign completed_projects = site.progetti | where: "status", "completato" %}
{% for project in completed_projects %}
<div class="project-item archived">
  <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tags:</strong> {{ project.technologies | join: ", " }}</p>
  <p><strong>Status:</strong> <span class="status-archived">{{ project.status }}</span></p>
  {% if project.github_url %}
  <p><a href="{{ project.github_url }}" target="_blank">View in GitHub →</a></p>
  {% endif %}
</div>
{% endfor %}

## Progetti Archiviati

{% assign archived_projects = site.progetti | where: "status", "archiviato" %}
{% for project in archived_projects %}
<div class="project-item archived">
  <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tags:</strong> {{ project.technologies | join: ", " }}</p>
  <p><strong>Status:</strong> <span class="status-archived">{{ project.status }}</span></p>
  {% if project.github_url %}
  <p><a href="{{ project.github_url }}" target="_blank">View in GitHub →</a></p>
  {% endif %}
</div>
{% endfor %}