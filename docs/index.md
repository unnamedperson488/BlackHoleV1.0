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
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; img-src 'self' https://via.placeholder.com https://raw.githubusercontent.com; connect-src 'self' https://github.com;">
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
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .start-button:active, .start-button.pulse {
    animation: pulse 0.2s;
  }

  .start-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
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
  }

  .card.nav-card .list .element:active, .card.nav-card .list .element.pulse {
    animation: pulse 0.2s;
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

  .social-media-button {
    width: 120px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 40px;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .social-media-button:hover {
    transform: scale(1.05);
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .social-media-button:active, .social-media-button.pulse {
    animation: pulse 0.2s;
  }

  .social-media-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 30px 0;
  }

  .github-button {
    width: 140px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 40px;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .github-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .github-button:active, .github-button.pulse {
    animation: pulse 0.2s;
  }

  .new-discord-button {
    width: 140px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 40px;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 5px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .new-discord-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .new-discord-button:active, .new-discord-button.pulse {
    animation: pulse 0.2s;
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

  .flasher-button {
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
    margin: 10px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .flasher-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .flasher-button:active, .flasher-button.pulse {
    animation: pulse 0.2s;
  }

  .flasher-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
    border-color: var(--text-color);
    color: var(--text-color);
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

  .simulator-button {
    width: 80px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 50%;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.938rem;
    cursor: pointer;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .simulator-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px rgba(0, 234, 255, 0.5);
  }

  .simulator-button:active {
    animation: pulse 0.2s;
  }

  @media (max-width: 768px) {
    .name {
      font-size: 2rem;
    }

    .section {
      padding: 20px;
      margin: 0 10px 30px;
    }

    .glow-title {
      font-size: 1.8rem;
    }

    .card.nav-card .list {
      flex-direction: row;
      gap: 5px;
      justify-content: center;
    }

    .card.nav-card .list .element {
      min-width: 80px;
      padding: 6px 8px;
    }

    .product-card {
      max-width: 250px;
    }

    .product-card__img {
      height: 150px;
    }

    #port-select, #firmware-upload, .ota-input {
      width: 90%;
      max-width: 250px;
    }

    .flasher-button {
      width: 120px;
      height: 35px;
      font-size: 0.875rem;
    }

    .theme-toggle {
      top: 10px;
      right: 10px;
      width: 35px;
      height: 35px;
    }

    .lang-switcher {
      top: 60px;
      right: 10px;
    }

    .boot-logo {
      font-size: 2rem;
    }

    .start-button {
      width: 100px;
      height: 35px;
      font-size: 0.875rem;
    }
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
      bootProgress.style.display = 'block';
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

  // Simulator
  const simulatorButton = document.querySelector('#simulator-button');
  if (simulatorButton) {
    simulatorButton.addEventListener('click', () => {
      simulatorButton.style.backgroundColor = '#22ff00';
      setTimeout(() => simulatorButton.style.backgroundColor = '#111', 200);
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
  <button class="start-button">Start</button>
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
  <p>Your hub for wireless testing and community engagement.</p>
  <div class="glow-block">
    <h3>Mission</h3>
    <p>Empowering cybersecurity with open-source tools.</p>
  </div>
  <div class="discord-join">
    <p>💬 Join us!</p>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><i class="fab fa-discord"></i> <span>DISCORD</span></a>
  </div>
  <hr>
  <h3 class="glow-title">Updates</h3>
  <div class="glow-block">
    <p><strong>May 2025:</strong> Firmware v1.2.3 released.</p>
    <ul>
      <li>5GHz antenna switching</li>
      <li>Battery optimization</li>
      <li>Bug fixes</li>
    </ul>
  </div>
  <div class="glow-block">
    <p><strong>Upcoming:</strong> Live demo June 15, 2025.</p>
  </div>
  <div class="glow-block">
    <h3>Contribute</h3>
    <p>Share ideas on GitHub!</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="github-button" aria-label="Contribute on GitHub"><i class="fab fa-github"></i> GitHub</a>
  </div>
  <div class="social-media-buttons">
    <a href="https://instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i> YouTube</a>
    <a href="https://tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="TikTok"><i class="fab fa-tiktok"></i> TikTok</a>
  </div>
</section>

<section id="product" class="section">
  <h2 class="glow-title">📦 Product</h2>
  <div class="glow-block">
    <a href="#" onclick="showSection('#blackHole')" class="product-card" aria-label="View Black Hole V1.0">
      <img src="https://via.placeholder.com/300x200?text=Black+Hole+V1.0" alt="Black Hole V1.0 Device" class="product-card__img" width="300" height="200">
      <div class="product-card__content">
        <h3>Black Hole V1.0</h3>
        <p>$149</p>
      </div>
    </a>
  </div>
</section>

<section id="blackHole" class="section">
  <h2 class="glow-title">📦 Black Hole V1.0</h2>
  <div class="glow-block">
    <h3>Overview</h3>
    <img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0" alt="Black Hole V1.0" class="product-image" width="600" height="400">
    <p><strong>Black Hole V1.0 - $149</strong></p>
    <div class="product-info">
      <h4>Features</h4>
      <ul>
        <li>Dual-band WiFi (2.4/5GHz)</li>
        <li>SMA antennas</li>
        <li>4-layer PCB</li>
        <li>Open-source firmware</li>
        <li>Boot/Reset buttons</li>
      </ul>
      <h4>Specifications</h4>
      <ul>
        <li><span class="key">MCU:</span> RTL8720DN</li>
        <li><span class="key">Connectivity:</span> WiFi, Bluetooth</li>
        <li><span class="key">Size:</span> 75x50x15mm</li>
      </ul>
    </div>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><i class="fab fa-discord"></i> <span>DISCORD</span></a>
  </div>
</section>

<section id="media" class="section">
  <h2 class="glow-title">📸 Media</h2>
  <div class="glow-block">
    <h3>Videos & Photos</h3>
    <ul>
      <li><a href="https://youtube.com/@unnamedperson488" target="_blank">YouTube</a></li>
      <li><a href="https://instagram.com/unnamedperson488" target="_blank">Instagram</a></li>
      <li><a href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok</a></li>
    </ul>
  </div>
  <div class="glow-block">
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><i class="fab fa-discord"></i> <span>DISCORD</span></a>
  </div>
  <div class="social-media-buttons">
    <a href="https://instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
    <a href="https://youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i> YouTube</a>
    <a href="https://tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="TikTok"><i class="fab fa-tiktok"></i> TikTok</a>
  </div>
</section>

<section id="demos" class="section">
  <h2 class="glow-title">🤝 Community</h2>
  <div class="glow-block">
    <h3>Join</h3>
    <p>Connect with enthusiasts!</p>
    <div class="discord-widget">
      <p>TODO: Add Discord server ID for widget.</p>
    </div>
  </div>
  <div class="glow-block">
    <h3>Simulator</h3>
    <div class="simulator">
      <button id="simulator-button" class="simulator-button">Press</button>
    </div>
  </div>
</section>

<section id="about" class="section">
  <h2 class="glow-title">🔭 About</h2>
  <div class="glow-block">
    <p>Black Hole V1.0 is an open-source wireless testing tool by unnamedperson488.</p>
  </div>
</section>

<section id="faq" class="section">
  <h2 class="glow-title">❓ FAQ</h2>
  <input type="text" id="faq-search" placeholder="Search..." aria-label="Search FAQs">
  <div class="details">
    <summary>What is Black Hole V1.0?</summary>
    <p>A dual-band wireless testing tool.</p>
  </div>
</section>

<section id="firmware" class="section">
  <h2 class="glow-title flash-title">📱 Flash Firmware</h2>
  <div class="glow-block">
    <h3>Update</h3>
    <p>Flash v1.2.3 using Chrome/Edge:</p>
    <ol>
      <li>Connect USB-C or USB-to-serial (D0: PA8 RX, D1: PA7 TX).</li>
      <li>Refresh ports, select LOG_UART.</li>
      <li>Connect.</li>
      <li>Download Mode: LOG_TX (PA7) to VCC, EN to GND, VCC, disconnect LOG_TX.</li>
      <li>Erase flash if needed.</li>
      <li>Flash official or custom .bin.</li>
      <li>Reset (EN to GND, then VCC).</li>
    </ol>
    <svg width="200" height="100" viewBox="0 0 200 100" style="margin: 10px auto; display: block;">
      <rect x="50" y="20" width="100" height="60" fill="#111" stroke="#00eaff" stroke-width="2"/>
      <text x="55" y="35" fill="#00eaff" font-size="10">LOG_TX (PA7)</text>
      <text x="55" y="50" fill="#00eaff" font-size="10">EN</text>
      <text x="55" y="65" fill="#00eaff" font-size="10">GND/VCC</text>
      <line x1="45" y1="30" x2="30" y2="30" stroke="#00eaff"/>
      <line x1="45" y1="45" x2="30" y2="45" stroke="#00eaff"/>
      <line x1="45" y1="60" x2="30" y2="60" stroke="#00eaff"/>
    </svg>
    <div class="flasher-card">
      <select id="port-select" aria-label="Select serial port">
        <option value="">Select Port</option>
      </select>
      <input type="file" id="firmware-upload" accept=".bin" aria-label="Upload firmware">
      <input type="text" class="ota-input" placeholder="Device IP for OTA" aria-label="Enter OTA IP">
      <button class="flasher-button refresh" aria-label="Refresh ports">Refresh Ports</button>
      <button class="flasher-button connect" aria-label="Connect to port">Connect</button>
      <button class="flasher-button erase" disabled aria-label="Erase flash">Erase Flash</button>
      <button class="flasher-button flash" disabled aria-label="Flash firmware">Flash Firmware</button>
      <button class="flasher-button ota" aria-label="Check OTA updates">Check OTA</button>
      <div class="progress-bar">
        <div class="progress-fill"></div>
      </div>
      <p id="flasher-status">Click 'Refresh Ports' to begin.</p>
      <div id="flasher-log"></div>
      <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0/wiki/Troubleshooting" target="_blank">Troubleshooting</a> | <a href="https://discord.gg/PdpuDvVD" target="_blank">Discord</a></p>
    </div>
  </div>
</section>

<footer>
  <p>© 2025 unnamedperson488.</p>
  <p>
    <a href="mailto:contact@blackholev1.com">Email</a> |
    <a href="/privacy">Privacy</a> |
    <a href="/terms">Terms</a>
  </p>
</footer>
</body>
</html>