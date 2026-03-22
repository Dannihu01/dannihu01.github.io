---
title: Gallery
description:
layout: default
permalink: /gallery/
published: true
---

<p class="gallery-intro">
  Click a tab below to switch galleries and see what I've been up to.
</p>
<!-- Tab structure -->
<div class="tabs">
  <button class="tablink active" onclick="openTab(event, 'wedding')">Our Wedding ♥️</button>
  <button class="tablink" onclick="openTab(event, 'undergrad')">Undergrad Graduation</button>
  <button class="tablink" onclick="openTab(event, 'orchestra')">Violin & Orchestra</button>
  <button class="tablink" onclick="openTab(event, 'travel')">Travel & Nature</button>
  <button class="tablink" onclick="openTab(event, 'food')">Food</button>
</div>



<!-- Wedding Tab -->
<div id="wedding" class="tabcontent active">
  <h2>Our Wedding ♥️ 12-20-2025</h2>
  <p class="wedding-credit">
    Thank you to 
    <a href="https://www.instagram.com/tabronstudios_/?hl=en" target="_blank" rel="noopener">Kalynn Tabron</a> 
    with 
    <a href="https://www.oncelikeaspark.com/" target="_blank" rel="noopener">Once Like a Spark</a> 
    for the lovely photos
  </p>
    

  {% include gallery-folder.html folder="/assets/images/Wedding/" alt_prefix="Wedding" %}
</div>

<!-- Undergrad Graduation Tab -->
<div id="undergrad" class="tabcontent">
  <h2>Undergrad Graduation 🎓 4-29-2023</h2>
  {% include gallery-folder.html folder="/assets/images/Undergrad Graduation/" alt_prefix="Undergrad Graduation" %}
</div>

<div id="orchestra" class="tabcontent">
  <h2>Violin & Orchestra</h2>

  <figure class="video-figure">
  <div class="video-embed">
    <iframe
      src="https://www.youtube.com/embed/M450rkYvtC0"
      title="YouTube video player"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen>
    </iframe>
  </div>
  <figcaption class="caption">
    Senior Year Concerto Competition (2019), Zigeunerweisen by Sarasate
  </figcaption>
</figure>

  {% include gallery-folder.html folder="/assets/images/Orchestra/" alt_prefix="Orchestra" %}

  

</div>
<!-- Travel and Nature Tab -->
<div id="travel" class="tabcontent">
  <h2>Travel and Nature</h2>
  <h5>A non-exhaustive collection of my wonderful exploration of the world</h5>

  {% assign base_path = "/assets/images/Travel&Nature/" %}
  {% assign folders = "" | split: "" %}

  {% for file in site.static_files %}
    {% if file.path contains base_path %}
      {% assign relative = file.path | remove: base_path %}
      {% assign folder = relative | split: "/" | first %}

      {% unless folders contains folder %}
        {% assign folders = folders | push: folder %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for folder in folders %}
    {% capture folder_path %}{{ base_path }}{{ folder }}/{% endcapture %}

    <div class="gallery-section">
      <h3>{{ folder | replace: "-", " " | replace: "_", " " }}</h3>
      {% include gallery-folder.html folder=folder_path alt_prefix=folder %}
    </div>
  {% endfor %}
</div>

<!-- Food Tab -->
<div id="food" class="tabcontent">
  <h2>Food 😋</h2>
  {% include gallery-folder.html folder="/assets/images/Food/" alt_prefix="Food" %}
</div>

<footer style="text-align: center; margin-top: 20px; font-size: 14px; color: #555;">
  &copy; 2026 Danniell Hu. All rights reserved.
  These images may not be used or reproduced without permission.
</footer>

<div id="imageModal" class="modal" onclick="closeModal()">
  <span class="close" onclick="closeModal()">&times;</span>
  <img class="modal-content" id="modalImage">
</div>

<script>
  function openTab(event, tabId) {
    const tabContents = document.querySelectorAll('.tabcontent');
    tabContents.forEach(content => content.classList.remove('active'));

    const tabLinks = document.querySelectorAll('.tablink');
    tabLinks.forEach(link => link.classList.remove('active'));

    document.getElementById(tabId).classList.add('active');
    event.currentTarget.classList.add('active');
  }

  function openModal(img) {
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImage');

    modal.style.display = "block";
    modalImg.src = img.src;
  }

  function closeModal() {
    document.getElementById('imageModal').style.display = "none";
  }
</script>

<style>


/* Tabs */
.tabs {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 12px;                 /* more space between buttons */
  margin-bottom: 28px;      /* more separation from content */
}

.tablink {
  padding: 16px 28px;       /* bigger click target */
  font-size: 1.05rem;       /* slightly larger text */
  font-weight: 600;         /* bolder text */
  cursor: pointer;
  background-color: #f5f5f5;
  border-radius: 12px;      /* rounder = more button-y */
  border: 2px solid #ccc;   /* thicker border */
  transition:
    background-color 0.15s ease,
    border-color 0.15s ease,
    transform 0.1s ease,
    box-shadow 0.1s ease;
}

/* Hover state */
.tablink:hover {
  background-color: #e9e9e9;
  border-color: #999;
  transform: translateY(-1px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

/* Active tab */
.tablink.active {
  background-color: #007BFF;
  color: white;
  border-color: #007BFF;
  box-shadow: 0 6px 14px rgba(0,123,255,0.35);
  transform: translateY(0);
}

.tabcontent { 
  display: none; 
  text-align: center; 
}

.tabcontent.active { 
  display: block; 
}





  /* Gallery grid */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 14px;
  margin-top: 10px;
}
.wedding-credit {
  margin-bottom: 20px;  /* space below the line */
  font-size: 1rem;     /* optional: match body text */
}

.gallery-intro {
  text-align: center;
  margin: 15px auto 36px;  /* was 18px → now more space below */
  max-width: 900px;
  font-size: 1.1rem;
  font-weight: 600;
  color: #222;
  background: #fafafa;
  border: 2px solid #e0e0e0;
  border-radius: 12px;
  padding: 12px 16px;
}
/* Make each tile a consistent crop box */
.gallery-item {
  aspect-ratio: 3 / 4;   /* square tiles; change to 4/3 or 3/2 if you prefer */
  overflow: hidden;
  border-radius: 8px;
  margin-bottom: 16px; 
}


.caption {
  margin-top: 6px;
  margin-bottom: 6px;   /* small space after caption */
}

/* Crop-to-fill */
.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;      /* key: crops instead of distorting */
  object-position: center;/* crop from center */
  display: block;
  cursor: pointer;
  transition: transform 0.2s;
}

.gallery-item img:hover {
  transform: scale(1.02);
}

/* Responsive YouTube embed */
.video-embed {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;       /* was 0 auto 16px */
  aspect-ratio: 16 / 9;
}


.video-embed iframe {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  border: 0;
  border-radius: 8px;
}

.video-figure {
  max-width: 960px;
  margin: 0 auto 16px; 
  text-align: center;
}


.video-figure .caption {
  margin-top: 16px;
  margin-bottom: 16px;
}
  /* Modal */
  .modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
  }
  .modal-content {
    margin: 5vh auto;
    display: block;
    max-width: 92vw;
    max-height: 90vh;
  }
  .close {
    position: fixed;
    top: 18px;
    right: 26px;
    color: white;
    font-size: 34px;
    font-weight: bold;
    cursor: pointer;
  }
  .close:hover { color: #bbb; }

#undergrad .gallery {
  grid-template-columns: 1fr;   /* one per row */
  gap: 8px;                     /* small, normal spacing */
}

#undergrad .gallery-item {
  aspect-ratio: auto;          /* remove forced tile height */
  overflow: visible;
}

#undergrad .gallery-item img {
  width: 100%;
  height: auto;                /* natural height */
  object-fit: contain;        /* no cropping */
  display: block;
}

#orchestra .gallery {
  grid-template-columns: 1fr;   /* one per row */
  gap: 8px;                     /* small, normal spacing */
}

#orchestra .gallery-item {
  aspect-ratio: auto;          /* remove forced tile height */
  overflow: visible;
}

#orchestra .gallery-item img {
  width: 100%;
  height: auto;                /* natural height */
  object-fit: contain;        /* no cropping */
  display: block;
}

#orchestra .video-figure {
  margin-bottom: 32px;  /* increase space before first photo */
}

#travel h2 {
  margin-bottom: 4px;              /* tighten gap to subtitle */
  color: $brand-color;             /* uses your site’s primary color */
}

#travel h5 {
  margin-top: 0;                   /* remove default gap */
  margin-bottom: 28px;             /* space before first images */
  color: $text-color;              /* consistent with your theme */
  font-weight: 400;                /* lighter subtitle feel */
}

/* Section headers (folder names) */
#travel .gallery-section h3 {
  margin-top: 32px;
  margin-bottom: 12px;
  color: $brand-color;
}

</style>

