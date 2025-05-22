---
layout: default
title: Black Hole V1.0
---

<style>
  body {
    background-color: #0a0a0a;
    color: #e0e0e0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 18px;
  }

  .nav-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #111;
    position: sticky;
    top: 0;
    z-index: 1000;
    padding: 30px 0;
  }

  .nav-title {
    font-size: 2.5rem;
    color: #00f0ff;
    font-weight: bold;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    margin-bottom: 15px;
  }

  .nav-row {
    display: flex;
    gap: 40px;
    justify-content: center;
    margin-bottom: 15px;
  }

  .neon-button {
    position: relative;
    padding: 0.75em 1.5em;
    border-radius: 0.625em;
    border: 2px solid #00ffff;
    font-size: 0.938em;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.125em;
    background: transparent;
    color: #00ffff;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 0 0 0 transparent;
    transition: all 0.3s ease-in-out;
    text-decoration: none;
  }

  .neon-button:hover {
    background: rgba(0, 255, 255, 0.1);
    box-shadow: 0 0 40px 10px rgba(0, 255, 255, 0.5);
    color: #ffffff;
  }

  .neon-button::before {
    content: "";
    display: block;
    width: 0px;
    height: 86%;
    position: absolute;
    top: 7%;
    left: 0%;
    opacity: 0;
    background: linear-gradient(90deg, transparent, #00ffff, transparent);
    box-shadow: 0 0 50px 30px #00ffff;
    transform: skewX(-20deg);
    transition: all 0.5s ease-in-out;
  }

  .neon-button:hover::before {
    animation: neon-shine 0.6s 0s linear;
  }

  @keyframes neon-shine {
    from {
      opacity: 0;
      left: 0%;
    }
    50% {
      opacity: 1;
    }
    to {
      opacity: 0;
      left: 100%;
    }
  }

  .neon-button:active {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 transparent;
    transition: all 0.2s ease-in;
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
    font-size: 2.2rem;
    margin-bottom: 20px;
  }

  .video-link {
    display: block;
    margin: 10px 0;
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff;
    text-decoration: none;
    font-size: 18px;
  }

  .glow-block {
    border: 1px solid #00f0ff44;
    padding: 25px;
    margin-bottom: 25px;
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
    font-size: 1.3rem;
  }

  .product-image {
    display: block;
    margin: 20px auto;
    max-width: 100%;
    height: auto;
    border: 2px solid #00f0ff44;
    box-shadow: 0 0 10px #00f0ff55;
    border-radius: 10px;
  }
</style>

<div class="nav-wrapper">
  <div class="nav-title">Black Hole V1.0</div>
  <div class="nav-row">
    <a href="#" onclick="showSection('home')" class="neon-button">Home</a>
    <a href="#" onclick="showSection('product')" class="neon-button">Product</a>
    <a href="#" onclick="showSection('media')" class="neon-button">Media</a>
    <a href="#" onclick="showSection('demos')" class="neon-button">Demos</a>
  </div>
  <div class="nav-row">
    <a href="#" onclick="showSection('about')" class="neon-button">About</a>
    <a href="#" onclick="showSection('faq')" class="neon-button">FAQ</a>
    <a href="#" onclick="showSection('firmware')" class="neon-button">Firmware</a>
    <a href="#" onclick="showSection('timeline')" class="neon-button">Timeline</a>
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
  <img class="product-image" src="https://via.placeholder.com/400x250?text=Product+Image" alt="Product Image Placeholder">
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
    <strong>Inventory:</strong> <em>0 in stock. 1 unit arriving in approximately 3 weeks.</em>
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
  <p>🎥 More videos coming soon, including teardown, setup walkthroughs, and real-time jamming footage.</p>
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
  <p>I'm <strong>unnamedperson488</strong> — professional hacker, builder, and creator of the Black Hole project. I specialize in security tools, Wi-Fi technology, and electronics innovation. This project showcases not just my skills but a mission to empower others with knowledge and reliable tools.</p>
  <p>I've spent years perfecting embedded systems, designing PCBs, and contributing to the hacker/maker community. Black Hole is a culmination of all of that work — combining functionality, sleek design, and cutting-edge capabilities into one portable device.</p>
</div>

<div id="faq" class="section">
  <h1 class="glow-title">Frequently Asked Questions</h1>
  <ul>
    <li><strong>Q:</strong> How do I use this device?<br><strong>A:</strong> A full guide is available in the documentation (firmware section).</li>
    <li><strong>Q:</strong> Is it legal to use?<br><strong>A:</strong> Use responsibly. Follow all applicable laws in your country.</li>
    <li><strong>Q:</strong> Does it support firmware updates?<br><strong>A:</strong> Yes. You can download the latest versions right here.</li>
    <li><strong>Q:</strong> What's included in the package?<br><strong>A:</strong> The Black Hole V1.0 device, dual SMA antennas, and a USB-C charging cable.</li>
    <li><strong>Q:</strong> Can I get support?<br><strong>A:</strong> Join the Discord server or contact @unnamedperson488 for assistance.</li>
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
