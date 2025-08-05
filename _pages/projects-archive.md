---
title: "Projects"
layout: default
permalink: /projects/
author_profile: false
---

<style>
  /* Outer wrapper full width, light background for page sides */
  .projects-wrapper {
    width: 100vw;
    background-color: #f0f0f0; /* light page side background */
    padding: 2rem 0;
    display: flex;
    justify-content: center; /* center projects-container horizontally */
  }

  /* Black box container centered on page */
  .projects-container {
    background-color: #000; /* projects background */
    max-width: 1200px;
    width: 100%;
    padding: 2rem;
    box-sizing: border-box;
  }

  ul.projects-list {
    list-style: none;
    padding: 0;
    margin: 0;
    width: 100%;
  }

  ul.projects-list li {
    display: flex;
    align-items: center;
    width: 100%;
    margin-bottom: 4rem;
    max-width: 800px; /* limit project block width */
  }

  /* Alternate alignment inside container */
  ul.projects-list li.left {
    justify-content: flex-start;
    text-align: left;
  }

  ul.projects-list li.right {
    justify-content: flex-end;
    text-align: right;
  }

  /* Content width and color */
  ul.projects-list li.left .content,
  ul.projects-list li.right .content {
    max-width: 600px;
    color: #eee;
  }

  ul.projects-list li img {
    width: 250px;
    border-radius: 8px;
    flex-shrink: 0;
  }

  ul.projects-list li .content h2 {
    text-decoration: underline;
  }

  ul.projects-list li .content h2 a {
    color: #2aa198;
    text-decoration: inherit;
  }

  ul.projects-list li .content h2 a:hover {
    color: #ffffff;
    text-decoration: inherit;
  }

  ul.projects-list li .content p {
    max-width: 600px;
  }

  ul.projects-list li img.large-image {
    width: 400px;
  }
</style>

<div class="projects-wrapper">
  <div class="projects-container">
    <ul class="projects-list">
      {% for project in site.projects %}
        {% assign is_odd = forloop.index | modulo: 2 %}
        {% if is_odd == 1 %}
          {% assign default_side = "left" %}
        {% else %}
          {% assign default_side = "right" %}
        {% endif %}
        {% assign side = project.image_position | default: default_side %}

        <li class="{{ side }}">
          {% if side == "left" %}
            {% if project.image %}
              <img src="{{ project.image }}" alt="{{ project.title }} image" class="{{ project.custom_image_class }}" />
            {% endif %}
          {% endif %}

          <div class="content">
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
              <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">
                Video: {{ project.video_label | default: "App Walkthrough" }}</a></p>
            {% endif %}

            <p>{{ project.excerpt }}</p>
          </div>

          {% if side == "right" %}
            {% if project.image %}
              <img src="{{ project.image }}" alt="{{ project.title }} image" class="{{ project.custom_image_class }}" />
            {% endif %}
          {% endif %}
        </li>
      {% endfor %}
    </ul>
  </div>
</div>
