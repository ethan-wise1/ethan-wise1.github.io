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
          <a href="{{ project.link_url }}">{{ project.title }}</a>
        {% else %}
          <span>{{ project.title }}</span>
        {% endif %}
      </h2>

      <p>{{ project.excerpt | strip_html | truncatewords: 30 }}</p>

      {% if project.github_url %}
        <p><a href="{{ project.github_url }}" target="_blank">GitHub Repository</a></p>
      {% endif %}

      {% if project.zip_file %}
        <p><a href="{{ project.zip_file }}" download>Download ZIP</a></p>
      {% endif %}

      {% if project.image %}
        <img src="{{ project.image }}" alt="{{ project.title }} image" style="max-width: 100%; height: auto;">
      {% endif %}

      {% if project.video %}
        <div class="video-container" style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%;">
          <iframe src="{{ project.video | replace: 'watch?v=', 'embed/' }}" frameborder="0" allowfullscreen
            style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
          </iframe>
        </div>
      {% endif %}
    </li>
  {% endfor %}
</ul>
