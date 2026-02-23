---
layout: default
title: Publications
permalink: /publications/
---

<section>
  <div class="wrapper">
    <!-- Filters -->
    <div style="margin-bottom: 30px; display: flex; gap: 20px; align-items: center; flex-wrap: wrap;">
      <div>
        <label for="year-filter" style="font-weight: 600; margin-right: 10px;">Year:</label>
        <select id="year-filter" onchange="filterPublications()" style="padding: 8px 12px; border-radius: 6px; border: 1px solid #ddd; outline: none; cursor: pointer;">
          <option value="all">All</option>
          {% assign years = site.data.publications.publications | map: "year" | uniq | sort | reverse %}
          {% for year in years %}
          <option value="{{ year }}">{{ year }}</option>
          {% endfor %}
        </select>
      </div>

      <div>
        <label for="type-filter" style="font-weight: 600; margin-right: 10px;">Type:</label>
        <select id="type-filter" onchange="filterPublications()" style="padding: 8px 12px; border-radius: 6px; border: 1px solid #ddd; outline: none; cursor: pointer;">
          <option value="all">All</option>
          <option value="journal">Journal</option>
          <option value="conference">Conference</option>
        </select>
      </div>
    </div>
    
    {% assign pubs_by_year = site.data.publications.publications | group_by: "year" | sort: "name" | reverse %}
    
    <div id="publications-container">
      {% for group in pubs_by_year %}
      <div class="pub-group" data-year="{{ group.name }}">
        <h3 class="pub-year">{{ group.name }}</h3>
        <ul class="pub-list">
          {% for pub in group.items %}
          {% assign pub_type = pub.is_journal | default: false %}
          <li class="pub-item" data-year="{{ pub.year }}" data-type="{% if pub_type %}journal{% else %}conference{% endif %}">
            <span class="pub-title">
              {% if pub.link %}
              <a href="{{ pub.link }}" target="_blank" style="color: var(--accent-blue); text-decoration: none; font-weight: 600;">{{ pub.title }}</a>
              {% else %}
              {{ pub.title }}
              {% endif %}
              {% if pub_type %}
              <span style="display: inline-block; font-size: 0.70rem; background: #e6f6f4; color: #108a7e; padding: 2px 8px; border-radius: 12px; margin-left: 8px; vertical-align: middle; font-weight: 700; border: 1px solid #bce6df;">Journal</span>
              {% else %}
              <span style="display: inline-block; font-size: 0.70rem; background: #f1f3f5; color: #495057; padding: 2px 8px; border-radius: 12px; margin-left: 8px; vertical-align: middle; font-weight: 700; border: 1px solid #dee2e6;">Conference</span>
              {% endif %}
            </span>
            <div class="pub-authors">{{ pub.authors }}</div>
            <div class="pub-meta" style="font-size: 0.9rem; margin-top: 5px;">
              <em>{{ pub.publisher }}</em>
            </div>
          </li>
          {% endfor %}
        </ul>
      </div>
      {% endfor %}
    </div>

    <!-- No results message -->
    <div id="no-results" style="display: none; text-align: center; margin-top: 40px; color: var(--text-light); font-size: 1.1rem;">
      No publications match your filter criteria.
    </div>
  </div>
</section>

<script>
function filterPublications() {
  const yearFilter = document.getElementById('year-filter').value;
  const typeFilter = document.getElementById('type-filter').value;
  const pubGroups = document.querySelectorAll('.pub-group');
  let totalVisible = 0;

  pubGroups.forEach(group => {
    const items = group.querySelectorAll('.pub-item');
    let groupVisibleCount = 0;

    items.forEach(item => {
      const itemYear = item.getAttribute('data-year');
      const itemType = item.getAttribute('data-type');
      
      const yearMatch = (yearFilter === 'all' || itemYear === yearFilter);
      const typeMatch = (typeFilter === 'all' || itemType === typeFilter);

      if (yearMatch && typeMatch) {
        item.style.display = '';
        groupVisibleCount++;
      } else {
        item.style.display = 'none';
      }
    });

    if (groupVisibleCount > 0) {
      group.style.display = '';
      totalVisible += groupVisibleCount;
    } else {
      group.style.display = 'none';
    }
  });

  const noResults = document.getElementById('no-results');
  if (totalVisible === 0) {
    noResults.style.display = 'block';
  } else {
    noResults.style.display = 'none';
  }
}
</script>
