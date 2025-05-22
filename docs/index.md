White card cards 
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

  nav a, nav span {
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

  .glow-block {
    border: 1px solid #00f0ff44;
    padding: 20px;
    margin-bottom: 20px;
    background-color: #111;
    box-shadow: 0 0 10px #00f0ff33;
    border-radius: 8px;
  }
</style>

<nav>
  <span style="font-size: 1.4rem;">Black Hole V1.0</span>
  <a href="#" onclick="showSection('home')">Home</a>
  <a href="#" onclick="showSection('product')">Product</a>
  <a href="#" onclick="showSection('about')">About</a>
  <a href="#" onclick="showSection('faq')">FAQ</a>
  <a href="#" onclick="showSection('media')">Media</a>
  <a href="#" onclick="showSection('demos')">Demos</a>
  <a href="#" onclick="showSection('firmware')">Firmware</a>
  <a href="#" onclick="showSection('timeline')">Timeline</a>
</nav>

<div id="home" class="section active">
  <h1 class="glow-title">🌌 Black Hole V1.0</h1>
  <p>Welcome to the official hub for development, documentation, and product information.</p>
</div>

<div id="product" class="section">
  <h1 class="glow-title">Product Information</h1>
  <div class="glow-block">
    <strong>Product:</strong> Black Hole V1.0<br>
    <strong>Features:</strong> Dual-band jamming, SMA antennas, LiPo support, case-compatible design.<br>
    <strong>Price:</strong> $140
  </div>
  <div class="glow-block">
    <strong>Inventory:</strong> <em>Live tracking coming soon — message @unnamedperson488 for availability.</em>
  </div>
</div>

<div id="about" class="section">
  <h1 class="glow-title">About Me</h1>
  <p>I’m unnamedperson488 — professional hacker, builder, and designer of the Black Hole project. This site documents the evolution and community around my custom ESP32-based tools.</p>
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
  <ul>
    <li><a class="video-link" href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a></li>
    <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a></li>
    <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a></li>
  </ul>
  <h2 class="glow-title">Video Placeholders</h2>
  <a class="video-link" href="#">Demo Clip 1</a>
  <a class="video-link" href="#">Demo Clip 2</a>
</div>

<div id="demos" class="section">
  <h1 class="glow-title">Performance Demos</h1>
  <div class="glow-block">
    <p><strong>Signal Range Test:</strong> Demonstrating both 2.4GHz and 5GHz range vs environment interference. <a href="#">[Link]</a></p>
  </div>
  <div class="glow-block">
    <p><strong>Battery Runtime:</strong> Using a 1200mAh LiPo. Real-world performance test. <a href="#">[Link]</a></p>
  </div>
</div>

<div id="firmware" class="section">
  <h1 class="glow-title">Firmware Download</h1>
  <div class="glow-block">
    <p>Latest firmware: <a href="#">BlackHoleV1.0_Firmware.bin</a></p>
    <p>How to flash: Use ESPTool or Arduino IDE. Full flashing guide will be linked here soon.</p>
  </div>
</div>

<div id="timeline" class="section">
  <h1 class="glow-title">Development Timeline</h1>
  <div class="glow-block">
    <strong>March 2024:</strong> Idea & research begins.
  </div>
  <div class="glow-block">
    <strong>April 2024:</strong> First ESP32 PCB prototype.
  </div>
  <div class="glow-block">
    <strong>May 2024:</strong> BW16 integration for dual-band.
  </div>
  <div class="glow-block">
    <strong>June 2024:</strong> Release of Black Hole V1.0 to public.
  </div>
</div>

<script>
function showSection(id) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}
</script>
