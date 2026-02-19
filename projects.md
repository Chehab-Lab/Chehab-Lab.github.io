---
layout: gallery
title: Projects
permalink: /projects/
---

<div class="gallery-content-wrapper">
<section style="padding-top: 20px; overflow-x: hidden;">
  <div class="horizontal-gallery">
    {% for project in site.projects %}
    <div class="project-card project-card-overlay">
      <img src="{{ project.image }}" alt="{{ project.title }}" class="project-image">
      <div class="project-overlay-content">
        <div class="project-tags">
          {% for tag in project.tags %}
          <span class="tag tag-{{ tag | downcase }}">{{ tag }}</span>
          {% endfor %}
        </div>
        <h3 class="project-title">{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <div style="margin-top: 20px;">
          <a href="{{ project.link | default: project.github }}" class="project-link">View Details →</a>
        </div>
      </div>
    </div>
    {% endfor %}
  </div>
</section>
</div>
