---
layout: default
title: Getting Started
---

<div class="hero fade-in">
  <h1>Getting Started with Black Hole</h1>
  <p>Your guide to setting up and using the Black Hole V1.0 WiFi security testing device.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">Introduction</h2>
  <p>Welcome to the Black Hole V1.0 documentation! This guide will help you get started with your new device, from initial setup to basic operations. Black Hole is a powerful WiFi security testing tool designed for educational purposes, allowing security professionals and enthusiasts to understand and improve wireless network security.</p>
  
  <div class="faq-item">
    <p class="faq-question">What's in the Box?</p>
    <div class="faq-answer">
      <ul>
        <li>Black Hole V1.0 device</li>
        <li>2× SMA antennas</li>
        <li>USB-C charging cable</li>
        <li>Quick start guide</li>
        <li>Stickers</li>
      </ul>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Quick Start Guide</h2>
  
  <h3>Step 1: Charge Your Device</h3>
  <p>Before first use, we recommend fully charging your Black Hole device using the included USB-C cable. Connect it to any USB power source. The charging LED will turn red while charging and green when fully charged.</p>
  
  <h3>Step 2: Attach the Antennas</h3>
  <p>Screw the included SMA antennas onto the antenna connectors on the device. Make sure they're securely attached for optimal performance.</p>
  
  <h3>Step 3: Power On</h3>
  <p>Press and hold the power button for 3 seconds to turn on the device. The status LED will light up, indicating the device is powered on and booting up.</p>
  
  <h3>Step 4: Connect to the Web Interface</h3>
  <p>The Black Hole creates its own WiFi network named "BlackHole_XXXX" (where XXXX is a unique identifier). Connect to this network using your computer or mobile device. The default password is "blackhole".</p>
  
  <h3>Step 5: Access the Control Panel</h3>
  <p>Open a web browser and navigate to <code>http://192.168.4.1</code>. This will open the Black Hole control panel, where you can access all features and settings.</p>
</section>

<section class="fade-in">
  <h2 class="section-title">Basic Operations</h2>
  
  <h3>Scanning Networks</h3>
  <p>From the control panel, click on "Scan Networks" to see all available WiFi networks in your vicinity. The scan will show network names (SSIDs), signal strength, channel, and security type.</p>
  
  <h3>Changing Operation Mode</h3>
  <p>Black Hole supports multiple operation modes, including:</p>
  <ul>
    <li><strong>Monitor Mode:</strong> Passively monitor WiFi traffic</li>
    <li><strong>Packet Injection Mode:</strong> For advanced testing scenarios</li>
    <li><strong>Access Point Mode:</strong> Create a test access point</li>
  </ul>
  <p>Select your desired mode from the "Operation Mode" dropdown in the control panel.</p>
  
  <h3>Updating Firmware</h3>
  <p>We regularly release firmware updates with new features and security improvements. To update:</p>
  <ol>
    <li>Download the latest firmware from the <a href="{{ '/firmware' | relative_url }}">Firmware page</a></li>
    <li>In the control panel, go to "Settings" > "Update Firmware"</li>
    <li>Select the downloaded firmware file and click "Upload"</li>
    <li>Wait for the update to complete and the device to restart</li>
  </ol>
</section>

<section class="fade-in">
  <h2 class="section-title">Next Steps</h2>
  <p>Now that you've set up your Black Hole device, you can explore its full capabilities:</p>
  
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-book"></i></div>
      <h3 class="feature-title">Read the Full Documentation</h3>
      <p class="feature-description">Explore all features and capabilities in our comprehensive documentation.</p>
      <a href="{{ '/features' | relative_url }}" class="btn btn-secondary mt-2">View Features</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-download"></i></div>
      <h3 class="feature-title">Install Custom Firmware</h3>
      <p class="feature-description">Extend functionality with specialized firmware options.</p>
      <a href="{{ '/firmware' | relative_url }}" class="btn btn-secondary mt-2">Firmware Options</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-users"></i></div>
      <h3 class="feature-title">Join the Community</h3>
      <p class="feature-description">Connect with other users for tips, tricks, and support.</p>
      <a href="https://discord.gg/" class="btn btn-secondary mt-2">Join Discord</a>
    </div>
  </div>
</section>

<div class="faq-item fade-in mt-5">
  <p class="faq-question">Important Note on Ethical Usage</p>
  <div class="faq-answer">
    <p>Black Hole is designed for educational purposes and security testing on networks you own or have explicit permission to test. Unauthorized testing on third-party networks may be illegal in your jurisdiction. Always use this device responsibly and ethically.</p>
    <p>For more information, please read our <a href="{{ '/disclaimer' | relative_url }}">Legal Disclaimer</a>.</p>
  </div>
</div>

<div class="btn-group mt-5 fade-in">
  <a href="{{ '/installation' | relative_url }}" class="btn">Detailed Installation Guide</a>
  <a href="{{ '/features' | relative_url }}" class="btn btn-secondary">Explore Features</a>
</div>
