---
layout: default
title: Technical Specifications
---

<div class="hero fade-in">
  <h1>Technical Specifications</h1>
  <p>Detailed hardware and software specifications for the Black Hole V1.0 device.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">Hardware Specifications</h2>
  
  <h3>Processor & System</h3>
  <table>
    <thead>
      <tr>
        <th>Component</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Main Processor</td>
        <td>ESP32-D0WDQ6 dual-core Tensilica LX6 microprocessor</td>
      </tr>
      <tr>
        <td>Clock Speed</td>
        <td>240 MHz (maximum)</td>
      </tr>
      <tr>
        <td>Co-processor</td>
        <td>BW16 for enhanced wireless capabilities</td>
      </tr>
      <tr>
        <td>RAM</td>
        <td>520 KB SRAM</td>
      </tr>
      <tr>
        <td>Flash Memory</td>
        <td>4 MB SPI flash</td>
      </tr>
      <tr>
        <td>GPIO Pins</td>
        <td>24 programmable GPIO pins</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Wireless Capabilities</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>WiFi Standards</td>
        <td>IEEE 802.11 b/g/n/ac</td>
      </tr>
      <tr>
        <td>Frequency Bands</td>
        <td>2.4 GHz and 5 GHz</td>
      </tr>
      <tr>
        <td>WiFi Modes</td>
        <td>Station, SoftAP, SoftAP+Station, P2P</td>
      </tr>
      <tr>
        <td>WiFi Security</td>
        <td>WPA/WPA2/WPA3/WEP</td>
      </tr>
      <tr>
        <td>Bluetooth</td>
        <td>Bluetooth 5.0 BR/EDR and BLE</td>
      </tr>
      <tr>
        <td>Antenna Connectors</td>
        <td>2× SMA female connectors</td>
      </tr>
      <tr>
        <td>Included Antennas</td>
        <td>2× 3dBi dual-band antennas</td>
      </tr>
      <tr>
        <td>TX Power</td>
        <td>Up to 20dBm (adjustable in software)</td>
      </tr>
      <tr>
        <td>RX Sensitivity</td>
        <td>-98dBm (typical)</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Power & Battery</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Battery Type</td>
        <td>1200mAh 3.7V LiPo (user replaceable)</td>
      </tr>
      <tr>
        <td>Battery Runtime</td>
        <td>4-6 hours (typical usage)</td>
      </tr>
      <tr>
        <td>Charging Port</td>
        <td>USB Type-C</td>
      </tr>
      <tr>
        <td>Charging Input</td>
        <td>5V/1A</td>
      </tr>
      <tr>
        <td>Charging Time</td>
        <td>Approximately 2-3 hours</td>
      </tr>
      <tr>
        <td>Power Management</td>
        <td>Integrated charge controller with overcharge protection</td>
      </tr>
      <tr>
        <td>Power Modes</td>
        <td>Active, Sleep, Deep Sleep</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Physical Specifications</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Dimensions</td>
        <td>80mm × 50mm × 15mm (without antennas)</td>
      </tr>
      <tr>
        <td>Weight</td>
        <td>60g (with battery, without antennas)</td>
      </tr>
      <tr>
        <td>Case Material</td>
        <td>ABS plastic (main unit)</td>
      </tr>
      <tr>
        <td>Operating Temperature</td>
        <td>0°C to 40°C (32°F to 104°F)</td>
      </tr>
      <tr>
        <td>Storage Temperature</td>
        <td>-20°C to 60°C (-4°F to 140°F)</td>
      </tr>
      <tr>
        <td>Humidity Range</td>
        <td>10% to 90% non-condensing</td>
      </tr>
      <tr>
        <td>Buttons</td>
        <td>Power button, Reset button</td>
      </tr>
      <tr>
        <td>LED Indicators</td>
        <td>Power LED, Status LED, Charging LED</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Interfaces & Expansion</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>USB Port</td>
        <td>USB Type-C (for charging and programming)</td>
      </tr>
      <tr>
        <td>Serial Interface</td>
        <td>UART via USB</td>
      </tr>
      <tr>
        <td>Expansion Headers</td>
        <td>2.54mm pitch GPIO headers (unpopulated)</td>
      </tr>
      <tr>
        <td>Debug Interface</td>
        <td>JTAG (via test points)</td>
      </tr>
    </tbody>
  </table>
</section>

<section class="fade-in">
  <h2 class="section-title">Software Specifications</h2>
  
  <h3>Firmware</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Operating System</td>
        <td>Custom RTOS-based firmware</td>
      </tr>
      <tr>
        <td>Current Version</td>
        <td>v1.2.5</td>
      </tr>
      <tr>
        <td>Update Method</td>
        <td>OTA (Over-The-Air) or USB</td>
      </tr>
      <tr>
        <td>Programming Languages</td>
        <td>C/C++, MicroPython support</td>
      </tr>
      <tr>
        <td>Open Source</td>
        <td>Yes, GitHub repository available</td>
      </tr>
      <tr>
        <td>License</td>
        <td>MIT License</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Web Interface</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Access Method</td>
        <td>Web browser via device IP (default: 192.168.4.1)</td>
      </tr>
      <tr>
        <td>Supported Browsers</td>
        <td>Chrome, Firefox, Safari, Edge (latest versions)</td>
      </tr>
      <tr>
        <td>Mobile Support</td>
        <td>Responsive design for smartphones and tablets</td>
      </tr>
      <tr>
        <td>Authentication</td>
        <td>Username/password (customizable)</td>
      </tr>
      <tr>
        <td>API Access</td>
        <td>RESTful API for automation</td>
      </tr>
    </tbody>
  </table>
  
  <h3>Software Features</h3>
  <table>
    <thead>
      <tr>
        <th>Feature</th>
        <th>Specification</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Network Scanning</td>
        <td>Active and passive scanning modes</td>
      </tr>
      <tr>
        <td>Client Detection</td>
        <td>Identify connected clients on networks</td>
      </tr>
      <tr>
        <td>Packet Capture</td>
        <td>PCAP format, filterable</td>
      </tr>
      <tr>
        <td>Traffic Analysis</td>
        <td>Real-time and historical data</td>
      </tr>
      <tr>
        <td>Deauthentication</td>
        <td>Targeted and broadcast modes</td>
      </tr>
      <tr>
        <td>Access Point Simulation</td>
        <td>Customizable SSID, security, and channel</td>
      </tr>
      <tr>
        <td>Logging</td>
        <td>Comprehensive event logging with export</td>
      </tr>
      <tr>
        <td>Scripting</td>
        <td>Custom script execution for automation</td>
      </tr>
    </tbody>
  </table>
</section>

<section class="fade-in">
  <h2 class="section-title">Performance Metrics</h2>
  
  <h3>WiFi Performance</h3>
  <table>
    <thead>
      <tr>
        <th>Metric</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Maximum Scan Range (Open Area)</td>
        <td>Up to 300m with standard antennas</td>
      </tr>
      <tr>
        <td>Maximum Scan Range (Indoor)</td>
        <td>Up to 50m with standard antennas</td>
      </tr>
      <tr>
        <td>Network Scan Time</td>
        <td>2-5 seconds (typical)</td>
      </tr>
      <tr>
        <td>Maximum Networks Displayed</td>
        <td>100 per scan</td>
      </tr>
      <tr>
        <td>Maximum Clients Tracked</td>
        <td>50 per network</td>
      </tr>
    </tbody>
  </table>
  
  <h3>System Performance</h3>
  <table>
    <thead>
      <tr>
        <th>Metric</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Boot Time</td>
        <td>10-15 seconds</td>
      </tr>
      <tr>
        <td>Web Interface Load Time</td>
        <td>1-2 seconds (typical)</td>
      </tr>
      <tr>
        <td>Maximum Log Size</td>
        <td>10MB (circular buffer)</td>
      </tr>
      <tr>
        <td>Firmware Update Time</td>
        <td>30-60 seconds</td>
      </tr>
    </tbody>
  </table>
</section>

<section class="fade-in">
  <h2 class="section-title">Certifications & Compliance</h2>
  
  <div class="faq-item">
    <p class="faq-question">Regulatory Compliance</p>
    <div class="faq-answer">
      <p>Black Hole V1.0 is designed for educational and research purposes. Users are responsible for ensuring compliance with local laws and regulations regarding WiFi devices and radio frequency transmissions. The device has the following certifications:</p>
      <ul>
        <li>FCC Part 15 Compliance (USA)</li>
        <li>CE Marking (European Union)</li>
        <li>RoHS Compliance</li>
        <li>WEEE Registered</li>
      </ul>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Usage Restrictions</p>
    <div class="faq-answer">
      <p>This device is intended for:</p>
      <ul>
        <li>Educational demonstrations</li>
        <li>Security research</li>
        <li>Testing of networks you own or have explicit permission to test</li>
      </ul>
      <p>This device is <strong>not</strong> intended for:</p>
      <ul>
        <li>Unauthorized network disruption</li>
        <li>Accessing networks without permission</li>
        <li>Any illegal activities</li>
      </ul>
      <p>Always consult local laws and regulations before using this device.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Package Contents</h2>
  
  <ul>
    <li>Black Hole V1.0 main unit</li>
    <li>2× 3dBi dual-band SMA antennas</li>
    <li>USB-C charging cable (1m)</li>
    <li>Quick start guide</li>
    <li>Sticker pack</li>
  </ul>
</section>

<div class="btn-group mt-5 fade-in">
  <a href="{{ '/features' | relative_url }}" class="btn">Back to Features</a>
  <a href="{{ '/firmware' | relative_url }}" class="btn btn-secondary">Firmware & Software</a>
</div>
