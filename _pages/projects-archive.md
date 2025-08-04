---
title: "Projects"
layout: default
permalink: /projects/
author_profile: false
---

<style>
  /* Full width wrapper for projects */
  .projects-wrapper {
    width: 100vw; /* full viewport width */
    position: relative;
    background-color: #000; /* add black background */
    padding: 2rem 0;
  }

  /* Max width container centered */
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
  }

  /* Left-aligned project */
  ul.projects-list li.left {
    justify-content: flex-start;
  }

  ul.projects-list li.left .content {
    margin-left: 2rem;
    color: #eee;
  }

  /* Right-aligned project */
  ul.projects-list li.right {
    justify-content: flex-end;
  }

  ul.projects-list li.right .content {
    margin-right: 2rem;
    text-align: right;
    color: #eee;
  }

  ul.projects-list li img {
    width: 250px;
    border-radius: 8px;
    flex-shrink: 0;
  }

   /* Underline all project titles */
  ul.projects-list li .content h2 {
    text-decoration: underline;
  }

  /* Project title link styles */
  ul.projects-list li .content h2 a {
  color: #2aa198; /* or use the same color your theme uses for normal links */
  text-decoration: inherit;
}
  ul.projects-list li .content h2 a:hover {
    color: #ffffff;
    text-decoration: inherit;
  }

  /* Paragraph text */
  ul.projects-list li .content p {
    max-width: 600px;
  }
</style>

<div class="projects-wrapper">
  <div class="projects-container">
    <ul class="projects-list">
      {% for project in site.projects %}
        {% assign is_odd = forloop.index | modulo: 2 %}
        <li class="{% if is_odd == 1 %}left{% else %}right{% endif %}">
          {% if is_odd == 1 %}
            {% if project.image %}
              <img src="{{ project.image }}" alt="{{ project.title }} image" />
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
                <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">Video: App Walkthrough</a></p>
              {% endif %}
              <p>{{ project.excerpt | strip_html | truncatewords: 30 }}</p>
            </div>
          {% else %}
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
                <p><a href="{{ project.video }}" target="_blank" rel="noopener noreferrer">Video: App Walkthrough</a></p>
              {% endif %}
              <p>{{ project.excerpt | truncatewords: 30 }}</p>
            </div>
            {% if project.image %}
              <img src="{{ project.image }}" alt="{{ project.title }} image" />
            {% endif %}
          {% endif %}
        </li>
      {% endfor %}
    </ul>
  </div>
</div>
