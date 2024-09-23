---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
<div style="border-bottom: 1px dotted #ccc; margin-bottom: 30px;"></div>

Recent News
======

<div style="margin-bottom: 30px;"></div>
<div style="display: flex; justify-content: space-between;">
  <div><strong> 🎉 New Paper Acceptance! 🎉</strong></div>
  <div><strong>9/18/2024</strong></div>
</div>
<div style="margin-bottom: 10px;">Our paper titled “Towards a Cognitive Model of Dynamic Debugging: Does Identifier Construction Matter?” was accepted to IEEE Transactions in Software Engineering (TSE)</div>

<div style="margin-bottom: 30px;"></div>

<div style="border-bottom: 1px dotted #ccc; margin-bottom: 30px;"></div>


Peer Reviewed Publications
======

{% if site.publication_category %}
  {% for category in site.publication_category  %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}

      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}

