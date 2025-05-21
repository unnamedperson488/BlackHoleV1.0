---
layout: default
title: Black Hole V1.0
---

<style>
  :root {
    --bg-dark: #0a0a1a;
    --text-light: #e0e0ff;
    --accent-neon: #39ff14;
    --accent-pink: #ff44cc;
    --section-bg: #12122f;
    --button-radius: 12px;
    --gap: 1.5rem;
    --font-retro: 'Courier New', Courier, monospace;
  }

  body {
    background-color: var(--bg-dark);
    color: var(--text-light);
    font-family: var(--font-retro);
    margin: 0;
    padding: 0 2rem;
  }

  h1, h2 {
    color: var(--accent-neon);
    text-shadow: 0 0 8px var(--accent-neon);
  }

  nav {
    margin-top: 1rem;
    display: flex;
    gap: 1rem;
    justify-content: center;
  }

  nav button {
    background-color: transparent;
    border: 2px solid var(--accent-pink);
    color: var(--accent-pink);
    padding: 0.6rem 1.4rem;
    font-weight: bold;
    border-radius: var(--button-radius);
    cursor: pointer;
    transition: background-color 0.3s ease, color 0.3s ease;
  }

  nav button.active,
  nav button:hover {
    background-color: var(--accent-pink);
    color: var(--bg-dark);
    box-shadow: 0 0 12px var(--accent-pink);
  }

  section.content-section {
    background-color: var(--section-bg);
    border-radius: var(--button-radius);
    padding: 2rem;
    margin-top: var(--gap);
    box-shadow: 0 0 20px var(--accent-neon);
    display: none;
  }

  section.content-section.active {
    display: block;
  }

  .image-placeholder {
    width: 100%;
    max-width: 400px;
    height: 250px;
    background: #222244;
    border: 2px dashed var(--accent-pink);
    border-radius: var(--button-radius);
    margin-top: 1rem;
    box-shadow: 0 0 10px var(--accent-pink);
  }

  p, ul, ol {
    line-height: 1.6;
  }

</style>

# 🌌 Black Hole V1.0

<nav>
  <button class="tab-btn active" data-target="home">Home</button>
  <button class="tab-btn" data-target="products">Products</button>
  <button class="tab-btn" data-target="social">Social</button>
  <button class="tab-btn" data-target="about">About</button>
</nav>

<section id="home" class="content-section active">
  <h2>Welcome</h2>
  <p>
    I’m <strong>unnamedperson488</strong> — a hacker, engineer, and reseller focused on building advanced DIY PCB projects and ChatGPT jailbreaks.
  </p>
  <p>All my projects and tools are paid products with professional support and quality assurance.</p>
  <div class="image-placeholder" aria-label="Home image placeholder"></div>
</section>

<section id="products" class="content-section">
  <h2>Products</h2>
  <p>Here you can find the products I currently offer:</p>
  
  <h3>Black Hole V1.0</h3>
  <div class="image-placeholder" aria-label="Black Hole V1.0 product image placeholder"></div>
  <ul>
    <li><strong>Type:</strong> Dual-band WiFi auditing tool</li>
    <li><strong>Features:</strong> 2.4GHz + 5GHz support, LiPo charging, dual SMA antennas</li>
    <li><strong>Price:</strong> $140</li>
    <li><strong>Production Time:</strong> Typically 5 days to build + 2 days shipping</li>
  </ul>
  <p>More products coming soon!</p>
</section>

<section id="social" class="content-section">
  <section style="background-color: #111; border: 1px solid #333; border-radius: 12px; padding: 1.5rem; margin-top: 2rem; box-shadow: 0 0 10px #ff00ff;">
  <h2 style="color: #ff00ff; font-size: 1.8rem; text-shadow: 0 0 6px #ff00ff;">📲 Social Media</h2>

  <!-- Instagram Section -->
  <div style="margin-top: 1.5rem;">
    <h3 style="color: #ff007f;">📸 Instagram Videos</h3>
    <ul style="list-style-type: none; padding-left: 0;">
      <li><a href="#" style="color: #ff007f; text-decoration: underline;">Instagram Video 1</a></li>
      <li><a href="#" style="color: #ff007f; text-decoration: underline;">Instagram Video 2</a></li>
      <li><a href="#" style="color: #ff007f; text-decoration: underline;">Instagram Video 3</a></li>
      <li><a href="#" style="color: #ff007f; text-decoration: underline;">Instagram Video 4</a></li>
      <li><a href="#" style="color: #ff007f; text-decoration: underline;">Instagram Video 5</a></li>
    </ul>
  </div>

  <!-- TikTok Section -->
  <div style="margin-top: 1.5rem;">
    <h3 style="color: #00f2ea;">🎵 TikTok Videos</h3>
    <ul style="list-style-type: none; padding-left: 0;">
      <li><a href="#" style="color: #00f2ea; text-decoration: underline;">TikTok Video 1</a></li>
      <li><a href="#" style="color: #00f2ea; text-decoration: underline;">TikTok Video 2</a></li>
      <li><a href="#" style="color: #00f2ea; text-decoration: underline;">TikTok Video 3</a></li>
      <li><a href="#" style="color: #00f2ea; text-decoration: underline;">TikTok Video 4</a></li>
      <li><a href="#" style="color: #00f2ea; text-decoration: underline;">TikTok Video 5</a></li>
    </ul>
  </div>

  <!-- YouTube Section -->
  <div style="margin-top: 1.5rem;">
    <h3 style="color: #ff0000;">▶️ YouTube Videos</h3>
    <ul style="list-style-type: none; padding-left: 0;">
      <li><a href="#" style="color: #ff0000; text-decoration: underline;">YouTube Video 1</a></li>
      <li><a href="#" style="color: #ff0000; text-decoration: underline;">YouTube Video 2</a></li>
      <li><a href="#" style="color: #ff0000; text-decoration: underline;">YouTube Video 3</a></li>
      <li><a href="#" style="color: #ff0000; text-decoration: underline;">YouTube Video 4</a></li>
      <li><a href="#" style="color: #ff0000; text-decoration: underline;">YouTube Video 5</a></li>
    </ul>
  </div>
</section>


</section>

<section id="about" class="content-section">
  <section style="background-color: #111; border: 1px solid #333; border-radius: 12px; padding: 1.5rem; margin-top: 2rem; box-shadow: 0 0 10px #0ff;">
  <h2 style="color: #00ffff; font-size: 1.8rem; text-shadow: 0 0 6px #0ff;">👤 About Me</h2>

  <p style="color: #ccc; font-size: 1rem; line-height: 1.6;">
    Hey, I'm <strong style="color: #0ff;">unnamedperson488</strong> — a developer, ethical hacker, and builder of next-gen WiFi tech. I specialize in:
  </p>

  <ul style="color: #0ff; margin-top: 1rem; font-size: 1rem; line-height: 1.6;">
    <li>🛠️ Custom DIY PCB Projects</li>
    <li>🤖 ChatGPT Jailbreak Scripts</li>
    <li>📡 Wireless Auditing Tools</li>
    <li>💾 Firmware Engineering & Reverse Engineering</li>
    <li>🧩 Unique, limited-edition paid hardware releases</li>
  </ul>

  <p style="color: #ccc; margin-top: 1rem;">
    All of my work is highly specialized and <strong style="color: #0ff;">paid only</strong>. I build everything from scratch — no templates, no clones. Every product or script you get is engineered for performance, security, and stealth.
  </p>

  <div style="margin-top: 1rem;">
    <img src="/assets/images/about-placeholder.png" alt="Profile or setup image" style="width: 100%; border-radius: 10px; box-shadow: 0 0 15px #0ff4;">
  </div>
</section>

</section>

<script>
  // Simple tab functionality
  const tabs = document.querySelectorAll('.tab-btn');
  const sections = document.querySelectorAll('.content-section');

  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      tabs.forEach(btn => btn.classList.remove('active'));
      tab.classList.add('active');

      const target = tab.getAttribute('data-target');
      sections.forEach(sec => {
        if (sec.id === target) {
          sec.classList.add('active');
        } else {
          sec.classList.remove('active');
        }
      });
    });
  });
</script>
