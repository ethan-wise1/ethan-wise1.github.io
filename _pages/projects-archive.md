---
title: "Projects"
layout: single
permalink: /projects/
author_profile: false
---

<ul>
  {% for project in site.projects %}
    <li style="display: flex; gap: 1.5em; margin-bottom: 3em; align-items: flex-start; flex-direction: row;">

      {% if project.image and project.image_position == "left" %}
        <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 200px; height: auto;">
      {% endif %}

      <div style="flex: 1;">
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
        <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 200px; height: auto;">
      {% endif %}

    </li>
  {% endfor %}
</ul>
