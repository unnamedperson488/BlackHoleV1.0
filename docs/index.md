---
layout: default
title: Black Hole V1.0
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Official hub for Black Hole V1.0, an ESP32-based dual-band jamming device by @unnamedperson488. Explore development, documentation, and product details.">
  <meta name="keywords" content="Black Hole V1.0, ESP32, dual-band jamming, unnamedperson488, hacker tools">
  <title>Black Hole V1.0</title>
  <style>
    body {
      background-color: #0a0a0a;
      color: #e0e0e0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      line-height: 1.6;
    }

    nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      padding: 15px;
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
      font-size: clamp(1rem, 4vw, 1.2rem);
    }

    nav a:hover, nav a:focus {
      transform: scale(1.1);
      outline: none;
    }

    .section {
      display: none;
      padding: 40px 20px;
      max-width: 800px;
      margin: 0 auto;
    }

    .section.active {
      display: block;
    }

    .glow-title {
      color: #00f0ff;
      text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
      font-size: clamp(1.8rem, 6vw, 2.2rem);
      margin-bottom: 20px;
    }

    .video-link {
      display: block;
      margin: 10px 0;
      color: #00f0ff;
      text-shadow: 0 0 5px #00f0ff;
      text-decoration: none;
      font-size: 1rem;
    }

    .video-link:hover, .video-link:focus {
      text-decoration: underline;
    }

    .glow-block {
      border: 1px solid #00f0ff44;
      padding: 20px;
      margin-bottom: 20px;
      background-color: #111;
      box-shadow: 0 0 10px #00f0ff33;
      border-radius: 8px;
    }

    @media (max-width: 600px) {
      nav {
        flex-direction: column;
        align-items: center;
        gap: 10px;
      }
      .section {
        padding: 20px 10px;
      }
    }
  </style>
</head>
<body>
  <nav role="navigation" aria-label="Main navigation">
    <span style="font-size: clamp(1.2rem, 5vw, 1.4rem);">Black Hole V1.0</span>
    <a href="#home" onclick="showSection('home')" aria-current="page">Home</a>
    <a href="#product" onclick="showSection('product')">Product</a>
    <a href="#about" onclick="showSection('自由

System: It looks like your message was cut off. I’ll proceed with fixing the provided HTML code based on the issues identified and the context from the TikTok profile information for @unnamedperson488. Below is the continuation of the revised code, completing the navigation links and the rest of the HTML structure, followed by a detailed explanation of the changes.

### Revised Code (Continued):
```html
    <a href="#about" onclick="showSection('about')">About</a>
    <a href="#faq" onclick="showSection('faq')">FAQ</a>
    <a href="#media" onclick="showSection('media')">Media</a>
    <a href="#demos" onclick="showSection('demos')">Demos</a>
    <a href="#firmware" onclick="showSection('firmware')">Firmware</a>
    <a href="#timeline" onclick="showSection('timeline')">Timeline</a>
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
      <strong>Inventory:</strong> <em>Live tracking coming soon — message <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for availability.</em>
    </div>
  </div>

  <div id="about" class="section">
    <h1 class="glow-title">About Me</h1>
    <p>I’m unnamedperson488 — professional hacker, builder, and designer of the Black Hole project. This site documents the evolution and community around my custom ESP32-based tools. Follow me on <a href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a> for updates.</p>
  </div>

  <div id="faq" class="section">
    <h1 class="glow-title">Frequently Asked Questions</h1>
    <ul>
      <li><strong>Q:</strong> How do I use this device?<br><strong>A:</strong> A full guide is available in the documentation. Contact <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for details.</li>
      <li><strong>Q:</strong> Is it legal to use?<br><strong>A:</strong> Use responsibly. Follow your local laws.</li>
    </ul>
  </div>

  <div id="media" class="section">
    <h1 class="glow-title">Media & Links</h1>
    <ul>
      <li><a class="video-link" href="https://www.instagram.com/unnamedperson488" target="_blank">Instagram</a></li>
      <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a></li>
      <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a></li>
    </ul>
    <h2 class="glow-title">Video Demos</h2>
    <p><em>Demo videos coming soon. Check <a href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a> for the latest clips.</em></p>
  </div>

  <div id="demos" class="section">
    <h1 class="glow-title">Performance Demos</h1>
    <div class="glow-block">
      <p><strong>Signal Range Test:</strong> Demonstrating both 2.4GHz and 5GHz range vs environment interference. <em>Contact <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for video access.</em></p>
    </div>
    <div class="glow-block">
      <p><strong>Battery Runtime:</strong> Using a 1200mAh LiPo. Real-world performance test. <em>Contact <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for video access.</em></p>
    </div>
  </div>

  <div id="firmware" class="section">
    <h1 class="glow-title">Firmware Download</h1>
    <div class="glow-block">
      <p>Latest firmware: <em>Contact <a href="https://tiktok.com/@unnamedperson488" target="_blank">@unnamedperson488</a> for download link.</em></p>
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
      try {
        const sections = document.querySelectorAll('.section');
        sections.forEach(s => s.classList.remove('active'));
        const target = document.getElementById(id);
        if (target) {
          target.classList.add('active');
          window.scrollTo({ top: 0, behavior: 'smooth' });
        } else {
          console.warn(`Section with ID ${id} not found`);
          document.getElementById('home').classList.add('active');
        }
      } catch (error) {
        console.error('Error in showSection:', error);
      }
    }

    // Ensure the home section is active on page load
    document.addEventListener('DOMContentLoaded', () => {
      showSection('home');
    });
  </script>
</body>
</html>