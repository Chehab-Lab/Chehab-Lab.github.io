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
                <a href="{{ '/chehab/' | relative_url }}">
                    For more about Dr. Chehab
                </a>
            </div>
        </div>
    </div>


    <h3>PhD Students</h3>
    <div class="team-grid">
      {% for member in site.data.team.phd_students %}
      <div class="team-card">
        <div style="position: relative; display: inline-block;">
          <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
          {% if member.email %}
          <a href="mailto:{{ member.email }}" class="team-email-icon" title="Email {{ member.name }}">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
          </a>
          {% endif %}
        </div>
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

    <h3>Master Students</h3>
    <div class="team-grid">
      {% for member in site.data.team.master_students %}
      <div class="team-card">
        <div style="position: relative; display: inline-block;">
          <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
          {% if member.email %}
          <a href="mailto:{{ member.email }}" class="team-email-icon" title="Email {{ member.name }}">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
          </a>
          {% endif %}
        </div>
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

    <h3>Interns</h3>
    <div class="team-grid">
      {% for member in site.data.team.interns %}
      <div class="team-card">
        <div style="position: relative; display: inline-block;">
          <img src="{{ member.image | default: 'https://ui-avatars.com/api/?background=random' }}" alt="{{ member.name }}" class="team-image">
          {% if member.email %}
          <a href="mailto:{{ member.email }}" class="team-email-icon" title="Email {{ member.name }}">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
          </a>
          {% endif %}
        </div>
        <div class="team-name">{{ member.name }}</div>
      </div>
      {% endfor %}
    </div>

  </div>
</section>
