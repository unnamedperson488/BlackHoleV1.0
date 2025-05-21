---
layout: default
title: Installation Guide
---

<div class="hero fade-in">
  <h1>Installation Guide</h1>
  <p>Complete instructions for setting up your Black Hole V1.0 device and its software components.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">Hardware Setup</h2>
  
  <h3>Physical Installation</h3>
  <p>Setting up your Black Hole device is straightforward:</p>
  
  <ol>
    <li><strong>Unbox the device:</strong> Carefully remove all components from the packaging.</li>
    <li><strong>Attach antennas:</strong> Screw the included SMA antennas clockwise onto the antenna connectors until finger-tight. Do not overtighten.</li>
    <li><strong>Charge the battery:</strong> Connect the USB-C cable to the device and a power source. The red charging LED will illuminate while charging and turn green when fully charged (approximately 2-3 hours for a full charge).</li>
  </ol>
  
  <div class="faq-item">
    <p class="faq-question">Antenna Positioning</p>
    <div class="faq-answer">
      <p>For optimal performance, position the antennas at a 90° angle to each other. This orientation provides the best signal reception and transmission capabilities across both 2.4GHz and 5GHz bands.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Initial Configuration</h2>
  
  <h3>First Boot</h3>
  <p>To power on your Black Hole device for the first time:</p>
  
  <ol>
    <li>Press and hold the power button for 3 seconds.</li>
    <li>The status LED will blink rapidly during boot-up (approximately 10-15 seconds).</li>
    <li>When the LED becomes solid, the device is ready to use.</li>
  </ol>
  
  <h3>Connecting to the Device</h3>
  <p>Black Hole creates its own WiFi network for configuration and control:</p>
  
  <ol>
    <li>On your computer or mobile device, scan for available WiFi networks.</li>
    <li>Connect to the network named "BlackHole_XXXX" (where XXXX is a unique identifier based on the device's MAC address).</li>
    <li>Enter the default password: <code>blackhole</code></li>
    <li>Open a web browser and navigate to <code>http://192.168.4.1</code></li>
    <li>You should now see the Black Hole control panel interface.</li>
  </ol>
  
  <div class="faq-item">
    <p class="faq-question">Changing Default Credentials</p>
    <div class="faq-answer">
      <p>For security reasons, we strongly recommend changing the default WiFi password after your first connection. This can be done in the "Settings" section of the control panel.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Software Installation</h2>
  
  <h3>Web Interface</h3>
  <p>The Black Hole comes pre-installed with its web interface, which requires no additional installation. However, for optimal performance, we recommend using the latest versions of Chrome, Firefox, or Safari browsers.</p>
  
  <h3>Companion App (Optional)</h3>
  <p>For enhanced functionality, you can install our companion app:</p>
  
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-android"></i></div>
      <h3 class="feature-title">Android</h3>
      <p class="feature-description">Available on Google Play Store</p>
      <a href="#" class="btn btn-secondary mt-2">Download for Android</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-apple"></i></div>
      <h3 class="feature-title">iOS</h3>
      <p class="feature-description">Available on Apple App Store</p>
      <a href="#" class="btn btn-secondary mt-2">Download for iOS</a>
    </div>
  </div>
  
  <h3>Custom Firmware Installation</h3>
  <p>To install custom or updated firmware:</p>
  
  <ol>
    <li>Download the desired firmware file from our <a href="{{ '/firmware' | relative_url }}">Firmware page</a>.</li>
    <li>Connect to your Black Hole device as described above.</li>
    <li>In the web interface, navigate to "Settings" > "Update Firmware".</li>
    <li>Click "Choose File" and select the downloaded firmware file.</li>
    <li>Click "Upload" and wait for the process to complete (do not disconnect or power off during this process).</li>
    <li>The device will automatically restart with the new firmware installed.</li>
  </ol>
  
  <div class="faq-item">
    <p class="faq-question">Firmware Recovery</p>
    <div class="faq-answer">
      <p>If a firmware update fails or the device becomes unresponsive, you can enter recovery mode by holding the reset button while powering on the device. Release the reset button after 5 seconds. The device will boot into recovery mode, allowing you to reinstall firmware via USB.</p>
      <p>For detailed recovery instructions, please see our <a href="{{ '/faq' | relative_url }}#firmware-recovery">FAQ page</a>.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Advanced Installation</h2>
  
  <h3>Custom Case Installation</h3>
  <p>Black Hole V1.0 is designed to fit into standard 3D-printed cases. To install your device in a custom case:</p>
  
  <ol>
    <li>Download the case design files from our <a href="https://github.com/blackhole/case-designs">GitHub repository</a>.</li>
    <li>3D print the case using PLA or ABS material (recommended settings: 0.2mm layer height, 20% infill).</li>
    <li>Remove the four screws from the bottom of the Black Hole device.</li>
    <li>Carefully place the device into the bottom half of the case.</li>
    <li>Secure with the provided longer screws through the case mounting holes.</li>
    <li>Snap the top half of the case into place.</li>
  </ol>
  
  <h3>External Antenna Upgrades</h3>
  <p>The standard SMA connectors allow for antenna upgrades. Compatible antennas include:</p>
  
  <ul>
    <li>High-gain directional antennas (up to 9dBi)</li>
    <li>Omnidirectional antennas for broader coverage</li>
    <li>Dual-band antennas optimized for both 2.4GHz and 5GHz</li>
  </ul>
  
  <p>Simply unscrew the standard antennas and replace them with your preferred compatible SMA antennas.</p>
</section>

<section class="fade-in">
  <h2 class="section-title">Troubleshooting</h2>
  
  <div class="faq-item">
    <p class="faq-question">Device Won't Power On</p>
    <div class="faq-answer">
      <p>If your Black Hole device doesn't power on:</p>
      <ul>
        <li>Ensure the battery is charged (connect to USB power for at least 30 minutes)</li>
        <li>Try a hard reset by holding the power and reset buttons simultaneously for 10 seconds</li>
        <li>Check the USB cable and power source with another device</li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Can't Connect to WiFi Network</p>
    <div class="faq-answer">
      <p>If you can't connect to the Black Hole WiFi network:</p>
      <ul>
        <li>Ensure the device is powered on and the status LED is solid</li>
        <li>Restart your computer or mobile device's WiFi</li>
        <li>Move closer to the Black Hole device</li>
        <li>Try resetting the device by pressing the reset button once</li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Web Interface Not Loading</p>
    <div class="faq-answer">
      <p>If the web interface doesn't load at 192.168.4.1:</p>
      <ul>
        <li>Ensure you're connected to the Black Hole WiFi network</li>
        <li>Try clearing your browser cache</li>
        <li>Try a different browser</li>
        <li>Restart the Black Hole device</li>
      </ul>
    </div>
  </div>
</section>

<div class="btn-group mt-5 fade-in">
  <a href="{{ '/getting-started' | relative_url }}" class="btn">Back to Getting Started</a>
  <a href="{{ '/features' | relative_url }}" class="btn btn-secondary">Explore Features</a>
</div>
