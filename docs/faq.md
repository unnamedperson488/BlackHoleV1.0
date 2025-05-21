---
layout: default
title: Frequently Asked Questions
---

<div class="hero fade-in">
  <h1>Frequently Asked Questions</h1>
  <p>Find answers to common questions about the Black Hole V1.0 device.</p>
</div>

<section class="fade-in">
  <h2 class="section-title">General Questions</h2>
  
  <div class="faq-item">
    <p class="faq-question">What is Black Hole V1.0?</p>
    <div class="faq-answer">
      <p>Black Hole V1.0 is a dual-band WiFi security testing device designed for educational purposes. It allows security professionals, researchers, and enthusiasts to learn about WiFi security principles and test their own networks for vulnerabilities.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Is Black Hole legal to use?</p>
    <div class="faq-answer">
      <p>Black Hole is designed for educational and security testing purposes on networks you own or have explicit permission to test. Using it on networks without authorization may be illegal in your jurisdiction. Always check local laws and regulations before use.</p>
      <p>For more information, please refer to our <a href="{{ '/disclaimer' | relative_url }}">Legal Disclaimer</a>.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What's the difference between Black Hole and other WiFi testing devices?</p>
    <div class="faq-answer">
      <p>Black Hole V1.0 stands out with its dual-band capabilities (2.4GHz and 5GHz), powerful ESP32 + BW16 chipset combination, built-in battery with charging circuit, external SMA antennas for range flexibility, and user-friendly web interface. It's designed to be accessible for beginners while providing advanced features for experienced users.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Do I need technical knowledge to use Black Hole?</p>
    <div class="faq-answer">
      <p>Basic networking knowledge is helpful, but not required. Our comprehensive documentation, tutorials, and user-friendly interface make Black Hole accessible to beginners. More advanced features are available as you become more comfortable with the device.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Technical Questions</h2>
  
  <div class="faq-item" id="firmware-recovery">
    <p class="faq-question">How do I update the firmware?</p>
    <div class="faq-answer">
      <p>You can update the firmware through the web interface:</p>
      <ol>
        <li>Connect to your Black Hole device's WiFi network</li>
        <li>Open the web interface at <code>http://192.168.4.1</code></li>
        <li>Navigate to "Settings" > "Update Firmware"</li>
        <li>Either use "Online Update" to check for and install the latest version automatically, or use "Manual Update" to upload a firmware file you've downloaded</li>
      </ol>
      <p>For detailed instructions, see our <a href="{{ '/firmware' | relative_url }}">Firmware page</a>.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What's the battery life of Black Hole?</p>
    <div class="faq-answer">
      <p>The 1200mAh LiPo battery provides approximately 4-6 hours of typical usage. Battery life varies depending on the features being used:</p>
      <ul>
        <li>Passive scanning: 5-6 hours</li>
        <li>Active scanning: 4-5 hours</li>
        <li>Packet injection: 3-4 hours</li>
      </ul>
      <p>The device can also be used while charging via USB-C.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Can I replace the battery?</p>
    <div class="faq-answer">
      <p>Yes, the battery is user-replaceable. The device uses a standard 1200mAh 3.7V LiPo battery with JST connector. Replacement batteries are available in our <a href="{{ '/pricing' | relative_url }}">store</a>, or you can use any compatible battery.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What's the range of the device?</p>
    <div class="faq-answer">
      <p>With the standard 3dBi antennas, the typical range is:</p>
      <ul>
        <li>Open areas: Up to 300 meters</li>
        <li>Indoor environments: Up to 50 meters</li>
      </ul>
      <p>Range can be extended by using high-gain antennas, which are available as accessories.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Can I use Black Hole with external antennas?</p>
    <div class="faq-answer">
      <p>Yes, Black Hole features standard SMA connectors that are compatible with a wide range of antennas. You can use directional antennas for focused testing or high-gain omnidirectional antennas for extended range.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">How do I reset the device to factory settings?</p>
    <div class="faq-answer">
      <p>To perform a factory reset:</p>
      <ol>
        <li>Power on the device</li>
        <li>Press and hold the reset button for 10 seconds</li>
        <li>Release the button when the status LED starts blinking rapidly</li>
        <li>The device will restart with factory settings</li>
      </ol>
      <p>Note that this will erase all custom settings and configurations.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Software & Compatibility</h2>
  
  <div class="faq-item">
    <p class="faq-question">Which operating systems are compatible with Black Hole?</p>
    <div class="faq-answer">
      <p>Black Hole's web interface works with any device that has a modern web browser, including:</p>
      <ul>
        <li>Windows, macOS, and Linux computers</li>
        <li>Android and iOS smartphones and tablets</li>
        <li>Chromebooks and other Chrome OS devices</li>
      </ul>
      <p>For advanced features, we also offer dedicated applications for Windows, macOS, Linux, Android, and iOS.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Can I develop custom software for Black Hole?</p>
    <div class="faq-answer">
      <p>Yes, Black Hole has an open API that allows developers to create custom applications. We provide SDKs for Python, JavaScript, C++, and Java. For more information, see our <a href="{{ '/firmware' | relative_url }}#development-resources">Development Resources</a>.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Is the firmware open source?</p>
    <div class="faq-answer">
      <p>Yes, the core firmware is open source and available on our GitHub repository. This allows for community contributions, custom modifications, and transparency about the device's capabilities.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Can I run custom scripts on Black Hole?</p>
    <div class="faq-answer">
      <p>Yes, Black Hole supports custom scripts written in Lua or MicroPython. These can be uploaded through the web interface and scheduled to run automatically or triggered manually.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Ordering & Shipping</h2>
  
  <div class="faq-item">
    <p class="faq-question">Where can I buy Black Hole?</p>
    <div class="faq-answer">
      <p>Black Hole is available for purchase directly from our <a href="{{ '/pricing' | relative_url }}">website</a>. We also have select authorized resellers in various countries. Be cautious of unauthorized sellers, as they may not provide genuine products or warranty support.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Do you ship internationally?</p>
    <div class="faq-answer">
      <p>Yes, we ship to most countries worldwide. Shipping times and costs vary by location. Please note that customers are responsible for any import duties, taxes, or customs fees that may apply in their country.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What's included in the package?</p>
    <div class="faq-answer">
      <p>The standard package includes:</p>
      <ul>
        <li>Black Hole V1.0 main unit</li>
        <li>2× 3dBi dual-band SMA antennas</li>
        <li>USB-C charging cable (1m)</li>
        <li>Quick start guide</li>
        <li>Sticker pack</li>
      </ul>
      <p>The deluxe package includes additional items. See our <a href="{{ '/pricing' | relative_url }}">Pricing page</a> for details.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What is your warranty policy?</p>
    <div class="faq-answer">
      <p>Black Hole comes with a 1-year limited warranty covering manufacturing defects. This warranty does not cover damage from misuse, accidents, or unauthorized modifications. For warranty claims, please contact our support team with your order number and a description of the issue.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">What is your return policy?</p>
    <div class="faq-answer">
      <p>We accept returns within 30 days of delivery for a full refund of the product price (excluding shipping costs). The product must be in its original condition with all accessories and packaging. To initiate a return, please contact our support team.</p>
    </div>
  </div>
</section>

<section class="fade-in">
  <h2 class="section-title">Support & Community</h2>
  
  <div class="faq-item">
    <p class="faq-question">How can I get technical support?</p>
    <div class="faq-answer">
      <p>We offer several support options:</p>
      <ul>
        <li><a href="{{ '/contact' | relative_url }}">Contact form</a> on our website</li>
        <li>Email support at support@blackhole.com</li>
        <li>Community forums on our Discord server</li>
        <li>Comprehensive documentation on this website</li>
      </ul>
      <p>For enterprise customers, we offer priority support with dedicated account managers.</p>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Is there a community for Black Hole users?</p>
    <div class="faq-answer">
      <p>Yes, we have an active community on Discord where users share tips, tricks, and custom projects. We also maintain a subreddit and GitHub repositories where community members contribute to the development of the device.</p>
      <a href="https://discord.gg/" class="btn btn-secondary mt-2">Join Discord Community</a>
    </div>
  </div>
  
  <div class="faq-item">
    <p class="faq-question">Do you offer training or workshops?</p>
    <div class="faq-answer">
      <p>Yes, we offer online workshops and webinars for both beginners and advanced users. For educational institutions and enterprises, we can arrange custom training sessions. Check our social media channels for announcements about upcoming events.</p>
    </div>
  </div>
</section>

<div class="faq-item fade-in mt-5">
  <p class="faq-question">Still have questions?</p>
  <div class="faq-answer">
    <p>If you couldn't find the answer to your question, please don't hesitate to reach out to our support team. We're here to help!</p>
    <a href="{{ '/contact' | relative_url }}" class="btn mt-2">Contact Support</a>
  </div>
</div>
