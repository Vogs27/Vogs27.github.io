---
layout: default
title: Home
---

# Welcome

Welcome to my page! Here I collect my archived projects and the latest I'm working on. You may also find some ideas for future projects that I have in mind.

## Latest news

{% for post in site.posts limit:3 %}
<div class="news-item">
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
  <p>{{ post.excerpt }}</p>
</div>
{% endfor %}

## Highlighted projects

{% assign featured_projects = site.progetti | where: "featured", true %}
{% for project in featured_projects limit:3 %}
<div class="project-preview">
  <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
  <p>{{ project.description }}</p>
  <p><strong>Tecnologie:</strong> {{ project.technologies | join: ", " }}</p>
</div>
{% endfor %}

[All projects →](/progetti/)