---
title: "Projects"
layout: single
permalink: /projects/
author_profile: false
---

<ul>
  {% for project in site.projects %}
    <li style="margin-bottom: 2em;">
      <h2>
        {% if project.link_url %}
          <a href="{{ project.link_url }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a>
        {% else %}
          <span>{{ project.title }}</span>
        {% endif %}
      </h2>

      <!-- LINKS: moved up here -->
      {% if project.github_url %}
        <p><a href="{{ project.github_url }}" target="_blank" rel="noopener noreferrer">GitHub Repository</a></p>
      {% endif %}

      {% if project.zip_file %}
        <p><a href="{{ project.zip_file }}" download target="_blank" rel="noopener noreferrer">Download ZIP</a></p>
      {% endif %}

      {% if project.video %}
        <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">Video: App Walkthrough</a></p>
      {% endif %}

      <!-- DESCRIPTION: now below the links -->
      <p>{{ project.excerpt | strip_html | truncatewords: 30 }}</p>

      {% if project.image %}
      <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 100%; height: auto;">
      {% endif %}

      {% if project.video %}
        <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">Video: App Walkthrough</a></p>
      {% endif %}
    </li>
  {% endfor %}
</ul>

  
