---
layout: about
permalink: /
profile:
  align: right
  image: profile.png
published: true
---

I am a first year PhD student in Computer Science at the University of Michigan, where I have the pleasure of working with [Dr. Elizabeth Bondi-Kelly](https://sites.google.com/view/elizabethbondi) in the [RealAIze Lab](https://sites.google.com/view/realize-lab). My research focuses on advancing artificial intelligence in healthcare through participatory AI frameworks, with an emphasis on applications in women’s health. I am passionate about developing ethical, trustworthy AI systems and exploring how inclusive, human-centered approaches can shape more adaptive and responsible AI.

Prior to my PhD, I worked as an R&D embedded software engineer at [Stryker](https://www.stryker.com/us/en/index.html). There, I gained hands-on experience by developing PCBs for hospital bed ecosystems, innovating in medical monitoring technologies, and debugging in the field, all while staying grounded to real-world needs through voice-of-customer visits.

Outside of research, I play violin with the university [Campus Symphony Orchestra](https://sites.google.com/a/umich.edu/campus-orchestras/) and enjoy creating music in FL Studio. I also love crocheting, cooking, and unwinding with PC video games.

## News

{% assign news_items = site.news | sort: "date" | reverse %}
<ul class="news-list">
  {% for news in news_items %}
    <li>
      <strong>{{ news.date | date: "%B %d, %Y" }}:</strong>
      <a href="{{ site.baseurl }}{{ news.publication_url }}">{{ news.title }}</a>
      <p>{{ news.content | strip_html | truncatewords: 20 }}</p>
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
