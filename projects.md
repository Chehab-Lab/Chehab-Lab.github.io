---
layout: gallery
title: Projects
permalink: /projects/
---

<section style="overflow-x: hidden; position: relative;">
  <button class="gallery-arrow gallery-arrow-left" onclick="document.querySelector('.horizontal-gallery').scrollBy({left: -420, behavior: 'smooth'})">&#8592;</button>
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
  <button class="gallery-arrow gallery-arrow-right" onclick="document.querySelector('.horizontal-gallery').scrollBy({left: 420, behavior: 'smooth'})">&#8594;</button>
</section>
