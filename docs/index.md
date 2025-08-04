<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Black Hole V1.0: Advanced open-source wireless testing tool powered by RTL8720DN for cybersecurity enthusiasts.">
  <meta name="keywords" content="Black Hole, wireless testing, RTL8720, cybersecurity, open-source, ethical hacking">
  <meta name="author" content="unnamedperson488">
  <meta property="og:title" content="Black Hole V1.0">
  <meta property="og:description" content="Explore wireless testing with Black Hole V1.0, a powerful tool for ethical hacking and IoT security.">
  <meta property="og:image" content="https://via.placeholder.com/1200x630?text=Black+Hole+V1.0">
  <meta property="og:url" content="https://unnamedperson488.github.io/BlackHoleV1.0">
  <meta name="twitter:card" content="summary_large_image">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://cdnjs.cloudflare.com https://cdn.jsdelivr.net; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com https://cdn.jsdelivr.net; img-src 'self' https://via.placeholder.com https://raw.githubusercontent.com; connect-src 'self' https://github.com; frame-src 'self' https://www.youtube.com;">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
  <title>Black Hole V1.0</title>
  <style>
    :root {
      --primary-color: #00eaff;
      --accent-color: #22ff00;
      --bg-color: #0a0a0a;
      --card-bg: rgba(17, 17, 17, 0.85);
      --text-color: #e0e0e0;
      --shadow-glow: 0 0 12px rgba(0, 234, 255, 0.5);
      --error-color: #ff4444;
      --success-color: #22ff00;
    }
    [data-theme="light"] {
      --bg-color: #e6f3ff;
      --card-bg: rgba(255, 255, 255, 0.95);
      --text-color: #1a1a1a;
      --shadow-glow: 0 0 8px rgba(0, 234, 255, 0.3);
      --primary-color: #00b7eb;
      --accent-color: #1ae01a;
    }
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      font-family: 'Roboto', sans-serif;
      font-size: 18px;
      line-height: 1.6;
      margin: 0;
      overflow-x: hidden;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
    #boot-screen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #000;
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
      font-family: 'Orbitron', sans-serif;
      font-size: 3rem;
      color: var(--primary-color);
      text-shadow: 0 0 15px var(--primary-color);
      animation: pulse 1.5s infinite;
      margin-bottom: 30px;
    }
    .boot-progress {
      width: 250px;
      height: 12px;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 6px;
      overflow: hidden;
    }
    .boot-progress-fill {
      width: 0;
      height: 100%;
      background: var(--accent-color);
      transition: width 0.5s ease;
    }
    .start-button {
      width: 140px;
      height: 45px;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 8px;
      color: var(--primary-color);
      font-family: 'Orbitron', sans-serif;
      font-size: 1.1rem;
      font-weight: 600;
      cursor: pointer;
      box-shadow: var(--shadow-glow);
      transition: all 0.3s ease;
    }
    .start-button:hover {
      background: rgba(0, 234, 255, 0.3);
      transform: scale(1.1);
      box-shadow: 0 0 20px rgba(0, 234, 255, 0.8);
      animation: neon-flicker 0.5s ease-in-out;
    }
    .start-button:focus {
      outline: 2px solid var(--accent-color);
      outline-offset: 2px;
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
      50% { transform: scale(1.1); }
    }
    @keyframes neon-flicker {
      0%, 100% { box-shadow: 0 0 10px var(--primary-color); }
      50% { box-shadow: 0 0 25px var(--primary-color), 0 0 35px var(--primary-color); }
    }
    @keyframes glow-burst {
      0% { box-shadow: 0 0 10px var(--primary-color); }
      50% { box-shadow: 0 0 25px var(--primary-color), 0 0 50px var(--primary-color); }
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
      transition: opacity 1.5s ease;
    }
    .stars.loaded, .twinkling.loaded, .clouds.loaded {
      opacity: 1;
    }
    .stars {
      background: var(--bg-color) url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png') repeat top center;
    }
    .twinkling {
      background: transparent url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png') repeat top center;
      animation: move-twink-back 180s linear infinite;
    }
    .clouds {
      background: transparent url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png') repeat top center;
      animation: move-clouds-back 180s linear infinite;
      opacity: 0.4;
    }
    @keyframes move-twink-back {
      from { background-position: 0 0; }
      to { background-position: -12000px 6000px; }
    }
    @keyframes move-clouds-back {
      from { background-position: 0 0; }
      to { background-position: 12000px 0; }
    }
    .loading-spinner {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      border: 5px solid var(--primary-color);
      border-top: 5px solid var(--accent-color);
      border-radius: 50%;
      width: 50px;
      height: 50px;
      animation: spin 0.8s linear infinite;
      z-index: 9999;
      opacity: 0;
      transition: opacity 0.5s ease;
    }
    .loading-spinner.visible {
      opacity: 1;
    }
    @keyframes spin {
      0% { transform: translate(-50%, -50%) rotate(0deg); }
      100% { transform: translate(-50%, -50%) rotate(360deg); }
    }
    .wrapper {
      width: 100%;
      background: var(--card-bg);
      padding: 15px 0;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
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
      padding: 10px 0;
      box-shadow: var(--shadow-glow);
    }
    .name {
      font-family: 'Orbitron', sans-serif;
      font-size: 3rem;
      color: var(--primary-color);
      text-shadow: 0 0 8px var(--primary-color);
      font-weight: 700;
      text-align: center;
      margin: 0;
      padding: 15px 0;
    }
    .nav-wrapper {
      display: flex;
      justify-content: center;
      padding: 15px 0;
      display: none;
    }
    .nav-wrapper.visible {
      display: flex;
    }
    .card.nav-card {
      width: 100%;
      max-width: 1000px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 12px;
      padding: 20px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
    }
    .card.nav-card .list {
      list-style: none;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      gap: 15px;
      padding: 0;
      margin: 0;
      justify-content: center;
    }
    .card.nav-card .list .element {
      flex: 1;
      min-width: 120px;
      padding: 10px 15px;
      color: var(--text-color);
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 8px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s ease;
      outline: none;
      position: relative;
      overflow: hidden;
    }
    .card.nav-card .list .element:hover {
      background: rgba(0, 234, 255, 0.3);
      color: var(--primary-color);
      transform: translateY(-3px);
      box-shadow: var(--shadow-glow);
      animation: neon-flicker 0.5s ease-in-out;
    }
    .card.nav-card .list .element:focus {
      outline: 2px solid var(--accent-color);
      outline-offset: 2px;
    }
    .card.nav-card .list .element:active, .card.nav-card .list .element.pulse {
      animation: glow-burst 0.2s;
    }
    .card.nav-card .list .element .label {
      font-size: 1rem;
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
      backdrop-filter: blur(8px);
    }
    .product-card:hover {
      transform: scale(1.08);
      box-shadow: 0 0 25px rgba(0, 234, 255, 0.6);
    }
    .product-card__img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-bottom: 2px solid var(--primary-color);
      border-radius: 12px 12px 0 0;
      loading: lazy;
    }
    .product-card__content {
      padding: 15px;
      text-align: center;
    }
    .product-card__content h3 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.4rem;
      color: var(--primary-color);
      margin: 0 0 8px;
    }
    .product-card__content p {
      font-size: 0.95rem;
      color: var(--text-color);
      margin: 0;
    }
    .product-info {
      width: 100%;
      max-width: 700px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 10px;
      padding: 20px;
      box-shadow: var(--shadow-glow);
      margin: 20px auto;
      backdrop-filter: blur(8px);
    }
    .product-info h4 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.6rem;
      color: var(--primary-color);
      margin: 0 0 15px;
    }
    .product-info ul {
      list-style: none;
      padding: 0;
      margin: 0 0 20px;
    }
    .product-info li {
      font-size: 1rem;
      color: var(--accent-color);
      margin-bottom: 10px;
    }
    .product-info li span.key {
      color: var(--text-color);
      font-weight: 600;
    }
    .social-media-button, .github-button, .new-discord-button, .flasher-button, .newsletter-button, .contact-button {
      width: 160px;
      height: 45px;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 8px;
      color: var(--primary-color);
      font-family: 'Orbitron', sans-serif;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      box-shadow: var(--shadow-glow);
      transition: all 0.3s ease;
      text-decoration: none;
    }
    .social-media-button:hover, .github-button:hover, .new-discord-button:hover, .flasher-button:hover, .newsletter-button:hover, .contact-button:hover {
      background: rgba(0, 234, 255, 0.3);
      transform: scale(1.1);
      box-shadow: 0 0 20px rgba(0, 234, 255, 0.8);
      animation: neon-flicker 0.5s ease-in-out;
    }
    .social-media-button:focus, .github-button:focus, .new-discord-button:focus, .flasher-button:focus, .newsletter-button:focus, .contact-button:focus {
      outline: 2px solid var(--accent-color);
      outline-offset: 2px;
    }
    .social-media-button:active, .github-button:active, .new-discord-button:active, .flasher-button:active, .newsletter-button:active, .contact-button:active,
    .social-media-button.pulse, .github-button.pulse, .new-discord-button.pulse, .flasher-button.pulse, .newsletter-button.pulse, .contact-button.pulse {
      animation: glow-burst 0.2s;
    }
    .social-media-button:disabled, .flasher-button:disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }
    .social-media-buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin: 25px 0;
    }
    .flasher-card {
      width: 100%;
      max-width: 600px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 10px;
      padding: 25px;
      box-shadow: var(--shadow-glow);
      margin: 0 auto 25px;
      text-align: center;
      backdrop-filter: blur(10px);
      display: flex;
      flex-direction: column;
      gap: 15px;
    }
    #port-select, #firmware-upload, .ota-input, #newsletter-input, #contact-name, #contact-email, #contact-message {
      width: 80%;
      max-width: 350px;
      padding: 10px;
      margin: 10px auto;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 6px;
      color: var(--text-color);
      font-family: 'Roboto', sans-serif;
      font-size: 1rem;
      box-shadow: var(--shadow-glow);
      transition: box-shadow 0.3s ease;
    }
    #port-select:focus, #firmware-upload:focus, .ota-input:focus, #newsletter-input:focus, #contact-name:focus, #contact-email:focus, #contact-message:focus {
      outline: none;
      box-shadow: 0 0 20px rgba(0, 234, 255, 0.6);
    }
    .progress-bar {
      width: 80%;
      height: 12px;
      background: #111;
      border: 1px solid var(--primary-color);
      border-radius: 6px;
      margin: 20px auto;
      overflow: hidden;
    }
    .progress-fill {
      width: 0;
      height: 100%;
      background: var(--accent-color);
      transition: width 0.5s ease;
    }
    #flasher-status {
      font-size: 1rem;
      color: var(--text-color);
      margin: 15px 0;
    }
    #flasher-log {
      width: 80%;
      max-width: 350px;
      max-height: 150px;
      margin: 15px auto;
      background: #111;
      border: 1px solid var(--primary-color);
      border-radius: 6px;
      padding: 15px;
      font-size: 0.9rem;
      overflow-y: auto;
      text-align: left;
    }
    .section {
      display: none;
      padding: 25px;
      max-width: 1000px;
      margin: 0 auto 40px;
      background: var(--card-bg);
      border-radius: 10px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(10px);
      opacity: 0;
      transition: opacity 0.5s ease;
    }
    .section.active {
      display: block;
      opacity: 1;
    }
    #simulator.section.active {
      max-width: 100%;
      margin: 0;
      padding: 0;
      background: none;
      box-shadow: none;
      backdrop-filter: none;
    }
    .glow-title {
      font-family: 'Orbitron', sans-serif;
      font-size: 2.5rem;
      color: var(--primary-color);
      text-shadow: 0 0 8px var(--primary-color);
      margin-bottom: 25px;
      text-align: center;
    }
    .glow-block {
      border: 1px solid rgba(0, 234, 255, 0.3);
      padding: 20px;
      margin-bottom: 20px;
      background: var(--card-bg);
      border-radius: 10px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
    }
    .glow-block h3 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.6rem;
      color: var(--text-color);
      margin-bottom: 15px;
    }
    #discord-link {
      text-align: center;
      margin: 25px 0;
    }
    #discord-link a {
      color: #5865F2;
      font-weight: bold;
      text-decoration: none;
      font-size: 1.1rem;
      transition: color 0.3s ease;
    }
    #discord-link a:hover {
      color: #7289DA;
    }
    #faq-search {
      width: 100%;
      max-width: 700px;
      padding: 12px;
      margin-bottom: 25px;
      border: 2px solid var(--primary-color);
      background: #111;
      color: var(--text-color);
      border-radius: 6px;
      font-family: 'Roboto', sans-serif;
      transition: box-shadow 0.3s ease;
    }
    #faq-search:focus {
      outline: none;
      box-shadow: 0 0 20px rgba(0, 234, 255, 0.6);
    }
    .details {
      margin-bottom: 20px;
      padding: 15px;
      border: 1px solid rgba(0, 234, 255, 0.3);
      border-radius: 6px;
      background: var(--card-bg);
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
    }
    summary {
      font-family: 'Orbitron', sans-serif;
      font-weight: 600;
      cursor: pointer;
      color: var(--primary-color);
      font-size: 1.1rem;
      outline: none;
      padding: 8px;
      transition: color 0.3s ease;
    }
    summary:hover {
      color: var(--accent-color);
    }
    .faq-no-results {
      display: none;
      color: var(--text-color);
      font-style: italic;
      margin: 25px 0;
      text-align: center;
    }
    .theme-toggle {
      position: fixed;
      top: 20px;
      right: 20px;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 50%;
      width: 45px;
      height: 45px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: var(--shadow-glow);
      transition: all 0.3s ease;
      font-size: 1.2rem;
      display: none;
    }
    .theme-toggle.visible {
      display: flex;
    }
    .lang-switcher {
      position: fixed;
      top: 80px;
      right: 20px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 6px;
      padding: 8px;
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
      font-size: 1rem;
      cursor: pointer;
    }
    footer {
      background: var(--card-bg);
      padding: 25px;
      text-align: center;
      border-top: 2px solid var(--primary-color);
      box-shadow: var(--shadow-glow);
      margin-top: 50px;
      backdrop-filter: blur(10px);
      display: none;
    }
    footer.visible {
      display: block;
    }
    footer a {
      color: var(--primary-color);
      text-decoration: none;
      margin: 0 15px;
      transition: color 0.3s ease;
    }
    footer a:hover {
      color: var(--accent-color);
    }
    .discord-widget {
      max-width: 600px;
      margin: 25px auto;
      padding: 15px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 10px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
    }
    .video-container {
      position: relative;
      width: 100%;
      max-width: 700px;
      margin: 25px auto;
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
      border-radius: 10px;
      box-shadow: var(--shadow-glow);
    }
    .newsletter-form, .contact-form {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin: 25px 0;
      flex-wrap: wrap;
    }
    .blog-card {
      width: 100%;
      max-width: 700px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 10px;
      padding: 20px;
      margin: 20px auto;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(8px);
    }
    .blog-card h3 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.6rem;
      color: var(--primary-color);
      margin-bottom: 15px;
    }
    .blog-card p {
      font-size: 1rem;
      color: var(--text-color);
      margin-bottom: 15px;
    }
    .blog-card a {
      color: var(--accent-color);
      text-decoration: none;
      font-weight: 600;
    }
    .blog-card a:hover {
      text-decoration: underline;
    }
    /* Simulator-specific styles */
    .deauther-simulator {
      background: #1f2128;
      color: #fff;
      font-family: 'Orbitron', sans-serif;
      padding: 25px;
      width: 100%;
      min-height: 100vh;
      overflow-y: auto;
      box-sizing: border-box;
    }
    .deauther-simulator h1 {
      font-size: 2rem;
      color: #fff;
      text-align: center;
      margin-bottom: 25px;
      border-left: 6px solid #43b581;
      border-right: 6px solid #43b581;
      padding: 0.3em 1.2em;
      background: #2f3136;
      border-radius: 4px;
    }
    .deauther-simulator h2 {
      font-size: 1.4rem;
      color: #fff;
      border-left: 6px solid #43b581;
      padding: 0.5em 1.2em;
      background: #2f3136;
      border-radius: 4px;
      margin: 1.5rem 0;
    }
    .deauther-simulator h3 {
      font-size: 1.2rem;
      color: #fff;
      text-align: center;
      background: #2f3136;
      padding: 0.3em 1.2em;
      border-radius: 4px;
      width: 60%;
      margin: 0 auto 1.5rem;
    }
    .deauther-simulator table {
      border-collapse: collapse;
      width: 100%;
      margin-bottom: 2.5em;
      background: #2f3136;
      border-radius: 4px;
    }
    .deauther-simulator th, .deauther-simulator td {
      border-bottom: 1px solid rgba(255, 255, 255, 0.15);
      padding: 12px;
      text-align: left;
    }
    .deauther-simulator .tdFixed {
      text-align: center;
    }
    .deauther-simulator .tdMeter {
      padding-right: 12px;
    }
    .deauther-simulator .meter_background {
      background: #111;
      width: 100%;
      border-radius: 4px;
    }
    .deauther-simulator .meter_foreground {
      background: #fff;
      padding: 5px 0;
      border-radius: 4px;
    }
    .deauther-meter_green {
      background: #43b581;
    }
    .meter_orange {
      background: #FAA61A;
    }
    .meter_red {
      background: #F04747;
    }
    .meter_value {
      padding-left: 10px;
      color: #fff;
      font-size: 0.9rem;
    }
    .deauther-simulator .checkBoxContainer {
      position: relative;
      padding-left: 30px;
      margin-bottom: 15px;
      cursor: pointer;
      font-size: 1.1rem;
      user-select: none;
      height: 35px;
      display: block;
    }
    .deauther-simulator .checkBoxContainer input {
      position: absolute;
      opacity: 0;
      cursor: pointer;
    }
    .deauther-simulator .checkmark {
      position: absolute;
      top: 10px;
      left: 0;
      height: 18px;
      width: 18px;
      background: #111;
      border: 2px solid #fff;
      border-radius: 4px;
    }
    .deauther-simulator .checkBoxContainer input:checked ~ .checkmark:after {
      content: "";
      position: absolute;
      display: block;
      left: 5px;
      top: 1px;
      width: 5px;
      height: 10px;
      border: solid #fff;
      border-width: 0 2px 2px 0;
      transform: rotate(45deg);
    }
    .deauther-simulator .button-container {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      column-gap: 10px;
      margin: 15px 0;
    }
    .deauther-simulator .button-double {
      display: flex;
      flex-direction: column;
      row-gap: 15px;
    }
    .deauther-simulator input[type=submit], .deauther-simulator button {
      width: 160px;
      height: 45px;
      background: #2f3136;
      border: 2px solid #43b581;
      border-radius: 8px;
      color: #fff;
      font-family: 'Orbitron', sans-serif;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      text-align: center;
      line-height: 45px;
    }
    .deauther-simulator input[type=submit]:hover, .deauther-simulator button:hover {
      background: #43b581;
      transform: scale(1.1);
      box-shadow: 0 0 15px rgba(67, 181, 129, 0.8);
    }
    .deauther-simulator input[type=submit]:focus, .deauther-simulator button:focus {
      outline: 2px solid #43b581;
      outline-offset: 2px;
    }
    .deauther-simulator input[type=submit]:active, .deauther-simulator button:active {
      transform: scale(1);
    }
    .deauther-simulator input[type=text] {
      width: 160px;
      height: 45px;
      padding: 0 10px;
      background: #2f3136;
      border: 2px solid #43b581;
      border-radius: 8px;
      color: #fff;
      font-family: 'Orbitron', sans-serif;
      text-align: center;
    }
    .deauther-simulator .right {
      display: flex;
      flex-direction: row-reverse;
    }
    .deauther-simulator .centered {
      display: flex;
      justify-content: center;
    }
    @media (max-width: 768px) {
      .name { font-size: 2.5rem; }
      .section { padding: 20px; margin: 0 15px 30px; }
      .glow-title { font-size: 2rem; }
      .card.nav-card .list { gap: 10px; }
      .card.nav-card .list .element { min-width: 100px; padding: 8px 10px; }
      .product-card { max-width: 250px; }
      .product-card__img { height: 150px; }
      #port-select, #firmware-upload, .ota-input, #newsletter-input, #contact-name, #contact-email, #contact-message { width: 90%; max-width: 300px; }
      .flasher-button, .social-media-button, .github-button, .new-discord-button, .newsletter-button, .contact-button { width: 140px; height: 40px; font-size: 0.9rem; }
      .theme-toggle { top: 15px; right: 15px; width: 40px; height: 40px; }
      .lang-switcher { top: 70px; right: 15px; }
      .boot-logo { font-size: 2.5rem; }
      .start-button { width: 120px; height: 40px; font-size: 0.9rem; }
      .deauther-simulator h1 { font-size: 1.8rem; }
      .deauther-simulator h2 { font-size: 1.2rem; }
      .deauther-simulator h3 { font-size: 1rem; width: 80%; }
      .deauther-simulator table { font-size: 0.9rem; }
      .deauther-simulator input[type=submit], .deauther-simulator button { width: 140px; height: 40px; font-size: 0.9rem; }
      .deauther-simulator input[type=text] { width: 140px; }
    }
    @media (max-width: 480px) {
      .name { font-size: 2rem; }
      .section { padding: 15px; margin: 0 10px 20px; }
      .glow-title { font-size: 1.8rem; }
      .card.nav-card .list .element { min-width: 80px; padding: 6px 8px; font-size: 0.85rem; }
      .product-card { max-width: 200px; }
      .product-card__img { height: 120px; }
      .flasher-button, .social-media-button, .github-button, .new-discord-button, .newsletter-button, .contact-button { width: 120px; height: 35px; font-size: 0.85rem; }
      .theme-toggle { width: 35px; height: 35px; font-size: 1rem; }
      .deauther-simulator h1 { font-size: 1.5rem; }
      .deauther-simulator h2 { font-size: 1rem; }
      .deauther-simulator h3 { font-size: 0.85rem; }
    }
  </style>
</head>
<body>
  <div id="boot-screen">
    <div class="boot-logo">Black Hole V1.0</div>
    <div class="boot-progress">
      <div class="boot-progress-fill"></div>
    </div>
    <button class="start-button" aria-label="Start loading" data-target-section="#home">Start</button>
  </div>
  <div class="loading-spinner"></div>
  <div class="stars"></div>
  <div class="twinkling"></div>
  <div class="clouds"></div>
  <div class="theme-toggle" aria-label="Toggle theme" role="button">🌑</div>
  <div class="lang-switcher">
    <select class="lang-select" aria-label="Select language">
      <option value="en">English</option>
      <option value="es">Español</option>
      <option value="fr">Français</option>
    </select>
  </div>
  <div class="wrapper">
    <div class="text">
      <h1 class="name">UNNAMEDPERSON</h1>
    </div>
  </div>
  <div class="nav-wrapper">
    <div class="card nav-card">
      <nav aria-label="Main navigation">
        <ul class="list">
          <li class="element" data-section="#home" role="button" tabindex="0"><span class="label nav-label">Home</span></li>
          <li class="element" data-section="#product" role="button" tabindex="0"><span class="label nav-label">Product</span></li>
          <li class="element" data-section="#media" role="button" tabindex="0"><span class="label nav-label">Media</span></li>
          <li class="element" data-section="#demos" role="button" tabindex="0"><span class="label nav-label">Community</span></li>
          <li class="element" data-section="#blog" role="button" tabindex="0"><span class="label nav-label">Blog</span></li>
          <li class="element" data-section="#about" role="button" tabindex="0"><span class="label nav-label">About</span></li>
          <li class="element" data-section="#faq" role="button" tabindex="0"><span class="label nav-label">FAQ</span></li>
          <li class="element" data-section="#firmware" role="button" tabindex="0"><span class="label nav-label">Firmware</span></li>
          <li class="element" data-section="#simulator" role="button" tabindex="0"><span class="label nav-label">Simulator</span></li>
          <li class="element" data-section="#contact" role="button" tabindex="0"><span class="label nav-label">Contact</span></li>
        </ul>
      </nav>
    </div>
  </div>
  <section id="home" class="section" role="region" aria-labelledby="home-title">
    <h2 class="glow-title" id="home-title">🌌 Welcome to Black Hole V1.0</h2>
    <p>An advanced open-source platform for wireless testing and cybersecurity exploration, built for enthusiasts and professionals.</p>
    <div class="glow-block">
      <h3>Our Mission</h3>
      <p>Empowering the cybersecurity community with cutting-edge tools for ethical wireless testing and IoT security research.</p>
    </div>
    <div class="glow-block">
      <h3>Project Roadmap</h3>
      <ul>
        <li><strong>Q3 2025:</strong> Firmware v1.3.0 with enhanced WiFi capabilities and BLE support.</li>
        <li><strong>Q4 2025:</strong> Community-driven feature updates and new SDK integrations.</li>
        <li><strong>Q1 2026:</strong> Release of Black Hole V1.1 with advanced hardware features.</li>
      </ul>
    </div>
    <div class="glow-block">
      <h3>Stay Updated</h3>
      <form id="newsletter-form" class="newsletter-form" aria-label="Newsletter subscription form">
        <input type="email" id="newsletter-input" placeholder="Enter your email" aria-label="Newsletter email" required>
        <button type="submit" class="newsletter-button">Subscribe</button>
      </form>
    </div>
    <div class="social-media-buttons">
      <a href="https://instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Visit Instagram"><i class="fab fa-instagram"></i> Instagram</a>
      <a href="https://youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="Visit YouTube"><i class="fab fa-youtube"></i> YouTube</a>
      <a href="https://twitter.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Visit Twitter"><i class="fab fa-twitter"></i> Twitter</a>
    </div>
  </section>
  <section id="product" class="section" role="region" aria-labelledby="product-title">
    <h2 class="glow-title" id="product-title">📡 Product</h2>
    <div class="glow-block">
      <h3>Black Hole V1.0 Device</h3>
      <p>A compact, powerful wireless testing tool powered by RTL8720DN, designed for ethical hacking and IoT security research.</p>
      <div class="product-card" data-section="#product">
        <img class="product-card__img" src="https://via.placeholder.com/300x180?text=Black+Hole+V1.0" alt="Black Hole V1.0 Device" loading="lazy">
        <div class="product-card__content">
          <h3>Black Hole V1.0</h3>
          <p>Portable, open-source, and optimized for advanced wireless testing.</p>
        </div>
      </div>
      <div class="product-info">
        <h4>Technical Specifications</h4>
        <ul>
          <li><span class="key">Chipset:</span> RTL8720DN (Dual-band WiFi + BLE)</li>
          <li><span class="key">Processor:</span> 32-bit ARM Cortex-M4 @ 200 MHz</li>
          <li><span class="key">Memory:</span> 4MB Flash, 192KB SRAM</li>
          <li><span class="key">Interfaces:</span> USB-C, UART, SPI, I2C</li>
          <li><span class="key">Supported Protocols:</span> 802.11b/g/n, BLE 5.0</li>
          <li><span class="key">Power:</span> 3.3V, USB-C or Battery</li>
        </ul>
      </div>
    </div>
  </section>
  <section id="media" class="section" role="region" aria-labelledby="media-title">
    <h2 class="glow-title" id="media-title">🎥 Media</h2>
    <div class="glow-block">
      <h3>Video Showcase</h3>
      <p>Watch tutorials, demos, and community showcases of Black Hole V1.0 in action.</p>
      <div class="video-container">
        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Black Hole V1.0 Demo Video" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
      <div class="video-container">
        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Black Hole V1.0 Tutorial" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
  </section>
  <section id="demos" class="section" role="region" aria-labelledby="demos-title">
    <h2 class="glow-title" id="demos-title">🌐 Community</h2>
    <div class="glow-block">
      <h3>Join the Discussion</h3>
      <p>Connect with a global community of cybersecurity enthusiasts and developers on our Discord server.</p>
      <div id="discord-link">
        <a href="https://discord.gg/zrmD6uzf" target="_blank" class="new-discord-button" aria-label="Join our Discord community">
          <i class="fab fa-discord"></i> Join Discord
        </a>
      </div>
      <div class="discord-widget">
        <p>Active Members: <strong>12,500+</strong></p>
        <p>Join discussions, share projects, and get support from our vibrant community.</p>
      </div>
    </div>
  </section>
  <section id="blog" class="section" role="region" aria-labelledby="blog-title">
    <h2 class="glow-title" id="blog-title">📝 Blog</h2>
    <div class="glow-block">
      <h3>Latest Updates</h3>
      <div class="blog-card">
        <h3>Introducing Firmware v1.2.3</h3>
        <p>Our latest firmware update brings improved WiFi stability and new features for BLE scanning. Learn how to upgrade and explore the new capabilities.</p>
        <p><a href="#" aria-label="Read more about firmware v1.2.3">Read More</a></p>
      </div>
      <div class="blog-card">
        <h3>Ethical Hacking with Black Hole</h3>
        <p>Discover how to use Black Hole V1.0 for penetration testing within legal boundaries. This guide covers best practices and real-world applications.</p>
        <p><a href="#" aria-label="Read more about ethical hacking">Read More</a></p>
      </div>
      <div class="blog-card">
        <h3>Community Spotlight: Custom Firmware</h3>
        <p>Learn how our community member, CyberNinja, developed a custom firmware for advanced packet injection. Get inspired and contribute your own!</p>
        <p><a href="#" aria-label="Read more about custom firmware">Read More</a></p>
      </div>
    </div>
  </section>
  <section id="about" class="section" role="region" aria-labelledby="about-title">
    <h2 class="glow-title" id="about-title">🔭 About Us</h2>
    <div class="glow-block">
      <h3>Our Vision</h3>
      <p>Black Hole V1.0 is an open-source initiative by unnamedperson488 to provide accessible, powerful tools for cybersecurity enthusiasts, educators, and professionals.</p>
      <p>Our goal is to foster a transparent, collaborative community focused on advancing wireless security and IoT innovation.</p>
      <ul>
        <li><strong>Founded:</strong> November 2023</li>
        <li><strong>Mission:</strong> Empower ethical hacking and IoT security research</li>
        <li><strong>Community:</strong> Over 12,500 members on Discord</li>
        <li><strong>License:</strong> MIT License for open-source contributions</li>
      </ul>
      <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="github-button" target="_blank" aria-label="Contribute on GitHub">
        <i class="fab fa-github"></i> Contribute on GitHub
      </a>
    </div>
  </section>
  <section id="faq" class="section" role="region" aria-labelledby="faq-title">
    <h2 class="glow-title" id="faq-title">❓ FAQs</h2>
    <input type="text" id="faq-search" placeholder="Search FAQs..." aria-label="Search FAQs">
    <p class="faq-no-results" id="faq-no-results">No FAQs match your search.</p>
    <div class="details">
      <summary>What is Black Hole V1.0?</summary>
      <p>An open-source wireless testing tool for cybersecurity and IoT applications, built on the RTL8720DN chipset.</p>
    </div>
    <div class="details">
      <summary>Is it legal to use Black Hole V1.0?</summary>
      <p>Yes, when used for ethical hacking and testing within legal boundaries and with proper authorization.</p>
    </div>
    <div class="details">
      <summary>How do I enter Download Mode?</summary>
      <p>Connect LOG to VCC, EN to GND, power on VCC, then disconnect LOG to enter Download Mode.</p>
    </div>
    <div class="details">
      <summary>Can I develop custom firmware?</summary>
      <p>Absolutely! Use the RTL8720 SDK and our GitHub repository to create and share custom firmware.</p>
    </div>
    <div class="details">
      <summary>How do I get support?</summary>
      <p>Join our Discord community or check our GitHub for documentation and troubleshooting guides.</p>
    </div>
    <div class="details">
      <summary>What are the power requirements?</summary>
      <p>Black Hole V1.0 operates at 3.3V and can be powered via USB-C or a compatible battery.</p>
    </div>
  </section>
  <section id="firmware" class="section" role="region" aria-labelledby="firmware-title">
    <h2 class="glow-title" id="firmware-title">📱 Flash Firmware</h2>
    <div class="glow-block">
      <h3>Firmware Update (v1.2.3)</h3>
      <p>Update your Black Hole V1.0 to the latest firmware for enhanced performance and new features. Use Chrome or Edge for Web Serial support.</p>
      <ol>
        <li>Connect your device via USB-C or serial interface.</li>
        <li>Click 'Refresh' and select your port.</li>
        <li>Click 'Connect' to establish a connection.</li>
        <li>Enter bootloader mode (Download Mode).</li>
        <li>Erase flash if required for a clean install.</li>
        <li>Upload and flash a .bin file.</li>
        <li>Reset the device to complete the process.</li>
      </ol>
      <svg width="250" height="120" viewBox="0 0 250 120" style="width: 60%; max-width: 350px; margin: 25px auto; display: block;">
        <rect x="60" y="20" width="120" height="80" fill="#111" stroke="var(--primary-color)" stroke-width="2"/>
        <text x="65" y="40" fill="#FFD700" font-size="14">Log</text>
        <text x="65" y="60" fill="#FFD700" font-size="14">EN</text>
        <text x="65" y="80" fill="#FFD700" font-size="12">GND/VCC</text>
        <line x1="55" y1="35" x2="35" y2="35" stroke="#FFD700"/>
        <line x1="55" y1="55" x2="35" y2="55" stroke="#FFD700"/>
        <line x1="55" y1="75" x2="35" y2="75" stroke="#FFD700"/>
      </svg>
      <div class="flasher-card">
        <select id="port-select" aria-label="Select serial port">
          <option value="">Select Port</option>
        </select>
        <input type="file" id="firmware-upload" accept=".bin" aria-label="Upload firmware file">
        <input type="text" class="ota-input" placeholder="Enter OTA IP" aria-label="OTA IP address">
        <button class="flasher-button refresh" aria-label="Refresh ports">Refresh</button>
        <button class="flasher-button connect" id="connect-button" aria-label="Connect to port">Connect</button>
        <button class="flasher-button erase" disabled aria-label="Erase flash">Erase Flash</button>
        <button class="flasher-button flash" disabled id="flash-btn" aria-label="Flash firmware">Flash</button>
        <button class="flasher-button ota" aria-label="OTA update">OTA Update</button>
        <div class="progress-bar">
          <div class="progress-fill"></div>
        </div>
        <p id="flasher-status">Click 'Refresh' to begin.</p>
        <div id="flasher-log" role="log" aria-live="polite"></div>
        <p><a href="https://github.com/SelfMadeSystem/selfFlash/blob/main/docs/Troubleshooting.md" target="_blank" aria-label="Troubleshooting guide">Troubleshooting</a> | <a href="https://discord.gg/zrmD6uzf" target="_blank" aria-label="Join Discord community">Join Discord</a></p>
      </div>
    </div>
  </section>
  <section id="simulator" class="section" role="region" aria-labelledby="simulator-title">
    <div class="deauther-simulator">
      <div class="container">
        <h1 id="simulator-title">Black Hole V1.0 Deauther Simulator</h1>
        <div class="right">
          <div class="button-container">
            <button id="rescan-network" aria-label="Rescan Network">Rescan Network</button>
            <button id="refresh-page" aria-label="Refresh Page">Refresh Page</button>
          </div>
        </div>
        <div class="right">
          <div class="button-container">
            <button id="start-attack" aria-label="Start Attack">Start Attack</button>
            <button id="stop-attack" aria-label="Stop Attack">Stop</button>
          </div>
        </div>
        <h2>Dashboard</h2>
        <table>
          <tr><th>State</th><th>Current</th></tr>
          <tr><td>Attack Status</td><td id="attack-status">Stopped</td></tr>
          <tr><td>LED</td><td id="led-status">Enabled</td></tr>
          <tr><td>Frames Sent</td><td id="frames-sent">0</td></tr>
          <tr><td>Send Delay</td><td id="send-delay">5</td></tr>
          <tr><td>Frames Per Send</td><td id="frames-per-send">5</td></tr>
        </table>
        <h2>2.4GHz Networks</h2>
        <table id="network-table">
          <tr><th>SSID</th><th>RSSI</th><th>Channel</th><th>Select</th></tr>
          <tr>
            <td>Network1</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground deauther-meter_green" style="width: 60%;"></div></div>
              <div class="meter_value green">-60 dBm</div>
            </td>
            <td>6</td>
            <td class="tdFixed">
              <label class="checkBoxContainer">
                <input type="checkbox" aria-label="Select Network1">
                <span class="checkmark"></span>
              </label>
            </td>
          </tr>
          <tr>
            <td>Network2</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground meter_orange" style="width: 40%;"></div></div>
              <div class="meter_value orange">-80 dBm</div>
            </td>
            <td>11</td>
            <td class="tdFixed">
              <label class="checkBoxContainer">
                <input type="checkbox" aria-label="Select Network2">
                <span class="checkmark"></span>
              </label>
            </td>
          </tr>
          <tr>
            <td>Network3</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground meter_red" style="width: 20%;"></div></div>
              <div class="meter_value red">-90 dBm</div>
            </td>
            <td>1</td>
            <td class="tdFixed">
              <label class="checkBoxContainer">
                <input type="checkbox" aria-label="Select Network3">
                <span class="checkmark"></span>
              </label>
            </td>
          </tr>
        </table>
        <h2>Setup</h2>
        <div class="right">
          <div class="button-double">
            <div class="button-container">
              <input type="text" id="frames-input" placeholder="Number of Frames" aria-label="Number of Frames">
              <button id="set-frames" aria-label="Set Frames">Set Frames</button>
            </div>
            <div class="button-container">
              <input type="text" id="delay-input" placeholder="Send Delay" aria-label="Send Delay">
              <button id="update-delay" aria-label="Update Delay">Update Delay</button>
            </div>
          </div>
        </div>
        <h2>LED Options</h2>
        <div class="right">
          <div class="button-container">
            <button id="led-on" aria-label="Turn On LED">Turn On</button>
            <button id="led-off" aria-label="Turn Off LED">Turn Off</button>
          </div>
        </div>
        <h2>Attack Configuration</h2>
        <div class="glow-block">
          <h3>Advanced Settings</h3>
          <label class="checkBoxContainer">
            <input type="checkbox" id="enable-beacon" aria-label="Enable Beacon Attack"> Enable Beacon Attack
            <span class="checkmark"></span>
          </label>
          <label class="checkBoxContainer">
            <input type="checkbox" id="enable-deauth" aria-label="Enable Deauthentication Attack"> Enable Deauthentication Attack
            <span class="checkmark"></span>
          </label>
          <label class="checkBoxContainer">
            <input type="checkbox" id="enable-probe" aria-label="Enable Probe Attack"> Enable Probe Attack
            <span class="checkmark"></span>
          </label>
        </div>
      </div>
    </div>
  </section>
  <section id="contact" class="section" role="region" aria-labelledby="contact-title">
    <h2 class="glow-title" id="contact-title">📧 Contact Us</h2>
    <div class="glow-block">
      <h3>Get in Touch</h3>
      <p>Have questions or want to contribute? Reach out to us!</p>
      <form id="contact-form" class="contact-form" aria-label="Contact form">
        <input type="text" id="contact-name" placeholder="Your Name" aria-label="Your name" required>
        <input type="email" id="contact-email" placeholder="Your Email" aria-label="Your email" required>
        <textarea id="contact-message" placeholder="Your Message" aria-label="Your message" rows="5" required></textarea>
        <button type="submit" class="contact-button">Send Message</button>
      </form>
    </div>
  </section>
  <footer role="contentinfo">
    <p>© 2025 SelfMadeSystem. All Rights Reserved.</p>
    <p>
      <a href="https://github.com/SelfMadeSystem" target="_blank" aria-label="Visit GitHub">GitHub</a> |
      <a href="https://discord.gg/zrmD6uzf" target="_blank" aria-label="Join Discord">Discord</a> |
      <a href="mailto:support@example.com" aria-label="Contact support">Support</a> |
      <a href="#privacy" aria-label="Privacy policy">Privacy Policy</a>
    </p>
  </footer>
<script type="module">
  import { gsap } from 'https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js';
  import axios from 'https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js';

  class BlackHoleApp {
    constructor() {
      this.elements = {
        bootScreen: document.querySelector('#boot-screen'),
        progressFill: document.querySelector('.boot-progress-fill'),
        startButton: document.querySelector('.start-button'),
        loadingSpinner: document.querySelector('.loading-spinner'),
        wrapper: document.querySelector('.wrapper'),
        navWrapper: document.querySelector('.nav-wrapper'),
        themeToggle: document.querySelector('.theme-toggle'),
        langSwitcher: document.querySelector('.lang-switcher'),
        footer: document.querySelector('footer'),
        backgrounds: document.querySelectorAll('.stars, .twinkling, .clouds'),
        sections: document.querySelectorAll('.section'),
        navElements: document.querySelectorAll('.element'),
        langSelect: document.querySelector('.lang-select'),
        faqSearch: document.querySelector('#faq-search'),
        faqItems: document.querySelectorAll('.details'),
        faqNoResults: document.querySelector('#faq-no-results'),
        newsletterForm: document.querySelector('#newsletter-form'),
        contactForm: document.querySelector('#contact-form'),
        portSelect: document.querySelector('#port-select'),
        refreshButton: document.querySelector('.flasher-button.refresh'),
        connectButton: document.querySelector('#connect-button'),
        eraseButton: document.querySelector('.flasher-button.erase'),
        flashButton: document.querySelector('#flash-btn'),
        otaButton: document.querySelector('.flasher-button.ota'),
        firmwareUpload: document.querySelector('#firmware-upload'),
        otaInput: document.querySelector('.ota-input'),
        progressBar: document.querySelector('.progress-fill'),
        statusText: document.querySelector('#flasher-status'),
        flasherLog: document.querySelector('#flasher-log'),
        simulatorButtons: {
          rescan: document.querySelector('#rescan-network'),
          refresh: document.querySelector('#refresh-page'),
          startAttack: document.querySelector('#start-attack'),
          stopAttack: document.querySelector('#stop-attack'),
          setFrames: document.querySelector('#set-frames'),
          updateDelay: document.querySelector('#update-delay'),
          ledOn: document.querySelector('#led-on'),
          ledOff: document.querySelector('#led-off'),
        },
        simulatorInputs: {
          frames: document.querySelector('#frames-input'),
          delay: document.querySelector('#delay-input'),
        },
        simulatorOutputs: {
          attackStatus: document.querySelector('#attack-status'),
          ledStatus: document.querySelector('#led-status'),
          framesSent: document.querySelector('#frames-sent'),
          sendDelay: document.querySelector('#send-delay'),
          framesPerSend: document.querySelector('#frames-per-send'),
          networkTable: document.querySelector('#network-table'),
        },
      };
      this.selectedPort = null;
      this.isAttacking = false;
      this.framesSent = 0;
      this.translations = {
        en: {
          home: 'Home', product: 'Product', media: 'Media', demos: 'Community', blog: 'Blog',
          about: 'About', faq: 'FAQs', firmware: 'Firmware', simulator: 'Simulator', contact: 'Contact',
          welcome: 'Welcome to Black Hole V1.0'
        },
        es: {
          home: 'Inicio', product: 'Producto', media: 'Medios', demos: 'Comunidad', blog: 'Blog',
          about: 'Acerca', faq: 'Preguntas Frecuentes', firmware: 'Firmware', simulator: 'Simulador', contact: 'Contacto',
          welcome: 'Bienvenidos a Black Hole V1.0'
        },
        fr: {
          home: 'Accueil', product: 'Produit', media: 'Médias', demos: 'Communauté', blog: 'Blog',
          about: 'À propos', faq: 'FAQ', firmware: 'Firmware', simulator: 'Simulateur', contact: 'Contact',
          welcome: 'Bienvenue à Black Hole V1.0'
        }
      };
      this.init();
    }

    init() {
      this.validateElements();
      this.setupEventListeners();
      this.setupAnimations();
      this.loadPreferences();
      this.populatePorts();
    }

    validateElements() {
      for (const [key, value] of Object.entries(this.elements)) {
        if (!value && typeof value !== 'object') {
          console.error(`Missing element: ${key}`);
          alert('Error: Critical UI element missing. Check console.');
          throw new Error(`Missing element: ${key}`);
        }
      }
    }

    setupEventListeners() {
      this.elements.startButton.addEventListener('click', () => this.handleStart());
      this.elements.themeToggle.addEventListener('click', () => this.toggleTheme());
      this.elements.langSelect.addEventListener('change', () => this.changeLanguage());
      this.elements.navElements.forEach(el => {
        el.addEventListener('click', () => this.showSection(el.dataset.section));
        el.addEventListener('keydown', e => {
          if (e.key === 'Enter' || e.key === ' ') {
            e.preventDefault();
            this.showSection(el.dataset.section);
          }
        });
      });
      this.elements.faqSearch.addEventListener('input', () => this.searchFAQs());
      this.elements.newsletterForm.addEventListener('submit', e => this.handleNewsletter(e));
      this.elements.contactForm.addEventListener('submit', e => this.handleContact(e));
      this.elements.refreshButton.addEventListener('click', e => this.handleRefresh(e));
      this.elements.connectButton.addEventListener('click', e => this.handleConnect(e));
      this.elements.eraseButton.addEventListener('click', e => this.handleErase(e));
      this.elements.flashButton.addEventListener('click', e => this.handleFlash(e));
      this.elements.otaButton.addEventListener('click', e => this.handleOTA(e));
      Object.values(this.elements.simulatorButtons).forEach(btn => btn.addEventListener('click', e => this.handleSimulatorAction(e)));
    }

    setupAnimations() {
      gsap.from('.boot-logo', { opacity: 0, y: -50, duration: 1, ease: 'power2.out' });
      gsap.from('.start-button', { opacity: 0, scale: 0.8, duration: 1, delay: 0.5, ease: 'elastic.out(1, 0.3)' });
    }

    loadPreferences() {
      const savedTheme = localStorage.getItem('theme') || 'dark';
      document.body.dataset.theme = savedTheme;
      this.elements.themeToggle.textContent = savedTheme === 'light' ? '🌙' : '☀️';
      const savedLang = localStorage.getItem('language') || 'en';
      this.elements.langSelect.value = savedLang;
      this.changeLanguage();
    }

    showSection(sectionId) {
      this.elements.sections.forEach(section => {
        section.classList.remove('active');
        section.style.display = 'none';
      });
      const target = document.querySelector(sectionId);
      if (target) {
        target.classList.add('active');
        target.style.display = 'block';
        gsap.from(target, { opacity: 0, y: 20, duration: 0.5, ease: 'power2.out' });
        window.scrollTo({ top: 0, behavior: 'smooth' });
        console.log(`Loaded section: ${sectionId}`);
      } else {
        console.error(`Section not found: ${sectionId}`);
      }
    }

    handleStart() {
      this.elements.startButton.disabled = true;
      this.elements.loadingSpinner.classList.add('visible');
      gsap.to(this.elements.progressFill, { width: '100%', duration: 1, ease: 'power2.inOut' });
      setTimeout(() => {
        this.elements.bootScreen.classList.add('hidden');
        this.elements.loadingSpinner.classList.remove('visible');
        this.elements.wrapper.classList.add('visible');
        this.elements.navWrapper.classList.add('visible');
        this.elements.themeToggle.classList.add('visible');
        this.elements.langSwitcher.classList.add('visible');
        this.elements.footer.classList.add('visible');
        this.elements.backgrounds.forEach(bg => bg.classList.add('loaded'));
        this.showSection('#home');
      }, 1000);
    }

    toggleTheme() {
      const isDark = document.body.dataset.theme !== 'light';
      document.body.dataset.theme = isDark ? 'light' : 'dark';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
      this.elements.themeToggle.textContent = isDark ? '☀️' : '🌙';
      console.log('Theme:', document.body.dataset.theme);
      gsap.to('body', { backgroundColor: isDark ? '#e6f3ff' : '#0a0a0a', duration: 0.3 });
    }

    changeLanguage() {
      const lang = this.elements.langSelect.value;
      document.querySelectorAll('.nav-label').forEach((el, idx) => {
        const keys = ['home', 'product', 'media', 'demos', 'blog', 'about', 'faq', 'firmware', 'simulator', 'contact'];
        el.textContent = this.translations[lang][keys[idx]];
      });
      document.querySelector('#home-title').textContent = `🌌 ${this.translations[lang].welcome}`;
      localStorage.setItem('language', lang);
      console.log('Language:', lang);
    }

    async populatePorts() {
      if (!navigator.serial) {
        this.elements.statusText.textContent = 'Web Serial not supported. Use Chrome/Edge';
        this.logMessage('Browser does not support Web Serial');
        [this.elements.portSelect, this.elements.refreshButton, this.elements.connectButton, this.elements.eraseButton, this.elements.flashButton, this.elements.otaButton].forEach(btn => btn.disabled = true);
        alert('Web Serial not supported. Please use Chrome or Edge.');
        return;
      }
      try {
        const ports = await navigator.serial.getPorts();
        this.elements.portSelect.innerHTML = '<option value="">Select Port</option>';
        ports.forEach((port, index) => {
          const option = document.createElement('option');
          option.value = index;
          option.text = `Port ${index + 1}`;
          this.elements.portSelect.appendChild(option);
        });
        this.elements.statusText.textContent = ports.length ? 'Select a port.' : 'No ports found.';
        this.logMessage(ports.length ? 'Ports detected' : 'No ports found');
      } catch (err) {
        this.elements.statusText.textContent = `Error: ${err.message}`;
        this.logMessage(`Port error: ${err.message}`);
      }
    }

    logMessage(msg) {
      this.elements.flasherLog.innerHTML += `<p>${new Date().toLocaleString()}: ${msg}</p>`;
      this.elements.flasherLog.scrollTop = this.elements.flasherLog.scrollHeight;
      console.log('Flasher:', msg);
    }

    async handleRefresh(e) {
      e.preventDefault();
      this.elements.statusText.textContent = 'Refreshing ports...';
      this.logMessage('Refreshing ports');
      await this.populatePorts();
    }

    async handleConnect(e) {
      e.preventDefault();
      const portIndex = Number(this.elements.portSelect.value);
      if (!isNaN(portIndex)) {
        try {
          const ports = await navigator.serial.getPorts();
          this.selectedPort = ports[portIndex];
          await this.selectedPort.open({ baudRate: 115200 });
          this.elements.statusText.textContent = 'Connected! Enter Download Mode';
          this.logMessage('Connected to port');
          this.elements.flashButton.disabled = false;
          this.elements.eraseButton.disabled = false;
          this.elements.connectButton.disabled = true;
          this.elements.refreshButton.disabled = true;
          this.elements.portSelect.disabled = true;
        } catch (err) {
          this.elements.statusText.textContent = `Error: ${err.message}`;
          this.logMessage(`Connect error: ${err.message}`);
        }
      } else {
        this.elements.statusText.textContent = 'Please select a port';
        this.logMessage('No port selected');
      }
    }

    async handleErase(e) {
      e.preventDefault();
      if (!this.selectedPort) {
        this.elements.statusText.textContent = 'No device connected';
        this.logMessage('No device connected');
        return;
      }
      this.elements.statusText.textContent = 'Erasing flash...';
      this.logMessage('Erasing flash');
      try {
        await new Promise(resolve => setTimeout(resolve, 1500));
        this.elements.statusText.textContent = 'Flash erased successfully';
        this.logMessage('Flash erased');
        gsap.to(this.elements.progressBar, { width: '100%', duration: 1, ease: 'power2.inOut' });
      } catch (err) {
        this.elements.statusText.textContent = `Error: ${err.message}`;
        this.logMessage(`Erase error: ${err.message}`);
      }
    }

    handleFlash(e) {
      e.preventDefault();
      if (!this.selectedPort) {
        this.elements.statusText.textContent = 'No device connected';
        this.logMessage('No device connected');
        return;
      }
      if (!this.elements.firmwareUpload.files.length) {
        this.elements.statusText.text
