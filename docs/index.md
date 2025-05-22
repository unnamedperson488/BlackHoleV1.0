---
layout: default
title: Black Hole V1.0
---

<style>
  :root {
    --primary-color: #00f0ff;
    --bg-color: #0a0a0a;
    --card-bg: #111;
    --text-color: #e0e0e0;
    --shadow-color: #00f0ff33;
    --shadow-glow: #00f0ff44;
  }

  [data-theme="light"] {
    --primary-color: #007bff;
    --bg-color: #f5f5f5;
    --card-bg: #ffffff;
    --text-color: #333333;
    --shadow-color: #0000001a;
    --shadow-glow: #007bff44;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    line-height: 1.6;
    transition: background-color 0.3s, color 0.3s;
  }

  nav {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    grid-template-rows: auto auto auto;
    justify-items: center;
    align-items: center;
    gap: 10px;
    padding: 15px;
    background-color: var(--card-bg);
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 5px var(--shadow-color);
  }

  nav span {
    grid-column: 1 / -1;
    grid-row: 3 / 4;
    justify-self: center;
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--shadow-glow);
  }

  nav a {
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 600;
    text-shadow: 0 0 5px var(--shadow-glow);
    transition: transform 0.2s, color 0.2s;
    padding: 8px 12px;
  }

  nav a:hover, nav a:focus {
    transform: scale(1.05);
    color: var(--primary-color);
    text-shadow: 0 0 8px var(--shadow-glow);
    outline: none;
  }

  .section {
    display: none;
    padding: 30px 15px;
    max-width: 1200px;
    margin: 0 auto;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s, transform 0.5s;
  }

  .section.active {
    display: block;
    opacity: 1;
    transform: translateY(0);
  }

  .glow-title {
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--shadow-glow);
    font-size: clamp(1.8rem, 5vw, 2.2rem);
    margin-bottom: 20px;
    position: relative;
  }

  .glow-title::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 50px;
    height: 2px;
    background: var(--primary-color);
    transition: width 0.3s;
  }

  .glow-title:hover::after {
    width: 100px;
  }

  .video-link {
    display: inline-block;
    margin: 8px 0;
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.2s;
  }

  .video-link:hover, .video-link:focus {
    color: var(--primary-color);
    text-shadow: 0 0 8px var(--shadow-glow);
  }

  .glow-block {
    border: 1px solid var(--shadow-glow);
    padding: 20px;
    margin-bottom: 20px;
    background-color: var(--card-bg);
    box-shadow: 0 0 10px var(--shadow-color);
    border-radius: 8px;
    transition: transform 0.3s, box-shadow 0.3s;
  }

  .glow-block:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px var(--shadow-color);
  }

  .followers-stats {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 15px;
    margin-bottom: 20px;
  }

  .stat-item {
    text-align: center;
    padding: 10px;
    background: var(--card-bg);
    border-radius: 6px;
    border: 1px solid var(--shadow-glow);
  }

  .stat-item span {
    display: block;
    font-size: 1.5rem;
    color: var(--primary-color);
    font-weight: bold;
    text-shadow: 0 0 5px var(--shadow-glow);
  }

  @media (max-width: 600px) {
    nav {
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 8px;
      padding: 10px;
    }

    nav a {
      padding: 6px 8px;
      font-size: 0.9rem;
    }

    .section {
      padding: 20px 10px;
    }
  }
</style>

<nav>
  <a href="#" onclick="showSection('home')" aria-label="Home Section">Home</a>
  <a href="#" onclick="showSection('product')" aria-label="Product Section">Product</a>
  <a href="#" onclick="showSection('about')" aria-label="About Section">About</a>
  <a href="#" onclick="showSection('faq')" aria-label="FAQ Section">FAQ</a>
  <a href="#" onclick="showSection('media')" aria-label="Media Section">Media</a>
  <a href="#" onclick="showSection('demos')" aria-label="Demos Section">Demos</a>
  <a href="#" onclick="showSection('firmware')" aria-label="Firmware Section">Firmware</a>
  <a href="#" onclick="showSection('timeline')" aria-label="Timeline Section">Timeline</a>
  <span>Black Hole V1.0</span>
</nav>

<div id="home" class="section active">
  <h1 class="glow-title">🌌 Black Hole V1.0</h1>
  <p>Welcome to the official hub for development, documentation, and product information.</p>
  <div class="followers-stats">
    <div class="stat-item">
      <span>84</span> TikTok Followers
    </div>
    <div class="stat-item">
      <span>0</span> YouTube Subscribers
    </div>
    <div class="stat-item">
      <span>0</span> Instagram Followers
    </div>
  </div>
</div>

<div id="product" class="section">
  <h1 class="glow-title">Product Information</h1>
  <div class="glow-block">
    <strong>Product:</strong> Black Hole V1.0<br>
    <strong>Features:</strong> Dual-band jamming, SMA antennas, LiPo support, case-compatible design.<br>
    <strong>Price:</strong> $140
  </div>
  <div class="glow-block">
    <strong>Inventory:</strong> <em>Live tracking coming soon — message <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for availability.</em>
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
    <li><a class="video-link" href="https://instagram.com/unnamedperson488" target="_blank" aria-label="Instagram Profile">Instagram</a></li>
    <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank" aria-label="TikTok Profile">TikTok</a></li>
    <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank" aria-label="YouTube Channel">YouTube</a></li>
  </ul>
  <h2 class="glow-title">Video Placeholders</h2>
  <a class="video-link" href="#" aria-label="Demo Clip 1">Demo Clip 1</a>
  <a class="video-link" href="#" aria-label="Demo Clip 2">Demo Clip 2</a>
</div>

<div id="demos" class="section">
  <h1 class="glow-title">Performance Demos</h1>
  <div class="glow-block">
    <p><strong>Signal Range Test:</strong> Demonstrating both 2.4GHz and 5GHz range vs environment interference. <a href="#" aria-label="Signal Range Test Video">[Link]</a></p>
  </div>
  <div class="glow-block">
    <p><strong>Battery Runtime:</strong> Using a 1200mAh LiPo. Real-world performance test. <a href="#" aria-label="Battery Runtime Test Video">[Link]</a></p>
  </div>
</div>

<div id="firmware" class="section">
  <h1 class="glow-title">Firmware Download</h1>
  <div class="glow-block">
    <p>Latest firmware: <a href="#" aria-label="Download Firmware">BlackHoleV1.0_Firmware.bin</a></p>
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
  document.querySelectorAll('.section').forEach(s => {
    s.classList.remove('active');
    s.setAttribute('aria-hidden', 'true');
  });
  const activeSection = document.getElementById(id);
  activeSection.classList.add('active');
  activeSection.setAttribute('aria-hidden', 'false');
}

// Theme toggle functionality
function toggleTheme() {
  const currentTheme = document.documentElement.getAttribute('data-theme') || 'dark';
  document.documentElement.setAttribute('data-theme', currentTheme === 'dark' ? 'light' : 'dark');
  localStorage.setItem('theme', currentTheme === 'dark' ? 'light' : 'dark');
}

// Apply saved theme on load
document.addEventListener('DOMContentLoaded', () => {
  const savedTheme = localStorage.getItem('theme') || 'dark';
  document.documentElement.setAttribute('data-theme', savedTheme);
});
</script>