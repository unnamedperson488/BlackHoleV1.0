---
layout: none
title: Black Hole V1.0
---

<style>
  body {
    margin: 0;
    background-color: #0a0a0a;
    color: #e0e0e0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  .nav-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #111;
    position: sticky;
    top: 0;
    z-index: 1000;
    padding: 20px 0;
    box-shadow: 0 2px 10px #00f0ff44;
  }

  .nav-title {
    font-size: 2rem;
    color: #00f0ff;
    font-weight: bold;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    margin-bottom: 10px;
  }

  .nav-row {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
    margin: 5px 0;
  }

  nav a, nav span, .nav-row a {
    color: #00f0ff;
    text-decoration: none;
    font-weight: bold;
    padding: 8px 16px;
    border: 1px solid #00f0ff55;
    border-radius: 6px;
    text-shadow: 0 0 5px #00f0ff, 0 0 10px #00f0ff;
    background-color: #0c0c0c;
    transition: transform 0.2s, background-color 0.3s;
  }

  .nav-row a:hover {
    transform: scale(1.08);
    background-color: #111122;
  }

  .section {
    display: none;
    padding: 40px 20px;
    max-width: 900px;
    margin: 0 auto;
  }

  .section.active {
    display: block;
  }

  .glow-title {
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff, 0 0 15px #00f0ff;
    font-size: 2rem;
    margin-bottom: 20px;
    text-align: center;
  }

  .video-link {
    display: block;
    margin: 10px 0;
    color: #00f0ff;
    text-shadow: 0 0 5px #00f0ff;
    text-decoration: none;
  }

  .glow-block {
    border: 1px solid #00f0ff44;
    padding: 20px;
    margin-bottom: 20px;
    background-color: #111;
    box-shadow: 0 0 10px #00f0ff33;
    border-radius: 10px;
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
    font-size: 1.2rem;
  }

  ul {
    padding-left: 20px;
  }

  li {
    margin-bottom: 8px;
  }

  @media (max-width: 600px) {
    .nav-row {
      gap: 10px;
    }

    .nav-row a {
      padding: 6px 12px;
      font-size: 0.9rem;
    }
  }
</style>

<div class="nav-wrapper">
  <div class="nav-title">Black Hole V1.0</div>
  <div class="nav-row">
    <a href="#" onclick="showSection('home')">Home</a>
    <a href="#" onclick="showSection('product')">Product</a>
    <a href="#" onclick="showSection('media')">Media</a>
    <a href="#" onclick="showSection('demos')">Demos</a>
  </div>
  <div class="nav-row">
    <a href="#" onclick="showSection('about')">About</a>
    <a href="#" onclick="showSection('faq')">FAQ</a>
    <a href="#" onclick="showSection('firmware')">Firmware</a>
    <a href="#" onclick="showSection('timeline')">Timeline</a>
  </div>
</div>

<div class="section active" id="home">
  <div class="glow-title">Welcome to the Black Hole V1.0</div>
  <div class="glow-block">
    <p>The ultimate Dual-Band Deauther with powerful features and sleek design. Built for professionals, researchers, and cybersecurity enthusiasts.</p>
  </div>
</div>

<div class="section" id="product">
  <div class="glow-title">Product Overview</div>
  <div class="glow-block">
    <ul>
      <li>ESP32 + BW16 Dual Wi-Fi chip support (2.4GHz + 5GHz)</li>
      <li>LiPo charging support</li>
      <li>SMA connectors for external antennas</li>
      <li>Compact rectangular PCB with no OLED</li>
      <li>Custom reset and power buttons</li>
      <li>Black 4-layer PCB for signal integrity</li>
    </ul>
  </div>
</div>

<div class="section" id="media">
  <div class="glow-title">Media</div>
  <div class="glow-block">
    <a href="https://www.instagram.com/unnamedperson488" class="video-link">Instagram</a>
    <a href="https://github.com/unnamedperson488" class="video-link">GitHub</a>
    <a href="https://www.youtube.com/@unnamedperson488" class="video-link">YouTube</a>
    <a href="https://discord.gg/yourserver" class="video-link">Discord</a>
    <a href="https://www.tiktok.com/@unnamedperson488" class="video-link">TikTok</a>
  </div>
</div>

<div class="section" id="demos">
  <div class="glow-title">Demos</div>
  <div class="glow-block">
    <p>Coming soon: Live hacking demonstrations and setup guides for Black Hole V1.0.</p>
  </div>
</div>

<div class="section" id="about">
  <div class="glow-title">About</div>
  <div class="glow-block">
    <p>Black Hole V1.0 was engineered by unnamedperson to provide a sleek, powerful, and fully capable dual-band Wi-Fi auditing tool.</p>
  </div>
</div>

<div class="section" id="faq">
  <div class="glow-title">FAQ</div>
  <div class="glow-block">
    <ul>
      <li><strong>Is this legal?</strong> — Use only on networks you own or have permission to audit.</li>
      <li><strong>How do I update firmware?</strong> — Visit the Firmware tab for the flashing guide.</li>
      <li><strong>Where do I buy?</strong> — Currently sold directly through Discord DMs or custom storefront (coming soon).</li>
    </ul>
  </div>
</div>

<div class="section" id="firmware">
  <div class="glow-title">Firmware</div>
  <div class="glow-block">
    <p>To flash firmware onto Black Hole V1.0, follow our GitHub instructions:</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="video-link">Firmware Flash Guide</a>
  </div>
</div>

<div class="section" id="timeline">
  <div class="glow-title">Timeline</div>
  <div class="glow-block">
    <ul>
      <li>✅ April 2025 — Concept & PCB layout</li>
      <li>✅ May 2025 — Finalized testing + GitHub launch</li>
      <li>🔜 June 2025 — First batch shipped + documentation complete</li>
    </ul>
  </div>
</div>

<div class="discord-join">
  <a href="https://discord.gg/yourserver">Join Our Discord</a>
</div>

<script>
  function showSection(id) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }
</script>
