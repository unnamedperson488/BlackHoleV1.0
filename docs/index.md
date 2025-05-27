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
  <meta name="keywords" content="Black Hole V1.0, wireless testing, RTL8720DN, cybersecurity, open-source, deauther">
  <meta name="author" content="unnamedperson488">
  <meta property="og:title" content="Black Hole V1.0">
  <meta property="og:description" content="Explore Black Hole V1.0, a powerful tool for wireless network testing.">
  <meta property="og:image" content="https://via.placeholder.com/1200x630?text=Black+Hole+V1.0">
  <meta property="og:url" content="https://unnamedperson488.github.io/BlackHoleV1.0">
  <meta name="twitter:card" content="summary_large_image">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://plausible.io; style-src 'self' 'unsafe-inline'; img-src 'self' https://via.placeholder.com; connect-src 'self' https://github.com https://plausible.io">
  <link rel="icon" type="image/png" href="favicon.png">
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
    --shadow-glow: 0 0 15px #00eaff44;
  }

  [data-theme="light"] {
    --bg-color: #f5f5f5;
    --card-bg: rgba(255, 255, 255, 0.9);
    --text-color: #333;
    --shadow-glow: 0 0 15px #00eaff22;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-color);
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 18px;
    line-height: 1.6;
    margin: 0;
    position: relative;
    overflow-x: hidden;
    transition: background-color 0.3s ease, color 0.3s ease;
  }

  .stars, .twinkling, .clouds {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    display: block;
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
    border: 4px solid #00eaff;
    border-top: 4px solid #22ff00;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
    z-index: 999;
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
    margin: 0;
    backdrop-filter: blur(2px);
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
    margin: 0;
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
    flex-direction: column;
    align-items: center;
    padding: 10px 0;
    user-select: none;
  }

  .card.nav-card {
    width: 100%;
    max-width: 900px;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 10px;
    padding: 15px 0;
    display: flex;
    flex-direction: column;
    gap: 10px;
    box-shadow: var(--shadow-glow);
    margin: 10px auto;
    backdrop-filter: blur(2px);
  }

  .card.nav-card .list {
    list-style-type: none;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px;
    padding: 0 10px;
  }

  .card.nav-card .list .element {
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--text-color);
    transition: all 0.3s ease-out;
    padding: 4px 7px;
    border-radius: 6px;
    cursor: pointer;
    flex: 1;
    min-width: 100px;
    text-align: center;
  }

  .card.nav-card .list .element .label {
    font-weight: 600;
    font-size: 0.938rem;
  }

  .card.nav-card .list .element:hover {
    background-color: rgba(0, 234, 255, 0.2);
    color: var(--primary-color);
    transform: translate(1px, -1px);
    box-shadow: var(--shadow-glow);
  }

  .card.nav-card .list .element:active {
    transform: scale(0.95);
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
    margin: 0 auto;
    text-decoration: none;
    color: inherit;
    backdrop-filter: blur(2px);
  }

  .product-card:hover {
    transform: scale(1.05);
    box-shadow: 0 0 25px #00eaff88;
  }

  .product-card__img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-bottom: 2px solid var(--primary-color);
    border-radius: 8px 8px 0 0;
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
    backdrop-filter: blur(2px);
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
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 40px;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: inline-block;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .social-media-button:hover {
    transform: scale(1.05);
    background: var(--accent-color);
    color: #111;
    box-shadow: 0 0 15px #00eaff88;
  }

  .social-media-buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
    margin: 30px 0;
  }

  .github-button {
    width: 160px;
    height: 45px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--primary-color);
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 45px;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: inline-block;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .github-button:hover {
    background: rgba(0, 234, 255, 0.2);
    color: var(--text-color);
    box-shadow: 0 0 15px #00eaff88;
  }

  .new-discord-button {
    width: 140px;
    height: 45px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 100px;
    color: var(--primary-color);
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    text-align: center;
    line-height: 45px;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: inline-block;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .new-discord-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px #00eaff88;
  }

  .new-discord-button::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, var(--primary-color), transparent);
    transition: 0.5s;
    z-index: 1;
  }

  .new-discord-button:hover::before {
    left: 100%;
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
    backdrop-filter: blur(2px);
  }

  #port-select, #firmware-upload, .ota-input {
    width: 80%;
    max-width: 300px;
    padding: 8px;
    margin: 10px 0;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--text-color);
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 0.938rem;
    cursor: pointer;
    box-shadow: var(--shadow-glow);
    transition: box-shadow 0.3s ease;
  }

  #port-select:focus, #firmware-upload:focus, .ota-input:focus {
    outline: none;
    box-shadow: 0 0 15px #00eaff88;
  }

  .flasher-button {
    width: 160px;
    height: 45px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    color: var(--primary-color);
    font-family: 'Orbitron', 'Segoe UI', Arial, sans-serif;
    font-size: 0.938rem;
    font-weight: 500;
    cursor: pointer;
    margin: 10px;
    box-shadow: var(--shadow-glow);
    transition: all 0.3s ease;
  }

  .flasher-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px #00eaff88;
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

  #flasher-status, #flasher-log {
    font-size: 1rem;
    color: var(--text-color);
    margin: 10px 0;
  }

  #flasher-log {
    max-height: 100px;
    overflow-y: auto;
    background: #111;
    border: 1px solid var(--primary-color);
    border-radius: 5px;
    padding: 10px;
    font-size: 0.875rem;
    text-align: left;
  }

  .section {
    display: none;
    padding: 30px 20px;
    max-width: 900px;
    margin: 0 auto 40px auto;
    background: var(--card-bg);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(2px);
  }

  .section.active {
    display: block;
  }

  .glow-title {
    color: var(--primary-color);
    text-shadow: 0 0 5px var(--primary-color);
    font-size: 2.2rem;
    margin-bottom: 20px;
  }

  .glow-block {
    border: 1px solid #00eaff44;
    padding: 20px 25px;
    margin-bottom: 20px;
    background: var(--card-bg);
    box-shadow: var(--shadow-glow) inset;
    border-radius: 8px;
    backdrop-filter: blur(2px);
  }

  .glow-block h3 {
    font-size: 1.4rem;
    margin-bottom: 15px;
    color: var(--text-color);
  }

  .discord-join {
    text-align: center;
    margin: 30px 0;
  }

  .discord-join a {
    color: #5865F2;
    font-weight: bold;
    text-shadow: 0 0 10px #5865F2;
    text-decoration: none;
    font-size: 1.2rem;
    transition: color 0.3s ease;
  }

  .discord-join a:hover {
    color: #a3b6ff;
  }

  #faq-search {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid var(--primary-color);
    background: #111;
    color: var(--text-color);
    border-radius: 8px;
    transition: box-shadow 0.3s ease;
  }

  #faq-search:focus {
    outline: none;
    box-shadow: 0 0 10px var(--primary-color);
  }

  details {
    margin-bottom: 0.75rem;
    border: 1px solid #00eaff44;
    border-radius: 4px;
    padding: 0.5rem 1rem;
    background: var(--card-bg);
    box-shadow: var(--shadow-glow);
    backdrop-filter: blur(2px);
  }

  summary {
    font-weight: 600;
    cursor: pointer;
    outline: none;
    color: var(--text-color);
    font-size: 1.1rem;
  }

  table {
    width: 100%;
    border-collapse: collapse;
  }

  table th, table td {
    border: var(--card-bg);
    border-bottom: 1px solid #00eaff44;
    padding: 10px;
  }

  table th {
    text-align: rgba(0, 234, 255, 0.2);
    color: var(--primary-color);
  }

  .product-image {
    width: 100%;
    max-width: 600px;
    height: auto;
    margin: 0 auto 20px;
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    box-shadow: var(--shadow-glow);
    transition: transform 0.3s ease;
    loading: lazy;
    display: block;
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
    border-radius: 8px;
    padding: 5px;
    box-shadow: var(--shadow-glow);
  }

  .lang-switcher select {
    background: none;
    border: none;
    color: var(--text-color);
    font-family: 'Orbitron', sans-serif;
    cursor: pointer;
  }

  footer {
    background: var(--card-bg);
    padding: 20px;
    text-align: center;
    border-top: 2px solid var(--primary-color);
    box-shadow: var(--shadow-glow);
    margin-top: 40px;
    backdrop-filter: blur(2px);
  }

  footer a {
    color: var(--primary-color);
    text-decoration: none;
    margin: 15px;
    transition: color 0.3s ease;
  }

  footer a:hover {
    color: var(--accent-color);
  }

  .discord-widget {
    max-width: 600px;
    margin: 20px auto;
    background: var(--card-bg);
    border: 2px solid var(--primary-color);
    border-radius: 8px;
    padding: 15px;
    box-shadow: var(--shadow-glow);
  }

  .simulator {
    width: 200px;
    height: #111;
    background: 2px solid var(--primary-color);
    border-radius: 8px;
    padding: 20px;
    margin: 20px auto;
    text-align: center;
    box-shadow: var(--shadow-glow);
  }

  .simulator-button {
    width: 80px;
    height: 40px;
    background: #111;
    border: 2px solid var(--primary-color);
    border-radius: 50%;
    color: var(--primary-color);
    font-family: 'Orbitron', sans-serif;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .simulator-button:hover {
    background: rgba(0, 234, 255, 0.2);
    box-shadow: 0 0 15px #00eaff88;
  }

  @media (max-width: 600px) {
    .name {
      font-size: 2rem;
    }

    .section {
      padding: 20px 10px;
      margin: 0 10px 30px;
    }

    .glow-title {
      font-size: 1.8rem;
    }

    .product-card {
      max-width: 250px;
    }

    .product-card__img {
      height: 150px;
    }

    #port-select, #firmware-upload, .ota-input {
      width: 90%;
      font-size: 0.875rem;
    }

    .flasher-button {
      width: 140px;
      font-size: 0.875rem;
      height: 40px;
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
  }
</style>

<script>
  // Background loading
  window.addEventListener('load', () => {
    document.querySelectorAll('.stars, .twinkling, .clouds').forEach(function(element) {
  element.classList.add('loaded');
});
    document.querySelector('.loading-spinner').style.display = 'none';
  });

  // Theme toggle
  const themeToggle = document.querySelector('.theme-toggle');
  if (themeToggle) {
    themeToggle.addEventListener('click', () => {
      const isDark = document.body.dataset.theme === 'dark' || !document.body.dataset.theme;
      document.body.dataset.theme = isDark ? 'light' : 'dark';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
      themeToggle.textContent = isDark ? '🌑' : '☀️';
    });
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme) {
      document.body.dataset.theme = savedTheme;
      themeToggle.textContent = savedTheme === 'dark' ? '☀️' : '🌑';
    } else {
      themeToggle.textContent = '☀️';
    }
  }

  // Language switcher
  const translations = {
    en: {
      home: 'Homepage',
      product: 'Product',
      media: 'About',
      demos: 'Community',
      about: 'Contact',
      faq: 'FAQ',
      firmware: 'Firmware',
      welcome: 'Welcome to Black Hole V1.0',
      flashFirmware: 'Flash Firmware'
    },
    es: {
      home: 'Inicio',
      product: 'Producto',
      media: 'Acerca de',
      demos: 'Comunidad',
      about: 'Contacto',
      faq: 'Preguntas Frecuentes',
      firmware: 'Actualización',
      welcome: 'Bienvenido a Black Hole V1.0',
      flashFirmware: 'Flash Firmware'
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
      document.querySelector('.flash-title').textContent = translations[lang].flashFirmware;
      localStorage.setItem('language', lang);
    });
    const savedLang = localStorage.getItem('language') || 'en';
    langSelect.value = savedLang;
    langSelect.dispatchEvent(new Event('change'));
  }

  // Web Flasher
  const portSelect = document.querySelector('#port-select');
  const refreshButton = document.querySelector('.flasher-button.refresh');
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
      statusText.textContent = 'Web Serial API not supported. Use Chrome or Edge.';
      portSelect.disabled = true;
      refreshButton.disabled = true;
      eraseButton.disabled = true;
      flashButton.disabled = true;
      otaButton.disabled = true;
      logMessage('Browser not supported');
      return;
    }

    try {
      const ports = await navigator.serial.getPorts();
      portSelect.innerHTML = '<option value="">Select Port</option>';
      ports.forEach(function(port, index) {
        const info = port.getInfo();
        const option = document.createElement('option');
        option.value = index;
        option.text = `Port ${index + 1} (USB: ${info.usbVendorId || 'N/A'}:${info.usbProductId || 'N/A'})`;
        portSelect.appendChild(option);
      });
      statusText.textContent = ports.length ? 'Select a port and click Connect.' : 'No serial ports detected.';
      logMessage(ports.length ? 'Ports detected.' : 'No ports found.');
    } catch (error) {
      statusText.textContent = `Error listing ports: ${error.message}`;
      logMessage('Failed to list ports');
    }
  }

  async function checkFirmwareVersion(port) {
    // Simulated version check
    log('Checking firmware version...');
    await new Promise(resolve => setTimeout(resolve, 200)));
    return 'v1.1.0'; // Simulated
  }

  async function detectDownloadMode(port) {
    // Simulated detection
    logMessage('Checking Download Mode...');
    await new Promise(resolve => setTimeout(resolve, 100));
    return false;
 // Simulated
  }

  if (refreshButton) {
    refreshButton.addEventListener('click', async function() {
      statusText.textContent = 'Refreshing ports...';
      logMessage('Refreshing ports');
      await populatePorts();
    });
  }

  if (eraseButton) {
    connectButton.addEventListener('click', async () => {
      const portIndex = parseInt(portSelect.value);
      if (isNaN(portIndex)) {
        statusText.textContent = 'Please select a port';
        logMessage('No port selected');
        return;
      }

      try {
        const ports = await navigator.serial.getPorts();
        selectedPort = ports[portIndex];
        if (!selectedPort) {
          statusText.textContent = 'Invalid port selected';
          logMessage('Invalid port');
          return;
        }

        await selectedPort.open({ baudRate: 115200 });
        statusText.textContent = 'Connected. Checking firmware version...';
        logMessage('Connected to port');
        const version = await checkFirmwareVersion(selectedPort);
        statusText.textContent = `Connected. Current version: ${version}. Enter Download Mode and click Flash.`;
        const isDownloadMode = await detectDownloadMode(selectedPort);
        if (!isDownloadMode) {
          statusText.textContent += ' (Device not in Download Mode. See instructions)';
          logMessage('Device not in Download Mode');
        }
        flashButton.disabled = false;
        eraseButton.disabled = false;
        connectButton.disabled = true;
        refreshButton.disabled = true;
        portSelect.disabled = true;
      } catch (error) {
        statusText.textContent = `Error connecting: ${error.message}`;
        logMessage(`Connection error: ${error.message}`);
      }
    });
  }

  if (eraseButton) {
    eraseButton.addEventListener('click', async () => {
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device for erase');
        return;
      }

      statusText.textContent = 'Erasing flash...';
      eraseButton.disabled = true;
      progressFill.style.width = '0%';

      try {
        // Simulate erase
        logMessage('Erasing flash memory...');
        await new Promise(resolve => setTimeout(resolve, 2000));
        progressFill.style.width = '100%';
        statusText.textContent = 'Flash erased. Connect to port and flash new firmware.';
        logMessage('Flash erased successfully');
      } catch (error) {
        statusText.textContent = `Error erasing: ${error.message}`;
        logMessage(`Erase failed: ${error}`);
        progressFill.style.width = '0%';
        eraseButton.disabled = false;
      }
    });
  }

  if (flashButton) {
    flashButton.addEventListener('click', async () => {
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device for flashing');
        return;
      }

      let firmware;
      if (firmwareUpload.files.length > 0) {
        const file = firmwareUpload.files[0];
        if (file.size > 1048576) { // 1MB limit
          statusText.textContent = 'Firmware file too large (max 1MB)';
          logMessage('Invalid firmware size');
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
        await populatePorts();
      } catch (error) {
        statusText.textContent = `Error flashing: ${error.message}`;
        logMessage(`Flash error: ${error.message}`);
        progressFill.style.width = '0%';
        flashButton.disabled = false;
        eraseButton.disabled = false;
      }
    });
  }

  if (otaButton) {
    otaButton.addEventListener('click', async () => {
      const ip = otaInput.value.trim();
      if (!ip.match(/^(\d{1,3}\.){3}\d{1,3}$/)) {
        statusText.textContent = 'Invalid IP address';
        logMessage('Invalid OTA IP');
        return;
      }

      statusText.textContent = 'Checking OTA updates...';
      otaButton.disabled = true;

      try {
        // Simulate OTA check
        logMessage(`Checking OTA at ${ip}`);
        await new Promise(resolve => setTimeout(resolve, 1000));
        statusText.textContent = 'OTA update initiated. Check device status.';
        logMessage('OTA update started');
      } catch (error) {
        statusText.textContent = `OTA error: ${error.message}`;
        logMessage(`OTA error: ${error.message}`);
        otaButton.disabled = false;
      }
    });
  }

  // Initialize ports
  if (portSelect) {
    populatePorts();
  }

  // FAQ Search
  const searchInput = document.querySelector('#faq-search');
  const faqItems = document.querySelectorAll('#faq details');
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
      simulatorButton.style.background = '#22ff00';
      setTimeout(() => {
        simulatorButton.style.background = '#111';
      }, 200);
      alert('Simulated button press on Black Hole V1.0!');
    });
  }
</script>

<div class="loading-spinner"></div>
<div class="stars"></div>
<div class="twinkling"></div>
<div class="clouds"></div>

<!-- Theme Toggle -->
<button class="theme-toggle" aria-label="Toggle theme">🌑</button>

<!-- Language Switcher -->
<div class="lang-switcher">
  <select class="lang-select" aria-label="Select language">
    <option value="en">English</option>
    <option value="es">Español</option>
  </select>
</div>

<!-- Header and Navigation -->
<div class="wrapper" role="banner">
  <div class="text">
    <h1 class="name">UNNAMEDPERSON</h1>
  </div>
</div>
<div class="nav-wrapper" role="navigation">
  <div class="card nav-card">
    <ul class="list">
      <li class="element" onclick="showSection('home')"><span class="label nav-label">Home</span></li>
      <li class="element" onclick="showSection('product')"><span class="label nav-label">Product</span></li>
      <li class="element" onclick="showSection('media')"><span class="label nav-label">Media</span></li>
      <li class="element" onclick="showSection('demos')"><span class="label nav-label">Demos</span></li>
      <li class="element" onclick="showSection('community')"><span class="label nav-label">Community</span></li>
      <li class="element" onclick="showSection('about')"><span class="label nav-label">About</span></li>
      <li class="element" onclick="showSection('faq')"><span class="label nav-label">FAQ</span></li>
      <li class="element" onclick="showSection('firmware')"><span class="label nav-label">Firmware</span></li>
    </ul>
  </div>
</div>

<!-- HOME -->
<div id="home" class="section active">
  <h1 class="glow-title" id="home-title">🌌 Welcome to Black Hole V1.0</h1>
  <p>Your hub for all things Black Hole: firmware updates, documentation, media, and community engagement.</p>
  <div class="glow-block">
    <h2>Our Mission</h2>
    <p>Empowering cybersecurity enthusiasts with a powerful, open-source tool for wireless network testing.</p>
  </div>
  <div class="discord-join">
    <p>💬 Join our community!</p>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><span>DISCORD</span></a>
  </div>
  <hr>
  <h2 class="glow-title">Latest Updates</h2>
  <div class="glow-block">
    <strong>May 2025:</strong> Firmware v1.2.3 released with improved stability and anti-jamming features.
    <ul>
      <li>Enhanced 5GHz antenna switching</li>
      <li>20% longer battery life</li>
      <li>Fixed connectivity bugs</li>
    </ul>
  </div>
  <div class="glow-block">
    <strong>Upcoming:</strong> Live demo event on June 10, 2025. Join our livestream!
  </div>
  <div class="glow-block">
    <h2>Contribute</h2>
    <p>Got ideas? Contribute on GitHub or join our discussions!</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0" target="_blank" class="github-button" aria-label="Contribute on GitHub">Contribute</a>
  </div>
  <div class="social-media-buttons">
    <a class="social-media-button" href="https://instagram.com/unnamedperson488" target="_blank" aria-label="Instagram"><svg>📷</svg> Instagram</a>
    <a class="social-media-button" href="https://youtube.com/@unnamedperson488" target="_blank" aria-label="YouTube"><svg>▶</svg> YouTube</a>
    <a class="social-media-button" href="https://tiktok.com/@unnamedperson488" target="_blank" aria-label="TikTok"><svg>🎵</svg> TikTok</a>
  </div>
</div>

<!-- PRODUCT -->
<div id="product" class="section">
  <h2 class="glow-title">📦 Product</h2>
  <div class="glow-block">
    <a onclick="showSection('blackHole')" class="product-card" aria-label="View Black Hole V1.0">
      <img src="https://via.placeholder.com/300x200?text=Black+Hole+V1.0" alt="Black Hole V1.0 Device" class="product-card__img" width="300" height="200">
      <div class="product-card__content">
        <h3>Black Hole V1.0</h3>
        <p>$149</p>
      </div>
    </a>
  </div>
</div>

<!-- BLACK HOLE -->
<div id="blackHole" class="section">
  <h2 class="glow-title">📦 Black Hole V1.0</h2>
  <div class="glow-block">
    <h3>Product Overview</h3>
    <img src="https://via.placeholder.com/600x200?text=Black+Hole+V1.0+Main" alt="Black Hole V1.0 Main View" class="product-image" width="600" height="400">
    <p><strong>Black Hole V1.0 - $149</strong></p>
    <div class="product-info">
      <h4>Key Features</h4>
      <ul>
        <li>Dual-band WiFi (2.4GHz/5GHz) via RTL8720d</li>
        <li>SMA antennas for maximum range</li>
        <li>4-layer black PCB</li>
        <li>Open-source firmware with anti-jamming</li>
        <li>Boot/Reset buttons</li>
        <li>Compact for pentesting</li>
        <li>Community support</li>
      </ul>
      <h4>Technical Specifications</h4>
      <ul>
        <li><span class="key">Microcontroller:</span> RTL8720 (ARM Cortex-M4F/M0)</li>
        <li><span class="key">Connectivity:</span> WiFi 802.11 a/b/g/n, Bluetooth 5.0</li>
        <li><span class="key">Antennas:</span> 2x SMA</li>
        <li><span class="key">Buttons:</span> Boot, Reset</li>
        <li><span class="key">PCB:</span> 4-layer black matte</li>
        <li><span class="key">Power:</span> LiPo battery</li>
        <li><span class="key">Dimensions:</span> 75x50x15mm</li>
      </ul>
      <h4>What's in the Box?</h4>
      <ul>
        <li>Black Hole V1.0 device</li>
        <li>2x SMA antennas</li>
        <li>USB-C cable</li>
        <li>User manual</li>
        <li>Community access</li>
      </ul>
    </div>
    <p>Designed for wireless security testing by unnamedperson488.</p>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><span>DISCORD</span></a>
  </div>
</div>

<!-- MEDIA -->
<div id="media" class="section">
  <h2 class="glow-title">📸 Media</h2>
  <div class="glow-block">
    <h3>Photos & Videos</h3>
    <p>Explore demos and testing footage.</p>
    <ul>
      <li><a href="https://youtube.com/@unnamedperson488" target="_blank">YouTube Demos</a></li>
      <li><a href="https://instagram.com/unnamedperson488" target="_blank">Instagram Photos</a></li>
      <li><a href="https://tiktok.com/@unnamedperson488" target="_blank">TikTok Clips</a></li>
    </ul>
  </div>
  <div class="glow-block">
    <h3>Community Showcase</h3>
    <p>Submit your projects and tutorials!</p>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><span>DISCORD</span></a>
  </div>
  <div class="glow-block">
    <h3>Follow Us</h3>
    <div class="social-media-buttons">
      <a class="social-media-button" href="https://instagram.com/unnamedperson488" target="_blank" aria-label="Instagram"><svg>📷</svg> Instagram</a>
      <a class="social-media-button" href="https://youtube.com/@unnamedperson488" target="_blank" aria-label="YouTube"><svg>▶</svg> YouTube</a>
      <a class="social-media-button" href="https://tiktok.com/@unnamedperson488" target="_blank" aria-label="TikTok"><svg>🎵</svg> TikTok</a>
    </div>
  </div>
</div>

<!-- DEMOS -->
<div id="demos" class="section">
  <h2 class="glow-title">⚙️ Demos</h2>
  <p>Explore interactive examples and live demos.</p>
  <div class="glow-block">
    <h3>Live Demo</h3>
    <p>Join our June 10, 2025, livestream!</p>
    <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" aria-label="Join Discord"><span>DISCORD</span></a>
  </div>
  <div class="glow-block">
    <h3>Interactive Simulator</h3>
    <p>Simulate Black Hole V1.0 button presses.</p>
    <div class="simulator">
      <button id="simulator-button" class="simulator-button">Press</button>
    </div>
  </div>
  <div class="glow-block">
    <h3>Code Examples</h3>
    <p>Explore APIs and scripts.</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0-examples" target="_blank" class="github-button" aria-label="View Code">Code Examples</a>
  </div>
</div>

<!-- COMMUNITY -->
<div id="community" class="section">
  <h2 class="glow-title">🤝 Community</h2>
  <div class="glow-block">
    <h3>Join the Conversation</h3>
    <p>Connect with other enthusiasts!</p>
    <div class="discord-widget">
      <iframe src="https://discord.com/widget?id=1234567890&theme=dark" width="100%" height="300" allowtransparency="true" frameborder="0"></iframe>
    </div>
  </div>
  <div class="glow-block">
    <h3>GitHub Activity</h3>
    <p>Follow our project updates.</p>
    <a href="https://github.com/unnamedperson488/BlackHoleV1.0" target="_blank" class="github-button" aria-label="View GitHub">GitHub</a>
  </div>
</div>

<!-- FIRMWARE -->
<div id="firmware" class="section">
  <h2 class="glow-title" id="flash-title">📱 Flash Firmware</h2>
  <div class="glow-block">
    <h3>Update Firmware</h3>
    <p>Flash firmware v1.2.0 using Chrome/Edge. Steps:</p>
    <ol>
      <li>Connect via USB-C or USB-to-serial adapter (D0: LOG_RX PA8, D1: LOG_TX PA7).</li>
      <li>Refresh ports and select LOG_UART.</li>
      <li>Connect to the port.</li>
      <li>Enter Download Mode: connect LOG_TX (PA7) to VCC, pull EN to GND, then VCC, disconnect LOG_TX.</li>
      <li>Optionally erase flash if needed.</li>
      <li>Flash official firmware or upload a custom .bin.</li>
      <li>Reset device (EN to GND, then VCC).</li>
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
      <p><a href="https://github.com/unnamedperson488/BlackHoleV1.0/wiki/Troubleshooting" target="_blank">Troubleshooting Guide</a> | <a href="https://discord.gg/PdpuDvVD" target="_blank">Ask on Discord</a></p>
    </div>
    <p><strong>Note:</strong> Erase flash if using default firmware.</p>
  </div>
  <div class="glow-block">
    <h3>Firmware Features</h3>
    <ul>
      <li>Web-based UI</li>
      <li>OTA updates</li>
      <li>Anti-jamming support</li>
      <li>Custom development</li>
      <li>Security features</li>
      <li>Customizable settings</li>
    </ul>
  </div>
</div>

<!-- ABOUT -->
<div id="about" class="section">
  <h2 class="glow-title">🔭 About</h2>
  <div class="glow-block">
    <p>Black Hole V1.0 is a dual-band wireless testing tool designed by unnamedperson488. It’s open-source and community-driven.</p>
    <p>Our mission is to empower cybersecurity research with reliable, accessible tools.</p>
  </div>
  <div class="glow-block">
    <h3>Project Goals</h3>
    <ul>
      <li>Deliver reliable tools</li>
      <li>Provide documentation</li>
      <li>Foster collaboration</li>
      <li>Drive innovation</li>
    </ul>
  </div>
</div>

<!-- FAQ -->
<div id="faq" class="section">
  <h2 class="glow-title">❓ FAQ</h2>
  <input type="text" id="faq-search" placeholder="Search FAQs..." aria-label="Search FAQs">
  <div class="faq-items">
    <details>
      <summary>What is Black Hole V1.0?</summary>
      <p>A dual-band wireless testing tool.</p>
    </details>
    <details>
      <summary>Does it support 5GHz?</summary>
      <p>Yes, via RTL8720d.</p>
    </details>
    <details>
      <summary>Can I flash custom firmware?</summary>
      <p>Yes, via web flasher.</p>
    </details>
    <details>
      <summary>Battery life?</summary>
      <p>3-5 hours with 1000mAh.</p>
    </details>
    <details>
      <summary>Is it legal?</summary>
      <p>For authorized testing only.</p>
    </details>
  </div>
</div>

<!-- Footer -->
<footer role="contentinfo">
  <p>&copy; 2025 unnamedperson488. All rights reserved.</p>
  <p>
    <a href="mailto:contact@blackholev1.com" aria-label="Contact email">Contact</a> |
    <a href="/privacy" aria-label="Privacy policy">Privacy</a> |
    <a href="/terms" aria-label="Terms of service">Terms</a>
  </p>
</footer>

<!-- Analytics (Optional) -->
<!-- <script async defer src="https://plausible.io/js/plausible.js" data-domain="unnamedperson488.github.io"></script> -->
</body>
</html>