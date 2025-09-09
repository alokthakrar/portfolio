---
title: Projects
layout: default
permalink: /projects/
published: true
---

<div class="ProjectContainer">
    {% assign project_order = site.collections.projects.order %}
    {% for project_filename in project_order %}
        {% assign project = site.projects | where_exp: "item", "item.path contains project_filename" | first %}
        {% if project %}
            {% comment %} Determine the link URL - either the redirect or the project's own page {% endcomment %}
            {% if project.redirect %}
                {% assign project_url = project.redirect %}
            {% else %}
                {% assign project_url = project.url | prepend: site.baseurl %}
            {% endif %}

            <div class="projectCard">
                <a href="{{ project_url }}" {% if project.redirect %}target="_blank"{% endif %}>

                    {% comment %} Part 1: The Image Container {% endcomment %}
                    <div class="project-image-container">
                        {% if project.thumbnail %}
                            <img class="projectThumbnail" src="{{ project.thumbnail | prepend: site.baseurl }}" alt="{{ project.title }} thumbnail">
                        {% else %}
                            <div class="project-image-placeholder"></div>
                        {% endif %}
                    </div>

                    {% comment %} Part 2: The Text Content Container {% endcomment %}
                    <div class="project-text-container">
                        <h2>{{ project.title }}</h2>
                        <p>{{ project.description }}</p>
                    </div>

                </a>
            </div>
        {% endif %}
    {% endfor %}
</div>
