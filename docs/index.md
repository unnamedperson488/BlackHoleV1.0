---
layout: default
title: Black Hole V1.0
---
<style>
  body {
    background-color: #0d0d0d;
    color: #00f0ff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
  }
  nav {
    background-color: #001f33;
    display: flex;
    justify-content: center;
    padding: 15px 0;
    box-shadow: 0 0 10px #00f0ff;
  }
  nav a {
    color: #00f0ff;
    text-decoration: none;
    font-weight: bold;
    font-size: 18px;
    margin: 0 25px;
    padding: 8px 15px;
    border-radius: 8px;
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
  }
  nav a:hover {
    background-color: #00f0ff;
    color: #001f33;
    box-shadow: 0 0 15px #00f0ff;
  }
  h1, h2, h3 {
    text-align: center;
    color: #00f0ff;
    text-shadow:
      0 0 5px #00f0ff,
      0 0 10px #00f0ff,
      0 0 20px #00f0ff,
      0 0 40px #00f0ff;
  }
  main {
    padding: 30px 20px;
    max-width: 900px;
    margin: 0 auto;
  }
</style>

<nav>
  <a href="index.html">Home</a>
  <a href="video1.html">Video 1</a>
  <a href="video2.html">Video 2</a>
  <a href="video3.html">Video 3</a>
</nav>


<style>
/* Your CSS styles */
.navbar {
  background-color: #222;
  padding: 10px;
  display: flex;
  gap: 10px;
}
.nav-btn {
  background-color: #444;
  color: white;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  font-size: 16px;
}
.nav-btn:hover {
  background-color: #666;
}
.section {
  margin-top: 20px;
}
</style>

<div class="navbar">
  <button class="nav-btn" onclick="showSection('home')">Home</button>
  <button class="nav-btn" onclick="showSection('video1')">Video 1</button>
  <button class="nav-btn" onclick="showSection('video2')">Video 2</button>
  <button class="nav-btn" onclick="showSection('video3')">Video 3</button>
</div>

<div id="home" class="section">
  <h1>Welcome to Black Hole V1.0</h1>
  <p>This is the home screen.</p>
</div>

<div id="video1" class="section" style="display:none;">
  <h2>Video 1</h2>
  <video width="320" height="240" controls>
    <source src="path_to_video1.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<div id="video2" class="section" style="display:none;">
  <h2>Video 2</h2>
  <video width="320" height="240" controls>
    <source src="path_to_video2.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<div id="video3" class="section" style="display:none;">
  <h2>Video 3</h2>
  <video width="320" height="240" controls>
    <source src="path_to_video3.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

<script>
function showSection(sectionId) {
  const sections = document.querySelectorAll('.section');
  sections.forEach(section => {
    section.style.display = section.id === sectionId ? 'block' : 'none';
  });
}
</script>

<div class="nav-bar">
  <button class="nav-button" onclick="showSection('home')" aria-label="Home">
    🏠 Home
  </button>
  <button class="nav-button" onclick="showSection('media')" aria-label="Media">
    🎥 Media
  </button>
  <button class="nav-button" onclick="showSection('features')" aria-label="Features">
    ⚙️ Features
  </button>
  <button class="nav-button" onclick="showSection('faq')" aria-label="FAQ">
    ❓ FAQ
  </button>
</div>


<div id="home" class="section active-section">
  <h1 class="text-3xl font-bold text-center my-8">Welcome to Black Hole V1.0</h1>
  <p class="text-center max-w-2xl mx-auto">This device is a powerful dual-band Wi-Fi deauther designed for testing network security. Use the tabs above to explore media, features, and more.</p>
</div>

<div id="media" class="section">
  <h2 class="text-2xl font-bold text-center my-4">Media</h2>
  <div class="flex flex-col items-center gap-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID_1" frameborder="0" allowfullscreen></iframe>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID_2" frameborder="0" allowfullscreen></iframe>
  </div>
</div>

<div id="features" class="section">
  <h2 class="text-2xl font-bold text-center my-4">Features</h2>
  <ul class="max-w-md mx-auto list-disc list-inside">
    <li>Dual-band jamming (2.4GHz & 5GHz)</li>
    <li>External SMA antenna support</li>
    <li>On/Off boot button & reset switch</li>
    <li>LiPo battery charging</li>
  </ul>
</div>

<div id="faq" class="section">
  <h2 class="text-2xl font-bold text-center my-4">FAQ</h2>
  <div class="max-w-2xl mx-auto">
    <p class="mb-2"><strong>Is this device legal?</strong><br />This tool is meant for educational and testing purposes only. Do not use it on unauthorized networks.</p>
    <p class="mb-2"><strong>How do I charge it?</strong><br />It includes a built-in LiPo charging circuit. Use a USB cable to charge.</p>
  </div>
</div>

<script>
  function showSection(id) {
    document.querySelectorAll('.section').forEach(section => {
      section.classList.remove('active-section');
    });
    document.getElementById(id).classList.add('active-section');
  }
</script>
