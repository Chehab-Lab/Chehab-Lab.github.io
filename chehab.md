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
        <p class="summary-role">{{ site.data.team.head.role }} &bull; American University of Beirut</p>
        <p class="bio">{{ site.data.team.head.bio }}</p>
      </div>
    </div>

    <!-- Top 2% highlight — before the numbers -->
    {% for award in site.data.chehab.awards %}
      {% if award.title contains "Top 2%" %}
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
    <div id="stats" class="kpis fade-in-section">
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.totals.journal_articles }}">0</div>
        <div class="kpi-label">Journal Articles</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.totals.conference_papers }}">0</div>
        <div class="kpi-label">Conference Papers</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.totals.book_chapters }}">0</div>
        <div class="kpi-label">Book Chapters</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.totals.total_publications }}">0</div>
        <div class="kpi-label">Total Publications</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.google_scholar.citations }}">0</div>
        <div class="kpi-label">Citations</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.google_scholar.h_index }}">0</div>
        <div class="kpi-label">h-index</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-number counter" data-target="{{ site.data.chehab.stats.google_scholar.i10_index }}">0</div>
        <div class="kpi-label">i10-index</div>
      </div>
    </div>
    <p class="stats-updated">Last updated: {{ site.data.chehab.stats.last_updated }}</p>

    <!-- Awards Carousel -->
    <h2 id="awards" class="section-title">Awards & Recognitions</h2>

    <div class="awards-carousel-outer fade-in-section">
      <button class="awards-nav-btn prev" id="awardsPrev" aria-label="Previous">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><polyline points="15 18 9 12 15 6"/></svg>
      </button>
      <div class="awards-carousel-mask">
        <div class="awards-track" id="awardsTrack">
          {% for award in site.data.chehab.awards %}
            {% assign badge_class = "badge-recognition" %}
            {% assign badge_top = "SPECIAL" %}
            {% assign badge_mid = "HONOR" %}
            {% assign badge_bot = "AWARD" %}
            {% if award.title contains "Top 2%" %}
              {% assign badge_class = "badge-featured" %}
              {% assign badge_top = "ELSEVIER" %}
              {% assign badge_mid = "2%" %}
              {% assign badge_bot = "TOP CITED" %}
            {% elsif award.title contains "Excellent Paper" %}
              {% assign badge_class = "badge-paper" %}
              {% assign badge_top = "EXCELLENT" %}
              {% assign badge_mid = "PAPER" %}
              {% assign badge_bot = "AWARD" %}
            {% elsif award.title contains "Best Paper" %}
              {% assign badge_class = "badge-paper" %}
              {% assign badge_top = "BEST" %}
              {% assign badge_mid = "PAPER" %}
              {% assign badge_bot = "AWARD" %}
            {% elsif award.title contains "Special Recognition" %}
              {% assign badge_class = "badge-recognition" %}
              {% assign badge_top = "ACM" %}
              {% assign badge_mid = "HONOR" %}
              {% assign badge_bot = "AWARD" %}
            {% endif %}
            <div class="award-badge {{ badge_class }}">
              <div class="badge-medal-wrap">
                <svg viewBox="0 0 140 165" class="badge-medal" aria-hidden="true">
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(200) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(216) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(232) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(248) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(264) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(280) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(296) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(312) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(328) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(344) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(160) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(144) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(128) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(112) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(96) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(80) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(64) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(48) translate(0,-54)" class="leaf-l"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(32) translate(0,-54)" class="leaf-d"/>
                  <ellipse rx="8" ry="3.5" transform="translate(70,90) rotate(16) translate(0,-54)" class="leaf-l"/>
                  <circle cx="70" cy="90" r="48" class="badge-ring"/>
                  <circle cx="70" cy="90" r="43" fill="white"/>
                  <circle cx="70" cy="90" r="39" class="badge-inner"/>
                  <ellipse cx="60" cy="72" rx="14" ry="9" fill="rgba(255,255,255,0.1)"/>
                  <path d="M55,42 L55,28 L63,36 L70,22 L77,36 L85,28 L85,42 Z" class="badge-crown"/>
                  <rect x="54" y="42" width="32" height="5" rx="2.5" class="badge-crown"/>
                  <text x="70" y="79" text-anchor="middle" font-family="Georgia,serif" font-size="7" fill="rgba(255,255,255,0.8)" letter-spacing="1.5">{{ badge_top }}</text>
                  <line x1="55" y1="83" x2="85" y2="83" stroke="rgba(255,255,255,0.25)" stroke-width="0.8"/>
                  <text x="70" y="103" text-anchor="middle" font-family="Georgia,serif" font-size="20" font-weight="bold" fill="white">{{ badge_mid }}</text>
                  <text x="70" y="117" text-anchor="middle" font-family="Georgia,serif" font-size="7" fill="rgba(255,255,255,0.75)" letter-spacing="1.5">{{ badge_bot }}</text>
                </svg>
              </div>
              <div class="badge-title">{{ award.title }}</div>
              <div class="badge-meta">
                {% if award.conference %}
                  {{ award.conference }}{% if award.location %} &mdash; {{ award.location }}{% endif %}<br>
                  <strong>{{ award.date }}</strong>
                {% elsif award.issuer %}
                  {{ award.issuer }} &middot; <strong>{{ award.year }}</strong>
                {% endif %}
              </div>
            </div>
          {% endfor %}
        </div>
      </div>
      <button class="awards-nav-btn next" id="awardsNext" aria-label="Next">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><polyline points="9 18 15 12 9 6"/></svg>
      </button>
      <div class="awards-dots" id="awardsDots">
        {% for award in site.data.chehab.awards %}
          <span class="award-dot {% if forloop.first %}active{% endif %}"></span>
        {% endfor %}
      </div>
    </div>

    <!-- Service & Associations -->
    <h2 id="service" class="section-title" style="margin-top:2.5rem;">Service & Associations</h2>

    <div class="service-grid fade-in-section">

      <!-- Professional Associations -->
      <div class="service-col">
        <h3 class="service-heading">Professional Associations</h3>
        <ul class="service-list">
          {% for assoc in site.data.chehab.professional_associations %}
          <li>
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="var(--accent-teal)" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="flex-shrink:0;margin-right:8px;vertical-align:-2px;">
              <polyline points="20 6 9 17 4 12"/>
            </svg>{{ assoc }}
          </li>
          {% endfor %}
        </ul>
      </div>

      <!-- Conference Organization -->
      <div class="service-col">
        <h3 class="service-heading">Conference Organization</h3>
        <ul class="service-list">
          {% for org in site.data.chehab.service_to_profession.conference_organization %}
          <li>
            <strong>{{ org.role }}</strong>
            <span class="service-detail">{% if org.event %}{{ org.event }}{% elsif org.institution %}{{ org.institution }} ({{ org.date }}){% endif %}</span>
          </li>
          {% endfor %}
        </ul>
      </div>

      <!-- Journal Reviews -->
      <div class="service-col">
        <h3 class="service-heading">Journal Reviews</h3>
        <table class="review-table">
          {% for jp in site.data.chehab.service_to_profession.journal_paper_reviews %}
          <tr>
            <td class="review-name">{{ jp.journal }}</td>
            <td class="review-years">{{ jp.years | join: ", " }}</td>
          </tr>
          {% endfor %}
        </table>
      </div>

      <!-- Book Reviews -->
      <div class="service-col">
        <h3 class="service-heading">Book Reviews</h3>
        <ul class="service-list">
          {% for br in site.data.chehab.service_to_profession.book_reviews %}
          <li>
            <strong>{{ br.title }}</strong>
            <span class="service-detail">
              {% if br.authors %}{{ br.authors }} &mdash; {% endif %}{{ br.publisher }}, {% if br.year %}{{ br.year }}{% else %}{{ br.date }}{% endif %}
            </span>
          </li>
          {% endfor %}
        </ul>
      </div>

    </div>

    <!-- TPC tag carousel -->
    <div class="tag-section fade-in-section">
      <h3 class="service-heading">Technical Program Committee</h3>
      <div class="tag-carousel-outer">
        <div class="tag-carousel-mask">
          <div class="tag-track tag-track-long" id="tpcTrack">
            {% for tpc in site.data.chehab.service_to_profession.technical_program_committee_member %}
              <span class="tpc-badge">{{ tpc }}</span>
            {% endfor %}
          </div>
        </div>
      </div>
    </div>

    <!-- Conf Paper Reviews tag carousel -->
    <div class="tag-section fade-in-section">
      <h3 class="service-heading">Conference Paper Reviews</h3>
      <div class="tag-carousel-outer">
        <div class="tag-carousel-mask">
          <div class="tag-track tag-track-short" id="confTrack">
            {% for conf in site.data.chehab.service_to_profession.conference_paper_reviews %}
              <span class="tpc-badge">{{ conf }}</span>
            {% endfor %}
          </div>
        </div>
      </div>
    </div>

    <!-- Supervision -->
    <h2 id="supervision" class="section-title">Research Supervision</h2>

    <div class="supervision-stats fade-in-section">
      <div class="supervision-stat-card">
        <span class="supervision-number">{{ site.data.chehab.stats.supervisions.phd }}</span>
        <span class="supervision-label">PhD Students</span>
      </div>
      <div class="supervision-stat-card">
        <span class="supervision-number">{{ site.data.chehab.stats.supervisions.master }}</span>
        <span class="supervision-label">Master Students</span>
      </div>
    </div>

    <h3 class="student-section-title">PhD Students</h3>
    <div class="supervision-three-col fade-in-section">
      {% for student in site.data.chehab.research_supervision.phd_students %}
      <div class="supervision-item">
        <div class="supv-status {% if student.status == 'Current' %}current-student{% endif %}">{{ student.status }}</div>
        <div class="supv-name">{{ student.name }}</div>
        <div class="supv-title">{{ student.title }}</div>
      </div>
      {% endfor %}
    </div>

    <h3 class="student-section-title" style="margin-top:40px;">Master Students</h3>
    <div class="supervision-three-col fade-in-section">
      {% for student in site.data.chehab.research_supervision.master_students %}
      <div class="supervision-item">
        <div class="supv-status {% if student.status == 'Current' %}current-student{% endif %}">{{ student.status }}</div>
        <div class="supv-name">{{ student.name }}</div>
        <div class="supv-title">{{ student.title }}</div>
      </div>
      {% endfor %}
    </div>

  </div>
</section>

<script>
document.addEventListener('DOMContentLoaded', () => {

  // Award carousel
  const track   = document.getElementById('awardsTrack');
  const prevBtn = document.getElementById('awardsPrev');
  const nextBtn = document.getElementById('awardsNext');
  const dots    = document.querySelectorAll('.award-dot');
  const STEP    = 260;

  if (track) {
    prevBtn.addEventListener('click', () => track.scrollBy({ left: -STEP, behavior: 'smooth' }));
    nextBtn.addEventListener('click', () => track.scrollBy({ left:  STEP, behavior: 'smooth' }));
    track.addEventListener('scroll', () => {
      const idx = Math.round(track.scrollLeft / STEP);
      dots.forEach((d, i) => d.classList.toggle('active', i === idx));
    }, { passive: true });
  }

  // Tag marquees — clone then run
  ['tpcTrack', 'confTrack'].forEach(id => {
    const t = document.getElementById(id);
    if (!t) return;
    Array.from(t.children).forEach(c => t.appendChild(c.cloneNode(true)));
    t.style.animationPlayState = 'running';
  });

  // Scroll-triggered counters
  const counterObs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting && !e.target.dataset.counted) {
        e.target.dataset.counted = '1';
        const target = +e.target.getAttribute('data-target');
        const inc = target / 84;
        let val = 0;
        const t = setInterval(() => {
          val = Math.min(val + inc, target);
          e.target.textContent = Math.floor(val).toLocaleString();
          if (val >= target) { e.target.textContent = target.toLocaleString(); clearInterval(t); }
        }, 1000 / 60);
      }
    });
  }, { threshold: 0.3 });
  document.querySelectorAll('.counter').forEach(c => counterObs.observe(c));

  // Fade-in sections
  const fadeObs = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); fadeObs.unobserve(e.target); } });
  }, { threshold: 0.07 });
  document.querySelectorAll('.fade-in-section').forEach(el => fadeObs.observe(el));

});
</script>
