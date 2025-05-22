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

  .nav-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #111;
    position: sticky;
    top: 0;
    z-index: 1000;
    padding: 20px 0;
  }

  .nav-title {
    font-size: 2rem;
    color: #00f0ff;
    font-weight: bold;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    margin-bottom: 10px;
  }

  .nav-row {
    display: flex;
    gap: 30px;
    justify-content: center;
    margin-bottom: 10px;
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

  .discord-join {
    text-align: center;
    margin-top: 40px;
  }

  .discord-join a {
    color: #5865F2;
    font-weight: bold;
    text-shadow: 0 0 10px #5865F2;
    text-decoration: none;
    font-size: 1.2rem;
  }
</style>

<div class="nav-wrapper">
  <div class="nav-title">Black Hole V1.0</div>
  <div class="nav-row">
    <a href="#" onclick="showSection('home')">Home</a>
    <a href="#" onclick="showSection('product')">Product</a>
    <a href="#" onclick="showSection('media')">Media</a>
    <a href="#" onclick="showSection('demos')">Demos</a>
  </div>
  <div class="nav-row">
    <a href="#" onclick="showSection('about')">About</a>
    <a href="#" onclick="showSection('faq')">FAQ</a>
    <a href="#" onclick="showSection('firmware')">Firmware</a>
    <a href="#" onclick="showSection('timeline')">Timeline</a>
  </div>
</div>

<div id="home" class="section active">
  <h1 class="glow-title">🌌 Welcome to Black Hole V1.0</h1>
  <p>This is your central hub for all things Black Hole — updates, documentation, media, and community interaction. Explore everything this project has to offer.</p>
  <div class="discord-join">
    <p>💬 Join the community on Discord!</p>
    <a href="https://discord.gg/YOUR_INVITE_CODE" target="_blank">Click here to join my Discord Server</a>
  </div>
</div>

<div id="product" class="section">
  <h1 class="glow-title">Product Information</h1>
  <div class="glow-block">
    <strong>Product:</strong> Black Hole V1.0<br>
    <strong>Features:</strong>
    <ul>
      <li>Dual-band jamming (2.4GHz + 5GHz)</li>
      <li>External SMA antennas for better range</li>
      <li>Rechargeable with LiPo battery support</li>
      <li>Durable, sleek black PCB with case support</li>
    </ul>
    <strong>Price:</strong> $140
  </div>
  <div class="glow-block">
    <strong>Inventory:</strong> <em>Live tracking coming soon — message @unnamedperson488 for availability.</em>
  </div>
</div>

<div id="media" class="section">
  <h1 class="glow-title">Media & Links</h1>
  <ul>
    <li><a class="video-link" href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a></li>
    <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a></li>
    <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a></li>
  </ul>
  <h2 class="glow-title">Video Previews</h2>
  <a class="video-link" href="#">Hardware Overview</a>
  <a class="video-link" href="#">Field Testing Clips</a>
</div>

<div id="demos" class="section">
  <h1 class="glow-title">Performance Demos</h1>
  <div class="glow-block">
    <p><strong>Signal Range Test:</strong> Demonstrates both 2.4GHz and 5GHz range vs environmental interference. <a href="#">[Watch Now]</a></p>
  </div>
  <div class="glow-block">
    <p><strong>Battery Runtime:</strong> Using a 1200mAh LiPo battery, real-world test results with typical usage. <a href="#">[View Results]</a></p>
  </div>
</div>

<div id="about" class="section">
  <h1 class="glow-title">About Me</h1>
  <p>I’m <strong>unnamedperson488</strong> — professional hacker, builder, and creator of the Black Hole project. I specialize in security tools, Wi-Fi technology, and electronics innovation. This project showcases not just my skills but a mission to empower others with knowledge and reliable tools.</p>
</div>

<div id="faq" class="section">
  <h1 class="glow-title">Frequently Asked Questions</h1>
  <ul>
    <li><strong>Q:</strong> How do I use this device?<br><strong>A:</strong> A full guide is available in the documentation (firmware section).</li>
    <li><strong>Q:</strong> Is it legal to use?<br><strong>A:</strong> Use responsibly. Follow all applicable laws in your country.</li>
    <li><strong>Q:</strong> Does it support firmware updates?<br><strong>A:</strong> Yes. You can download the latest versions right here.</li>
  </ul>
</div>

<div id="firmware" class="section">
  <h1 class="glow-title">Firmware & Flashing</h1>
  <div class="glow-block">
    <p><strong>Latest Firmware:</strong> <a href="#">BlackHoleV1.0_Firmware.bin</a></p>
    <p><strong>Flashing Instructions:</strong></p>
    <ol>
      <li>Download and install <code>ESPTool</code> or use Arduino IDE.</li>
      <li>Connect the device via USB.</li>
      <li>Run the appropriate flashing command or upload sketch.</li>
    </ol>
  </div>
</div>

<div id="timeline" class="section">
  <h1 class="glow-title">Development Timeline</h1>
  <div class="glow-block">
    <strong>March 2024:</strong> Idea and planning begin.
  </div>
  <div class="glow-block">
    <strong>April 2024:</strong> First working PCB prototype is created using ESP32.
  </div>
  <div class="glow-block">
    <strong>May 2024:</strong> BW16 module added for dual-band functionality.
  </div>
  <div class="glow-block">
    <strong>June 2024:</strong> Final testing completed, Black Hole V1.0 released to the public.
  </div>
</div>

<script>
function showSection(id) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}
</script>
