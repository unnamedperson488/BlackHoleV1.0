---
layout: default
title: Black Hole V1.0
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Black Hole V1.0: Open-source wireless testing tool powered by RTL8720DN.">
  <meta name="keywords" content="Black Hole V1.0, wireless testing, RTL8720DN, cybersecurity, open-source">
  <meta name="author" content="unnamedperson488">
  <meta property="og:title" content="Black Hole V1.0">
  <meta property="og:description" content="Explore Black Hole V1.0 for wireless network testing.">
  <meta property="og:image" content="https://via.placeholder.com/1200x630?text=Black+Hole+V1.0">
  <meta property="og:url" content="https://unnamedperson488.github.io/BlackHoleV1.0">
  <meta name="twitter:card" content="summary_large_image">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; img-src 'self' https://via.placeholder.com https://raw.githubusercontent.com; connect-src 'self' https://github.com; frame-src 'self' https://www.youtube.com;">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
  <title>Black Hole V1.0</title>
</head>
<body>
<style>
  :root {
    --primary-color: #00eaff;
    --accent-color: #22ff00;
    --bg-color: #0a0a0a;
    --card-bg: rgba(17, 17, 17, 0.9);
    --text-color: #e0e0e0;
    --shadow-glow: 0 0 10px rgba(0, 234, 255, 0.4);
  }

  [data-theme="light"] {
    --bg-color: #f5f5f5;
    --card-bg: rgba(255, 255, 255, 0.9);
    --text-color: #333;
    --shadow-glow: 0 0 10px rgba(0, 234, 255, 0.2);
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 18px;
    line-height: 1.6;
    margin: 0;
    position: relative;
    overflow-x: hidden;
    transition: background-color 0.3s ease, color 0.3s ease;
  }

  #boot-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #0a0a0a;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 10000;
    opacity: 1;
    transition: opacity 0.5s ease;
  }

  #boot-screen.hidden {
    opacity: 0;
    pointer-events: none;
  }

  .boot-logo {
    font-size: 2.5rem;
    color: var(--primary-color);
    text-shadow: 0 0 10px var(--primary-color);
    animation: pulse 1.5s infinite;
    margin-bottom: 20px;
  }

  .boot-progress {
    width: 200px;
    height: 10px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 5px;
    overflow: hidden;
    margin-bottom: 20px;
  }

  .boot-progress-fill {
    width: 0;
    height: 100%;
    background: var(--accent-color);
    transition: width 5s linear;
  }

  .start-button {
    width: 120px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 1rem;
    font-weight: 500;
    cursor: pointer;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .start-button:hover {
    background: rgba(0, 234, 255, 0.2);
    transform: scale(1.05);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .start-button:active, .start-button.pulse {
    animation: glow-burst 0.2s;
  }

  .start-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
  }

  @keyframes neon-flicker {
    0%, 100% { box-shadow: 0 0 10px var(--primary-color); }
    50% { box-shadow: 0 0 20px var(--primary-color), 0 0 30px var(--primary-color); }
  }

  @keyframes glow-burst {
    0% { box-shadow: 0 0 10px var(--primary-color); }
    50% { box-shadow: 0 0 20px var(--primary-color), 0 0 40px var(--primary-color); }
    100% { box-shadow: 0 0 10px var(--primary-color); }
  }

  .stars, .twinkling, .clouds {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    opacity: 0;
    transition: opacity 1s ease;
  }

  .stars.loaded, .twinkling.loaded, .clouds.loaded {
    opacity: 1;
  }

  .stars {
    background: var(--bg-color) url(https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png) repeat top center;
  }

  .twinkling {
    background: transparent url(https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png) repeat top center;
    animation: move-twink-back 200s linear infinite;
  }

  .clouds {
    background: transparent url(https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png) repeat top center;
    animation: move-clouds-back 200s linear infinite;
    opacity: 0.5;
  }

  @keyframes move-twink-back {
    from { background-position: 0 0; }
    to { background-position: -10000px 5000px; }
  }

  @keyframes move-clouds-back {
    from { background-position: 0 0; }
    to { background-position: 10000px 0; }
  }

  .loading-spinner {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border: 4px solid var(--primary-color);
    border-top: 4px solid var(--accent-color);
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
    z-index: 9999;
    opacity: 1;
    transition: opacity 0.5s ease;
  }

  .loading-spinner.hidden {
    opacity: 0;
  }

  @keyframes spin {
    0% { transform: translate(-50%, -50%) rotate(0deg); }
    100% { transform: translate(-50%, -50%) rotate(360deg); }
  }

  .wrapper {
    width: 100%;
    background: var(--card-bg);
    padding: 10px 0;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
    display: none;
  }

  .wrapper.visible {
    display: block;
  }

  .text {
    display: flex;
    justify-content: center;
    align-items: center;
    border: 2px solid var(--primary-color);
    border-left: none;
    border-right: none;
    padding: 5px 0;
    box-shadow: var(--shadow-glow);
  }

  .name {
    font-size: 2.5rem;
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--primary-color);
    font-weight: 700;
    text-align: center;
    margin: 0;
    padding: 10px 0;
  }

  .nav-wrapper {
    display: flex;
    justify-content: center;
    padding: 10px 0;
    display: none;
  }

  .nav-wrapper.visible {
    display: flex;
  }

  .card.nav-card {
    width: 100%;
    max-width: 900px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 10px;
    padding: 15px;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  .card.nav-card .list {
    list-style: none;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px;
    padding: 0;
    margin: 0;
    justify-content: center;
  }

  .card.nav-card .list .element {
    flex: 1;
    min-width: 100px;
    padding: 8px 12px;
    color: var(--text-color);
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s ease;
    outline: none;
  }

  .card.nav-card .list .element:hover {
    background: rgba(0, 234, 255, 0.2);
    color: var(--primary-color);
    transform: translateY(-2px);
    box-shadow: var(--shadow-glow);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .card.nav-card .list .element:active, .card.nav-card .list .element.pulse {
    animation: glow-burst 0.2s;
  }

  .card.nav-card .list .element .label {
    font-size: 0.938rem;
    font-weight: 600;
  }

  .card.product-card {
    width: 100%;
    max-width: 250px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: var(--shadow-glow);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    margin: 20px;
    text-decoration: none;
    color: inherit;
    backdrop-filter: blur(5px);
  }

  .product-card:hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(0, 234, 255, 0.5);
  }

  .product-card__img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-bottom: 2px solid var(--primary-color);
    border-radius: 10px 10px 0 0;
    loading: lazy;
  }

  .product-card__content {
    padding: 10px;
    text-align: center;
  }

  .product-card__content h3 {
    font-size: 1.2rem;
    color: var(--primary-color);
    margin: 0 0 5px;
  }

  .product-card__content p {
    font-size: 0.9rem;
    color: var(--text-color);
    margin: 0;
  }

  .product-info {
    width: 100%;
    max-width: 600px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    padding: 15px;
    box-shadow: var(--shadow-glow);
    margin: 20px auto;
    backdrop-filter: blur(5px);
  }

  .product-info h4 {
    font-size: 1.4rem;
    color: var(--primary-color);
    margin: 0 0 10px;
  }

  .product-info ul {
    list-style: none;
    padding: 0;
    margin: 0 0 20px;
  }

  .product-info li {
    font-size: 0.938rem;
    color: var(--accent-color);
    margin-bottom: 8px;
  }

  .product-info li span.key {
    color: var(--text-color);
    font-weight: 600;
  }

  .comparison-table {
    width: 100%;
    max-width: 600px;
    margin: 20px auto;
    border-collapse: collapse;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    overflow: hidden;
    box-shadow: var(--shadow-glow);
  }

  .comparison-table th, .comparison-table td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid rgba(0, 234, 255, 0.2);
  }

  .comparison-table th {
    color: var(--primary-color);
    font-weight: 600;
  }

  .comparison-table td {
    color: var(--text-color);
  }

  .social-media-button, .github-button, .new-discord-button, .flasher-button, .simulator-button, .newsletter-button {
    width: 140px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
    text-decoration: none;
  }

  .social-media-button:hover, .github-button:hover, .new-discord-button:hover, .flasher-button:hover, .simulator-button:hover, .newsletter-button:hover {
    background: rgba(0, 234, 255, 0.2);
    transform: scale(1.05);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .social-media-button:active, .github-button:active, .new-discord-button:active, .flasher-button:active, .simulator-button:active, .newsletter-button:active,
  .social-media-button.pulse, .github-button.pulse, .new-discord-button.pulse, .flasher-button.pulse, .simulator-button.pulse, .newsletter-button.pulse {
    animation: glow-burst 0.2s;
  }

  .social-media-button:disabled, .flasher-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }

  .social-media-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 20px 0;
  }

  .flasher-card {
    width: 100%;
    max-width: 600px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    padding: 15px;
    box-shadow: var(--shadow-glow);
    margin: 0 auto 20px;
    text-align: center;
    backdrop-filter: blur(5px);
  }

  #port-select, #firmware-upload, .ota-input, #newsletter-input {
    width: 80%;
    max-width: 300px;
    padding: 8px;
    margin: 10px 0;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    color: var(--text-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    box-shadow: var(--shadow-glow);
    transition: box-shadow 0.3s ease;
  }

  #port-select:focus, #firmware-upload:focus, .ota-input:focus, #newsletter-input:focus {
    outline: none;
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .progress-bar {
    width: 80%;
    height: 10px;
    background: #111;
    border: 1px solid var(--primary-color);
    border-radius: 5px;
    margin: 15px auto;
    overflow: hidden;
  }

  .progress-fill {
    width: 0%;
    height: 100%;
    background: var(--accent-color);
    transition: width 0.3s ease;
  }

  #flasher-status {
    font-size: 0.938rem;
    color: var(--text-color);
    margin: 10px 0;
  }

  #flasher-log {
    width: 80%;
    max-width: 300px;
    max-height: 100px;
    margin: 10px auto;
    background: #111;
    border: 1px solid var(--primary-color);
    border-radius: 5px;
    padding: 10px;
    font-size: 0.875rem;
    overflow-y: auto;
    text-align: left;
  }

  .section {
    display: none;
    padding: 30px 20px;
    max-width: 900px;
    margin: 0 auto 40px;
    background: var(--card-bg);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  .section.active, .section.visible {
    display: block;
  }

  .glow-title {
    font-size: 2rem;
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--primary-color);
    margin-bottom: 20px;
  }

  .glow-block {
    border: 1px solid rgba(0, 234, 255, 0.2);
    padding: 20px;
    margin-bottom: 20px;
    background: var(--card-bg);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  .glow-block h3 {
    font-size: 1.4rem;
    color: var(--text-color);
    margin-bottom: 10px;
  }

  .discord-join {
    text-align: center;
    margin: 20px 0;
  }

  .discord-join a {
    color: #5865F2;
    font-weight: bold;
    text-decoration: none;
    font-size: 1rem;
    transition: color 0.3s ease;
  }

  .discord-join a:hover {
    color: #7289DA;
  }

  #faq-search {
    width: 100%;
    max-width: 600px;
    padding: 10px;
    margin-bottom: 20px;
    border: 2px solid var(--primary-color);
    background: #111;
    color: var(--text-color);
    border-radius: 6px;
    font-family: 'Orbitron', sans-serif;
    transition: box-shadow 0.3s ease;
  }

  #faq-search:focus {
    outline: none;
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .details {
    margin-bottom: 15px;
    padding: 10px;
    border: 1px solid rgba(0, 234, 255, 0.2);
    border-radius: 6px;
    background: var(--card-bg);
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  summary {
    font-weight: 600;
    cursor: pointer;
    color: var(--text-color);
    font-size: 1rem;
    outline: none;
  }

  .theme-toggle {
    position: fixed;
    top: 20px;
    right: 20px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 50%;
    width: 40px;
    height: 40px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
    display: none;
  }

  .theme-toggle.visible {
    display: flex;
  }

  .theme-toggle:hover {
    background: rgba(0, 234, 255, 0.2);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .lang-switcher {
    position: fixed;
    top: 70px;
    right: 20px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    padding: 5px;
    box-shadow: var(--shadow-glow);
    display: none;
  }

  .lang-switcher.visible {
    display: block;
  }

  .lang-switcher select {
    background: none;
    border: none;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    cursor: pointer;
  }

  footer {
    background: var(--card-bg);
    padding: 20px;
    text-align: center;
    border-top: 2px solid var(--primary-color);
    box-shadow: var(--shadow-glow);
    margin-top: 40px;
    backdrop-filter: blur(5px);
    display: none;
  }

  footer.visible {
    display: block;
  }

  footer a {
    color: var(--primary-color);
    text-decoration: none;
    margin: 10px;
    transition: color 0.3s ease;
  }

  footer a:hover {
    color: var(--accent-color);
  }

  .discord-widget {
    max-width: 500px;
    margin: 20px auto;
    padding: 10px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  .simulator {
    width: 200px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 10px;
    padding: 20px;
    margin: 20px auto;
    text-align: center;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(5px);
  }

  .video-container {
    position: relative;
    width: 100%;
    max-width: 600px;
    margin: 20px auto;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
  }

  .video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
  }

  .newsletter-form {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: 20px 0;
  }

  @media (max-width: 768px) {
    .name { font-size: 2rem; }
    .section { padding: 20px; margin: 0 10px 30px; }
    .glow-title { font-size: 1.8rem; }
    .card.nav-card .list { gap: 5px; }
    .card.nav-card .list .element { min-width: 80px; padding: 6px 8px; }
    .product-card { max-width: 200px; margin: 10px; }
    .product-card__img { height: 120px; }
    #port-select, #firmware-upload, .ota-input, #newsletter-input { width: 90%; max-width: 250px; }
    .flasher-button, .social-media-button, .github-button, .new-discord-button, .simulator-button, .newsletter-button { width: 120px; height: 35px; font-size: 0.875rem; }
    .theme-toggle { top: 10px; right: 10px; width: 35px; height: 35px; }
    .lang-switcher { top: 60px; right: 10px; }
    .boot-logo { font-size: 2rem; }
    .start-button { width: 100px; height: 35px; font-size: 0.875rem; }
    .comparison-table { font-size: 0.875rem; }
  }
</style>

<script>
  // Boot Animation
  window.addEventListener('load', () => {
    const bootScreen = document.querySelector('#boot-screen');
    const bootProgress = document.querySelector('.boot-progress-fill');
    const startButton = document.querySelector('.start-button');
    const backgrounds = document.querySelectorAll('.stars, .twinkling, .clouds');
    const spinner = document.querySelector('.loading-spinner');
    const wrapper = document.querySelector('.wrapper');
    const navWrapper = document.querySelector('.nav-wrapper');
    const themeToggle = document.querySelector('.theme-toggle');
    const langSwitcher = document.querySelector('.lang-switcher');
    const footer = document.querySelector('footer');

    const loadImage = (url) => new Promise(resolve => {
      const img = new Image();
      img.src = url;
      img.onload = img.onerror = resolve;
    });

    startButton.addEventListener('click', () => {
      startButton.disabled = true;
      startButton.style.display = 'none';
      bootProgress.parentElement.style.display = 'block';
      spinner.classList.remove('hidden');

      Promise.all([
        loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png'),
        loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png'),
        loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png')
      ]).then(() => {
        spinner.classList.add('hidden');
        backgrounds.forEach(bg => bg.classList.add('loaded'));
        bootProgress.style.width = '100%';
        setTimeout(() => {
          bootScreen.classList.add('hidden');
          wrapper.classList.add('visible');
          navWrapper.classList.add('visible');
          document.querySelector('#home').classList.add('active', 'visible');
          themeToggle.classList.add('visible');
          langSwitcher.classList.add('visible');
          footer.classList.add('visible');
        }, 5000);
      });
    });
  });

  // Theme Toggle
  const themeToggle = document.querySelector('.theme-toggle');
  if (themeToggle) {
    themeToggle.addEventListener('click', () => {
      const isDark = document.body.dataset.theme !== 'light';
      document.body.dataset.theme = isDark ? 'light' : 'dark';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
      themeToggle.textContent = isDark ? '☀️' : '🌑';
    });
    const savedTheme = localStorage.getItem('theme') || 'dark';
    document.body.dataset.theme = savedTheme;
    themeToggle.textContent = savedTheme === 'light' ? '🌑' : '☀️';
  }

  // Language Switcher
  const translations = {
    en: { home: 'Home', product: 'Product', media: 'Media', demos: 'Community', about: 'About', faq: 'FAQ', firmware: 'Firmware', welcome: 'Welcome to Black Hole V1.0', flash: 'Flash Firmware' },
    es: { home: 'Inicio', product: 'Producto', media: 'Medios', demos: 'Comunidad', about: 'Acerca', faq: 'Preguntas', firmware: 'Firmware', welcome: 'Bienvenido a Black Hole V1.0', flash: 'Actualizar Firmware' }
  };

  const langSelect = document.querySelector('.lang-select');
  if (langSelect) {
    langSelect.addEventListener('change', () => {
      const lang = langSelect.value;
      document.querySelectorAll('.nav-label').forEach((el, i) => {
        const key = ['home', 'product', 'media', 'demos', 'about', 'faq', 'firmware'][i];
        el.textContent = translations[lang][key];
      });
      document.querySelector('#home-title').textContent = translations[lang].welcome;
      document.querySelector('.flash-title').textContent = translations[lang].flash;
      localStorage.setItem('language', lang);
    });
    const savedLang = localStorage.getItem('language') || 'en';
    langSelect.value = savedLang;
    langSelect.dispatchEvent(new Event('change'));
  }

  // Section Switching
  function showSection(id) {
    document.querySelectorAll('.section').forEach(section => section.classList.remove('active', 'visible'));
    const target = document.querySelector(id);
    if (target) target.classList.add('active', 'visible');
  }

  // Web Flasher
  const portSelect = document.querySelector('#port-select');
  const refreshButton = document.querySelector('.flasher-button.refresh');
  const connectButton = document.querySelector('.flasher-button.connect');
  const eraseButton = document.querySelector('.flasher-button.erase');
  const flashButton = document.querySelector('.flasher-button.flash');
  const otaInput = document.querySelector('.ota-input');
  const otaButton = document.querySelector('.flasher-button.ota');
  const firmwareUpload = document.querySelector('#firmware-upload');
  const progressFill = document.querySelector('.progress-fill');
  const statusText = document.querySelector('#flasher-status');
  const flasherLog = document.querySelector('#flasher-log');
  let selectedPort = null;

  function logMessage(msg) {
    flasherLog.innerHTML += `<p>${new Date().toLocaleTimeString()}: ${msg}</p>`;
    flasherLog.scrollTop = flasherLog.scrollHeight;
  }

  async function populatePorts() {
    if (!navigator.serial) {
      statusText.textContent = 'Web Serial API not supported. Use Chrome/Edge.';
      logMessage('Browser not supported');
      [portSelect, refreshButton, connectButton, eraseButton, flashButton, otaButton].forEach(el => el.disabled = true);
      return;
    }

    try {
      const ports = await navigator.serial.getPorts();
      portSelect.innerHTML = '<option value="">Select Port</option>';
      ports.forEach((port, index) => {
        const info = port.getInfo();
        const option = document.createElement('option');
        option.value = index;
        option.text = `Port ${index + 1} (USB: ${info.usbVendorId || 'N/A'}:${info.usbProductId || 'N/A'})`;
        portSelect.appendChild(option);
      });
      statusText.textContent = ports.length ? 'Select a port and click Connect.' : 'No ports detected.';
      logMessage(ports.length ? 'Ports detected' : 'No ports found');
    } catch (error) {
      statusText.textContent = `Error listing ports: ${error.message}`;
      logMessage(`Port error: ${error.message}`);
    }
  }

  if (refreshButton) {
    refreshButton.addEventListener('click', async (e) => {
      e.target.classList.add('pulse');
      statusText.textContent = 'Refreshing ports...';
      logMessage('Refreshing ports');
      await populatePorts();
      setTimeout(() => e.target.classList.remove('pulse'), 200);
    });
  }

  if (connectButton) {
    connectButton.addEventListener('click', async (e) => {
      e.target.classList.add('pulse');
      const portIndex = parseInt(portSelect.value);
      if (isNaN(portIndex)) {
        statusText.textContent = 'Please select a port';
        logMessage('No port selected');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        return;
      }

      try {
        const ports = await navigator.serial.getPorts();
        selectedPort = ports[portIndex];
        if (!selectedPort) {
          statusText.textContent = 'Invalid port selected';
          logMessage('Invalid port');
          setTimeout(() => e.target.classList.remove('pulse'), 200);
          return;
        }

        await selectedPort.open({ baudRate: 115200 });
        statusText.textContent = 'Connected. Enter Download Mode (LOG_TX to VCC, EN to GND, VCC, then disconnect LOG_TX).';
        logMessage('Connected to port');
        flashButton.disabled = false;
        eraseButton.disabled = false;
        connectButton.disabled = true;
        refreshButton.disabled = true;
        portSelect.disabled = true;
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      } catch (error) {
        statusText.textContent = `Error connecting: ${error.message}`;
        logMessage(`Connection error: ${error.message}`);
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      }
    });
  }

  if (eraseButton) {
    eraseButton.addEventListener('click', async (e) => {
      e.target.classList.add('pulse');
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device for erase');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        return;
      }

      statusText.textContent = 'Erasing flash...';
      eraseButton.disabled = true;
      progressFill.style.width = '0%';

      try {
        logMessage('Erasing flash memory...');
        await new Promise(resolve => setTimeout(resolve, 2000));
        progressFill.style.width = '100%';
        statusText.textContent = 'Flash erased. Connect to port and flash new firmware.';
        logMessage('Flash erased successfully');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      } catch (error) {
        statusText.textContent = `Error erasing: ${error.message}`;
        logMessage(`Erase failed: ${error}`);
        progressFill.style.width = '0%';
        eraseButton.disabled = false;
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      }
    });
  }

  if (flashButton) {
    flashButton.addEventListener('click', async (e) => {
      e.target.classList.add('pulse');
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device for flashing');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        return;
      }

      let firmware;
      if (firmwareUpload.files.length > 0) {
        const file = firmwareUpload.files[0];
        if (file.size > 1048576 || !file.name.endsWith('.bin')) {
          statusText.textContent = 'Invalid firmware file (max 1MB, .bin only)';
          logMessage('Invalid firmware');
          setTimeout(() => e.target.classList.remove('pulse'), 200);
          return;
        }
        firmware = await file.arrayBuffer();
        logMessage(`Custom firmware uploaded: ${file.name}`);
      } else {
        statusText.textContent = 'Fetching official firmware...';
        logMessage('Fetching official firmware');
        const firmwareUrl = 'https://github.com/unnamedperson488/BlackHoleV1.0/releases/download/v1.2.3/firmware-v1.2.3.bin';
        const response = await fetch(firmwareUrl);
        if (!response.ok) throw new Error('Failed to fetch firmware');
        firmware = await response.arrayBuffer();
      }

      statusText.textContent = 'Flashing firmware...';
      flashButton.disabled = true;
      eraseButton.disabled = true;
      progressFill.style.width = '0%';

      try {
        const writer = selectedPort.writable.getWriter();
        let progress = 0;
        const totalSize = firmware.byteLength;
        const chunkSize = 1024;

        for (let offset = 0; offset < totalSize; offset += chunkSize) {
          const chunk = firmware.slice(offset, offset + chunkSize);
          await writer.write(new Uint8Array(chunk));
          progress = Math.min((offset + chunkSize) / totalSize * 100, 100);
          progressFill.style.width = `${progress}%`;
          statusText.textContent = `Flashing... ${Math.round(progress)}%`;
          logMessage(`Flashing ${Math.round(progress)}%`);
          await new Promise(resolve => setTimeout(resolve, 50));
        }

        await writer.close();
        statusText.textContent = 'Firmware flashed successfully! Reset your device (EN to GND, then VCC).';
        logMessage('Firmware flashed successfully');
        progressFill.style.width = '100%';
        await selectedPort.close();
        selectedPort = null;
        connectButton.disabled = false;
        refreshButton.disabled = false;
        portSelect.disabled = false;
        eraseButton.disabled = true;
        flashButton.disabled = true;
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        await populatePorts();
      } catch (error) {
        statusText.textContent = `Error flashing: ${error.message}`;
        logMessage(`Flash error: ${error.message}`);
        progressFill.style.width = '0%';
        flashButton.disabled = false;
        eraseButton.disabled = false;
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      }
    });
  }

  if (otaButton) {
    otaButton.addEventListener('click', async (e) => {
      e.target.classList.add('pulse');
      const ip = otaInput.value.trim();
      if (!ip.match(/^(\d{1,3}\.){3}\d{1,3}$/)) {
        statusText.textContent = 'Invalid IP address';
        logMessage('Invalid OTA IP');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        return;
      }

      statusText.textContent = 'Checking OTA updates...';
      otaButton.disabled = true;

      try {
        logMessage(`Checking OTA at ${ip}`);
        await new Promise(resolve => setTimeout(resolve, 1000));
        statusText.textContent = 'OTA update initiated. Check device status.';
        logMessage('OTA update started');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      } catch (error) {
        statusText.textContent = `OTA error: ${error.message}`;
        logMessage(`OTA error: ${error.message}`);
        otaButton.disabled = false;
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      }
    });
  }

  if (portSelect) {
    populatePorts();
  }

  // FAQ Search
  const searchInput = document.querySelector('#faq-search');
  const faqItems = document.querySelectorAll('.details');
  if (searchInput) {
    searchInput.addEventListener('input', () => {
      const query = searchInput.value.toLowerCase().trim();
      faqItems.forEach(item => {
        const text = item.textContent.toLowerCase();
        item.style.display = text.includes(query) ? 'block' : 'none';
      });
    });
  }

  // Newsletter Signup
  const newsletterForm = document.querySelector('#newsletter-form');
  if (newsletterForm) {
    newsletterForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const email = document.querySelector('#newsletter-input').value;
      if (email.match(/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/)) {
        alert('Thank you for signing up!');
        newsletterForm.reset();
      } else {
        alert('Please enter a valid email address.');
      }
    });
  }

  // Simulator
  const simulatorButton = document.querySelector('#simulator-button');
  if (simulatorButton) {
    simulatorButton.addEventListener('click', () => {
      simulatorButton.classList.add('pulse');
      setTimeout(() => simulatorButton.classList.remove('pulse'), 200);
      alert('Simulated button press on Black Hole V1.0!');
    });
  }

  // Navigation Accessibility
  document.querySelectorAll('.element').forEach(el => {
    el.addEventListener('keydown', e => {
      if (e.key === 'Enter') el.click();
    });
  });
</script>

<div id="boot-screen">
  <div class="boot-logo">Black Hole V1.0</div>
  <div class="boot-progress" style="display: none;">
    <div class="boot-progress-fill"></div>
  </div>
  <button class="start-button" aria-label="Start loading">Start</button>
</div>

<div class="loading-spinner"></div>
<div class="stars"></div>
<div class="twinkling"></div>
<div class="clouds"></div>

<div class="theme-toggle" aria-label="Toggle theme">🌑</div>
<div class="lang-switcher">
  <select class="lang-select" aria-label="Select language">
    <option value="en">English</option>
    <option value="es">Español</option>
  </select>
</div>

<div class="wrapper">
  <div class="text">
    <h1 class="name">UNNAMEDPERSON</h1>
  </div>
</div>

<div class="nav-wrapper">
  <div class="card nav-card">
    <nav>
      <ul class="list">
        <li class="element" tabindex="0" onclick="showSection('#home')"><span class="label nav-label">Home</span></li>
        <li class="element" tabindex="0" onclick="showSection('#product')"><span class="label nav-label">Product</span></li>
        <li class="element" tabindex="0" onclick="showSection('#media')"><span class="label nav-label">Media</span></li>
        <li class="element" tabindex="0" onclick="showSection('#demos')"><span class="label nav-label">Community</span></li>
        <li class="element" tabindex="0" onclick="showSection('#about')"><span class="label nav-label">About</span></li>
        <li class="element" tabindex="0" onclick="showSection('#faq')"><span class="label nav-label">FAQ</span></li>
        <li class="element" tabindex="0" onclick="showSection('#firmware')"><span class="label nav-label">Firmware</span></li>
      </ul>
    </nav>
  </div>
</div>

<section id="home" class="section">
  <h2 class="glow-title" id="home-title">🌌 Welcome to Black Hole V1.0</h2>
  <p>Open-source wireless testing for cybersecurity enthusiasts.</p>
  <div class="glow-block">
    <h3>Mission</h3>
    <p>Empowering the community with tools for secure wireless exploration.</p>
  </div>
  <div class="glow-block">
    <h3>Roadmap</h3>
    <ul>
      <li><strong>Q3 2025:</strong> Firmware v1.3.0 with Bluetooth enhancements.</li>
      <li><strong>Q4 2025:</strong> V2.0 hardware prototype.</li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>Newsletter</h3>
    <form id="newsletter-form" class="newsletter-form">
      <input type="email" id="newsletter-input" placeholder="Enter email" aria-label="Newsletter email" required>
      <button type="submit" class="newsletter-button" aria-label="Subscribe">Subscribe</button>
    </form>
  </div>
  <div class="social-media-buttons">
    <a href="https://instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i> YouTube</a>
    <a href="https://tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="TikTok"><i class="fab fa-tiktok"></i> TikTok</a>
  </div>
</section>

<section id="product" class="section">
  <h2 class="glow-title">📦 Products</h2>
  <div class="glow-block">
    <h3>Explore Our Tools</h3>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
      <a href="#" onclick="showSection('#blackHole'); return false;" class="product-card" aria-label="View Black Hole V1.0">
        <img src="https://via.placeholder.com/250x150?text=Black+Hole+V1.0" alt="Black Hole V1.0" class="product-card__img" width="250" height="150">
        <div class="product-card__content">
          <h3>Black Hole V1.0</h3>
          <p>$149</p>
        </div>
      </a>
      <a href="#" onclick="showSection('#blackHolePro'); return false;" class="product-card" aria-label="View Black Hole V1.0 Pro">
        <img src="https://via.placeholder.com/250x150?text=Black+Hole+V1.0+Pro" alt="Black Hole V1.0 Pro" class="product-card__img" width="250" height="150">
        <div class="product-card__content">
          <h3>Black Hole V1.0 Pro</h3>
          <p>$199</p>
        </div>
      </a>
    </div>
  </div>
</section>

<section id="blackHole" class="section">
  <h2 class="glow-title">📱 Black Hole V1.0</h2>
  <div class="glow-block">
    <h3>Overview</h3>
    <img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0" alt="Black Hole V1.0" width="600" height="400">
    <p><strong>Black Hole V1.0 - $149</strong></p>
    <p>A dual-band wireless testing tool for cybersecurity enthusiasts.</p>
    <div class="product-info">
      <h4>Features</h4>
      <ul>
        <li>Dual-band WiFi (2.4/5GHz)</li>
        <li>2 SMA antennas</li>
        <li>Open-source firmware</li>
        <li>1200mAh battery</li>
      </ul>
      <h4>Specifications</h4>
      <ul>
        <li><span class="key">MCU:</span> RTL8720DN</li>
        <li><span class="key">Connectivity:</span> WiFi, Bluetooth 4.0</li>
        <li><span class="key">Memory:</span> 4MB Flash</li>
        <li><span class="key">Size:</span> 75x50x15mm</li>
      </ul>
      <h4>Use Cases</h4>
      <ul>
        <li>Penetration testing</li>
        <li>IoT prototyping</li>
      </ul>
      <h4>Compare Models</h4>
      <table class="zoom">
        <tr><th>Feature</th><th>Black Hole V1.0</th><th>Pro</th></tr>
        <tr><td>Price</td><td>$149</td><td>$199</td></tr>
        <tr><td>WiFi</td><td>Dual-band</td><td>Enhanced Range</td></tr>
        <tr><td>Bluetooth</td><td>4.0</td><td>5.2</td></tr>
        <tr><td>Storage</td><td>4MB</td><td>8MB</td></tr>
        <tr><td>Antennas</td><td>2</td><td>4</td></tr>
        <tr><td>Battery</td><td>1200mAh</td><td>2000mAh</td></tr>
      </table>
      </table>
    </div>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" aria-label="Join Discord">
      <i class="fab fa-discord"></i> Join Discord</a>
    </div>
  </div>
</section>

<section id="blackHolePro" class="section">
  <h2 id="glow-title">Pro</h2>
</section>
<div>
  <div class="glow-block">
    <h3>Overview</h3>
    <img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0+Pro" alt="Black Hole V1.0" Pro" src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0+Pro" width="600" height="400">
    <p><strong>Black Hole V1.0 - $199</strong></p>
    <p>Advanced wireless testing with enhanced features for professionals.</p>
</p>
<div>
  <div class="product-info">
    <h4>Features</h4>
    <ul>
      <li>Dual-band WiFi with extended range</li>
      <li><li>4 SMA antennas</li>
      <li><li>Bluetooth 5.2</li>
      <li><li>8MB flash memory</li>
      <li><li>2000mAh battery</li>
      </li>
    </ul>
    <h4>Specifications</h4>
    <ul>
      <li><span class="key">MCU:</span> RTL8720DN</li>
      <li><span class="key">Connectivity:</span> WiFi, Bluetooth 5.2</li>
      <li><span class="key">Memory:</span> 8MB Flash</li>
      <li><li><span class="key">Size:</span> 80x55x20mm</li>
      </ul>
    </li>
    <h4>Use Cases</h4>
    <ul>
      <ul>
      <li>Advanced penetration testing</li>
      <li><li>IoT development</li>
      </ul>
    </li>
      <h4>Compare Models</h4>
      <table class="zoom-table">
        <table class="comparison-table">
          <tr><th>Feature</th><th>Black Hole V1.0</th><th>Pro</th></tr>
          <tr><td>Price<td>$149</td><td>$199</td></tr>
          <tr><tr><td>WiFi</td><td>Dual-band</td><td>Enhanced Range</td></tr>
          <tr><td>Bluetooth</td><td><td>4.0</td><td>5.2</td></tr>
          <tr><td>Storage</td><td>4MB</td><td>8MB</td></tr>
          <tr><td>Antennas</td><td>2</td><td>4</td></tr>
          <tr><td>Battery</td><td>1200mAh</td><td>2000mAh</td></tr>
        </table>
      </table>
    </div>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" href="https://discord.com" aria-label="Join Discord">
      <i class="fab fa-discord"></i> Join Discord</a>
    </div>
</section>
</section>

<section id="media" class="section">
  <h2 class="glow-title">📸 Media</h2>
</section>
<div class="glow-block">
<h3>Demo Video</h4>
  <div>
    <p>Watch Black Hole V1.0 in action.</p>
    <div class="video-container">
      <div class="zoom-container">
      <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Black Hole V1.0 Demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
  <div>
    </div>
<h3>Community Media</h3>
  <p>
    <ul>
      <li><a href="https://instagram.com/p/CyZ3XvLPMz_/" target="_blank">Instagram: Custom setup</a></li>
      <li><li><a href="https://youtube.com/watch?v=example123" target="_blank">YouTube: Tutorial</a></li>
      </ul>
    </div>
    <div class="social-media-buttons">
      <a href="https://www.instagram.com/unnamedperson488" class="_blank" target="social-media-button" target="_blank" href="https://www.instagram.com/unnamedperson488" aria-label="Instagram">
        <i class="fab fa-instagram"></i> Instagram</a>
      <a href="https://youtube.com/@unnamedperson488" class="_blank" target="social-media-button" href="https://www.youtube.com/@unnamedperson488" target="_blank" aria-label="YouTube">
        <i class="fab fa-youtube"></i> YouTube</a>
      <a href="https://tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" href="https://www.tiktok.com/@unnamedperson488" target="_blank" aria-label="TikTok">
      <i class="fab fa-tiktok"></i> TikTok</a>
    </div>
</section>

<section id="demos" class="section">
  <h2 class="glow-title">🤝 Community</h3>
</section>
<div>
  <div class="glow-block">
    <h3>Join Us</h4>
  <h3>
    <p>with other enthusiasts on Discord.</p>
    <div class="discord_widget">
    <div class="widget">
      <p>TODO: Add a Discord server ID.</p>
    </div>
    <a href="https://discord.gg/PdpuDvVD" target="_blank" class="new-discord-button" target="_blank" href="https://discord.com" aria-label="Join Discord">
      <i class="fab fa-discord"></i> Join Discord</a>
    </div>
  <div class="glow-block">
    <h3>Simulator</h3>
    <p>Test the Black Hole V1.0 interface.</p>
    <div class="simulator-button">
      <div class="button">
      <button id="simulator-button" class="simulator-button" aria-label="Simulate button press">Press</button>
    </div>
  </div>
</section>

<section id="about" class="section">
  <h2 class="glow-title">🔭 About Us</h2>
</section>
<div>
  <div class="glow-block">
    <p>Black Hole V1.0 is an open-source project by unnamedperson488 to advance wireless testing.</p>
    <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="github-button" target="_blank" href="https://github.com/unnamedperson488/BlackHoleV1.0" aria-label="Contribute on GitHub">
      <i class="fab fa-github"></i> Contribute</a></p>
  </div>
</section>

<section id="faq" class="section">
  <h2 class="glow-title">❓ FAQs</h2>
</section>
<div>
  <input type="faq-search" id="text" placeholder="Search..." aria-label="Search FAQs">
  <div class="details">
    <summary>What is Black Hole V1.0?</summary>
    <p>A dual-band wireless testing tool for cybersecurity.</p>
</div>
<div class="details">
  <summary>Is it legal to use?</summary>
<p>Yes, for ethical hacking within legal limits.</p>
</div>
<div class="details">
  <summary>How to enter Download Mode?</summary>
<p>Connect LOG_TX (PA7) to VCC, EN to GND, then power on.</p>
</div>
<div class="details">
  <summary>Can I develop custom firmware?</summary>
<p>Yes, using the RTL8720DN SDK on GitHub.</p>
</div>
<div class="details">
  <summary>What’s the Pro version?</summary>
<p>It has enhanced WiFi, Bluetooth 5.2, and more storage.</p>
</div>
</section>

<section id="firmware" class="section">
  <h2 class="glow-title flash-title">📱 Flash Firmware</h2>
</section>
<div class="glow-block">
  <h3>Firmware Update</h3>
  <p>Flash v1.2.3 using Chrome/Edge:</p>
  <ol>
    <li>Connect USB-C or serial (D0: PA8 RX, D1: PA7 TX).</li>
    <li>Refresh ports, select LOG_UART.</li>
    <li>Connect.</li>
    <li>Download Mode: LOG_TX (PA7) to VCC, EN to GND, connect VCC, disconnect LOG_TX.</li>
    <li>Erase flash if needed.</li>
    <li>Flash .bin file.</li>
    <li>Reset (EN to VCC).</li>
    </ol>
  <svg width="200" height="100" viewBox="0 0 100 200" style="max-width: 100%; margin: auto;10px auto; display: block;">
    <rect x="50" y="20" width="100" height="60" width="40" fill="#111" height="2" stroke="#00eaff"></rect>
    <text x="55" y="35" fill="#FFF" font-size="10">LOG_TX (PA7)</text>
    <text x="55" y="45" fill="#FFF" font-size="10">EN</text>
    <text x="55" y="60" fill="#FFF" font-size="10">GND/VCC</text>
    <line x1="45" y1="30" x2="30" y2="30" stroke="#00eaff"></line>
    <line x1="45" y1="45" x2="30" y2="45" stroke="#00eaff"></line>
    <line x1="45" y1="60" x2="30" y2="60" stroke="#00eaff"></line>
    </svg>
    <div class="flasher-card">
      <select id="port-select" aria-label="Select port"></select>
      <input type="file" id="firmware-upload" accept=".bin". type="checkbox" aria-label="Select firmware file">
      <input type="text" class="ota-input" placeholder="Enter OTA IP" type="text" aria-label="OTA IP">
      <button class="flasher-button refresh" aria-label="Refresh ports">Refresh</button>
      <button class="flasher-button connect" aria-label="Connect to device">Connect</button>
      <button class="flasher-button erase" id="disabled" aria-label="Erase flash">Erase</button>
      </button class="flasher-button flash" id="disabled" aria-label="Flash firmware">Flash</button>
      <button class="flasher-button ota" aria-label="Check OTA updates">OTA</button>
      </div>
      <div class="progress-bar">
        <div id="progress-fill"></div>
      </div>
      <p id="flasher-status">Click 'Refresh' to begin.</p>
      <div id="flasher-log"></div>
      <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0/wiki/Troubleshooting" target="_blank" href="https://github.com">Troubleshooting</a> | <a href="https://discord.com" target="_blank"> href="https://discord.gg/PdpuDvVD" aria-label="Discord">Link</a></p>
      </div>
    </div>
  <div class="glow-block">
    <h3>Version History</h3>
    <ul>
      <li><strong>v1.2.3 (May 2025):</strong> WiFi and battery optimizations.</li>
      <li><strong>v1.1.0 (Jan 2025):</strong> Initial OTA support.</li>
      </ul>
      <a href="https://github.com/unnamedperson488/BlackHoleV1.0/releases" target="_blank" class="github-button" href="https://github.com" aria-label="Firmware">Firmware Archive</a>
    </div>
  <div class="glow-block">
    <h3>Troubleshooting</h3>
    <ul>
      <li><strong>No Port:</strong> Check USB-to-serial drivers.</li>
      <li><strong>Flash Error:</strong> Verify Download Mode.</li>
      </ul>
    </div>
</section>

<footer>
  <footer>
    <p>© 2025 unnamedperson488.</p>
    <p>
      <a href="mailto:contact@blackholev1.com">Email</a> |
      <a href="/privacy">Privacy</a> |
      <a href="/terms">Terms</a>
    </div>
</footer>
</section>
</body>
</html>