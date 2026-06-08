---
layout: about
permalink: /
profile:
  align: right
  image: danni_profile.jpg
published: true
---

Hi! My name is Danniell, but I usually go by Danni. 

I'm a second-year PhD Candidate in Computer Science at the University of Michigan, where I have the pleasure of working with Professor [**Elizabeth Bondi-Kelly**](https://sites.google.com/view/elizabethbondi) in the [**Realize Lab**](https://sites.google.com/view/realize-lab) and Professor [**Westley Weimer**](https://web.eecs.umich.edu/~weimerw/) in the Weimer Research Group.

<div class="research-highlight">
  <strong>My research is in AI for Social Impact (AISI). I study how we can design human-centered AI systems to address pressing societal challenges.</strong>  
  My work sits at the intersection of artificial intelligence, software engineering, and psychology, with a focus on participatory-driven approaches. I'm particularly interested in medical contexts such as women's reproductive health.
</div>

Previously, I was an R&D Embedded Software Engineer at [**Stryker**](https://www.stryker.com/us/en/index.html), where I developed PCBs and software for hospital bed ecosystems and medical monitoring technologies. I primarily worked in the medical division.

Outside of research, music is a huge part of my life. I've been playing violin for 18 years (and counting!) and continue to be involved by playing in the University of Michigan's [**Campus Symphony Orchestra**](https://sites.google.com/a/umich.edu/campus-orchestras/). I also love working with my hands (crocheting, sewing, gardening), cooking, and playing multiplayer competitive video games. I also really enjoy going fishing! 

<br> 

---

<div class="news-section-heading"><h2>News</h2></div>

{% assign news_items = site.news | sort: "date" | reverse %}
<ul class="news-list">
  {% for news in news_items %}
    <li class="news-item">

      <time class="news-date-col" datetime="{{ news.date | date: '%Y-%m-%d' }}">
        <span class="news-month-day">{{ news.date | date: "%b %d" }}</span>
        <span class="news-year">{{ news.date | date: "%Y" }}</span>
      </time>

      <div class="news-body">
        <div class="news-header">
          <span class="news-title">{{ news.title }}</span>
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
