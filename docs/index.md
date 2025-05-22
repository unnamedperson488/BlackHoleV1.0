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

<div class="nav-row">
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('home');">Home</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('product');">Product</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('media');">Media</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('demos');">Demos</a>
</div>
<div class="nav-row">
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('about');">About</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('faq');">FAQ</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('firmware');">Firmware</a>
  <a href="#" class="neon-button" onclick="event.preventDefault(); showSection('timeline');">Timeline</a>
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
  <h2 class="glow-title">❓ FAQ</h2>
  <div class="glow-block">
    <h3>Is Black Hole V1.0 legal to use?</h3>
    <p>The device is intended strictly for educational and authorized security testing purposes. Always comply with your local laws before using the device.</p>
  </div>
  <div class="glow-block">
    <h3>Can I use this for 5GHz deauthing?</h3>
    <p>Yes — Black Hole V1.0 includes a BW16 chipset to enable dual-band support, including 5GHz deauthentication capabilities.</p>
  </div>
  <div class="glow-block">
    <h3>How do I flash new firmware?</h3>
    <p>You can follow the Firmware section on this site or refer to the GitHub repository for detailed flashing instructions.</p>
  </div>
  <div class="glow-block">
    <h3>What devices are compatible?</h3>
    <p>Any WiFi-enabled device in range may be affected during testing. The tool is platform-agnostic but requires proper use and responsibility.</p>
  </div>
</div>

    <h3>What is Black Hole V1.0 used for?</h3>
    <p>Black Hole V1.0 is designed for wireless security research, network stress testing, and educational pentesting environments. It allows users to analyze, test, and experiment with 2.4GHz and 5GHz WiFi signals.</p>
  </div>

  <div class="glow-block">
    <h3>Is it legal to use this device?</h3>
    <p>Using deauther or jamming functionality on networks you do not own or have explicit permission to test is illegal in many countries. This device is intended for responsible use only — always comply with local laws and use it ethically.</p>
  </div>

  <div class="glow-block">
    <h3>How do I flash new firmware?</h3>
    <p>Refer to the Firmware section of this site. You’ll download the latest release, use a flashing tool like ESPFlashTool, and follow the step-by-step process. Always verify you’re using the correct firmware file for your board revision.</p>
  </div>

  <div class="glow-block">
    <h3>Can I power it with any battery?</h3>
    <p>Black Hole V1.0 supports standard LiPo batteries. We recommend 3.7V single-cell packs with JST connectors. Avoid exceeding voltage specs to prevent hardware damage.</p>
  </div>

  <div class="glow-block">
    <h3>How do I join the community?</h3>
    <p>Click the Discord invite link in the Home section or social buttons. You’ll get access to support, beta testing info, and a group of fellow developers and hackers using Black Hole V1.0.</p>
  </div>

  <div class="glow-block">
    <h3>Can I contribute to the project?</h3>
    <p>Yes! Visit our <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="neon-link" target="_blank">GitHub repository</a> to report bugs, suggest features, or contribute code/documentation. Community contributions are welcomed and appreciated.</p>
  </div>
</div>




<section id="firmware" style="max-width: 600px; margin: auto; background: #fff; padding: 1rem; border-radius: 8px; box-shadow: 0 0 12px rgba(0,0,0,0.1); font-family: Arial, sans-serif;">

  <h1 style="text-align:center; margin-bottom:1rem;">Firmware</h1>



</section>

<script>
  // FAQ Search functionality
  const searchInput = document.getElementById('faq-search');
  const faqItems = document.querySelectorAll('#faq details');

  searchInput.addEventListener('input', () => {
    const query = searchInput.value.toLowerCase();
    faqItems.forEach(item => {
      const text = item.textContent.toLowerCase();
      item.style.display = text.includes(query) ? 'block' : 'none';
    });
  });
</script>

<style>
  /* Responsive and mobile-friendly */
  #firmware {
    background: #fff;
    color: #222;
  }

  #firmware h1, #firmware h2 {
    color: #333;
  }

  details {
    margin-bottom: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    background: #f9f9f9;
  }

  summary {
    font-weight: 600;
    cursor: pointer;
    outline: none;
  }

  summary::-webkit-details-marker {
    display: none;
  }

  summary::before {
    content: "▶";
    display: inline-block;
    margin-right: 8px;
    transform: rotate(0deg);
    transition: transform 0.2s ease-in-out;
  }

  details[open] summary::before {
    transform: rotate(90deg);
  }

  @media (max-width: 600px) {
    #firmware {
      margin: 0.5rem;
      padding: 0.75rem;
    }

    #faq-search {
      font-size: 1rem;
    }

    ol {
      padding-left: 1.25rem;
    }
  }
</style>


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

