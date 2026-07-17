---
title: Publications
layout: default
permalink: /publications/
published: true
---

<div class="publications-container">
  <h1>Publications</h1>

  <p>More information about publications can be found on my <a href="https://scholar.google.com/citations?user=AUVET5QAAAAJ&hl" target="_blank">Google Scholar profile</a>.</p>

  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}

  {% for publication in sorted_publications %}
    <div class="publication-entry" id="publication-{{ publication.title | slugify }}">
      <div class="publication-venue-bubble">
        <span class="publication-venue-name">{{ publication.venue_short | default: publication.journal }}</span>
        <span class="publication-venue-year">{{ publication.year }}</span>
      </div>

      <div class="publication-details">
        <h2 class="publication-title">
          {% if publication.external_url %}
            <a href="{{ publication.external_url }}" target="_blank">{{ publication.title }}</a>
          {% else %}
            {{ publication.title }} <span class="publication-link-soon">(link coming soon)</span>
          {% endif %}
        </h2>

        <p class="publication-authors">{{ publication.authors }}</p>
        <p class="publication-journal">
          <em>{{ publication.journal }}</em>{% if publication.acceptance_rate %} <span class="publication-rate">· {{ publication.acceptance_rate }}</span>{% endif %}
        </p>

        <div class="publication-links">
          {% if publication.external_url %}
            <a href="{{ publication.external_url }}" target="_blank">Paper</a>
          {% endif %}
          {% if publication.abstract %}
            <details class="publication-abstract">
              <summary>Abstract</summary>
              <p>{{ publication.abstract }}</p>
            </details>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
