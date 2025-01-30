---
title: Gallery
description: 
layout: default
permalink: /gallery/
published: true
---

Welcome to my gallery! Click tabs to see what I've been up to.

<!-- Tab structure -->
<div class="tabs">
  <button class="tablink active" onclick="openTab(event, 'undergrad')">Undergrad Graduation</button>
  <button class="tablink" onclick="openTab(event, 'orchestra')">Orchestra</button>
  <button class="tablink" onclick="openTab(event, 'food')">Food</button>
  <button class="tablink" onclick="openTab(event, 'travel')">Travel & Nature</button>
</div>

<!-- Undergrad Graduation Tab -->
<div id="undergrad" class="tabcontent active">
  <h2>Undergrad Graduation</h2>
  <img src="../assets/images/grad1.jpg" alt="Undergrad Graduation 1">
  <p>In the Law Quad.</p>
  <img src="../assets/images/grad2.jpg" alt="Undergrad Graduation 2">
  <p>My wonderful best friends.</p>
</div>

<!-- Orchestra Tab -->
<div id="orchestra" class="tabcontent">
  <h2>Orchestra</h2>
  <img src="../assets/images/orchestra242.jpg" alt="Orchestra 4">
  <img src="../assets/images/orchestra241.jpg" alt="Orchestra 3">
  
  <p>Late 2024</p>
  <img src="../assets/images/orchestra21.jpg" alt="Orchestra 1">
  <img src="../assets/images/orchestra213.jpg" alt="Orchestra 2">
  <p>Early 2021</p>
  
</div>


<!-- Food Tab -->
<div id="food" class="tabcontent">
  <h2>Food</h2>
  <div class="gallery">
    <img src="../assets/images/Food/IMG_1828_Original.JPG" alt="Food 1" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_1986_Original.JPG" alt="Food 2" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_2503_Original.JPG" alt="Food 3" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_2505_Original.JPG" alt="Food 4" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_2987_Original.JPG" alt="Food 5" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3016_Original.JPG" alt="Food 6" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3067_Original.JPG" alt="Food 7" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3162_Original.JPG" alt="Food 8" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3208_Original.JPG" alt="Food 9" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3624_Original.JPG" alt="Food 11" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3733_Original.JPG" alt="Food 12" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3738_Original.JPG" alt="Food 13" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_3740_Original.JPG" alt="Food 14" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_4467_Original.JPG" alt="Food 16" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_5331_Original.JPG" alt="Food 17" onclick="openModal(this)">
    <img src="../assets/images/Food/IMG_5394_Original.JPG" alt="Food 18" onclick="openModal(this)">
  </div>
</div>

<!-- Travel and Nature Tab -->
<div id="travel" class="tabcontent">
  <h2>Travel and Nature</h2>
  <div class="gallery">
    <img src="../assets/images/Travel&Nature/IMG_1134_Original.JPG" alt="Travel and Nature 1" onclick="openModal(this)">
    <img src="../assets/images/Travel&Nature/IMG_2969_Original.JPG" alt="Travel and Nature 2" onclick="openModal(this)">
    <img src="../assets/images/Travel&Nature/IMG_4277_Original.JPG" alt="Travel and Nature 3" onclick="openModal(this)">
    <img src="../assets/images/Travel&Nature/IMG_4308_Original.JPG" alt="Travel and Nature 4" onclick="openModal(this)">
    <img src="../assets/images/Travel&Nature/IMG_5214_Original.JPG" alt="Travel and Nature 5" onclick="openModal(this)">
    <img src="../assets/images/Travel&Nature/IMG_5851_Original.JPG" alt="Travel and Nature 6" onclick="openModal(this)">
  </div>
</div>

<footer style="text-align: center; margin-top: 20px; font-size: 14px; color: #555;">
  &copy; 2025 [Danniell Hu]. All rights reserved. 
  These images are the property of Danniell Hu and may not be used or reproduced without permission.
</footer>

<div id="imageModal" class="modal" onclick="closeModal()">
  <span class="close" onclick="closeModal()">&times;</span>
  <img class="modal-content" id="modalImage">
  <div id="caption"></div>
</div>

<!-- Tab functionality -->
<script>
  function openTab(event, tabId) {
    // Hide all tab contents
    const tabContents = document.querySelectorAll('.tabcontent');
    tabContents.forEach(content => content.classList.remove('active'));

    // Remove active class from all tab links
    const tabLinks = document.querySelectorAll('.tablink');
    tabLinks.forEach(link => link.classList.remove('active'));

    // Show the clicked tab and set it as active
    document.getElementById(tabId).classList.add('active');
    event.currentTarget.classList.add('active');
  }

  function openModal(img) {
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImage');
    const captionText = document.getElementById('caption');

    modal.style.display = "block";
    modalImg.src = img.src;
    captionText.innerHTML = img.alt;
  }

  // Close the modal
  function closeModal() {
    const modal = document.getElementById('imageModal');
    modal.style.display = "none";
  }


</script>

<style>
  /* Tab styles */
  .tabs {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  .tablink {
    padding: 15px 30px;
    cursor: pointer;
    background-color: #f0f0f0;
    margin: 0 5px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  .tablink.active {
    background-color: #007BFF;
    color: white;
    border-color: #007BFF;
  }
  .tabcontent {
    display: none;
    text-align: center;
  }
  .tabcontent.active {
    display: block;
  }
  .tabcontent img {
    max-width: 100%;
    margin: 10px 0;
  }

  /* Gallery Images */
  .gallery img {
    width: auto ; /* Adjust as needed */
    height: auto;
    margin: 10px;
    cursor: pointer;
    border-radius: 5px;
    transition: transform 0.2s; /* Add hover effect */
  }
  .gallery img:hover {
    transform: scale(1.05); /* Slight zoom on hover */
  }

  /* Modal */
  .modal {
    display: none; /* Hidden by default */
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.9); /* Black background with transparency */
  }

  /* Modal Content */
  .modal-content {
    margin: auto;
    display: block;
    max-width: 90%;
    max-height: 90%;
  }

  /* Caption */
  #caption {
    text-align: center;
    color: white;
    padding: 10px 20px;
    font-size: 16px;
  }

  /* Close Button */
  .close {
    position: absolute;
    top: 20px;
    right: 35px;
    color: white;
    font-size: 30px;
    font-weight: bold;
    cursor: pointer;
  }
  .close:hover, .close:focus {
    color: #bbb;
    text-decoration: none;
    cursor: pointer;
  }
</style>
