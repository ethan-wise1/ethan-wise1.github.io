---
title: "Projects"
layout: fullwidth
permalink: /projects/
author_profile: false
---

<ul style="list-style: none; padding: 0;">
  {% for project in site.projects %}
    <li style="display: flex; flex-wrap: wrap; gap: 2em; margin-bottom: 3em; align-items: flex-start;">

      {% if project.image and project.image_position == "left" %}
        <div style="flex: 0 0 250px;">
          <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 100%; height: auto;">
        </div>
      {% endif %}

      <div style="flex: 1; min-width: 250px;">
        <h2>
          {% if project.link_url %}
            <a href="{{ project.link_url }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a>
          {% else %}
            <span>{{ project.title }}</span>
          {% endif %}
        </h2>

        {% if project.github_url %}
          <p><a href="{{ project.github_url }}" target="_blank" rel="noopener noreferrer">GitHub Repository</a></p>
        {% endif %}

        {% if project.zip_file %}
          <p><a href="{{ project.zip_file }}" download target="_blank" rel="noopener noreferrer">Download ZIP</a></p>
        {% endif %}

        {% if project.video %}
          <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">Video: App Walkthrough</a></p>
        {% endif %}

        <p>{{ project.excerpt | strip_html | truncatewords: 30 }}</p>
      </div>

      {% if project.image and project.image_position == "right" %}
        <div style="flex: 0 0 250px;">
          <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 100%; height: auto;">
        </div>
      {% endif %}

    </li>
  {% endfor %}
</ul>
