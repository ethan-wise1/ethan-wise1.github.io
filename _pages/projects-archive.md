---
title: "Projects"
layout: fullwidth   # or default if you want
permalink: /projects/
author_profile: false
---

<ul style="list-style:none; padding:0; margin:0; width: 100%;">
  {% for project in site.projects %}
    {% assign is_odd = forloop.index | modulo: 2 %}
    <li style="display: flex; justify-content: {% if is_odd == 1 %}flex-start{% else %}flex-end{% endif %}; width: 100%; margin-bottom: 4em;">
      <div style="display: flex; max-width: 800px; width: 100%; gap: 2em; align-items: center;">
        {% if is_odd == 1 %}
          {% if project.image %}
            <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 250px; border-radius: 8px;" />
          {% endif %}
          <div>
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
          <div style="text-align: right;">
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
            <img src="{{ project.image }}" alt="{{ project.title }} image" style="width: 250px; border-radius: 8px; margin-left: 2em;" />
          {% endif %}
        {% endif %}
      </div>
    </li>
  {% endfor %}
</ul>
