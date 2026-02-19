---
layout: default
title: Team
permalink: /team/
---

<section class="team-section">
  <div class="wrapper">
    <div class="team-grid" style="grid-template-columns: 1fr; margin-bottom: 60px;">
        <div class="team-card team-head-card" style="text-align: left; display: flex; align-items: center; gap: 40px; background: var(--bg-light); padding: 40px; border-radius: 24px;">
            <img src="{{ site.data.team.head.image }}" alt="{{ site.data.team.head.name }}" class="team-image team-head-image" style="width: 240px; height: 240px;">
            <div>
                <h3 style="border: none; margin: 0;">{{ site.data.team.head.name }}</h3>
                <div class="team-role" style="font-size: 1.2rem; font-weight: 600; color: #000;">{{ site.data.team.head.role }}</div>
                <p style="margin-top: 20px;">{{ site.data.team.head.bio }}</p>
            </div>
        </div>
    </div>


    <h3>PhD Students</h3>
    <div class="team-grid">
      {% for member in site.data.team.phd_students %}
      <div class="team-card">
        <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

    <h3>Master Students</h3>
    <div class="team-grid">
      {% for member in site.data.team.master_students %}
      <div class="team-card">
        <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

    <h3>Interns</h3>
    <div class="team-grid">
      {% for member in site.data.team.interns %}
      <div class="team-card">
        <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

  </div>
</section>
