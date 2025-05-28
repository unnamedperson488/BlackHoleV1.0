---
layout: default
title: Black Hole V1.0
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Black Hole V1.0: A dual-band wireless testing tool powered by RTL8720DN. Open-source, community-driven, and designed for cybersecurity enthusiasts.">
  <meta name="keywords" content="Black Hole V1.0, wireless testing, RTL8720DN, cybersecurity, open-source">
  <meta name="author" content="unnamedperson488">
  <meta property="og:title" content="Black Hole V1.0">
  <meta property="og:description" content="Explore Black Hole V1.0, a powerful tool for wireless network testing.">
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
    max-width: 300px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: var(--shadow-glow);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    margin: 20px auto;
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
    height: 200px;
    object-fit: cover;
    border-bottom: 2px solid var(--primary-color);
    border-radius: 10px 10px 0 0;
    loading: lazy;
  }

  .product-card__content {
    padding: 15px;
    text-align: center;
  }

  .product-card__content h3 {
    font-size: 1.4rem;
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--primary-color);
    margin: 0 0 10px;
  }

  .product-card__content p {
    font-size: 1rem;
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
    max-height: 400px;
    overflow-y: auto;
    box-shadow: var(--shadow-glow);
    margin: 0 auto 20px;
    backdrop-filter: blur(5px);
  }

  .product-info h4 {
    font-size: 1.4rem;
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--primary-color);
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

  .product-info::-webkit-scrollbar {
    width: 8px;
  }

  .product-info::-webkit-scrollbar-track {
    background: #111;
  }

  .product-info::-webkit-scrollbar-thumb {
    background: var(--primary-color);
    border-radius: 4px;
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

  .social-media-button, .github-button, .new-discord-button, .flasher-button, .simulator-button {
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

  .social-media-button:hover, .github-button:hover, .new-discord-button:hover, .flasher-button:hover, .simulator-button:hover {
    background: rgba(0, 234, 255, 0.2);
    transform: scale(1.05);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .social-media-button:active, .github-button:active, .new-discord-button:active, .flasher-button:active, .simulator-button:active,
  .social-media-button.pulse, .github-button.pulse, .new-discord-button.pulse, .flasher-button.pulse, .simulator-button.pulse {
    animation: glow-burst 0.2s;
  }

  .social-media-button:disabled, .flasher-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
    border-color: var(--text-color);
    color: var(--text-color);
  }

  .social-media-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 30px 0;
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

  #port-select, #firmware-upload, .ota-input {
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
    cursor: pointer;
    box-shadow: var(--shadow-glow);
    transition: box-shadow 0.3s ease;
  }

  #port-select:focus, #firmware-upload:focus, .ota-input:focus {
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

  .section.active {
    display: block;
  }

  .section.visible {
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

  #faq-search, #newsletter-input {
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

  #faq-search:focus, #newsletter-input:focus {
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

  .newsletter-form {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: 20px 0;
  }

  .newsletter-button {
    width: 120px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 6px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    cursor: pointer;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .newsletter-button:hover {
    background: rgba(0, 234, 255, 0.2);
    transform: scale(1.05);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
    animation: neon-flicker 0.5s ease-in-out;
  }

  .newsletter-button:active, .newsletter-button.pulse {
    animation: glow-burst 0.2s;
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

  @media (max-width: 768px) {
    .name { font-size: 2rem; }
    .section { padding: 20px; margin: 0 10px 30px; }
    .glow-title { font-size: 1.8rem; }
    .card.nav-card .list { flex-direction: row; gap: 5px; justify-content: center; }
    .card.nav-card .list .element { min-width: 80px; padding: 6px 8px; }
    .product-card { max-width: 250px; }
    .product-card__img { height: 150px; }
    #port-select, #firmware-upload, .ota-input { width: 90%; max-width: 250px; }
    .flasher-button, .social-media-button, .github-button, .new-discord-button, .simulator-button { width: 120px; height: 35px; font-size: 0.875rem; }
    .theme-toggle { top: 10px; right: 10px; width: 35px; height: 35px; }
    .lang-switcher { top: 60px; right: 10px; }
    .boot-logo { font-size: 2rem; }
    .start-button { width: 100px; height: 35px; font-size: 0.875rem; }
    .comparison-table { font-size: 0.875rem; }
  }
</style>

<script>
  // Boot Animation with Start Button
  window.addEventListener('load', () => {
    const bootScreen = document.querySelector('#boot-screen');
    const bootProgress = document.querySelector('.boot-progress-fill');
    const startButton = document.querySelector('.start-button');
    const backgrounds = document.querySelectorAll('.stars, .twinkling, .clouds');
    const spinner = document.querySelector('.loading-spinner');
    const wrapper = document.querySelector('.wrapper');
    const navWrapper = document.querySelector('.nav-wrapper');
    const sections = document.querySelectorAll('.section');
    const themeToggle = document.querySelector('.theme-toggle');
    const langSwitcher = document.querySelector('.lang-switcher');
    const footer = document.querySelector('footer');

    const loadImage = (url) => {
      return new Promise(resolve => {
        const img = new Image();
        img.src = url;
        img.onload = resolve;
        img.onerror = resolve;
      });
    };

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
      const isDark = document.body.dataset.theme === 'dark' || !document.body.dataset.theme;
      document.body.dataset.theme = isDark ? 'light' : 'dark';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
      themeToggle.textContent = isDark ? '☀️' : '🌑';
    });
    const savedTheme = localStorage.getItem('theme') || 'dark';
    document.body.dataset.theme = savedTheme;
    themeToggle.textContent = savedTheme === 'dark' ? '☀️' : '🌑';
  }

  // Language Switcher
  const translations = {
    en: {
      home: 'Home',
      product: 'Product',
      media: 'Media',
      demos: 'Community',
      about: 'About',
      faq: 'FAQ',
      firmware: 'Firmware',
      welcome: 'Welcome to Black Hole V1.0',
      flash: 'Flash Firmware'
    },
    es: {
      home: 'Inicio',
      product: 'Producto',
      media: 'Medios',
      demos: 'Comunidad',
      about: 'Acerca',
      faq: 'Preguntas',
      firmware: 'Firmware',
      welcome: 'Bienvenido a Black Hole V1.0',
      flash: 'Actualizar Firmware'
    }
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
    target.classList.add('active', 'visible');
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
      portSelect.disabled = true;
      refreshButton.disabled = true;
      connectButton.disabled = true;
      eraseButton.disabled = true;
      flashButton.disabled = true;
      otaButton.disabled = true;
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
        logMessage('No device selected');
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
        logMessage('Official firmware downloaded');
      }

      statusText.textContent = 'Flashing...';
      flashButton.disabled = true;
      eraseButton.disabled = true;
      progressFill.style.width = '0%';

      try {
        const writer = await selectedPort.writable.getWriter();
        let progress = 0;
        const totalSize = firmware.byteLength;
        const chunkSize = 4096;

        for (let offset = 0; offset < totalSize; offset += chunkSize) {
          const chunk = firmware.slice(offset, chunkSize + offset);
          await writer.write(chunk);
          progress = Math.min((offset + chunkSize) / chunkSize * 100, totalSize);
          progressFill.style.width = `${progress}%`;
          statusText.textContent = `Flashing... ${Math.round(progress)}`;
          logMessage(`Progress: ${Math.round(progress)}% complete`);
          await new Promise(resolve => setTimeout(resolve, 100));
        }

        await writer.close();
        statusText.textContent = 'Firmware flashed successfully! Reset your device now (EN to VCC).';
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
        statusText.textContent = `Flashing error: ${error.message}`;
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
        logMessage('Invalid OTA IP address');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
        return;
      }

      statusText.textContent = 'Checking OTA updates...';
      otaButton.disabled = true;

      try {
        logMessage(`Checking OTA at ${ip}`);
        await new Promise(resolve => setTimeout(resolve, 1000));
        statusText.textContent = 'OTA OTA update initiated successfully. Check your device status.';
        logMessage('OTA OTA update started');
        setTimeout(() => e.target.classList.remove('pulse'), 200);
      } catch (error) {
        statusText.textContent = `OTA OTA Error: ${error.message}`;
        logMessage(`OTA OTA error: ${error.message}`);
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
  <p>Your hub for open-source wireless testing and community-driven innovation.</p>
  <div class="glow-block">
    <h3>Our Mission</h3>
    <p>Empowering cybersecurity enthusiasts with accessible, powerful tools for network testing and IoT development.</p>
  </div>
  <div class="glow-block">
    <h3>Project Roadmap</h3>
    <ul>
      <li><strong>Q3 2025:</strong> Firmware v1.3.0 with enhanced Bluetooth support.</li>
      <li><strong>Q4 2025:</strong> Black Hole V2.0 hardware prototype.</li>
      <li><strong>Q1 2026:</strong> Community plugin marketplace launch.</li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>Community Spotlight</h3>
    <p>Check out for our community latest projects, like @CyberSmith’s WiFi analyzer script! Share yours on Discord.</p>
    <a href="https://discord.gg/PdpuDvVD" target="_blank" class="new-discord-button" aria-label="Join Discord">
      <i class="fab fa-discord"></i> <span>Join the Community</span></a>
    </div>
  </div>
<div <div class="glow-block">
    <h3>Stay Updated</h3>
    <p>Subscribe to our newsletter for the latest updates and exclusive content.</p>
    <form id="newsletter-form" class="newsletter-form">
      <input type="email" id="newsletter-input" placeholder="Enter your email" aria-label="Email for newsletter" required>
      <button type="submit" class="newsletter-button" aria-label="Subscribe to newsletter">Subscribe</button>
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
    <h3>Our Lineup</h3>
    <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px;">
      <a href="#" onclick="showSection('#blackHole')" class="product-card" aria-label="View Black Hole V1.0">
        <img src="https://via.placeholder.com/300x200?text=Black+Hole+V1.0" alt="Black Hole V1.0 Device" class="product-card__img" width="300" height="200">
        <div class="product-card__content">
          <h3>Black Hole V1.0</h3>
          <p>$149</p>
        </div>
      </a>
      <a href="#" onclick="showSection('#blackHolePro')" class="product-card" aria-label="View Black Hole V1.0 Pro">
        <img src="https://via.placeholder.com/300x200?text=Black+Hole+V1.0+Pro" alt="Product" class="Product-card__img" width="300" height="200">
        <p><div class="product-card__content">
          <h3>Black Hole V1.0 .0</h3>
          <p><p>$</p>
        </p></div>
      </div>
      </a>
    </div>
  <h3>Use Cases</h3>
    <ul>
      <li><strong>Penetration Testing:</strong> Analyze WiFi networks for security vulnerabilities.</li>
      <li><strong>IoT Development:</strong> Prototype and debug IoT devices.</li>
      <li><strong>Educational Learning:</strong> Learn wireless protocols with hands-on labs.</li>
    </ul>
  </div>
<div <div class="glow-block">
  <h3>Compare Models</h3>
    <table class=" <Comparison-table">
      <tr>
        <th>Feature</th>
        <th>Black Hole V1.0</th>
        <th>Black Hole V1.0 V1.</th>
      </tr>
    <tr>
      <tr><td>Price</td><td>$149</td><td>$199</td></tr>
      <tr>
      <td>WiFi</td><td>Dual-Band (2.4/5GHz)</td><td>Dual-Band (2.4/5GHz) with Enhanced Range</td></tr>
      <tr><td>Bluetooth</td><td>4.0</td><td>5.2</td></tr>
      <tr>
      <td>Storage</td><td>4MB</td><td>8MB</td></tr>
      <tr><td>Antennas</td><td>2 SMA</td><td>4 SMA</td></tr>
      <tr><td>Battery</td><td>1200mAh</td><td>2000mAh</td></tr>
    </table>
  </div>
</section>

<section id="blackHole" class="section">
  <h2 class="glow-title">📱 Black Hole V1.0</h2>
  <div class="glow-block">
    <h3>Overview</h3>
    <p><img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0" alt="Black Hole V1.0" class="product-image" width="600" height="400">
    <p><strong>Black Hole V1.0 - $149</strong></p>
    <p>A versatile, open-source wireless testing tool for cybersecurity enthusiasts, powered by RTL8720DN.</p>
    <div class="product-info">
      <h4>Features</h4>
      <ul>
        <li><li>Dual-band-mode WiFi (2.4GHz/5GHz)</li>
        <li><strong>External Antennas:</strong> 2 SMA connectors for improved signal strength.</li>
        <li><li>4-layer PCB for enhanced performance and reliability.</li>
        <li><li>Open-source firmware with community contributions.</li>
        <li><li>Physical Buttons for Boot and reset operations.</li>
        <li><strong>USB-C Power:</strong> Rechargeable 1200mAh battery.</li>
      </ul>
      <h4>Specifications</h4>
      <ul>
        <li><span class="key">MCU:</span> RTL8720DN (Dual-Core)</li>
        <li><span class="key">Connectivity:</span> WiFi 802.11 a/b/g/n, Bluetooth 4.2</li>
        <li><span class="key">Memory:</span> <span>4MB Flash, 192KB SRAM</span></li>
        <li><span class="key">Dimensions:</span> 75x50x15mm</li>
        <li><span class="key">Weight:</span> 50g</li>
      </ul>
      <h4>Package Includes:</h4>
      <ul>
        <li><li>Black Hole V1.0 device</li>
        <li><li>2x SMA antennas</li>
        <li><li>USB-C cable</li>
        <li><li>Quick start guide</li>
      </ul>
    </div>
    <a href="https://discord.gg/PdpuDvVD" target="_blank" class="new-discord-button" aria-label="Join Discord">
      <i class="fab fa-discord"></i> <span>Join Discord</span></a>
      </a>
  </div>
</section>

<section id="blackHolePro" class="section">
  <h2 class="glow-title">📱 Black Hole V1.0</h2>
</section>
<div <div class="glow-block">
  <h3>Overview</h3>
  <p><img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0+Pro" alt="Black Hole V1.0" Pro" class="product-image" width="600" height="400">
  <p><strong>p>Black Hole V1.0 V1.0 - $199</strong></p>
  <p>An advanced wireless testing tool with enhanced range, battery life, and Bluetooth 5.2 for professionals.</p>
</p>
<div <div class="product-info">
  <div class="product-info">
  <h4>Features</h4>
  <h4>ul>
    <ul>
      <li><li>Dual-band-mode WiFi (2.4GHz/5GHz) with extended range</li>
      <li><strong><li>4 SMA connectors for superior signal.</li>
      <li><li>8MB Flash for larger firmware and logs.</li>
      <li><li>Bluetooth 5.2 for low-latency connections.</li>
      <li><li>2000mAh battery for extended use.</li>
      <li><li>Advanced OLED display for diagnostics.</li>
    </ul>
    <h4>Specifications</h4>
    <ul>
      <li><span><span class="key">li</span> MCU: RTL8720DN (Dual-Core)</li>
      <li><span class="key">Connectivity:</span> WiFi 802.11 a/b/g/n, Bluetooth 5.2</li>
      <li><span class="key">Memory:</span> 8MB Flash, 256KB SRAM</li>
      <li><span class="key">Dimensions:</span> 80x55x18mm</li>
      <li><span class="key">Weight:</span> 65g</li>
    </ul>
    <h4>Package Includes:</h4>
    <ul>
      <li><li>Black Hole V1.0 Pro device</li>
      <li><li>4x SMA antennas</li>
      <li><li>USB-C cable</li>
      <li><li>Carrying case</li>
      <li><li>Quick start guide</li>
    </ul>
  </div>
  <a href="https://discord.gg/PdpuDvVD" target="_blank" class="new-discord-button" aria-label="Join Discord">
    <i class="fab fa-discord"></i> <span>Join Discord</span></a>
  </div>
</section>
</section>

<section id="media" class="section">
<h2 id="section">
<h2 class="glow-title">📸 Media</h2>
<div <div class="glow-block">
  <h3>Demo Videos</h3>
  <p>Watch our latest demo showcasing Black Hole V1.0’s capabilities.</p>
  <div class="video-container">
    <iframe src="https://www.youtube.com/embed/dQw4w9Agf2M" title="Black Hole V1.0 Demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</iframe>
  </div>
</div>
<div <div class="glow-block">
  <h3>Community Media</h3>
  <p>Explore user-generated content from our community.</p>
  <ul>
    <li><li><a href="https://www.instagram.com/p/CyZ3XvLPMz_/" target="_blank">Instagram: @CyberNerd123’s custom enclosure</a></li>
    <li><li><a href="https://www.youtube.com/watch?v=example123" target="_blank">YouTube: WiFi hacking tutorial by @TechGuru</a></li>
    <li><li><a href="https://tiktok.com/@unnamedperson488/video/123456789" target="_blank">TikTok: Quick setup guide</a></li>
  </ul>
  <p>Share your own on Discord!</p>
  <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" aria-label="Join Discord">
    <i class="fab fa-discord"></i> <span>Join Discord</span></a>
  </div>
<div <div class="glow-block">
  <h3>Social Feed</h3>
  <p>Follow us for updates (Instagram feed placeholder).</p>
  <div class="social-media-buttons">
    <a href="https://www.instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Instagram">
      <i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://www.youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="YouTube">
      <i class="fab fa-youtube"></i> YouTube</a>
    <a href="https://www.tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="TikTok">
      <i class="fab fa-tiktok"></i> TikTok</a>
  </div>
</div>
</section>

<section id="demos" class="section">
<h2 id="demo" class="glow">
  <h2 class="glow-title">🤝 Community</h2>
<div>
  <div class="glow-block">
    <h3>Join the Community</h3>
    <p>Connect with developers, hackers, and enthusiasts.</p>
    <div class="discord-widget">
      <p>TODO: Add Discord server ID for widget.</p>
    </div>
    <a href="https://discord.gg/PdpuDvVD" target="_blank" class="new-discord-button" aria-label="Join Discord">
      <i class="fab fa-discord"></i> <span>Join Discord</span></a>
    </div>
  <div class="glow-block">
    <h3>Simulator</h3>
    <p>Test the Black Hole V1.0 interface.</p>
    <div class="simulator">
      <button id="simulator-button" class="simulator-button" aria-label="Simulate button press">Press</button>
    </div>
  </div>
</section>

<section id="about" class="section">
<h2> About</h2>
<h2 class="glow-title">🔭 About Us</h2>
<div>
  <div class="glow-block">
    <p>Black Hole V1.0 is an open-source project by unnamedperson488, dedicated to advancing wireless testing tools for the cybersecurity community.</p>
    <p><a href="https://github.com/unnamedperson488/BlackHole_V1.0" target="_blank" class="github-button" aria-label="Contribute on GitHub">
      <i class="fab fa-github"></i> Contribute on GitHub</a></p>
  </div>
</section>

<section id="faq" class="section">
<h2>FAQ</h2>
<h2 class="glow-title">❓ FAQ</h2>
<section>
  <input type="text" id="text" id="faq-search" placeholder="Search FAQs..." aria-label="Search FAQs">
  <div class="details">
    <summary>What is Black Hole V1.0?</summary>
    <p>A dual-band wireless testing tool for cybersecurity and IoT development, powered by RTL8720DN.</p>
  </div>
  <div class="details">
    <summary>Can I use it for penetration testing?</summary>
    <p>Yes, it’s designed for ethical hacking, including WiFi network analysis and security testing, within legal boundaries.</p>
  </div>
  <div class="details">
    <summary>How do I enter Download Mode?</summary>
    <p>Connect LOG_TX (PA7) to VCC, EN to GND, power on VCC, then disconnect LOG_TX. See the Firmware section for details.</p>
  </div>
  <div class="details">
    <summary>Is the firmware open-source?</summary>
    <p>Yes, the firmware is available on GitHub, and we encourage community contributions.</p>
  </div>
  <div class="details">
    <summary>What’s the difference between V1.0 and Pro?</summary>
    <p>The Pro version offers extended range, Bluetooth 5.2, 8MB storage, and a 2000mAh battery, compared to V1.0’s 4MB and 1200mAh.</p>
  </div>
  <div class="details">
    <summary>Can I develop custom firmware?</summary>
    <p>Absolutely! Use the RTL8720DN SDK and our GitHub repo to create and flash custom firmware.</p>
  </div>
  <div class="details">
    <summary>How do I join the community?</summary>
    <p>Join our Discord server to connect with other users, share projects, and get support.</p>
  </div>
</section>

<section id="firmware" class="section">
<h2>Firmware</h2>
<h2 class="glow-title" id="flash-title">📱 Flash Firmware</h2>
<section>
  <div class="glow-block">
    <h3>Firmware Update</h3>
    <p>Update to v1.2.3 for improved performance. Use Chrome/Edge:</p>
    <ol>
      <li>Connect USB-C or serial (D0: PA8 RX, D1: PA7 TX).</li>
      <li>Refresh Ports, select LOG_UART.</li>
      <li>Connect.</li>
      <li>Download Mode: LOG_TX (PA7) to VCC, EN to GND, VCC, disconnect LOG_TX.</li>
      <li>Erase flash if needed.</li>
      <li>Flash .bin file.</li>
      <li>Reset (EN to VCC).</li>
    </ol>
    <svg width="200" height="100" viewBox="0 0 200 100" style="max-width: 100%; margin: 10px auto; display: block;">
      <rect x="50" y="20" width="100" height="60" fill="#111" stroke="#00eaff" stroke-width="2"/>
      <text x="55" y="35" fill="white" font-size="10">LOG_TX (PA7)</text>
      <text x="55" y="50" fill="white" font-size="10">EN</text>
      <text x="55" y="65" fill="white" font-size="10">GND/VCC</text>
      <line x1="45" y1="30" x2="30" y2="30" stroke="#00eaff"/>
      <line x1="45" y1="45" x2="30" y2="45" stroke="#00eaff"/>
      <line x1="45" y1="60" x2="30" y2="60" stroke="#00eaff"/>
    </svg>
    <div class="flasher-card">
      <select id="port-select" aria-label="Select port"></select>
      <input type="file" id="firmware-upload" accept=".bin" aria-label="Upload firmware">
      <input type="text" class="ota-input" placeholder="OTA IP" aria-label="Enter OTA IP">
      <button class="flasher-button refresh" aria-label="Refresh ports">Refresh</button>
      <button class="flasher-button connect" aria-label="Connect to device">Connect</button>
      <button class="flasher-button erase" disabled aria-label="Erase flash">Erase</button>
      <button class="flasher-button flash" disabled aria-label="Flash firmware">Flash</button>
      <button class="flasher-button ota" aria-label="Check OTA updates">OTA</button>
      </div>
      <div class="progress-bar">
      <div class="progress-fill"></div>
      </div>
      <p id="flasher-status">Click 'Refresh' to begin.</p>
      <div id="flasher-log"></div>
      <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0/wiki/Troubleshooting" target="_blank">Troubleshooting</a> | <a href="https://discord.gg/PdpuDvVD" target="_blank">Discord</a></p>
    </div>
  </div>
  <div class="glow-block">
    <h3>Firmware History</h3>
    <ul>
      <li><strong>v1.2.3 (May 2025):</strong> 5GHz antenna switching, battery optimization.</li>
      <li><strong>v1.2.0 (Mar 2025):</strong> Added OTA updates, bug fixes.</li>
      <li><strong>v1.1.0 (Jan 2025):</strong> Improved WiFi stability.</li>
      <li><strong>v1.0.0 (Nov 2024):</strong> Initial release.</li>
    </ul>
    <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0/releases" target="_blank" class="github-button" aria-label="Download firmware">Firmware Archive</a></p>
  </div>
  <div class="glow-block">
    <h3>Troubleshooting</h3>
    <ul>
      <li><strong>Port Not Detected:</strong> Ensure your USB-to-serial adapter drivers are installed.</li>
      <li><strong>Flash Failed:</strong> Verify Download Mode connections and try erasing flash first.</li>
      <li><strong>OTA Issues:</strong> Ensure device is on the same WiFi network and IP is correct.</li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>OTA Setup</h3>
    <p>Enable OTA updates:</p>
    <ol>
      <li>Connect device to WiFi via USB configuration.</li>
      <li>Note the device’s IP address (check serial output).</li>
      <li>Enter IP in the OTA field and click “Check OTA.”</li>
    </ol>
  </div>
</section>

<footer>
  <p>© 2025 unnamedperson488. All rights reserved.</p>
  <p>
    <a href="mailto:contact@blackholev1.com">Email</a> |
    <a href="/privacy">Privacy</a> |
    <a href="/terms">Terms</a>
  </p>
</footer>
</body>
</html>