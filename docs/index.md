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
    line-height: 1.6;
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
    user-select: none;
  }

  .nav-title {
    font-size: 2.5rem;
    color: #00f0ff;
    font-weight: bold;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    margin-bottom: 15px;
    font-family: 'Orbitron', sans-serif;
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
    user-select: none;
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
    max-width: 900px;
    margin: 0 auto 60px auto;
  }

  .section.active {
    display: block;
  }

  .glow-title {
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    font-size: 2.2rem;
    margin-bottom: 20px;
    font-family: 'Orbitron', sans-serif;
  }

  .glow-block {
    border: 1px solid #00f0ff44;
    padding: 25px 30px;
    margin-bottom: 25px;
    background-color: #111;
    box-shadow: 0 0 15px #00f0ff44 inset;
    border-radius: 8px;
  }

  .discord-join {
    text-align: center;
    margin-top: 40px;
    margin-bottom: 50px;
  }

  .discord-join a {
    color: #5865F2;
    font-weight: bold;
    text-shadow: 0 0 10px #5865F2;
    text-decoration: none;
    font-size: 1.3rem;
  }

  .discord-join a:hover {
    color: #a3b6ff;
  }

  .social-buttons {
    display: flex;
    justify-content: center;
    gap: 18px;
    flex-wrap: wrap;
    margin-top: 40px;
    margin-bottom: 60px;
  }

  .social-button {
    background-color: #111;
    color: #00f0ff;
    border: 2px solid #00f0ff;
    padding: 12px 20px;
    font-size: 1rem;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.3s ease;
    font-weight: bold;
    box-shadow: 0 0 10px #00f0ff44;
    text-align: center;
  }

  .social-button:hover {
    background-color: #00f0ff;
    color: #000;
    box-shadow: 0 0 25px #00f0ff88;
  }

  .social-button:focus {
    outline: 2px solid #00f0ff;
    outline-offset: 4px;
  }
</style>

<script>
  function showSection(id) {
    const sections = document.querySelectorAll('.section');
    sections.forEach(section => {
      section.classList.remove('active');
    });
    document.getElementById(id).classList.add('active');
  }
</script>

<div class="nav-wrapper">
  <div class="nav-title">Black Hole V1.0</div>
  <div class="nav-row">
    <a href="#" class="neon-button" onclick="showSection('home')">Home</a>
    <a href="#" class="neon-button" onclick="showSection('product')">Product</a>
    <a href="#" class="neon-button" onclick="showSection('media')">Media</a>
    <a href="#" class="neon-button" onclick="showSection('demos')">Demos</a>
  </div>
  <div class="nav-row">
    <a href="#" class="neon-button" onclick="showSection('about')">About</a>
    <a href="#" class="neon-button" onclick="showSection('faq')">FAQ</a>
    <a href="#" class="neon-button" onclick="showSection('firmware')">Firmware</a>
    <a href="#" class="neon-button" onclick="showSection('timeline')">Timeline</a>
  </div>
</div>

<!-- HOME -->
<div id="home" class="section active">
  <h1 class="glow-title">🌌 Welcome to Black Hole V1.0</h1>
  <p>This is your central hub for all things Black Hole — updates, documentation, media, and community interaction. Explore everything this project has to offer.</p>
  <div class="discord-join">
    <p>💬 Join the community on Discord!</p>
    <a href="https://discord.gg/YOUR_INVITE_CODE" target="_blank">Click here to join my Discord Server</a>
  </div>
  <hr>
  <h2 class="glow-title">Latest Updates</h2>
  <div class="glow-block">
    <strong>May 2025:</strong> Released new firmware v1.2.3 with enhanced stability and new anti-jamming features.
    <ul>
      <li>Improved 5GHz antenna switching</li>
      <li>Battery optimization for longer runtime</li>
      <li>Bug fixes for ESP32 connectivity</li>
    </ul>
  </div>
  <div class="glow-block">
    <strong>Upcoming:</strong> Live demo event scheduled for June 10, 2025 — join via Discord or YouTube livestream.
  </div>
  <div class="social-buttons">
    <a class="social-button" href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a>
    <a class="social-button" href="https://github.com/unnamedperson488" target="_blank">GitHub</a>
    <a class="social-button" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a>
    <a class="social-button" href="https://discord.gg/YOUR_INVITE_CODE" target="_blank">Discord</a>
    <a class="social-button" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a>
  </div>
</div>

<div id="product" class="section">
  <h2 class="glow-title">📦 Product</h2>
  <p>Introducing <strong>Black Hole V1.0</strong> — a cutting-edge dual-band deauther device designed for advanced wireless security testing and research.</p>

  <div class="glow-block">
    <h3>Key Features</h3>
    <ul>
      <li>Dual-band operation: 2.4GHz ESP32 + 5GHz BW16 chipset</li>
      <li>Separate antennas with SMA connectors for max signal strength</li>
      <li>4-layer black PCB with high-quality components</li>
      <li>Custom firmware with anti-jamming and launch control</li>
      <li>Boot and Reset buttons designed for easy hardware control</li>
      <li>Compact and rugged design, suitable for wardriving and pentesting</li>
    </ul>
  </div>

  <div class="glow-block">
    <h3>Technical Specifications</h3>
    <table style="width:100%; border-collapse: collapse;">
      <tr>
        <th style="text-align:left; border-bottom: 1px solid #00f0ff;">Component</th>
        <th style="text-align:left; border-bottom: 1px solid #00f0ff;">Details</th>
      </tr>
      <tr>
        <td>Microcontroller</td>
        <td>ESP32-WROOM-32 (dual-core 240 MHz)</td>
      </tr>
      <tr>
        <td>5GHz Chipset</td>
        <td>BW16 5GHz WiFi chip</td>
      </tr>
      <tr>
        <td>Antennas</td>
        <td>2 x SMA connectors (external antennas for 2.4GHz & 5GHz)</td>
      </tr>
      <tr>
        <td>Buttons</td>
        <td>Boot (power) button, Reset button</td>
      </tr>
      <tr>
        <td>PCB</td>
        <td>4-layer black matte, custom silkscreen 'ENGINEERED BY unnamedperson'</td>
      </tr>
      <tr>
        <td>Power</td>
        <td>LiPo battery charging onboard</td>
      </tr>
      <tr>
        <td>Dimensions</td>
        <td>Approx. 75mm x 50mm x 15mm</td>
      </tr>
    </table>
  </div>

  <div class="glow-block">
    <h3>What's in the Box?</h3>
    <ul>
      <li>Black Hole V1.0 device</li>
      <li>Two SMA antennas (2.4GHz and 5GHz)</li>
      <li>USB-C charging cable</li>
      <li>User manual & quick start guide</li>
      <li>Access to exclusive Discord support community</li>
    </ul>
  </div>
</div>

<div id="media" class="section">
  <h2 class="glow-title">🎥 Media</h2>
  <p>Explore photos, videos, and demos showcasing the Black Hole V1.0 in action.</p>

  <div class="glow-block">
    <h3>Gallery</h3>
    <div style="display: flex; gap: 15px; flex-wrap: wrap; justify-content: center;">
      <img src="https://via.placeholder.com/180x120?text=Device+Front" alt="Black Hole Front View" style="border-radius: 8px; box-shadow: 0 0 10px #00f0ff77;">
      <img src="https://via.placeholder.com/180x120?text=Device+Back" alt="Black Hole Back View" style="border-radius: 8px; box-shadow: 0 0 10px #00f0ff77;">
      <img src="https://via.placeholder.com/180x120?text=PCB+Layout" alt="PCB Layout" style="border-radius: 8px; box-shadow: 0 0 10px #00f0ff77;">
    </div>
  </div>

  <div class="glow-block">
    <h3>Videos</h3>
    <iframe width="100%" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Black Hole V1.0 Demo" frameborder="0" allowfullscreen style="border-radius: 8px; box-shadow: 0 0 15px #00f0ff88;"></iframe>
  </div>
</div>
<div id="demos" class="section">
  <h2 class="glow-title">⚙️ Demos</h2>
  <p>Try out live demos or explore interactive examples of Black Hole V1.0 features.</p>

  <div class="glow-block">
    <h3>Live Demo</h3>
    <p>Experience the device in real time through our web interface:</p>
    <a href="https://example.com/live-demo" target="_blank" class="neon-button">Open Live Demo</a>
  </div>

  <div class="glow-block">
    <h3>Interactive Simulator</h3>
    <p>Test functionalities and settings with our online simulator.</p>
    <a href="https://example.com/simulator" target="_blank" class="neon-button">Open Simulator</a>
  </div>

  <div class="glow-block">
    <h3>Code Examples</h3>
    <p>Explore example scripts and how to use the device APIs.</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0-examples" target="_blank" class="neon-button">View Code on GitHub</a>
  </div>
</div>
<div id="about" class="section">
  <h2 class="glow-title">🔭 About Black Hole V1.0</h2>
  <div class="glow-block">
    <p>
      Black Hole V1.0 is a cutting-edge dual-band deauther device engineered for maximum performance in wireless network testing and security research. 
      Designed by <strong>unnamedperson488</strong>, it features advanced antenna switching, anti-jamming capabilities, and an intuitive interface.
    </p>
    <p>
      The project is open-source and community-driven, aiming to empower cybersecurity enthusiasts and professionals to explore and improve wireless security.
    </p>
  </div>

  <div class="glow-block">
    <h3>Project Goals</h3>
    <ul>
      <li>Deliver a reliable and efficient dual-band deauther device.</li>
      <li>Provide extensive documentation and support for users.</li>
      <li>Encourage community collaboration and feature development.</li>
    </ul>
  </div>
</div>
<div id="faq" class="section">
  <h2 class="glow-title">❓ Frequently Asked Questions</h2>

  <div class="glow-block">
    <button class="faq-question neon-button" onclick="toggleFAQ(this)">What is Black Hole V1.0?</button>
    <p class="faq-answer" style="display:none; margin-top: 10px;">
      Black Hole V1.0 is a powerful dual-band deauther device designed for network security testing and research.
    </p>
  </div>

  <div class="glow-block">
    <button class="faq-question neon-button" onclick="toggleFAQ(this)">Is Black Hole V1.0 open source?</button>
    <p class="faq-answer" style="display:none; margin-top: 10px;">
      Yes! The project is fully open source, and contributions are welcome.
    </p>
  </div>

  <div class="glow-block">
    <button class="faq-question neon-button" onclick="toggleFAQ(this)">Where can I download the firmware?</button>
    <p class="faq-answer" style="display:none; margin-top: 10px;">
      Firmware downloads and instructions are available in the Firmware section.
    </p>
  </div>
</div>

<script>
  function toggleFAQ(button) {
    const answer = button.nextElementSibling;
    if (answer.style.display === "none" || answer.style.display === "") {
      answer.style.display = "block";
      button.style.boxShadow = "0 0 40px 10px rgba(0, 255, 255, 0.7)";
    } else {
      answer.style.display = "none";
      button.style.boxShadow = "0 0 0 0 transparent";
    }
  }
</script>
<div id="firmware" class="section">
  <h2 class="glow-title">⚙️ Firmware Downloads</h2>

  <div class="glow-block">
    <p><strong>Current Version:</strong> v1.2.3</p>
    <p>Release Date: May 2025</p>
    <p>This firmware includes improved antenna switching, better battery management, and enhanced stability.</p>
  </div>

  <div class="glow-block">
    <a href="firmware/blackhole-v1.2.3.bin" download class="neon-button">Download v1.2.3</a>
    <p style="margin-top: 10px;">Instructions: Use the provided flashing tool or follow the guide in the documentation to update your device.</p>
  </div>

  <div class="glow-block">
    <h3>Previous Versions</h3>
    <ul>
      <li><a href="firmware/blackhole-v1.2.0.bin" download>v1.2.0</a> – April 2025</li>
      <li><a href="firmware/blackhole-v1.1.5.bin" download>v1.1.5</a> – March 2025</li>
      <li><a href="firmware/blackhole-v1.1.0.bin" download>v1.1.0</a> – January 2025</li>
    </ul>
  </div>
</div>

<div id="timeline" class="section">
  <h2 class="glow-title">⏳ Project Timeline</h2>

  <div class="glow-block">
    <ul>
      <li><strong>Jan 2024:</strong> Project conception and initial research.</li>
      <li><strong>Jun 2024:</strong> Prototype development with ESP32 and BW16 chipset.</li>
      <li><strong>Nov 2024:</strong> Hardware design finalized, 4-layer PCB created.</li>
      <li><strong>Feb 2025:</strong> Firmware v1.0 released to beta testers.</li>
      <li><strong>May 2025:</strong> Firmware v1.2.3 released with key feature updates.</li>
      <li><strong>Jun 2025:</strong> Planned live demo event and community Q&A.</li>
    </ul>
  </div>
</div>

<div id="timeline" class="section">
  <h2 class="glow-title">📅 Project Timeline</h2>

  <div class="glow-block">
    <ul style="list-style-type: none; padding-left: 0;">
      <li>
        <strong>Jan 2024:</strong> Project conception and initial design sketches.
      </li>
      <li>
        <strong>Mar 2024:</strong> First prototype PCB manufactured and tested.
      </li>
      <li>
        <strong>Jul 2024:</strong> Firmware development v1.0 started.
      </li>
      <li>
        <strong>Dec 2024:</strong> Beta firmware released to testers.
      </li>
      <li>
        <strong>Feb 2025:</strong> Hardware revisions based on beta feedback.
      </li>
      <li>
        <strong>May 2025:</strong> Official release of Black Hole V1.0 with firmware v1.2.3.
      </li>
      <li>
        <strong>Jun 2025:</strong> Upcoming live demo and community events.
      </li>
    </ul>
  </div>
</div>

