---
layout: default
title: "Projects"
permalink: /projects/
---

<div class="projects-grid">
  {% for project in site.projects %}
    <div class="project-card">
      <a href="{% if project.redirect %}{{ project.redirect }}{% else %}{{ project.url | relative_url }}{% endif %}" target="_blank" rel="noopener noreferrer">
        <img src="{{ project.thumbnail | relative_url }}" alt="{{ project.title }}">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
      </a>
    </div>
  {% endfor %}
</div>
