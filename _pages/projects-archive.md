---
title: "Projects"
layout: default
permalink: /projects/
author_profile: false
---

<style>
  .projects-wrapper {
    width: 100vw;
    position: relative;
    background-color: transparent;
    padding: 0;
  }

  .projects-container {
    max-width: 1200px;
    margin: 0 auto;
  }

  ul.projects-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  ul.projects-list li {
    display: flex;
    align-items: center;
    margin-bottom: 4rem;
    padding: 1rem;
    background-color: #000;
    border-radius: 8px;
  }

  ul.projects-list li.left {
    justify-content: flex-start;
  }

  ul.projects-list li.left .content {
    margin-left: 2rem;
    color: #eee;
    text-align: left;
  }

  ul.projects-list li.right {
    justify-content: flex-end;
  }

  ul.projects-list li.right .content {
    margin-right: 2rem;
    color: #eee;
    text-align: right;
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

  li.arrow-connector {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: -2rem 0 2rem;
  }

  .arrow-svg {
    width: 150px;
    height: 30px;
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

        {% if forloop.last == false %}
          <li class="arrow-connector">
            <svg class="arrow-svg" viewBox="0 0 100 20" preserveAspectRatio="none">
              {% if side == "left" %}
                <path d="M0,10 Q50,0 100,10" stroke="#888" stroke-width="2" fill="none" marker-end="url(#arrowhead)" />
              {% else %}
                <path d="M100,10 Q50,20 0,10" stroke="#888" stroke-width="2" fill="none" marker-end="url(#arrowhead)" />
              {% endif %}
              <defs>
                <marker id="arrowhead" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
                  <polygon points="0 0, 6 3, 0 6" fill="#888" />
                </marker>
              </defs>
            </svg>
          </li>
        {% endif %}

      {% endfor %}
    </ul>
  </div>
</div>
