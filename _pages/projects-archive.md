---
title: "Projects"
layout: single
permalink: /projects/
author_profile: false
---

<div style="width: 100%; max-width: none; padding: 2em; background: #f9f9f9;">

  <ul style="list-style: none; padding: 0;">
    {% for project in site.projects %}
      <li style="display: flex; gap: 2em; margin-bottom: 3em; align-items: flex-start; flex-direction: row; max-width: 1000px; margin-left: auto; margin-right: auto;">

        {% if project.image and project.image_position == "left" %}
          <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 250px; height: auto; flex-shrink: 0;">
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
          <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 250px; height: auto; flex-shrink: 0;">
        {% endif %}

      </li>
    {% endfor %}
  </ul>

</div>
