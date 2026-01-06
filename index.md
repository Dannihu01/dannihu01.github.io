---
layout: about
permalink: /
profile:
  align: right
  image: profile.png
published: true
---

Hi! My name is Danniell, but I usually go by Danni. 

I'm a PhD Candidate in Computer Science at the University of Michigan, where I have the pleasure of working with Professor [**Elizabeth Bondi-Kelly**](https://sites.google.com/view/elizabethbondi) in the [**Realize Lab**](https://sites.google.com/view/realize-lab) and Professor [**Westley Weimer**](https://web.eecs.umich.edu/~weimerw/) in the Weimer Research Group.

<!-- <div style="background: #f0f8ff; border-left: 4px solid #007bc0; padding: 1rem; margin: 1rem 2rem 1rem 0; max-width: 600px;">
  <strong>I design AI systems for Social Impact.</strong> My research focuses on building human-centered AI systems that integrate participatory design and interdisciplinary methods. I'm particularly interested in medical contexts such as women's reproductive health.
</div> -->
<!-- #e6f0fa -->

<div style="background-color: #D1E3FF; border-left: 4px solid #005fa3; border-right: 4px solid #005fa3;padding: 1rem; border-radius: 6px; margin: 1rem 2rem 1rem 0; max-width: 620px;">
  <strong>My research is in AI for Social Impact (AISI). I study how we can design human-centered AI systems to address pressing societal challenges.</strong>  
  My work sits at the intersection of artificial intelligence, software engineering, and psychology, with a focus on participatory-driven approaches.  I'm particularly interested in medical contexts such as women's reproductive health.
</div>

<!-- <div style="background-color: #e6f0fa; border-left: 4px solid #005fa3; border-right: 4px solid #005fa3; padding: 1rem; border-radius: 6px; margin: 1rem 2rem 1rem 0;">
<strong>Why is this important?</strong>  
  AI technologies are increasingly deployed in areas such as healthcare, conservation, and social services, which are domains where decisions directly affect people's lives. However, many AI systems fail because they are misaligned with the needs, values, and priorities of the communities they are meant to serve. Without intentional design practices, we risk building tools that reinforce inequities, waste resources, and cause harm.  

</div> -->



Previously, I was an R&D Embedded Software Engineer at [**Stryker**](https://www.stryker.com/us/en/index.html), where I developed PCBs for hospital bed ecosystems and medical monitoring technologies. I primarily worked in the medical division.

Outside of research, music is a huge part of my life. I play violin in the University of Michigan’s [**Campus Symphony Orchestra**](https://sites.google.com/a/umich.edu/campus-orchestras/) and I’m always looking for new music to listen to. 

I also love working with my hands (crocheting, sewing, cricut-ing, etc.), cooking, and playing video games. Recently, I've become Grandmaster in Teamfight Tactics! 

<br> 

---

## News

{% assign news_items = site.news | sort: "date" | reverse %}
<ul class="news-list">
  {% for news in news_items %}
    <li style="margin-bottom: 1.5rem; padding-bottom: 1rem; border-bottom: 1px solid #ccc;">

      <div style="display: flex; align-items: baseline; gap: 0.5rem; flex-wrap: wrap;">
        <strong>{{ news.date | date: "%B %d, %Y" }}:</strong>
        <span style="color: #005fa3; font-weight: 700;">{{ news.title }}</span>

        {% if news.publication_url and news.publication_url != "" %}
          <a href="{{ news.publication_url }}" target="_blank" rel="noopener"
             style="margin-right: auto; display: inline-block; padding: 0.25rem 0.7rem;
                    font-size: 0.85rem; font-weight: 600; background-color: #D1E3FF;
                    color: #005fa3; border: 2px solid #005fa3; text-decoration: none;
                    border-radius: 6px;">
            Read more
          </a>
        {% endif %}
      </div>

      {% if news.image %}
        <div style="margin: 0.75rem 0 0.25rem 0;">
          <img src="{{ news.image | relative_url }}"
               alt="{{ news.title }}"
               style="max-width: 100%; height: auto; border-radius: 6px; display: block;">
        </div>

        {% if news.image_credit %}
          <div style="margin: 0 0 0.9rem 0; font-size: 0.9rem; color: #555;">
            {{ news.image_credit }}
          </div>
        {% endif %}
      {% endif %}

      <p style="margin: 0.5rem 0 0 0;">
        {{ news.content | strip_html | truncatewords: 150 }}
      </p>

    </li>
  {% endfor %}
</ul>



<!-- [Gradfolio](https://github.com/jitinnair1/gradfolio){:target="_blank"} is a responsive, dark-mode ready Jekyll theme designed keeping academia in mind. The easiest way to install the theme is to fork it using GitHub. Check the README file for [instructions](https://github.com/jitinnair1/gradfolio#installation){:target="_blank"}.

If you want to use this space to write your biography here, edit the `index.md` file. You can put a picture in, too. Rename your picture to `profile.png` and put it in the `assets/images/` folder.

The social-icons footer can be used to link profiles from GitHub, OrcID and ReasearchGate aprart form the usual Twitter, LinkedIn and Facebook. You can add your user ID in the `_config.yml` file to link your accounts.

PS: If you liked the theme, do star it on GitHub!

### Also, check out:

- [autoCV](https://github.com/jitinnair1/autocv) - a LaTeX template that builds and deploys the CV using GitHub Actions, so you will always have a ready link for your latest CV
- [Tail](https://github.com/jitinnair1/tail) - a minimal, quick-setup template for a blog -->
