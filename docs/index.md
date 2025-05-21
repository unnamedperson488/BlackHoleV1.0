---
layout: default
title: Black Hole V1.0
---

<style>
  body {
    background-color: #0a0a0a;
    color: #e0e0e0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  nav {
    display: flex;
    justify-content: center;
    gap: 30px;
    padding: 20px;
    background-color: #111;
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  nav a {
    color: #00f0ff;
    text-decoration: none;
    font-weight: bold;
    text-shadow: 0 0 5px #00f0ff, 0 0 10px #00f0ff;
    transition: transform 0.2s;
  }

  nav a:hover {
    transform: scale(1.1);
  }

  .section {
    display: none;
    padding: 40px 20px;
  }

  .section.active {
    display: block;
  }

  .glow-title {
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    font-size: 2rem;
    margin-bottom: 20px;
  }

  .video-link {
    display: block;
    margin: 10px 0;
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff;
    text-decoration: none;
  }
</style>

<nav>
  <a href="#" onclick="showSection('home')">Home</a>
  <a href="#" onclick="showSection('product')">Product</a>
  <a href="#" onclick="showSection('about')">About</a>
  <a href="#" onclick="showSection('faq')">FAQ</a>
  <a href="#" onclick="showSection('media')">Media</a>
</nav>

<div id="home" class="section active">
  <h1 class="glow-title">Welcome to Black Hole V1.0</h1>
  <p>This is the main page of the site.</p>
</div>

<div id="product" class="section">
  <h1 class="glow-title">Product Information</h1>
  <ul>
    <li><strong>Product:</strong> Black Hole V1.0</li>
    <li><strong>Features:</strong> Dual-band jamming, compact case, long battery life</li>
    <li><strong>Price:</strong> $140</li>
  </ul>
</div>

<div id="about" class="section">
  <h1 class="glow-title">About Me</h1>
  <p>I’m unnamedperson488 — a professional hacker, builder, and creator of tech tools like Black Hole V1.0.</p>
</div>

<div id="faq" class="section">
  <h1 class="glow-title">Frequently Asked Questions</h1>
  <ul>
    <li><strong>Q:</strong> How do I use this device?<br><strong>A:</strong> A full guide is available in the documentation.</li>
    <li><strong>Q:</strong> Is it legal to use?<br><strong>A:</strong> Use responsibly. Follow your local laws.</li>
  </ul>
</div>

<div id="media" class="section">
  <h1 class="glow-title">Media & Links</h1>
  <p>Follow me on social media:</p>
  <ul>
    <li><a class="video-link" href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a></li>
    <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a></li>
    <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a></li>
  </ul>
  <h2 class="glow-title">Media Placeholders</h2>
  <a class="video-link" href="#">Video Placeholder 1</a>
  <a class="video-link" href="#">Video Placeholder 2</a>
  <a class="video-link" href="#">Video Placeholder 3</a>
</div>

<script>
function showSection(id) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}
</script>
