---
layout: default
title: Publications
---

<section>
  <div class="wrapper">
    <h2>Noticable Research Publications</h2>
    
    {% assign pubs_by_year = site.publications | group_by: "year" | sort: "name" | reverse %}
    
    {% for group in pubs_by_year %}
    <h3 class="pub-year">{{ group.name }}</h3>
    <ul class="pub-list">
      {% for pub in group.items %}
      <li class="pub-item">
        <span class="pub-title">{{ pub.title }}</span>
        <div class="pub-authors">{{ pub.authors }}</div>
        <div class="pub-meta" style="font-size: 0.9rem; margin-top: 5px;">
          <em>{{ pub.journal }}</em> | 
          <a href="{{ pub.link }}" style="color: var(--accent-blue); text-decoration: none;">Link to Paper</a>
          {% if pub.citations %}
          <span class="pub-citations" style="margin-left: 15px; font-weight: 600; color: #555;">Cited by: {{ pub.citations }}</span>
          {% endif %}
        </div>
      </li>
      {% endfor %}
    </ul>
    {% endfor %}

    <div style="margin-top: 60px; text-align: center;">
      <p style="color: var(--text-light); font-size: 1rem;">
        Want more? 
        <a href="https://scholar.google.com/citations?user=pu2imbMAAAAJ" target="_blank" style="color: var(--accent-blue); text-decoration: none; font-weight: 600; margin-left: 5px; transition: opacity 0.3s;">
          View Google Scholar →
        </a>
      </p>
    </div>
  </div>
</section>
