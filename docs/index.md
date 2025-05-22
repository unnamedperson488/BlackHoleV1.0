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
    overflow-x: hidden;
    margin: 0;
  }

  .nav-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #111;
    padding: 20px 10px;
    user-select: none;
    max-width: 100%;
    box-sizing: border-box;
    box-shadow: 0 2px 10px rgba(0, 234, 255, 0.2);
  }

  .nav-title {
    font-size: 2.5rem;
    color: #00eaff;
    font-weight: bold;
    text-shadow: 0 0 5px #00eaff, 0 0 15px #00eaff;
    margin: 0 0 15px 0;
    font-family: 'Orbitron', sans-serif;
    text-align: center;
  }

  .nav-row {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
    margin-bottom: 10px;
  }

  .neon-button {
    position: relative;
    padding: 0.75em 1.5em;
    border-radius: 8px;
    border: 2px solid #00eaff;
    font-size: 0.938em;
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 0.125em;
    background: transparent;
    color: #00eaff;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 0 10px #00eaff44;
    transition: all 0.3s ease-in-out;
    text-decoration: none;
    user-select: none;
  }

  .neon-button:hover {
    background: rgba(0, 234, 255, 0.1);
    box-shadow: 0 0 40px 10px rgba(0, 234, 255, 0.5);
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
    background: linear-gradient(90deg, transparent, #00eaff, transparent);
    box-shadow: 0 0 50px 30px #00eaff;
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
    padding: 30px 20px;
    max-width: 900px;
    margin: 0 auto 40px auto;
    background: linear-gradient(180deg, #0a0a0a 0%, #111 100%);
    border-radius: 8px;
    box-shadow: 0 0 15px #00eaff44;
  }

  .section.active {
    display: block;
  }

  .glow-title {
    color: #00eaff;
    text-shadow: 0 0 5px #00eaff, 0 0 15px #00eaff;
    font-size: 2.2rem;
    margin-bottom: 20px;
    font-family: 'Orbitron', sans-serif;
  }

  .glow-block {
    border: 1px solid #00eaff44;
    padding: 20px 25px;
    margin-bottom: 20px;
    background-color: #111;
    box-shadow: 0 0 15px #00eaff44 inset;
    border-radius: 8px;
  }

  .glow-block h3 {
    font-size: 1.4rem;
    margin-bottom: 15px;
    color: #e0e0e0;
  }

  .glow-block p, .glow-block li {
    font-size: 1rem;
  }

  .discord-join {
    text-align: center;
    margin: 30px 0;
  }

  .discord-join a {
    color: #5865F2;
    font-weight: bold;
    text-shadow: 0 0 10px #5865F2;
    text-decoration: none;
    font-size: 1.2rem;
    transition: color 0.3s ease;
  }

  .discord-join a:hover {
    color: #a3b6ff;
  }

  .social-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 30px 0;
  }

  .social-button {
    background-color: #111;
    color: #00eaff;
    border: 2px solid #00eaff;
    padding: 10px 18px;
    font-size: 0.938rem;
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.3s ease;
    font-weight: bold;
    box-shadow: 0 0 10px #00eaff44;
    text-align: center;
  }

  .social-button:hover {
    background-color: #00eaff;
    color: #000;
    box-shadow: 0 0 25px #00eaff88;
  }

  .social-button:focus {
    outline: 2px solid #00eaff;
    outline-offset: 4px;
  }

  #faq-search {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid #00eaff;
    background: #111;
    color: #e0e0e0;
    border-radius: 8px;
    transition: box-shadow 0.3s ease;
  }

  #faq-search:focus {
    outline: none;
    box-shadow: 0 0 10px #00eaff;
  }

  details {
    margin-bottom: 0.75rem;
    border: 1px solid #00eaff44;
    border-radius: 8px;
    padding: 0.5rem 1rem;
    background: #111;
    box-shadow: 0 0 10px #00eaff44;
  }

  summary {
    font-weight: 600;
    cursor: pointer;
    outline: none;
    color: #e0e0e0;
    font-size: 1rem;
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

  table {
    width: 100%;
    border-collapse: collapse;
  }

  table th, table td {
    padding: 10px;
    background: #111;
    border-bottom: 1px solid #00eaff44;
  }

  table tr:nth-child(even) td {
    background: #151515;
  }

  table th {
    text-align: left;
    border-bottom: 1px solid #00eaff;
    color: #00eaff;
  }

  ul.border-l-4 li {
    position: relative;
    transition: transform 0.3s ease;
  }

  ul.border-l-4 li:hover {
    transform: translateX(5px);
  }

  @media (max-width: 600px) {
    .section {
      padding: 20px 10px;
      margin: 0 10px 30px 10px;
    }

    .glow-title {
      font-size: 1.8rem;
    }

    .glow-block h3 {
      font-size: 1.2rem;
    }

    .glow-block p, .glow-block li {
      font-size: 0.938rem;
    }

    .neon-button {
      font-size: 0.75rem;
      padding: 0.5em 1em;
      min-width: 80px;
    }

    .nav-title {
      font-size: 2rem;
    }

    .nav-row {
      gap: 10px;
      padding: 0 10px;
    }

    .social-button {
      font-size: 0.875rem;
      padding: 8px 15px;
    }

    .discord-join a {
      font-size: 1rem;
    }
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

  // FAQ Search functionality
  const searchInput = document.getElementById('faq-search');
  const faqItems = document.querySelectorAll('#faq details');

  if (searchInput) {
    searchInput.addEventListener('input', () => {
      const query = searchInput.value.toLowerCase();
      faqItems.forEach(item => {
        const text = item.textContent.toLowerCase();
        item.style.display = text.includes(query) ? 'block' : 'none';
      });
    });
  }
</script>

<!-- Navigation -->
<div class="nav-wrapper">
  <h1 class="nav-title">Black Hole V1.0</h1>
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
</div>

<!-- HOME -->
<div id="home" class="section active">
  <h1 class="glow-title">🌌 Welcome to Black Hole V1.0</h1>
  <p>This is your central hub for all things Black Hole — updates, documentation, media, and community interaction. Explore everything this project has to offer.</p>
  <div class="glow-block">
    <h3>Our Mission</h3>
    <p>Black Hole V1.0 aims to empower cybersecurity enthusiasts with a powerful, open-source tool for wireless network testing, fostering education and innovation in ethical hacking.</p>
  </div>
  <div class="discord-join">
    <p>💬 Join the community on Discord!</p>
    <a href="https://discord.gg/actual-invite-code" target="_blank">Click here to join my Discord Server</a>
  </div>
  <hr>
  <h2 class="glow-title">Latest Updates</h2>
  <div class="glow-block">
    <strong>May 2025:</strong> Released new firmware v1.2.3 with enhanced stability and new anti-jamming features.
    <ul>
      <li>Improved 5GHz antenna switching for seamless dual-band operation</li>
      <li>Battery optimization for up to 20% longer runtime</li>
      <li>Bug fixes for ESP32 connectivity issues under high load</li>
    </ul>
  </div>
  <div class="glow-block">
    <strong>Upcoming:</strong> Live demo event scheduled for June 10, 2025 — join via Discord or YouTube livestream for a deep dive into Black Hole’s capabilities.
  </div>
  <div class="glow-block">
    <h3>Contribute</h3>
    <p>Have ideas or improvements? Contribute to the project on GitHub or join our Discord to share feedback!</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0" target="_blank" class="neon-button">Contribute on GitHub</a>
  </div>
  <div class="social-buttons">
    <a class="social-button" href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a>
    <a class="social-button" href="https://github.com/unnamedperson488" target="_blank">GitHub</a>
    <a class="social-button" href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a>
    <a class="social-button" href="https://discord.gg/actual-invite-code" target="_blank">Discord</a>
    <a class="social-button" href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a>
  </div>
</div>

<!-- PRODUCT -->
<div id="product" class="section">
  <h2 class="glow-title">📦 Product</h2>
  <p>Introducing <strong>Black Hole V1.0</strong> — a cutting-edge dual-band deauther device designed for advanced wireless security testing and research.</p>

  <div class="glow-block">
    <h3>Key Features</h3>
    <ul>
      <li>Dual-band operation: 2.4GHz ESP32 + 5GHz BW16 chipset for versatile network testing</li>
      <li>Separate antennas with SMA connectors for maximum signal strength and range</li>
      <li>4-layer black PCB with high-quality components for durability</li>
      <li>Custom open-source firmware with anti-jamming and launch control capabilities</li>
      <li>Boot and Reset buttons designed for easy hardware control</li>
      <li>Compact and rugged design, ideal for wardriving, pentesting, and field research</li>
      <li>Community-driven updates and support via Discord and GitHub</li>
    </ul>
  </div>

  <div class="glow-block">
    <h3>Technical Specifications</h3>
    <table>
      <tr>
        <th>Component</th>
        <th>Details</th>
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

  <div class="glow-block">
    <h3>Use Cases</h3>
    <ul>
      <li>Penetration testing for WiFi network security audits</li>
      <li>Educational workshops on wireless protocol vulnerabilities</li>
      <li>Research into advanced deauthentication and packet injection techniques</li>
      <li>Wardriving for mapping WiFi networks in field environments</li>
    </ul>
  </div>
</div>

<!-- MEDIA -->
<div id="media" class="section">
  <h2 class="glow-title">📸 Media</h2>
  <div class="glow-block">
    <h3>Photos & Videos</h3>
    <p>Check out photos and videos showcasing Black Hole V1.0 in action, including hardware demos and testing scenarios.</p>
    <ul>
      <li><a href="https://youtube.com/@unnamedperson488" target="_blank">Watch demos on YouTube</a></li>
      <li><a href="https://instagram.com/unnamedperson488" target="_blank">View photos on Instagram</a></li>
      <li><a href="https://tiktok.com/@unnamedperson488" target="_blank">See short clips on TikTok</a></li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>Community Showcase</h3>
    <p>Coming soon: User-submitted projects, tutorials, and custom firmware demos. Share your work on Discord!</p>
    <a href="https://discord.gg/actual-invite-code" target="_blank" class="neon-button">Join Discord</a>
  </div>
</div>

<!-- DEMOS -->
<div id="demos" class="section">
  <h2 class="glow-title">⚙️ Demos</h2>
  <p>Try out live demos or explore interactive examples of Black Hole V1.0 features. Stay tuned for our June 2025 demo event!</p>

  <div class="glow-block">
    <h3>Live Demo</h3>
    <p>Live demo coming soon. Join our Discord for updates on the June 10, 2025, livestream event!</p>
    <a href="https://discord.gg/actual-invite-code" target="_blank" class="neon-button">Join Discord</a>
  </div>

  <div class="glow-block">
    <h3>Interactive Simulator</h3>
    <p>Simulator coming soon. Check back for updates or suggest features on GitHub!</p>
    <a href="https://discord.gg/actual-invite-code" target="_blank" class="neon-button">Join Discord</a>
  </div>

  <div class="glow-block">
    <h3>Code Examples</h3>
    <p>Explore example scripts and APIs for custom integrations with Black Hole V1.0.</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0-examples" target="_blank" class="neon-button">View Code on GitHub</a>
  </div>

  <div class="glow-block">
    <h3>Request a Feature</h3>
    <p>Have an idea for a demo or feature? Submit it to our GitHub issues page!</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0/issues" target="_blank" class="neon-button">Submit a Feature Request</a>
  </div>
</div>

<!-- ABOUT -->
<div id="about" class="section">
  <h2 class="glow-title">🔭 About Black Hole V1.0</h2>
  <div class="glow-block">
    <p>
      Black Hole V1.0 is a cutting-edge dual-band deauther device engineered for maximum performance in wireless network testing and security research. 
      Designed by <strong>unnamedperson488</strong>, it features advanced antenna switching, anti-jamming capabilities, and an intuitive interface.
    </p>
    <p>
      The project is open-source and community-driven, aiming to empower cybersecurity enthusiasts and professionals to explore and improve wireless security. 
      From initial prototyping to public release, the design process emphasizes reliability, accessibility, and collaboration.
    </p>
  </div>

  <div class="glow-block">
    <h3>Project Goals</h3>
    <ul>
      <li>Deliver a reliable and efficient dual-band deauther device for ethical hacking.</li>
      <li>Provide extensive documentation, tutorials, and support for users of all skill levels.</li>
      <li>Encourage community collaboration through GitHub contributions and Discord discussions.</li>
      <li>Foster innovation in wireless security research with open-source tools.</li>
    </ul>
  </div>
</div>

<!-- FAQ -->
<div id="faq" class="section">
  <h2 class="glow-title">❓ FAQ</h2>
  <input type="text" id="faq-search" placeholder="Search FAQs..." style="width: 100%; padding: 10px; margin-bottom: 20px; border: 1px solid #00eaff; background: #111; color: #e0e0e0; border-radius: 8px;">
  <div class="faq-items">
    <details>
      <summary>What is Black Hole V1.0?</summary>
      <p>A dual-band WiFi deauther designed for educational use, security testing, and research. It supports both 2.4GHz and 5GHz via ESP32 and BW16 chipsets.</p>
    </details>
    <details>
      <summary>Is 5GHz support real?</summary>
      <p>Yes. It uses the Realtek BW16 module with SDK-based implementation for 5GHz deauth and packet injection.</p>
    </details>
    <details>
      <summary>Can I flash my own firmware?</summary>
      <p>Absolutely. The board supports PlatformIO, Arduino IDE, and direct UART flashing. Open-source firmware is provided.</p>
    </details>
    <details>
      <summary>How long does the battery last?</summary>
      <p>It depends on usage and battery size. A 1000mAh LiPo can last ~4-5 hours under moderate scanning/jamming.</p>
    </details>
    <details>
      <summary>Is it legal?</summary>
      <p>This device is for educational and authorized testing only. Unauthorized use may violate local laws. You are responsible for how you use it.</p>
    </details>
    <details>
      <summary>Is Black Hole V1.0 compatible with other tools?</summary>
      <p>Yes, it integrates with tools like Wireshark and Aircrack-ng for advanced analysis, and supports custom scripts via its APIs.</p>
    </details>
    <details>
      <summary>What safety precautions should I take?</summary>
      <p>Use only on networks you own or have permission to test. Ensure proper handling of the LiPo battery to avoid damage or hazards.</p>
    </details>
  </div>
</div>

<!-- FIRMWARE -->
<div id="firmware" class="section">
  <h2 class="glow-title">📱 Firmware</h2>
  <div class="glow-block">
    <h3>Firmware Downloads</h3>
    <p>Download the latest firmware for Black Hole V1.0 to keep your device up to date:</p>
    <ul>
      <li><a href="https://github.com/unnamedperson488/BlackHoleV1.0/releases" target="_blank">Firmware v1.2.3 (Latest, May 2025)</a></li>
      <li><a href="https://github.com/unnamedperson488/BlackHoleV1.0/wiki/Firmware-Installation" target="_blank">Installation Guide</a></li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>Firmware Features</h3>
    <ul>
      <li>Web-based UI for easy configuration and control</li>
      <li>Over-the-air (OTA) updates for seamless upgrades</li>
      <li>Anti-jamming and packet injection support for robust testing</li>
      <li>Compatible with PlatformIO and Arduino IDE for custom development</li>
      <li>Enhanced security features to prevent unauthorized access</li>
      <li>Customizable settings for tailored network testing scenarios</li>
    </ul>
  </div>
</div>

<!-- TIMELINE -->
<div id="timeline" class="section">
  <h2 class="glow-title">🗓️ Timeline</h2>
  <ul class="border-l-4 border-[#00eaff] pl-6 space-y-6 mt-4">
    <li>
      <div class="font-bold">🔧 Prototype 1 – Complete</div>
      <p>Initial ESP32-based design with 2.4GHz deauth and LiPo charging.</p>
    </li>
    <li>
      <div class="font-bold">📡 Dual-Band Upgrade – Complete</div>
      <p>Integrated BW16 for 5GHz support. Redesigned to fit SMA antennas and new boot/reset layout.</p>
    </li>
    <li>
      <div class="font-bold">💻 Firmware V1.0 – Released</div>
      <p>Stable release with web UI and OTA support.</p>
    </li>
    <li>
      <div class="font-bold">📣 Community Feedback – Ongoing</div>
      <p>Collecting user feedback via Discord and GitHub to improve features and usability.</p>
    </li>
    <li>
      <div class="font-bold">📦 Public Release – Coming June 2025</div>
      <p>Final hardware with case design and shipping options for first 100 units.</p>
    </li>
    <li>
      <div class="font-bold">🚀 V2 Development – Q4 2025</div>
      <p>Research into integrated GPS and better chipset support for future expansion (wardriving module).</p>
    </li>
    <li>
      <div class="font-bold">🔄 Firmware V2.0 – Q1 2026</div>
      <p>Planned update with advanced analytics and expanded API support.</p>
    </li>
  </ul>
</div>