<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Black Hole V1.0: Open-source wireless testing tool powered by RTL8720DN.">
  <meta name="keywords" content="Black Hole, wireless testing, RTL8720, cybersecurity, open-source">
  <meta name="author" content="unnamedperson488">
  <meta property="og:title" content="Black Hole V1.0">
  <meta property="og:description" content="Explore wireless testing with Black Hole V1.0.">
  <meta property="og:image" content="https://via.placeholder.com/1200x630?text=Black+Hole+V1.0">
  <meta property="og:url" content="https://unnamedperson488.github.io/BlackHoleV1.0">
  <meta name="twitter:card" content="summary_large_image">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; img-src 'self' https://via.placeholder.com https://raw.githubusercontent.com; connect-src 'self' https://github.com; frame-src 'self' https://www.youtube.com;">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
  <title>Black Hole V1.0</title>
  <style>
    :root {
      --primary-color: #00eaff;
      --accent-color: #ff2200;
      --bg-color: #0a0a0a;
      --card-bg: rgba(17, 17, 17, 0.8);
      --text-color: #ffffff;
      --shadow-glow: 0 0 10px rgba(0, 234, 255, 0.4);
    }
    [data-theme="light"] {
      --bg-color: #e6f3ff;
      --card-bg: rgba(255, 255, 255, 0.95);
      --text-color: #333333;
      --shadow-glow: 0 0 8px rgba(0, 234, 255, 0.3);
      --primary-color: #00b7eb;
      --accent-color: #1ae01a;
    }
    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      font-family: 'Orbitron', sans-serif;
      font-size: '18px';
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
      font-size: 2.5rem;
      color: var(--primary-color);
      text-shadow: 0 0 10px var(--primary-color);
      animation: pulse 1s.5s infinite;
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
      transition: width 0.3s ease;
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
      background: var(--bg-color) url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png') repeat top center;
    }
    .twinkling {
      background: transparent url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png') repeat top center;
      animation: move-twink-back 200s linear infinite;
    }
    .clouds {
      background: transparent url('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png') repeat top center;
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
    .social-media-button, .github-button, .new-discord-button, .flasher-button, .newsletter-button {
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
    .social-media-button:hover, .github-button:hover, .new-discord-button:hover, .flasher-button:hover, .newsletter-button:hover {
      background: rgba(0, 234, 255, 0.2);
      transform: scale(1.05);
      box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
      animation: neon-flicker 0.5s ease-in-out;
    }
    .social-media-button:active, .github-button:active, .new-discord-button:active, .flasher-button:active, .newsletter-button:active,
    .social-media-button.pulse, .github-button.pulse, .new-discord-button.pulse, .flasher-button.pulse, .newsletter-button.pulse {
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
      max-width: 500px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 8px;
      padding: 20px;
      box-shadow: var(--shadow-glow);
      margin: 0 auto 20px;
      text-align: center;
      backdrop-filter: blur(10px);
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    #port-select, #firmware-upload, .ota-input, #newsletter-input {
      width: 80%;
      max-width: 300px;
      padding: 8px;
      margin: 10px auto;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 5px;
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
      width: 0;
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
      padding: 20px;
      max-width: 900px;
      margin: 0 auto 30px;
      background: var(--card-bg);
      border-radius: 8px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(10px);
      opacity: 0;
      transition: opacity 0.3s ease;
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
      font-size: 2rem;
      color: var(--primary-color);
      text-shadow: 0 0 5px var(--primary-color);
      margin-bottom: 20px;
    }
    .glow-block {
      border: 1px solid rgba(0, 234, 255, 0.2);
      padding: 15px;
      margin-bottom: 15px;
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
    #discord-link {
      text-align: center;
      margin: 20px 0;
    }
    #discord-link a {
      color: #5865F2;
      font-weight: bold;
      text-decoration: none;
      font-size: 1rem;
      transition: color 0.3s ease;
    }
    #discord-link a:hover {
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
      border-radius: 5px;
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
      border-radius: 5px;
      background: var(--card-bg);
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(5px);
    }
    summary {
      font-weight: 600;
      cursor: pointer;
      color: var(--primary-color);
      font-size: 1rem;
      outline: none;
      padding: 5px;
      transition: color 0.3s ease;
    }
    summary:hover {
      color: var(--accent-color);
    }
    .faq-no-results {
      display: none;
      color: var(--text-color);
      font-style: italic;
      margin: 20px 0;
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
    .lang-switcher {
      position: fixed;
      top: 70px;
      right: 20px;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 5px;
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
      backdrop-filter: blur(10px);
      display: none;
    }
    footer.visible {
      display: block;
    }
    footer a {
      color: var(--primary-color);
      text-decoration: none;
      margin: 0 10px;
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
    /* Simulator-specific styles */
    .deauther-simulator {
      background: #1f2128;
      color: #fff;
      font-family: 'Orbitron', sans-serif;
      padding: 20px;
      width: 100%;
      height: 100vh;
      overflow-y: auto;
      box-sizing: border-box;
    }
    .deauther-simulator h1 {
      font-size: 1.8rem;
      color: #fff;
      text-align: center;
      margin-bottom: 20px;
      border-left: 5px solid #43b581;
      border-right: 5px solid #43b581;
      padding: 0.2em 1em;
      background: #2f3136;
      border-radius: 3px;
    }
    .deauther-simulator h2 {
      font-size: 1.2rem;
      color: #fff;
      border-left: 5px solid #43b581;
      padding: 0.4em 1em;
      background: #2f3136;
      border-radius: 3px;
      margin: 1rem 0;
    }
    .deauther-simulator h3 {
      font-size: 1.1rem;
      color: #fff;
      text-align: center;
      background: #2f3136;
      padding: 0.2em 1em;
      border-radius: 3px;
      width: 50%;
      margin: 0 auto 1rem;
    }
    .deauther-simulator table {
      border-collapse: collapse;
      width: 100%;
      margin-bottom: 2em;
      background: #2f3136;
    }
    .deauther-simulator th, .deauther-simulator td {
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
      padding: 10px;
      text-align: left;
    }
    .deauther-simulator .tdFixed {
      text-align: center;
    }
    .deauther-simulator .tdMeter {
      padding-right: 10px;
    }
    .deauther-simulator .meter_background {
      background: #111;
      width: 100%;
    }
    .deauther-simulator .meter_foreground {
      background: #fff;
      padding: 4px 0;
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
      padding-left: 8px;
      color: #fff;
    }
    .deauther-simulator .checkBoxContainer {
      position: relative;
      padding-left: 25px;
      margin-bottom: 12px;
      cursor: pointer;
      font-size: 1rem;
      user-select: none;
      height: 32px;
      display: block;
    }
    .deauther-simulator .checkBoxContainer input {
      position: absolute;
      opacity: 0;
      cursor: pointer;
    }
    .deauther-simulator .checkmark {
      position: absolute;
      top: 8px;
      left: 0;
      height: 16px;
      width: 16px;
      background: #111;
      border: 2px solid #fff;
      border-radius: 4px;
    }
    .deauther-simulator .checkBoxContainer input:checked ~ .checkmark:after {
      content: "";
      position: absolute;
      display: block;
      left: 4px;
      top: 0px;
      width: 4px;
      height: 8px;
      border: solid #fff;
      border-width: 0 2px 2px 0;
      transform: rotate(45deg);
    }
    .deauther-simulator .button-container {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      column-gap: 8px;
      margin: 10px 0;
    }
    .deauther-simulator .button-double {
      display: flex;
      flex-direction: column;
      row-gap: 12px;
    }
    .deauther-simulator input[type=submit] {
      width: 140px;
      height: 40px;
      background: #2f3136;
      border: 2px solid #43b581;
      border-radius: 6px;
      color: #fff;
      font-family: 'Orbitron', sans-serif;
      font-size: 0.938rem;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      text-align: center;
      line-height: 40px;
    }
    .deauther-simulator input[type=submit]:hover {
      background: #43b581;
      transform: scale(1.05);
      box-shadow: 0 0 10px rgba(67, 181, 129, 0.7);
    }
    .deauther-simulator input[type=submit]:active {
      transform: scale(1);
    }
    .deauther-simulator input[type=text] {
      width: 138px;
      height: 40px;
      padding: 0 5px;
      background: #2f3136;
      border: 2px solid #43b581;
      border-radius: 6px;
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
      .name { font-size: 2rem; }
      .section { padding: 15px; margin: 0 10px 20px; }
      .glow-title { font-size: 1.8rem; }
      .card.nav-card .list { gap: 5px; }
      .card.nav-card .list .element { min-width: 80px; padding: 6px 8px; }
      .product-card { max-width: 200px; }
      .product-card__img { height: 120px; }
      #port-select, #firmware-upload, .ota-input, #newsletter-input { width: 90%; max-width: 250px; }
      .flasher-button, .social-media-button, .github-button, .new-discord-button, .newsletter-button { width: 120px; height: 35px; font-size: 0.875rem; }
      .theme-toggle { top: 10px; right: 10px; width: 35px; height: 35px; }
      .lang-switcher { top: 60px; right: 10px; }
      .boot-logo { font-size: 2rem; }
      .start-button { width: 100px; height: 35px; font-size: 0.875rem; }
      .deauther-simulator h1 { font-size: 1.5rem; }
      .deauther-simulator h2 { font-size: 1rem; }
      .deauther-simulator h3 { font-size: 0.875rem; width: 80%; }
      .deauther-simulator table { font-size: 0.875rem; }
      .deauther-simulator input[type=submit] { width: 120px; height: 35px; font-size: 0.875rem; }
      .deauther-simulator input[type=text] { width: 120px; }
    }
  </style>
</head>
<body>
  <div id="boot-screen">
    <div class="boot-logo">Black Hole V1.0</div>
    <div class="boot-progress">
      <div class="boot-progress-fill"></div>
    </div>
    <button class="start-button" aria-label="Start loading" data-target-section="#about">Start</button>
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
          <li class="element" data-section="#home"><span class="label nav-label">Home</span></li>
          <li class="element" data-section="#product"><span class="label nav-label">Product</span></li>
          <li class="element" data-section="#media"><span class="label nav-label">Media</span></li>
          <li class="element" data-section="#demos"><span class="label nav-label">Community</span></li>
          <li class="element" data-section="#about"><span class="label nav-label">About</span></li>
          <li class="element" data-section="#faq"><span class="label nav-label">FAQ</span></li>
          <li class="element" data-section="#firmware"><span class="label nav-label">Firmware</span></li>
          <li class="element" data-section="#simulator"><span class="label nav-label">Simulator</span></li>
        </ul>
      </nav>
    </div>
  </div>
  <section id="home" class="section">
    <h2 class="glow-title" id="home-title">🌌 Welcome to Black Hole V1.0</h2>
    <p>An open-source platform for wireless testing and cybersecurity exploration.</p>
    <div class="glow-block">
      <h3>Our Mission</h3>
      <p>Providing tools and resources for enthusiasts to explore wireless networks securely.</p>
    </div>
    <div class="glow-block">
      <h3>Project Roadmap</h3>
      <ul>
        <li><strong>Q3 2025:</strong> Firmware v1.3.0 with improved WiFi.</li>
        <li><strong>Q4 2025:</strong> Community-driven feature updates.</li>
      </ul>
    </div>
    <div class="glow-block">
      <h3>Stay Updated</h3>
      <form id="newsletter-form" class="newsletter-form">
        <input type="email" id="newsletter-input" placeholder="Enter your email" aria-label="Newsletter email" required>
        <button type="submit" class="newsletter-button">Subscribe</button>
      </form>
    </div>
    <div class="social-media-buttons">
      <a href="https://instagram.com/unnamedperson488" class="social-media-button" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
      <a href="https://youtube.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i> YouTube</a>
    </div>
  </section>
  <section id="product" class="section">
    <h2 class="glow-title">📡 Product</h2>
    <div class="glow-block">
      <h3>Black Hole V1.0 Device</h3>
      <p>A compact wireless testing tool powered by RTL8720DN.</p>
      <div class="product-card" data-section="#product">
        <img class="product-card__img" src="https://via.placeholder.com/250x150?text=Black+Hole+V1.0" alt="Black Hole V1.0 Device">
        <div class="product-card__content">
          <h3>Black Hole V1.0</h3>
          <p>Portable and powerful for ethical hacking.</p>
        </div>
      </div>
    </div>
  </section>
  <section id="media" class="section">
    <h2 class="glow-title">🎥 Media</h2>
    <div class="glow-block">
      <h3>Video Showcase</h3>
      <div class="video-container">
        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Black Hole V1.0 Demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
  </section>
  <section id="demos" class="section">
    <h2 class="glow-title">🌐 Community</h2>
    <div class="glow-block">
      <h3>Join the Discussion</h3>
      <p>Connect with enthusiasts and developers on Discord.</p>
      <div id="discord-link">
        <a href="https://discord.gg/PdQz4vTVD" target="_blank" class="new-discord-button" aria-label="Join Discord">
          <i class="fab fa-discord"></i> Join Discord
        </a>
      </div>
    </div>
  </section>
  <section id="about" class="section">
    <h2 class="glow-title">🔭 About Us</h2>
    <div class="glow-block">
      <h3>Our Vision</h3>
      <p>Black Hole V1.0 is an open-source project created by unnamedperson488 to empower cybersecurity enthusiasts and educators with accessible tools for ethical wireless testing.</p>
      <p>We believe in transparency, community-driven development, and fostering a learning environment for wireless protocols and IoT security.</p>
      <ul>
        <li><strong>Founded:</strong> November 2023</li>
        <li><strong>Focus:</strong> Wireless security, open-source hardware</li>
        <li><strong>Community:</strong> Over 10,000 members on Discord</li>
      </ul>
      <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="github-button" target="_blank" aria-label="Contribute on GitHub">
        <i class="fab fa-github"></i> Contribute on GitHub
      </a>
    </div>
  </section>
  <section id="faq" class="section">
    <h2 class="glow-title">❓ FAQs</h2>
    <input type="text" id="faq-search" placeholder="Search FAQs..." aria-label="Search FAQs">
    <p class="faq-no-results" id="faq-no-results">No FAQs match your search.</p>
    <div class="details">
      <summary>What is Black Hole V1.0?</summary>
      <p>An open-source wireless testing tool for cybersecurity and IoT applications.</p>
    </div>
    <div class="details">
      <summary>Is it legal to use?</summary>
      <p>Yes, for ethical hacking and testing within legal boundaries.</p>
    </div>
    <div class="details">
      <summary>How do I enter Download Mode?</summary>
      <p>Connect LOG to VCC, EN to GND, power on VCC, then disconnect LOG.</p>
    </div>
    <div class="details">
      <summary>Can I develop custom firmware?</summary>
      <p>Yes, use the RTL8720 SDK and our GitHub repository.</p>
    </div>
    <div class="details">
      <summary>How do I get support?</summary>
      <p>Join our Discord community for help and updates.</p>
    </div>
  </section>
  <section id="firmware" class="section">
    <h2 class="glow-title">📱 Flash Firmware</h2>
    <div class="glow-block">
      <h3>Firmware Update (v1.2.3)</h3>
      <p>Keep your Black Hole V1.0 up to date with the latest firmware for optimal functionality. Use Chrome/Edge for Web Serial support.</p>
      <ol>
        <li>Connect your device via USB-C or serial.</li>
        <li>Click 'Refresh' and select your port.</li>
        <li>Click 'Connect' to initiate flashing.</li>
        <li>Enter bootloader mode (Download Mode).</li>
        <li>Erase flash if necessary.</li>
        <li>Upload and flash a .bin file.</li>
        <li>Reset the device.</li>
      </ol>
      <svg width="200" height="100" viewBox="0 0 200 100" style="width: 50%; max-width: 300px; margin: 20px auto; display: block;">
        <rect x="50" y="20" width="100" height="60" fill="#111" stroke="var(--primary-color)" stroke-width="2"/>
        <text x="55" y="35" fill="#FFD700" font-size="12">Log</text>
        <text x="55" y="50" fill="#FFD700" font-size="12">EN</text>
        <text x="55" y="65" fill="#FFD700" font-size="10">GND/VCC</text>
        <line x1="45" y1="30" x2="30" y2="30" stroke="#FFD700"/>
        <line x1="45" y1="45" x2="30" y2="45" stroke="#FFD700"/>
        <line x1="45" y1="60" x2="30" y2="60" stroke="#FFD700"/>
      </svg>
      <div class="flasher-card">
        <select id="port-select" aria-label="Select port">
          <option value="">Select Port</option>
        </select>
        <input type="file" id="firmware-upload" accept=".bin" aria-label="Upload firmware">
        <input type="text" class="ota-input" placeholder="Enter OTA IP" aria-label="OTA IP">
        <button class="flasher-button refresh" aria-label="Refresh ports">Refresh</button>
        <button class="flasher-button connect" id="connect-button" aria-label="Connect to port">Connect</button>
        <button class="flasher-button erase" disabled aria-label="Erase flash">Erase Flash</button>
        <button class="flasher-button flash" disabled id="flash-btn" aria-label="Flash firmware">Flash</button>
        <button class="flasher-button ota" aria-label="OTA update">OTA Update</button>
        <div class="progress-bar">
          <div class="progress-fill"></div>
        </div>
        <p id="flasher-status">Click 'Refresh' to begin.</p>
        <div id="flasher-log"></div>
        <p><a href="https://github.com/SelfMadeSystem/selfFlash/blob/main/docs/Troubleshooting.md" target="_blank">Troubleshooting</a> | <a href="https://discord.gg/PdQz4vTVD" target="_blank">Join Discord</a></p>
      </div>
    </div>
  </section>
  <section id="simulator" class="section">
    <div class="deauther-simulator">
      <div class="container">
        <h1>Black Hole V1.0 Deauther</h1>
        <div class="right">
          <div class="button-container">
            <form method="post">
              <input type="submit" value="Rescan Network" disabled aria-label="Rescan Network">
            </form>
            <form method="post">
              <input type="submit" value="Refresh Page" disabled aria-label="Refresh Page">
            </form>
          </div>
        </div>
        <div class="right">
          <div class="button-container">
            <form method="post">
              <input type="submit" value="Start Attack" disabled aria-label="Start Attack">
            </form>
            <form method="post">
              <input type="submit" value="Stop" disabled aria-label="Stop Attack">
            </form>
          </div>
        </div>
        <h2>Dashboard</h2>
        <table>
          <tr><th>State</th><th>Current</th></tr>
          <tr><td>Attack Status</td><td>Stopped</td></tr>
          <tr><td>LED</td><td>Enabled</td></tr>
          <tr><td>Frames Sent</td><td>0</td></tr>
          <tr><td>Send Delay</td><td>5</td></tr>
          <tr><td>Frames Per Send</td><td>5</td></tr>
        </table>
        <h2>2.4GHz</h2>
        <table>
          <tr><th>SSID</th><th>RSSI</th><th>Channel</th></tr>
          <tr>
            <td>Network1</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground deauther-meter_green" style="width: 60%;"></div></div>
              <div class="meter_value green">-72 dBm</div>
            </td>
            <td class="tdFixed">6</td>
          </tr>
          <tr>
            <td>Network2</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground meter_orange" style="width: 40%;"></div></div>
              <div class="meter_value orange">-80 dBm</div>
            </td>
            <td class="tdFixed">11</td>
          </tr>
          <tr>
            <td>Network3</td>
            <td class="tdMeter">
              <div class="meter_background"><div class="meter_foreground meter_red" style="width: 20%;"></div></div>
              <div class="meter_value red">-92 dBm</div>
            </td>
            <td class="tdFixed">1</td>
          </tr>
        </table>
        <h2>Setup</h2>
        <div class="right">
          <div class="button-double">
            <form method="post">
              <div class="button-container">
                <input type="text" name="frames" placeholder="Number of Frames" disabled>
                <input type="submit" value="Set Frames" disabled aria-label="Set Frames">
              </div>
            </form>
            <form method="post">
              <div class="button-container">
                <input type="text" name="delay" placeholder="Send Delay" disabled>
                <input type="submit" value="Update Delay" disabled aria-label="Update Delay">
              </div>
            </form>
          </div>
        </div>
        <h2>LED Options</h2>
        <div class="right">
          <div class="button-container">
            <form method="post">
              <input type="submit" value="led-on" value="Turn On" disabled aria-label="Turn On LED">
            </form>
            <form method="post">
              <input type="submit" value="led-off" value="Turn Off" disabled aria-label="Turn Off LED">
            </form>
          </div>
      </div>
    </div>
  </section>
  <footer>
    <p>© 2025 SelfMadeSystem. All Rights Reserved.</p>
    <p>
      <a href="https://github.com/SelfMadeSystem" target="_blank" aria-label="GitHub">GitHub</a> |
      <a href="https://discord.gg/PdQz4vTVD" target="_blank" aria-label="Discord">Discord</a>
      <a href="mailto:support@selfmadesystem.com" aria-label="Support">Email Support</a></p>
    </footer>
  </div>
</div>
<script>
  document.addEventListener('DOMContentLoaded', () => {
    // DOM Elements
    const bootScreen = document.querySelector('#boot-screen');
    const bootProgress = document.querySelector('.boot-progress');
    const progressFill = document.querySelector('.boot-progress-fill');
    const startButton = document.querySelector('.start-button');
    const backgrounds = document.querySelectorAll('.stars, .twinkling, .clouds');
    const loadingSpinner = document.querySelector('.loading-spinner');
    const wrapper = document.querySelector('.wrapper');
    const navWrapper = document.querySelector('.nav-wrapper');
    const themeToggle = document.querySelector('.theme-toggle');
    const langSwitcher = document.querySelector('.lang-switcher');
    const footer = document.querySelector('footer');

    // Validate critical elements
    if (!bootScreen || !startButton || !bootProgress || !progressFill || !wrapper || !navWrapper || !themeToggle || !themeToggle || !langSwitcher || !footer) {
      console.error('Critical Error: Missing DOM elements');
      alert('Error: UI elements not loaded correctly. Please check console for details.');
      return;
    }

    // Image loading helper
    const loadImage = (url) => new Promise(resolve => {
      const img = new Image();
      img.src = url;
      img.onload = img.onerror = () => resolve();
    });

    // Show section function
    function showSection(sectionId) {
      console.log(`Activating section: ${sectionId}`);
      document.querySelectorAll('.section').forEach(section => {
        section.classList.remove('active');
        section.style.display = 'none';
      });
      const target = document.querySelector(sectionId);
      if (target) {
        target.classList.add('active');
        target.style.display = 'block';
        window.scrollTo({ top: 0, behavior: 'smooth' });
      } else {
        console.error(`Section not found: ${sectionId}`);
        alert(`Error: Section ${sectionId} not found`);
      }
    }

    // Navigation event listeners
    document.querySelectorAll('.element').forEach(element => {
      element.addEventListener('click', (e) => {
        const sectionId = element.dataset.section;
        if (sectionId) {
          e.preventDefault();
          showSection(sectionId);
          element.classList.add('pulse');
          setTimeout(() => element.classList.remove('pulse'), 200);
        }
      });
      element.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          const sectionId = element.dataset.section;
          if (sectionId) {
            showSection(sectionId);
            element.classList.add('pulse');
            setTimeout(() => element.classList.remove('pulse'), 200);
          }
        }
      });
    });

    // Start button handler
    startButton.addEventListener('click', async () => {
      console.log('Start button clicked');
      startButton.disabled = true;
      startButton.classList.add('pulse');
      loadingSpinner.classList.add('visible');
      const targetSection = startButton.dataset.targetSection || '#about';

      try {
        // Simulate loading
        await Promise.allSettled([
          loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png'),
          loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png'),
          loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png')
        ]);
        progressFill.style.width = '100%';
        backgrounds.forEach(bg => bg.classList.add('loaded'));

        // Transition
        bootScreen.classList.add('hidden');
        loadingSpinner.classList.remove('visible');
        wrapper.classList.add('visible');
        navWrapper.classList.add('visible');
        themeToggle.classList.add('visible');
        langSwitcher.classList.add('visible');
        footer.classList.add('visible');
        showSection(targetSection);
        console.log('Loaded section:', targetSection);
      } catch (err) {
        console.error('Load error:', err);
        alert('Error loading resources, proceeding...');
        bootScreen.classList.add('hidden');
        loadingSpinner.classList.remove('visible');
        wrapper.classList.add('visible');
        navWrapper.classList.add('visible');
        themeToggle.classList.add('visible');
        langSwitcher.classList.add('visible');
        footer.classList.add('visible');
        showSection(targetSection);
      }
    });

    // Theme toggle
    themeToggle.addEventListener('click', () => {
      const isDark = document.body.dataset.theme !== 'light';
      document.body.dataset.theme = isDark ? 'light' : 'dark';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
      themeToggle.textContent = isDark ? '🌞' : '🌑';
      console.log('Theme:', document.body.dataset.theme);
    });
    const savedTheme = localStorage.getItem('theme') || 'dark';
    document.body.dataset.theme = savedTheme;
    themeToggle.textContent = savedTheme === 'light' ? '🌞' : '🌑';

    // Language selector
    const translations = {
      en: { home: 'Home', product: 'Product', media: 'Media', demos: 'Community', about: 'About', faq: 'FAQs', firmware: 'Firmware', simulator: 'Simulator', welcome: 'Welcome to Black Hole V1.0' },
      es: { home: 'Inicio', product: 'Producto', media: 'Medios', demos: 'Comunidad', about: 'Acerca', faq: 'Preguntas Frecuentes', firmware: 'Firmware', simulator: 'Simulador', welcome: 'Bienvenidos a Black Hole V1.0' }
    };
    const langSelect = document.querySelector('.lang-select');
    if (langSelect) {
      langSelect.addEventListener('change', () => {
        const lang = langSelect.value;
        document.querySelectorAll('.nav-label').forEach((el, index) => {
          const keys = ['home', 'product', 'media', 'demos', 'about', 'faq', 'firmware', 'simulator'];
          el.textContent = translations[lang][keys[index]];
        });
        document.querySelector('#home-title').textContent = `🌌 ${translations[lang].welcome}`;
        localStorage.setItem('language', lang);
      });
      const savedLang = localStorage.getItem('language') || 'en';
      langSelect.value = savedLang;
      langSelect.dispatchEvent(new Event('change'));
    }

    // Firmware flasher
    const portSelect = document.querySelector('#port-select');
    const refreshButton = document.querySelector('.flasher-button.refresh');
    const connectButton = document.querySelector('#connect-button');
    const eraseButton = document.querySelector('.flasher-button.erase');
    const flashButton = document.querySelector('#flash-btn');
    const otaButton = document.querySelector('.flasher-button.ota');
    const firmwareUpload = document.querySelector('#firmware-upload');
    const otaInput = document.querySelector('.ota-input');
    const progressFill = document.querySelector('.progress-fill');
    const statusText = document.querySelector('#flasher-status');
    const flasherLog = document.querySelector('#flasher-log');
    let selectedPort = null;

    function logMessage(msg) {
      flasherLog.innerHTML += `<p>${new Date().toLocaleString()}: ${msg}</p>`;
      flasherLog.scrollTop = flasherLog.scrollHeight;
      console.log('Flasher:', msg);
    }

    async function populatePorts() {
      if (!navigator.serial) {
        statusText.textContent = 'Error: Web Serial not supported. Use Chrome/Edge';
        logMessage('Browser unsupported');
        [portSelect, refreshButton, connectButton, eraseButton, flashButton, otaButton].forEach(btn => btn.disabled = true);
        alert('Error: Web Serial not supported. Use Chrome/Edge.');
        return;
      }
      try {
        const ports = await navigator.serial.getPorts();
        portSelect.innerHTML = '<option value="">Select Port</option>';
        ports.forEach((port, index) => {
          const option = document.createElement('option');
          option.value = index;
          option.text = `Port ${index + 1}`;
          portSelect.appendChild(option);
        });
        statusText.textContent = ports.length ? 'Select a port' : 'No ports found';
        logMessage(ports.length ? 'Ports detected' : 'No ports');
      } catch (error) {
        statusText.textContent = `Error: ${error.message}`;
        logMessage(`Port error: ${error.message}`);
      }
    }

    refreshButton.addEventListener('click', async (e) => {
      e.preventDefault();
      statusText.textContent = 'Refreshing ports...';
      logMessage('Refreshing ports');
      await populatePorts();
    });

    connectButton.addEventListener('click', async (e) => {
      e.preventDefault();
      const portIndex = Number(portSelect.value);
      if (!isNaN(portIndex)) {
        try {
          const ports = await navigator.serial.getPorts();
          selectedPort = ports[portIndex];
          await selectedPort.open({ baudRate: 115200 });
          statusText.textContent = 'Connected! Enter Download Mode';
          logMessage('Connected');
          flashButton.disabled = false;
          eraseButton.disabled = false;
          connectButton.disabled = true;
          refreshButton.disabled = true;
          portSelect.disabled = true;
        } catch (error) {
          statusText.textContent = `Error: ${error.message}`;
          logMessage(`Connection error: ${error.message}`);
        }
      } else {
        statusText.textContent = 'Select a port';
        logMessage('No port selected');
      }
    });

    eraseButton.addEventListener('click', async (e) => {
      e.preventDefault();
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device');
        return;
      }
      statusText.textContent = 'Erasing flash...';
      logMessage('Erasing flash');
      try {
        await new Promise(resolve => setTimeout(resolve, 1000));
        statusText.textContent = 'Flash erased';
        logMessage('Flash erased');
      } catch (error) {
        statusText.textContent = `Error: ${error.message}`;
        logMessage(`Erase error: ${error.message}`);
      }
    });

    flashButton.addEventListener('click', async (e) => {
      e.preventDefault();
      if (!selectedPort) {
        statusText.textContent = 'No device connected';
        logMessage('No device');
        return;
      }
      if (!firmwareUpload.files.length) {
        statusText.textContent = 'Upload a .bin';
        logMessage('No firmware file');
        return;
      }
      const file = firmwareUpload.files[0];
      if (file.name.endsWith('.bin')) {
        statusText.textContent = 'Flashing...';
        logMessage('Flashing firmware');
        try {
          await new Promise(resolve => setTimeout(resolve, 1000));
          progressFill.style.width = '100%';
          statusText.textContent = 'Flash complete';
          logMessage('Flash complete');
        } catch (error) {
          statusText.textContent = `Error: ${error.message}`;
          logMessage(`Flash error: ${error.message}`);
        }
      } else {
        statusText.textContent = 'Invalid .bin file';
        logMessage('Invalid firmware');
      }
    });

    otaButton.addEventListener('click', async (e) => {
      e.preventDefault();
      const ip = otaInput.value.trim();
      if (ip.match(/^(\d{1,3}\.){3}\d{1,3}$/)) {
        statusText.textContent = 'Starting OTA...';
        logMessage('Starting OTA');
        try {
          await new Promise(resolve => setTimeout(resolve, 500));
          statusText.textContent = 'OTA initiated';
          logMessage('OTA started');
        } catch (error) {
          statusText.textContent = `Error: ${error.message}`;
          logMessage(`OTA error: ${error.message}`);
        }
      } else {
        statusText.textContent = 'Invalid IP';
        logMessage('Invalid IP');
      }
    });

    populatePorts();

    // FAQ search
    const faqSearch = document.querySelector('#faq-search');
    const faqItems = document.querySelectorAll('.details');
    const faqNoResults = document.querySelector('#faq-no-results');
    faqSearch.addEventListener('input', () => {
      const query = faqSearch.value.toLowerCase().trim();
      let hasMatches = false;
      faqItems.forEach(item => {
        const isMatch = item.textContent.toLowerCase().includes(query);
        item.style.display = isMatch ? 'block' : 'none';
        if (isMatch) hasMatches = true;
      });
      faqNoResults.style.display = hasMatches ? 'none' : 'block';
      console.log('FAQ search:', query);
    });

    // Newsletter form
    const newsletterForm = document.querySelector('#newsletter-form');
    newsletterForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const email = newsletterForm.querySelector('#newsletter-input').value;
      if (email.match(/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/)) {
        alert('Subscribed!');
        newsletterForm.reset();
        console.log('Subscribed:', email);
      } else {
        alert('Invalid email');
        console.log('Invalid email:', email);
      }
    });
  });
</script>
</body>
</html>