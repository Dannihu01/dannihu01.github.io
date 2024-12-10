---
layout: about
permalink: /
profile:
  align: right
  image: profile.png
published: true
---

I am a first year PhD student in Computer Science at the University of Michigan, where I have the pleasure of working with [Dr. Elizabeth Bondi-Kelly](https://sites.google.com/view/elizabethbondi) in the [Realize Lab](https://sites.google.com/view/realize-lab). My current research focuses on advancing artificial intelligence in healthcare through participatory AI frameworks, multi-agent systems, and exploring how we can apply requirements engineering techniques to the development of AI systems. I am especially interested in applications in women’s health and am driven by a passion for developing AI systems that are ethical, trustworthy, and human-centered. 

In addition to my current work, I’ve explored research in software engineering and medical imaging, studying how programmer brains work at a foundational, cognitive level.

Prior to my PhD, I worked as an R&D embedded software engineer at [Stryker](https://www.stryker.com/us/en/index.html). There, I gained hands-on experience by developing PCBs for hospital bed ecosystems and innovating in medical monitoring technologies while staying grounded to real-world needs through voice-of-customer visits.

Outside of research, I play violin with the university [Campus Symphony Orchestra](https://sites.google.com/a/umich.edu/campus-orchestras/) and enjoy creating music in FL Studio. I also love crocheting, cooking, playing video games, and building computers.

## News

{% assign news_items = site.news | sort: "date" | reverse %}
<ul class="news-list">
  {% for news in news_items %}
    <li>
      <strong>{{ news.date | date: "%B %d, %Y" }}:</strong>
      <a href="{{ site.baseurl }}{{ news.publication_url }}">{{ news.title }}</a>
      <p>{{ news.content | strip_html | truncatewords: 150 }}</p>
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
