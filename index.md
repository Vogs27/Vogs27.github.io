---
layout: default
title: Home
permalink: /
---

# Welcome

Welcome! Here I collect my archived projects and the latest I'm working on. You may also find some ideas for future projects that I have in mind.  
**This page is in a work-in-progress state! Thanks for your understanding!**


## Latest news

{% for post in site.posts limit:3 %}
<div class="news-item">
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  <p class="date">{{ post.date | date: "%d %B %Y" }}</p>
  <p>{{ post.excerpt }}</p>
</div>
{% endfor %}

{% if site.posts.size == 0 %}
<div class="news-item">
  <h3>Benvenuto!</h3>
  <p class="date">19 Settembre 2025</p>
  <p>This section is still empty, but soon some contents will appear, please be patient.</p>
</div>
{% endif %}


## Highlighted projects

{% assign featured_projects = site.progetti | where: "featured", true %}
{% if featured_projects.size > 0 %}
  {% for project in featured_projects limit:3 %}
  <div class="project-preview">
    <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
    <p>{{ project.description }}</p>
    <p><strong>Tags:</strong> {{ project.technologies | join: ", " }}</p>
  </div>
  {% endfor %}
{% else %}
<div class="project-preview">
  <h3>Soon...</h3>
  <p>Great things require time, come back soon!</p>
</div>
{% endif %}

<p style="text-align: center; margin-top: 30px;">
  <a href="{{ '/progetti/' | relative_url }}" style="display: inline-block; background: #0366d6; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">All projects →</a>
</p>