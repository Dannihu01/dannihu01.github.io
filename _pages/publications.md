---
title:
description: 
layout: default
permalink: /publications/
published: true
---


<div class="publications-container">
  <h1>Publications</h1>

  <!-- Google Scholar Link -->
  <p>More information about publications can be found on my <a href="https://scholar.google.com/citations?user=AUVET5QAAAAJ&hl" target="_blank">Google Scholar profile</a>.</p>

  <!-- Publications Loop -->
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}

{% for publication in sorted_publications %}
  <div class="publication-entry" id="publication-{{ publication.title | slugify }}">
    <h2 class="publication-title">
      <a href="{{ publication.external_url }}" target="_blank">{{ publication.title }}</a>
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

<style>
  .publications-container {
    max-width: 1100px;
    margin: auto;
    padding: 20px;
  }
  .publication-entry {
    margin-bottom: 20px;
    padding: 15px;
    border-radius: 8px;
    /* background-color: #f9f9f9; */
    background-color: #ECECEC;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  .publication-title {
    font-size: 1.4em;
    /* color: #333; */
    color: #0066cc;
    margin-bottom: 8px;
  }
  .publication-authors, .publication-journal {
    font-size: 0.9em;
    color: #555;
    margin: 4px 0;
  }
  .publication-link a {
    /* color: #0066cc; */
    color: #black;
    text-decoration: none;
    font-weight: bold;
  }
  .publication-link a:hover {
    text-decoration: underline;
  }
  .publication-abstract summary {
    font-weight: bold;
    color: #333;
    cursor: pointer;
  }
  .publication-abstract p {
    font-size: 0.9em;
    color: #333;
    margin-top: 5px;
  }

  /* Highlighted author style */
  .highlight-author {
    color: #20A4F3; /* Change to your preferred color */
    font-weight: bold;
  }
</style>