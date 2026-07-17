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
      <h2 class="publication-title">
        {% if publication.external_url %}
          <a href="{{ publication.external_url }}" target="_blank">{{ publication.title }}</a>
        {% else %}
          {{ publication.title }} <span class="publication-link-soon">(link coming soon)</span>
        {% endif %}
      </h2>

      <p class="publication-authors"><strong>Authors:</strong> {{ publication.authors }}</p>
      <p class="publication-journal">
        <strong>Published in:</strong> <em>{{ publication.journal }}</em>, {{ publication.year }}
      </p>

      {% if publication.abstract %}
        <details class="publication-abstract">
          <summary>View Abstract</summary>
          <p>{{ publication.abstract }}</p>
        </details>
      {% endif %}
    </div>
    <hr/>
  {% endfor %}
</div>
