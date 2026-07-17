---
layout: about
permalink: /
published: true
---

<div class="availability-note">
  <strong>🔎 I'm seeking a research internship for summer 2027.</strong>
  Check out my <a href="{{ '/CV/' | relative_url }}">CV</a> and
  <a href="{{ '/publications/' | relative_url }}">publications</a>.
</div>

<div class="profile-card right">
  <img class="profile" src="{{ '/assets/images/danni_profile.jpg' | relative_url }}" alt="Danniell Hu">
  <p class="profile-contact">dannihu [at] umich [dot] edu</p>
</div>

Hi! My name is Danniell, but I usually go by Danni.


I'm a PhD Candidate in Computer Science at the University of Michigan, advised by [**Elizabeth Bondi-Kelly**](https://sites.google.com/view/elizabethbondi) in the [**Realize Lab**](https://sites.google.com/view/realize-lab) and [**Westley Weimer**](https://web.eecs.umich.edu/~weimerw/) in the Weimer Research Group. 


<div class="research-highlight">
  <strong>I study why AI systems built for social impact fail the people they're meant to serve, and how to build ones that don't.</strong>
  Human context (needs, constraints, values) gets lost during development, and deployed systems reshape the people around them in return. My research develops methods for both directions: stakeholder-grounded design, and evaluation of how AI affects real users. I'm particularly interested in medical contexts such as women's reproductive health. 
</div>


<hr class="section-rule">

Previously, I was an R&D Embedded Software Engineer at [**Stryker**](https://www.stryker.com/us/en/index.html), where I developed PCBs and software for hospital bed ecosystems and medical monitoring technologies. I primarily worked in the medical division.

Outside of research, music is a huge part of my life. I've been playing violin for 18 years (and counting!) and continue to be involved by playing in the University of Michigan's [**Campus Symphony Orchestra**](https://sites.google.com/a/umich.edu/campus-orchestras/). I also love sewing, crocheting, cooking, and playing multiplayer competitive video games. 

<hr class="section-rule">

<div class="news-section-heading"><h2>News</h2></div>

{% assign news_items = site.news | sort: "date" | reverse %}
<ul class="news-list">
  {% for news in news_items %}
    <li class="news-item">

      <time class="news-date" datetime="{{ news.date | date: '%Y-%m-%d' }}">
        <span class="news-date__month">{{ news.date | date: "%b" }}</span>
        <span class="news-date__day">{{ news.date | date: "%d" }}</span>
        <span class="news-date__year">{{ news.date | date: "%Y" }}</span>
      </time>

      <div class="news-body">
        <div class="news-header">
          <span class="news-title">{{ news.title }}</span>
          {% if news.acceptance_rate %}
            <span class="acceptance-rate-badge">{{ news.acceptance_rate }}</span>
          {% endif %}
          {% if news.publication_url and news.publication_url != "" %}
            <a href="{{ news.publication_url }}" target="_blank" rel="noopener" class="news-read-more">
              Read more →
            </a>
          {% endif %}
        </div>

        {% if news.image %}
          <div class="news-image-wrapper">
            <img src="{{ news.image | relative_url }}"
                 alt="{{ news.title }}"
                 class="news-image">
          </div>
          {% if news.image_credit %}
            <div class="news-image-credit">{{ news.image_credit }}</div>
          {% endif %}
        {% endif %}

        <p class="news-content">{{ news.content | strip_html | truncatewords: 150 }}</p>
      </div>

    </li>
  {% endfor %}
</ul>
