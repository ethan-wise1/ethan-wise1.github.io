---
title: "Projects"
layout: fullwidth   # or default if you want
permalink: /projects/
author_profile: false
---

<ul style="list-style: none; padding: 0; margin: 0;">
  {% for project in site.projects %}
    {% assign is_odd = forloop.index | modulo: 2 %}
    <li style="display: flex; flex-wrap: wrap; align-items: flex-start; margin-bottom: 3em; 
               justify-content: {% if is_odd == 1 %}flex-start{% else %}flex-end{% endif %}; gap: 2em;">

      {% if is_odd == 1 %}
        <!-- Image Left -->
        {% if project.image %}
          <div style="flex: 0 0 250px;">
            <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 100%; height: auto; border-radius: 8px;">
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

      {% else %}
        <!-- Image Right -->
        <div style="flex: 1; min-width: 250px; text-align: right;">
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

        {% if project.image %}
          <div style="flex: 0 0 250px; margin-left: 2em;">
            <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 100%; height: auto; border-radius: 8px;">
          </div>
        {% endif %}
      {% endif %}

    </li>
  {% endfor %}
</ul>
