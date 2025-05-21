---
layout: default
title: Firmware & Software
---

<div class="hero fade-in">
  <h1>Firmware & Software</h1>
  <p>Download the latest firmware and software for your Black Hole V1.0 device.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">Official Firmware</h2>
  
  <div class="faq-item">
    <p class="faq-question">Current Stable Release: v1.2.5</p>
    <div class="faq-answer">
      <p>Our latest stable firmware release includes performance improvements, bug fixes, and new features:</p>
      <ul>
        <li>Enhanced 5GHz band scanning capabilities</li>
        <li>Improved battery life management</li>
        <li>New traffic analysis visualization tools</li>
        <li>Fixed connection stability issues on certain networks</li>
        <li>Added support for WPA3 networks</li>
      </ul>
      <a href="#" class="btn btn-secondary mt-2">Download v1.2.5</a>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Beta Release: v1.3.0-beta</p>
    <div class="faq-answer">
      <p>For users who want to test upcoming features, our beta firmware offers:</p>
      <ul>
        <li>Experimental client fingerprinting capabilities</li>
        <li>Advanced packet injection tools</li>
        <li>New command-line interface options</li>
        <li>Customizable dashboard widgets</li>
      </ul>
      <p><strong>Note:</strong> Beta firmware may contain bugs and is not recommended for critical applications.</p>
      <a href="#" class="btn btn-secondary mt-2">Download v1.3.0-beta</a>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Legacy Firmware</p>
    <div class="faq-answer">
      <p>Previous stable releases are available for users who require specific versions:</p>
      <ul>
        <li><a href="#">v1.2.0</a> - Initial 5GHz support</li>
        <li><a href="#">v1.1.5</a> - Performance optimization update</li>
        <li><a href="#">v1.1.0</a> - Web interface redesign</li>
        <li><a href="#">v1.0.0</a> - Initial release</li>
      </ul>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Installation Instructions</h2>
  
  <h3>Over-the-Air Update (Recommended)</h3>
  <ol>
    <li>Connect to your Black Hole device's WiFi network</li>
    <li>Open the web interface at <code>http://192.168.4.1</code></li>
    <li>Navigate to "Settings" > "Update Firmware"</li>
    <li>Select "Online Update" and click "Check for Updates"</li>
    <li>If an update is available, click "Install Update"</li>
    <li>Wait for the update to complete and the device to restart</li>
  </ol>
  
  <h3>Manual Update</h3>
  <ol>
    <li>Download the firmware file from the links above</li>
    <li>Connect to your Black Hole device's WiFi network</li>
    <li>Open the web interface at <code>http://192.168.4.1</code></li>
    <li>Navigate to "Settings" > "Update Firmware"</li>
    <li>Select "Manual Update"</li>
    <li>Click "Choose File" and select the downloaded firmware file</li>
    <li>Click "Upload" and wait for the update to complete</li>
    <li>The device will automatically restart with the new firmware</li>
  </ol>
  
  <div class="faq-item">
    <p class="faq-question">Recovery Mode</p>
    <div class="faq-answer">
      <p>If your device becomes unresponsive after a firmware update, you can use recovery mode:</p>
      <ol>
        <li>Power off the device</li>
        <li>Press and hold the reset button</li>
        <li>While holding the reset button, power on the device</li>
        <li>Continue holding the reset button for 5 seconds, then release</li>
        <li>The device will boot into recovery mode with the status LED blinking rapidly</li>
        <li>Connect to the "BlackHole_Recovery" WiFi network (password: "recovery")</li>
        <li>Open <code>http://192.168.4.1</code> and follow the recovery instructions</li>
      </ol>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Custom Firmware Options</h2>
  
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-shield-alt"></i></div>
      <h3 class="feature-title">Security Researcher Edition</h3>
      <p class="feature-description">Enhanced packet injection capabilities, advanced scanning tools, and raw packet access.</p>
      <a href="#" class="btn btn-secondary mt-2">Download SR Edition</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-network-wired"></i></div>
      <h3 class="feature-title">Network Analyzer Edition</h3>
      <p class="feature-description">Focused on traffic analysis, bandwidth monitoring, and network diagnostics.</p>
      <a href="#" class="btn btn-secondary mt-2">Download NA Edition</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fas fa-code"></i></div>
      <h3 class="feature-title">Developer Edition</h3>
      <p class="feature-description">Includes SDK, API documentation, and example code for custom development.</p>
      <a href="#" class="btn btn-secondary mt-2">Download Dev Edition</a>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Companion Software</h2>
  
  <h3>Mobile Applications</h3>
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-android"></i></div>
      <h3 class="feature-title">Android App</h3>
      <p class="feature-description">Control your Black Hole device from your Android smartphone or tablet.</p>
      <a href="#" class="btn btn-secondary mt-2">Download for Android</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-apple"></i></div>
      <h3 class="feature-title">iOS App</h3>
      <p class="feature-description">Control your Black Hole device from your iPhone or iPad.</p>
      <a href="#" class="btn btn-secondary mt-2">Download for iOS</a>
    </div>
  </div>
  
  <h3>Desktop Applications</h3>
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-windows"></i></div>
      <h3 class="feature-title">Windows Application</h3>
      <p class="feature-description">Advanced control and analysis tools for Windows 10/11.</p>
      <a href="#" class="btn btn-secondary mt-2">Download for Windows</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-apple"></i></div>
      <h3 class="feature-title">macOS Application</h3>
      <p class="feature-description">Advanced control and analysis tools for macOS.</p>
      <a href="#" class="btn btn-secondary mt-2">Download for macOS</a>
    </div>
    
    <div class="feature-card">
      <div class="feature-icon"><i class="fab fa-linux"></i></div>
      <h3 class="feature-title">Linux Application</h3>
      <p class="feature-description">Advanced control and analysis tools for Linux distributions.</p>
      <a href="#" class="btn btn-secondary mt-2">Download for Linux</a>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Development Resources</h2>
  
  <div class="faq-item">
    <p class="faq-question">API Documentation</p>
    <div class="faq-answer">
      <p>Our comprehensive API documentation allows you to create custom applications that interact with the Black Hole device:</p>
      <ul>
        <li><a href="#">RESTful API Reference</a></li>
        <li><a href="#">WebSocket API Guide</a></li>
        <li><a href="#">Authentication Methods</a></li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">SDK & Libraries</p>
    <div class="faq-answer">
      <p>Development kits and libraries for various programming languages:</p>
      <ul>
        <li><a href="#">Python SDK</a></li>
        <li><a href="#">JavaScript Library</a></li>
        <li><a href="#">C++ Library</a></li>
        <li><a href="#">Java Library</a></li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">GitHub Repository</p>
    <div class="faq-answer">
      <p>Our open-source components are available on GitHub:</p>
      <ul>
        <li><a href="#">Black Hole Firmware</a> - Core firmware source code</li>
        <li><a href="#">Black Hole Web Interface</a> - Web UI source code</li>
        <li><a href="#">Black Hole Mobile Apps</a> - Mobile application source code</li>
        <li><a href="#">Black Hole Hardware</a> - Hardware design files and schematics</li>
      </ul>
      <a href="https://github.com/blackhole" class="btn btn-secondary mt-2">Visit GitHub</a>
    </div>
  </div>
</section>

<div class="faq-item fade-in mt-5">
  <p class="faq-question">Firmware Update Policy</p>
  <div class="faq-answer">
    <p>We are committed to providing regular firmware updates for the Black Hole V1.0 device:</p>
    <ul>
      <li><strong>Security Updates:</strong> Critical security patches are released as needed</li>
      <li><strong>Feature Updates:</strong> New features are released approximately every 3 months</li>
      <li><strong>Major Versions:</strong> Significant updates are released approximately every 6-12 months</li>
    </ul>
    <p>All updates are provided free of charge to Black Hole owners.</p>
  </div>
</div>

<div class="btn-group mt-5 fade-in">
  <a href="{{ '/specs' | relative_url }}" class="btn">Technical Specifications</a>
  <a href="{{ '/faq' | relative_url }}" class="btn btn-secondary">Frequently Asked Questions</a>
</div>
