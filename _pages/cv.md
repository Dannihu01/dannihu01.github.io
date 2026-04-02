---
title: CV
layout: default
permalink: /cv/
published: true
---

{% assign cv_pdf = '/assets/files/danni_cv.pdf' %}

<div class="cv-header">
  <a class="cv-download" href="{{ cv_pdf | relative_url }}" download>
    Download CV (PDF)
  </a>
</div>

<div class="cv-embed">
  <iframe src="{{ cv_pdf | relative_url }}" title="CV PDF"></iframe>
</div>

<p class="cv-fallback">
  If the PDF preview doesn’t load, you can
  <a href="{{ cv_pdf | relative_url }}" target="_blank" rel="noopener">open it in a new tab</a>.
</p>
