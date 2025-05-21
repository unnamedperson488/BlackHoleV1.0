---
layout: default
title: Black Hole V1.0
---

<style>
  body {
    background-color: #0a0a0a;
    color: #d0f0ff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
  }

  nav {
    display: flex;
    justify-content: center;
    gap: 35px;
    padding: 18px 0;
    background-color: #111111dd;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 0 15px #00f0ff88;
  }

  nav a {
    color: #00ccff;
    text-decoration: none;
    font-weight: 700;
    font-size: 1.1rem;
    text-shadow:
      0 0 8px #00ccff,
      0 0 15px #00ccff,
      0 0 20px #00aacc,
      0 0 30px #00aacc88;
    transition: color 0.3s ease, text-shadow 0.3s ease;
    position: relative;
  }

  nav a::after {
    content: "";
    position: absolute;
    bottom: -6px;
    left: 0;
    width: 100%;
    height: 3px;
    background: #00ccff;
    opacity: 0;
    border-radius: 2px;
    box-shadow: 0 0 8px #00ccff, 0 0 15px #00ccff;
    transition: opacity 0.3s ease;
  }

  nav a:hover {
    color: #00e5ff;
    text-shadow:
      0 0 12px #00e5ff,
      0 0 25px #00e5ff,
      0 0 40px #00cce5,
      0 0 50px #00cce5cc;
  }

  nav a:hover::after {
    opacity: 1;
  }

  .section {
    display: none;
    padding: 50px 15px;
    max-width: 900px;
    margin: 0 auto;
    animation: fadeIn 0.4s ease forwards;
  }

  .section.active {
    display: block;
  }

  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(10px);}
    to {opacity: 1; transform: translateY(0);}
  }

  .glow-title {
    color: #00bfff;
    font-size: 2.4rem;
    font-weight: 900;
    text-shadow:
      0 0 8px #00bfff,
      0 0 20px #00bfff,
      0 0 35px #0099cc,
      0 0 50px #0099cc;
    margin-bottom: 25px;
    user-select: none;
  }

  ul {
    line-height: 1.7;
    font-size: 1.15rem;
  }

  .video-link {
    display: inline-block;
    margin: 12px 20px 12px 0;
    padding: 8px 12px;
    background-color: #002233cc;
    border-radius: 7px;
    color: #00bfff;
    text-shadow:
      0 0 5px #00bfff,
      0 0 15px #00bfff;
    text-decoration: none;
    font-weight: 600;
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
  }

  .video-link:hover {
    background-color: #005577cc;
    box-shadow:
      0 0 10px #00bfff,
      0 0 25px #00bfff;
  }

  /* Footer */
  footer {
    text-align: center;
    padding: 18px 0;
    font-size: 0.9rem;
    color: #0077aa;
    text-shadow:
      0 0 5px #0077aa,
      0 0 10px #004466;
    user-select: none;
    background-color: #111111cc;
    margin-top: 50px;
  }

  /* Back to top button */
  #backToTop {
    position: fixed;
    bottom: 25px;
    right: 25px;
    background-color: #00bfffcc;
    color: #001f33;
    border: none;
    border-radius: 50%;
    width: 45px;
    height: 45px;
    font-size: 22px;
    cursor: pointer;
    box-shadow:
      0 0 12px #00bfff,
      0 0 25px #00bfff;
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 1100;
    transition: background-color 0.3s ease;
  }

  #backToTop:hover {
    background-color: #0099ccdd;
  }
</style>

<nav>
  <a href="#" onclick="showSection('home')">Home</a>
  <a href="#" onclick="showSection('product')">Product</a>
  <a href="#" onclick="showSection('about')">About</a>
  <a href="#" onclick="showSection('faq')">FAQ</a>
  <a href="#" onclick="showSection('media')">Media</a>
</nav>

<div id="home" class="section active">
  <h1 class="glow-title">Welcome to Black Hole V1.0</h1>
  <p>This is the main page of the site where you’ll find the latest updates and info.</p>
</div>

<div id="product" class="section">
  <h1 class="glow-title">Product Information</h1>
  <ul>
    <li><strong>Product:</strong> Black Hole V1.0</li>
    <li><strong>Features:</strong> Dual-band jamming, compact case, long battery life</li>
    <li><strong>Price:</strong> $140</li>
  </ul>
</div>

<div id="about" class="section">
  <h1 class="glow-title">About Me</h1>
  <p>I’m <strong>unnamedperson488</strong> — a professional hacker, builder, and creator of tech tools like Black Hole V1.0.</p>
</div>

<div id="faq" class="section">
  <h1 class="glow-title">Frequently Asked Questions</h1>
  <ul>
    <li><strong>Q:</strong> How do I use this device?<br><strong>A:</strong> A full guide is available in the documentation.</li>
    <li><strong>Q:</strong> Is it legal to use?<br><strong>A:</strong> Use responsibly. Follow your local laws.</li>
  </ul>
</div>

<div id="media" class="section">
  <h1 class="glow-title">Media & Links</h1>
  <p>Follow me on social media:</p>
  <ul>
    <li><a class="video-link" href="https://instagram.com/unnamedperson488" target="_blank" rel="noopener noreferrer">Instagram</a></li>
    <li><a class="video-link" href="https://tiktok.com/@unnamedperson488" target="_blank" rel="noopener noreferrer">TikTok</a></li>
    <li><a class="video-link" href="https://youtube.com/@unnamedperson488" target="_blank" rel="noopener noreferrer">YouTube</a></li>
  </ul>

  <h2 class="glow-title" style="margin-top: 30px;">Video Placeholders</h2>
  <a class="video-link" href="#" tabindex="0">Video Placeholder 1</a>
  <a class="video-link" href="#" tabindex="0">Video Placeholder 2</a>
  <a class="video-link" href="#" tabindex="0">Video Placeholder 3</a>
</div>

<footer>
  &copy; 2025 unnamedperson488 — All rights reserved
</footer>

<button id="backToTop" title="Back to Top" onclick="scrollToTop()">↑</button>

<script>
  function showSection(id) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    window.scrollTo(0, 0);
  }

  // Back to Top button logic
  const backToTopBtn = document.getElementById('backToTop');
  window.addEventListener('scroll', () => {
    if (window.pageYOffset > 200) {
      backToTopBtn.style.display = 'flex';
    } else {
      backToTopBtn.style.display = 'none';
    }
  });

  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>
