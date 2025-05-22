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

  .video-link, .external-link {
    display: inline-block;
    margin: 8px 0;
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff;
    text-decoration: none;
    font-size: 18px;
    transition: color 0.3s ease;
  }

  .video-link:hover, .external-link:hover {
    color: #80ffff;
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

  .product-image {
    display: block;
    margin: 20px auto 30px auto;
    max-width: 100%;
    height: auto;
    border: 2px solid #00f0ff44;
    box-shadow: 0 0 15px #00f0ff55;
    border-radius: 10px;
  }

  ul, ol {
    margin-left: 20px;
    margin-bottom: 20px;
  }

  code {
    background: #001f1f;
    padding: 2px 6px;
    border-radius: 4px;
    font-family: monospace;
    font-size: 16px;
  }

  pre {
    background: #001f1f;
    padding: 15px;
    border-radius: 8px;
    overflow-x: auto;
    font-family: monospace;
    font-size: 16px;
    margin-bottom: 25px;
  }

  hr {
    border: none;
    border-top: 1px solid #004f4f;
    margin: 40px 0;
  }
</style>

<div class="nav-wrapper" role="navigation" aria-label="Primary Navigation">
  <div class="nav-title" tabindex="0" aria-label="Site title">Black Hole V1.0</div>
  <div class="nav-row">
    <a href="#" onclick="showSection('home')" class="neon-button" role="button" aria-pressed="true" tabindex="0">Home</a>
    <a href="#" onclick="showSection('product')" class="neon-button" role="button" aria-pressed="false" tabindex="0">Product</a>
    <a href="#" onclick="showSection('media')" class="neon-button" role="button" aria-pressed="false" tabindex="0">Media</a>
    <a href="#" onclick="showSection('demos')" class="neon-button" role="button" aria-pressed="false" tabindex="0">Demos</a>
  </div>
  <div class="nav-row">
    <a href="#" onclick="showSection('about')" class="neon-button" role="button" aria-pressed="false" tabindex="0">About</a>
    <a href="#" onclick="showSection('faq')" class="neon-button" role="button" aria-pressed="false" tabindex="0">FAQ</a>
    <a href="#" onclick="showSection('firmware')" class="neon-button" role="button" aria-pressed="false" tabindex="0">Firmware</a>
    <a href="#" onclick="showSection('timeline')" class="neon-button" role="button" aria-pressed="false" tabindex="0">Timeline</a>
  </div>
</div>

<!-- Home Section -->
<div id="home" class="section active" tabindex="0" aria-live="polite" aria-label="Home Section">
  <h1 class="glow-title">🌌 Welcome to Black Hole V1.0</h1>
  <p>This is your central hub for all things Black Hole — updates, documentation, media, and community interaction. Explore everything this project has to offer.</p>
  <div class="discord-join" role="region" aria-label="Discord community invite">
    <p>💬 Join the community on Discord!</p>
    <a href="https://discord.gg/YOUR_INVITE_CODE" target="_blank" rel="noopener noreferrer" aria-label="Join Discord server">Click here to join my Discord Server</a>
  </div>
  <hr>
  <h2 class="glow-title">Latest Updates</h2>
  <div class="glow-block" role="article" aria-label="Latest news update March 2025">
    <strong>May 2025:</strong> Released new firmware v1.2.3 with enhanced stability and new anti-jamming features.
    <ul>
      <li>Improved 5GHz antenna switching</li>
      <li>Battery optimization for longer runtime</li>
      <li>Bug fixes for ESP32 connectivity</li>
    </ul>
  </div>
  <div class="glow-block" role="article" aria-label="Upcoming events April 2025">
    <strong>Upcoming:</strong> Live demo event scheduled for June 10, 2025 — join via Discord or YouTube livestream.
  </div>
</div>

<!-- Product Section -->
<div id="product" class="section" tabindex="0" aria-live="polite" aria-label="Product Information Section">
  <h1 class="glow-title">Product Information</h1>
  <img class="product-image" src="https://via.placeholder.com/600x350?text=Black+Hole+V1.0+Device" alt="Black Hole V1.0 Device Image">
  <div class="glow-block" role="region" aria-label="Product features and details">
    <strong>Product:</strong> Black Hole V1.0<br>
    <strong>Features:</strong>
    <ul>
      <li>Dual-band WiFi jamming (2.4GHz + 5GHz)</li>
      <li>External SMA antennas for improved signal range and stability</li>
      <li>Rechargeable LiPo battery support with USB-C charging</li>
      <li>Compact, sleek black PCB with protective case</li>
      <li>Easy firmware upgrades via USB</li>
      <li>Customizable launch control and anti-lag settings</li>
    </ul>
    <strong>Price:</strong> $140
  </div>
  <div class="glow-block" role="region" aria-label="Product inventory status">
    <strong>Inventory:</strong> <em>0 in stock. 1 unit arriving in approximately 3 weeks.</em>
  </div>
  <hr>
  <h2 class="glow-title">Detailed Specifications</h2>
  <table style="width:100%; border-collapse: collapse; margin-bottom: 30px;">
    <thead>
      <tr style="border-bottom: 2px solid #00f0ff;">
        <th style="text-align:left; padding:10px; color:#00f0ff;">Component</th>
        <th style="text-align:left; padding:10px; color:#00f0ff;">Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr style="border-bottom: 1px solid #004f4f;">
        <td style="padding:10px;">Microcontroller</td>
        <td style="padding:10px;">ESP32-WROOM-32U</td>
      </tr>
      <tr style="border-bottom: 1px solid #004f4f;">
        <td style="padding:10px;">Dual-band Module</td>
        <td style="padding:10px;">BW16 (2.4GHz + 5GHz)</td>
      </tr>
      <tr style="border-bottom: 1px solid #004f4f;">
        <td style="padding:10px;">Antennas</td>
        <td style="padding:10px;">2x SMA connectors, external antennas</td>
      </tr>
      <tr style="border-bottom: 1px solid #004f4f;">
        <td style="padding:10px;">Battery</td>
        <td style="padding:10px;">Single-cell LiPo, 3.7V, USB-C charge</td>
      </tr>
      <tr style="border-bottom: 1px solid #004f4f;">
        <td style="padding:10px;">Dimensions</td>
        <td style="padding:10px;">85mm x 60mm x 15mm (with case)</td>
      </tr>
      <tr>
        <td style="padding:10px;">Weight</td>
        <td style="padding:10px;">150g</td>
      </tr>
    </tbody>
  </table>
  <hr>
  <h2 class="glow-title">Included Parts List</h2>
  <ol>
    <li>ESP32-WROOM-32U Microcontroller Module</li>
    <li>BW16 Dual-band WiFi Module</li>
    <li>2x SMA Connectors (2.4GHz & 5GHz Antennas)</li>
    <li>LiPo Battery Charging Circuit</li>
    <li>USB-C Charging Port</li>
    <li>Reset Button (Red Tip)</li>
    <li>Power Button (Black, Centered)</li>
    <li>4-layer Black PCB</li>
    <li>Protective Custom Case</li>
    <li>Firmware Preloaded on Device</li>
    <li>Instruction Manual PDF</li>
  </ol>
  <hr>
  <h2 class="glow-title">Ordering Information</h2>
  <p>To place an order or request a custom build, please contact me via Discord or GitHub:</p>
  <ul>
    <li><a href="https://discord.gg/YOUR_INVITE_CODE" class="external-link" target="_blank" rel="noopener noreferrer">Discord Server</a></li>
    <li><a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="external-link" target="_blank" rel="noopener noreferrer">GitHub Repository</a></li>
  </ul>
</div>

<!-- Media Section -->
<div id="media" class="section" tabindex="0" aria-live="polite" aria-label="Media Section">
  <h1 class="glow-title">Media</h1>
  <p>Explore videos, images, and walkthroughs of the Black Hole V1.0 device in action.</p>
  
  <h2>Video Walkthroughs</h2>
  <ul>
    <li><a href="https://youtu.be/example1" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch Black Hole V1.0 introduction video on YouTube">Introduction to Black Hole V1.0</a></li>
    <li><a href="https://youtu.be/example2" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch detailed teardown and build guide video">Teardown and Build Guide</a></li>
    <li><a href="https://youtu.be/example3" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch firmware update tutorial video">Firmware Update Tutorial</a></li>
  </ul>

  <h2>Photo Gallery</h2>
  <img src="https://via.placeholder.com/450x300?text=Black+Hole+PCB+Closeup" alt="Close-up image of Black Hole V1.0 PCB" class="product-image" />
  <img src="https://via.placeholder.com/450x300?text=Black+Hole+In+Case" alt="Black Hole V1.0 device inside protective case" class="product-image" />
  <img src="https://via.placeholder.com/450x300?text=Black+Hole+Setup" alt="Black Hole V1.0 setup during a test" class="product-image" />

  <h2>Demo Clips</h2>
  <ul>
    <li><a href="https://youtu.be/demo1" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch WiFi jamming demo clip">WiFi Jamming Demo</a></li>
    <li><a href="https://youtu.be/demo2" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch antenna range comparison video">Antenna Range Comparison</a></li>
    <li><a href="https://youtu.be/demo3" target="_blank" rel="noopener noreferrer" class="video-link" aria-label="Watch battery life test video">Battery Life Test</a></li>
  </ul>
</div>

<!-- Demos Section -->
<div id="demos" class="section" tabindex="0" aria-live="polite" aria-label="Demo Section">
  <h1 class="glow-title">Live Demos & Interactive Content</h1>
  <p>Try out firmware simulation or explore interactive demos below.</p>

  <h2>Firmware Simulator</h2>
  <p>Simulate key firmware functions in a web interface:</p>
  <pre><code>
  # Example firmware simulation commands
  # Start jamming on 2.4GHz band
  start_jamming(2.4)

  # Switch to 5GHz band
  switch_band(5)

  # Check battery status
  battery_status()
  </code></pre>
  <p><em>Note: This is a conceptual simulator and not a real device emulator.</em></p>

  <h2>Interactive Signal Range Map</h2>
  <p>Explore how the signal strength varies with antenna type and distance (conceptual visualization):</p>
  <ul>
    <li><strong>Short-range mode:</strong> Up to 50 meters</li>
    <li><strong>Medium-range mode:</strong> Up to 150 meters</li>
    <li><strong>Long-range mode:</strong> Up to 300 meters (with external antenna)</li>
  </ul>

  <h2>Source Code Snippet</h2>
  <pre><code class="language-c">
// Setup WiFi jamming
void start_jamming(float band) {
  if (band == 2.4) {
    // Initialize 2.4GHz band jammer
    initialize_24GHz();
  } else if (band == 5.0) {
    // Initialize 5GHz band jammer
    initialize_5GHz();
  }
  start_jamming_routine();
}
  </code></pre>

  <h2>Download Firmware</h2>
  <p><a href="firmware/BlackHoleV1.0_v1.2.3.bin" class="external-link" download aria-label="Download Black Hole V1.0 firmware version 1.2.3">Black Hole V1.0 Firmware v1.2.3</a></p>
</div>

<!-- About Section -->
<div id="about" class="section" tabindex="0" aria-live="polite" aria-label="About Section">
  <h1 class="glow-title">About Black Hole V1.0</h1>
  <p>Black Hole V1.0 is a project developed and engineered by <strong>unnamedperson488</strong>. Designed as a powerful dual-band WiFi auditing and jamming tool, it combines cutting-edge hardware with sleek design and robust software.</p>
  <p>This project was inspired by the need for a reliable, compact, and customizable wireless security tool for ethical hacking and testing purposes.</p>

  <h2>Project Goals</h2>
  <ul>
    <li>Provide a dual-band WiFi jammer with external antennas for increased effectiveness.</li>
    <li>Make firmware easily upgradeable and customizable.</li>
    <li>Create a user-friendly interface and community for support.</li>
    <li>Use high-quality, accessible hardware components.</li>
  </ul>

  <h2>Future Plans</h2>
  <ol>
    <li>Develop a wardriving module with GPS integration.</li>
    <li>Expand firmware features including launch control and anti-lag systems.</li>
    <li>Introduce additional external antenna options for extended range.</li>
    <li>Open-source select portions of the project to encourage community contribution.</li>
  </ol>

  <h2>Contact</h2>
  <p>Reach out via <a href="https://discord.gg/YOUR_INVITE_CODE" class="external-link" target="_blank" rel="noopener noreferrer">Discord</a> or check the <a href="https://github.com/unnamedperson488" class="external-link" target="_blank" rel="noopener noreferrer">GitHub</a> profile for collaboration opportunities.</p>
</div>

<!-- FAQ Section -->
<div id="faq" class="section" tabindex="0" aria-live="polite" aria-label="FAQ Section">
  <h1 class="glow-title">Frequently Asked Questions</h1>
  
  <h2>Q: What is the range of the Black Hole V1.0?</h2>
  <p>A: It varies based on antenna and environment, typically 100-300 meters outdoors with external antennas.</p>

  <h2>Q: Can I update the firmware myself?</h2>
  <p>A: Yes, firmware updates are user-friendly and downloadable from the Media section.</p>

  <h2>Q: Is the device legal to use?</h2>
  <p>A: Usage depends on local laws. The device is intended for ethical testing and research only.</p>

  <h2>Q: How long does the battery last?</h2>
  <p>A: Typical battery life is 3-4 hours under continuous use.</p>

  <h2>Q: Can I customize the device hardware?</h2>
  <p>A: Yes, the project encourages customization with available hardware parts and open schematics.</p>

  <h2>Q: What support do you offer?</h2>
  <p>A: Community support is available on Discord; official support via GitHub issues.</p>
</div>

<!-- Firmware Section -->
<div id="firmware" class="section" tabindex="0" aria-live="polite" aria-label="Firmware Section">
  <h1 class="glow-title">Firmware</h1>
  <p>Firmware updates are released regularly to improve functionality, fix bugs, and add features.</p>
  <ul>
    <li><strong>Current Version:</strong> v1.2.3 (May 2025)</li>
    <li><strong>Supported Devices:</strong> Black Hole V1.0</li>
  </ul>

  <h2>Download Firmware</h2>
  <p><a href="firmware/BlackHoleV1.0_v1.2.3.bin" class="external-link" download aria-label="Download firmware version 1.2.3">Black Hole V1.0 Firmware v1.2.3</a></p>

  <h2>Flashing Instructions</h2>
  <ol>
    <li>Connect your Black Hole V1.0 device to your PC via USB-C cable.</li>
    <li>Download the <code>flash_tool.exe</code> or use <code>esptool.py</code> on Linux/Mac.</li>
    <li>Open a terminal or command prompt in the directory containing the firmware binary.</li>
    <li>Run the following command to flash:
      <pre><code>esptool.py --chip esp32 --port COM3 write_flash -z 0x1000 BlackHoleV1.0_v1.2.3.bin</code></pre>
    </li>
    <li>After flashing, reset the device by pressing the reset button.</li>
    <li>Verify the device boots correctly and check functionality.</li>
  </ol>
  
  <h2>Troubleshooting</h2>
  <ul>
    <li>Make sure drivers for the ESP32 are installed.</li>
    <li>Verify the correct COM port is selected.</li>
    <li>Check USB cable and connection.</li>
    <li>If flashing fails, press and hold the boot button while connecting.</li>
  </ul>
</div>

<!-- Timeline Section -->
<div id="timeline" class="section" tabindex="0" aria-live="polite" aria-label="Timeline Section">
  <h1 class="glow-title">Development Timeline</h1>
  
  <ul>
    <li><strong>January 2025:</strong> Conceptual design and initial hardware research.</li>
    <li><strong>February 2025:</strong> Prototype PCB designed and fabricated.</li>
    <li><strong>March 2025:</strong> Firmware v1.0 released; basic jamming functions tested.</li>
    <li><strong>April 2025:</strong> Integration of external antennas and battery management.</li>
    <li><strong>May 2025:</strong> Firmware v1.2.3 released; stability improvements and bug fixes.</li>
    <li><strong>June 2025 (Planned):</strong> Live demo and release of wardriving module concept.</li>
    <li><strong>July 2025 (Planned):</strong> Community open source collaboration starts.</li>
  </ul>
</div>

<script>
  function showSection(sectionId) {
    const sections = document.querySelectorAll('.section');
    sections.forEach(sec => {
      if (sec.id === sectionId) {
        sec.classList.add('active');
        sec.setAttribute('aria-hidden', 'false');
      } else {
        sec.classList.remove('active');
        sec.setAttribute('aria-hidden', 'true');
      }
    });

    // Update aria-pressed attributes on nav buttons
    const buttons = document.querySelectorAll('.nav-row a.neon-button');
    buttons.forEach(button => {
      button.setAttribute('aria-pressed', 'false');
    });
    const activeButton = Array.from(buttons).find(btn => btn.textContent.toLowerCase() === sectionId);
    if (activeButton) activeButton.setAttribute('aria-pressed', 'true');

    // Focus the shown section for screen readers
    const activeSection = document.getElementById(sectionId);
    if (activeSection) activeSection.focus();
  }
</script>
