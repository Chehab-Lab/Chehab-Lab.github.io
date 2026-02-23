---
layout: default
title: Dr. Ali Chehab
permalink: /chehab/
---



<section class="summary-section">
  <div class="wrapper">
    <div class="summary-header">
      <img src="{{ site.data.team.head.image }}" alt="{{ site.data.team.head.name }}" class="summary-image">
      <div style="max-width: 600px;">
        <h1>{{ site.data.team.head.name }}</h1>
        <p class="bio">{{ site.data.team.head.bio }}</p>
      </div>
    </div>

    <!-- Highlighted Award -->
    {% for award in site.data.chehab.awards %}
      {% if award.title == "Top 2% Most-Cited Scientists Worldwide" %}
        <div class="highlight-quote">
          <h2>&ldquo;{{ award.title }}&rdquo;</h2>
          <span>&mdash; 
            <a href="https://manuelgarcia.info/worlds-top-scientists/author/Chehab,+Ali~American+University+of+Beirut">
              {{ award.issuer }}, {{ award.year }}
            </a>
          </span>
        </div>
      {% endif %}
    {% endfor %}

    <!-- KPIs -->
    <div class="kpis">
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.publication_stats.totals.journal_articles }}">0</div>
        <div class="kpi-label">Journal Articles</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.publication_stats.totals.conference_papers }}">0</div>
        <div class="kpi-label">Conference Papers</div>
      </div>
      <!-- Book Chapters Feature -->
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.publication_stats.totals.book_chapters }}">0</div>
        <div class="kpi-label">Book Chapters</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.publication_stats.totals.total_publications }}">0</div>
        <div class="kpi-label">Total Publications</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.publication_stats.google_scholar.citations }}">0</div>
        <div class="kpi-label">Citations</div>
      </div>
    </div>
    <p style="text-align: right; color: var(--text-light); font-size: 0.85rem;"><em>Last updated: {{ site.data.chehab.publication_stats.last_updated }}</em></p>

    <h2 class="section-title">Awards & Recognitions</h2>
    <div class="award-grid">
      {% for award in site.data.chehab.awards %}
        {% if award.title != "Top 2% Most-Cited Scientists Worldwide" %}
          <div class="award-card">
            <div class="award-title">{{ award.title }}</div>
            <div style="color: var(--text-light); font-size: 0.9rem;">
              {% if award.conference %}
                {{ award.conference }}
                {% if award.location %} ({{ award.location }}){% endif %}
                <br><strong style="color: var(--accent-teal);">{{ award.date }}</strong>
              {% elsif award.issuer %}
                {{ award.issuer }} &middot; <strong style="color: var(--accent-teal);">{{ award.year }}</strong>
              {% endif %}
            </div>
          </div>
        {% endif %}
      {% endfor %}
    </div>

    <!-- Right and Left boxes -->
    <div class="two-column-layout">
      <!-- Left Box -->
      <div class="service-box">
        <h3>Service to the Profession</h3>
        <ul class="clean-list">
          {% for org in site.data.chehab.service_to_profession.conference_organization %}
          <li>
            <strong style="color: var(--primary-color);">{{ org.role }}</strong><br>
            <span style="font-size: 0.95rem; color: var(--text-light);">
              {% if org.event %}
                {{ org.event }}
              {% elsif org.institution %}
                {{ org.institution }} ({{ org.date }})
              {% endif %}
            </span>
          </li>
          {% endfor %}
        </ul>
      </div>

      <!-- Right Box -->
      <div class="service-box">
        <h3>Professional Associations</h3>
        <ul class="clean-list">
          {% for assoc in site.data.chehab.professional_associations %}
          <li class="assoc-item">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"></path>
              <polyline points="22 4 12 14.01 9 11.01"></polyline>
            </svg>
            {{ assoc }}
          </li>
          {% endfor %}
        </ul>
      </div>
    </div>

    <h2 class="section-title">Research Supervision</h2>
    
    <h3>PhD Students</h3>
    <div class="student-grid">
      {% for student in site.data.chehab.research_supervision.phd_students %}
      <div class="student-card">
        <span class="student-status {% if student.status == 'Current' %}current{% endif %}">{{ student.status }}</span>
        <div style="font-weight: 700; font-size: 1.1rem; margin-bottom: 5px;">{{ student.name }}</div>
        <div style="font-size: 0.9rem; color: #555; line-height: 1.4;">{{ student.title }}</div>
      </div>
      {% endfor %}
    </div>

    <h3 style="margin-top: 40px;">Master Students</h3>
    <div class="student-grid">
      {% for student in site.data.chehab.research_supervision.master_students %}
      <div class="student-card">
        <span class="student-status {% if student.status == 'Current' %}current{% endif %}">{{ student.status }}</span>
        <div style="font-weight: 700; font-size: 1.1rem; margin-bottom: 5px;">{{ student.name }}</div>
        <div style="font-size: 0.9rem; color: #555; line-height: 1.4;">{{ student.title }}</div>
      </div>
      {% endfor %}
    </div>

  </div>
</section>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    const counters = document.querySelectorAll('.counter');
    const speed = 200;

    counters.forEach(counter => {
      const updateCount = () => {
        const target = +counter.getAttribute('data-target');
        const count = +counter.innerText;
        
        // Increase step
        const inc = Math.max(1, Math.ceil(target / speed));

        if (count < target) {
          counter.innerText = count + inc;
          requestAnimationFrame(updateCount);
        } else {
          // ensure it hits exact final target
          counter.innerText = target;
        }
      };
      updateCount();
    });
  });
</script>
