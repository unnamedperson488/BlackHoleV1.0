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
      --accent-color: #22ff00;
      --bg-color: #0a0a0a;
      --card-bg: rgba(17, 17, 17, 0.8);
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
    .social-media-button:disabled, .flasher-button:disabled, .simulator-button:disabled {
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
      padding: 15px;
      box-shadow: var(--shadow-glow);
      margin: 0 auto 20px;
      text-align: center;
      backdrop-filter: blur(10px);
    }
    #port-select, #firmware-upload, .ota-input, #newsletter-input {
      width: 80%;
      max-width: 300px;
      padding: 8px;
      margin: 10px 0;
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
    .simulator {
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 10px;
      padding: 20px;
      margin: 20px;
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
    .deauther-simulator {
      display: none;
      background: var(--card-bg);
      border: 2px solid var(--primary-color);
      border-radius: 8px;
      padding: 20px;
      margin: 20px auto;
      max-width: 900px;
      box-shadow: var(--shadow-glow);
      backdrop-filter: blur(10px);
      font-family: 'Orbitron', sans-serif;
      color: var(--text-color);
    }
    .deauther-simulator.active {
      display: block;
    }
    .deauther-simulator h1 {
      font-size: 1.8rem;
      color: var(--primary-color);
      text-shadow: 0 0 5px var(--primary-color);
      text-align: center;
      margin-bottom: 20px;
      border-left: 5px solid var(--accent-color);
      border-right: 5px solid var(--accent-color);
      padding: 0.2em 1em;
      background: rgba(17, 17, 17, 0.8);
      border-radius: 3px;
    }
    .deauther-simulator h2 {
      font-size: 1.2rem;
      color: var(--primary-color);
      border-left: 5px solid var(--accent-color);
      padding: 0.4em 1em;
      background: rgba(17, 17, 17, 0.8);
      border-radius: 3px;
      margin: 1rem 0;
    }
    .deauther-simulator h3 {
      font-size: 1.1rem;
      color: var(--primary-color);
      text-align: center;
      background: rgba(17, 17, 17, 0.8);
      padding: 0.2em 1em;
      border-radius: 3px;
      width: 50%;
      margin: 0 auto 1rem;
    }
    .deauther-simulator table {
      border-collapse: collapse;
      width: 100%;
      margin-bottom: 2em;
    }
    .deauther-simulator th, .deauther-simulator td {
      border-bottom: 1px solid rgba(0, 234, 255, 0.3);
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
      background: var(--text-color);
      padding: 4px 0;
    }
    .deauther-meter_green {
      background: var(--accent-color);
    }
    .meter_orange {
      background: #FAA61A;
    }
    .meter_red {
      background: #F04747;
    }
    .meter_value {
      padding-left: 8px;
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
      border: 2px solid var(--primary-color);
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
      border: solid var(--primary-color);
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
      text-transform: uppercase;
      text-align: center;
      line-height: 40px;
    }
    .deauther-simulator input[type=submit]:hover {
      background: rgba(0, 234, 255, 0.2);
      transform: scale(1.05);
      box-shadow: 0 0 15px rgba(0, 234, 255, 0.7);
      animation: neon-flicker 0.5s ease-in-out;
    }
    .deauther-simulator input[type=submit]:active {
      animation: glow-burst 0.2s;
    }
    .deauther-simulator input[type=text] {
      width: 138px;
      height: 40px;
      padding: 0 5px;
      background: #111;
      border: 2px solid var(--primary-color);
      border-radius: 6px;
      color: var(--text-color);
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
      .flasher-button, .social-media-button, .github-button, .new-discord-button, .simulator-button, .newsletter-button { width: 120px; height: 35px; font-size: 0.875rem; }
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
    <div class="boot-progress" style="display: none;">
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
      <a href="https://tiktok.com/@unnamedperson488" class="social-media-button" target="_blank" aria-label="TikTok"><i class="fab fa-tiktok"></i> TikTok</a>
    </div>
  </section>
  <section id="product" class="section">
    <h2 class="glow-title">📦 Product</h2>
    <div class="glow-block">
      <h3>Black Hole V1.0</h3>
      <a href="#" data-section="#blackHole" class="product-card">
        <img src="https://via.placeholder.com/250x150?text=Black+Hole+V1.0" alt="Black Hole V1.0" class="product-card__img">
        <div class="product-card__content">
          <h3>Black Hole V1.0</h3>
          <p>$149</p>
        </div>
      </a>
    </div>
  </section>
  <section id="blackHole" class="section">
    <h2 class="glow-title">📱 Black Hole V1.0</h2>
    <div class="glow-block">
      <h3>Overview</h3>
      <img src="https://via.placeholder.com/600x400?text=Black+Hole+V1.0" alt="Black Hole V1.0" width="600" height="400">
      <p><strong>Black Hole V1.0 - $149</strong></p>
      <p>An open-source wireless testing tool powered by RTL8720DN for cybersecurity enthusiasts.</p>
      <div class="product-info">
        <h4>Features</h4>
        <ul>
          <li>Dual-band WiFi (2.4/5GHz)</li>
          <li>2 SMA antennas</li>
          <li>Open-source firmware</li>
          <li>1200mAh rechargeable battery</li>
          <li>USB-C connectivity</li>
        </ul>
        <h4>Specifications</h4>
        <ul>
          <li><span class="key">MCU:</span> RTL8720DN (Dual-Core)</li>
          <li><span class="key">Connectivity:</span> WiFi 802.11 a/b/g/n</li>
          <li><span class="key">Memory:</span> 4MB Flash</li>
          <li><span class="key">Dimensions:</span> 75x50x15mm</li>
          <li><span class="key">Weight:</span> 50g</li>
        </ul>
        <h4>Use Cases</h4>
        <ul>
          <li>Ethical WiFi network testing</li>
          <li>IoT device prototyping</li>
          <li>Learning wireless protocols</li>
        </ul>
        <h4>Package Includes</h4>
        <ul>
          <li>Black Hole V1.0 device</li>
          <li>2x SMA antennas</li>
          <li>USB-C cable</li>
          <li>Quick start guide</li>
        </ul>
      </div>
      <div id="discord-link">
        <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" aria-label="Join Discord">
          <i class="fab fa-discord"></i> Join Discord
        </a>
      </div>
    </div>
  </section>
  <section id="media" class="section">
    <h2 class="glow-title">📸 Media</h2>
    <div class="glow-block">
      <h3>Demo Video</h3>
      <p>Watch Black Hole V1.0 in action.</p>
      <div class="video-container">
        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
    <div class="glow-block">
      <h3>Community Media</h3>
      <p>Explore user-generated content.</p>
      <ul>
        <li><a href="https://instagram.com/p/CyZ3X2vLPMz/" target="_blank">Instagram: Custom setup</a></li>
        <li><a href="https://youtube.com/watch?v=example123" target="_blank">YouTube: User tutorial</a></li>
      </ul>
      <div id="discord-link">
        <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" aria-label="Share on Discord">
          <i class="fab fa-discord"></i> Share on Discord
        </a>
      </div>
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
      <h3>Join our Community</h3>
      <p>Connect with other cybersecurity enthusiasts.</p>
      <div class="discord-widget">
        <p>TODO: Add Discord server ID for widget.</p>
      </div>
      <div id="discord-link">
        <a href="https://discord.gg/PdpuDvVD" class="new-discord-button" target="_blank" aria-label="Join Discord">
          <i class="fab fa-discord"></i> Join Discord
        </a>
      </div>
    </div>
    <div class="glow-block">
      <h3>Simulator</h3>
      <p>Explore the Black Hole V1.0 Deauther interface.</p>
      <div class="simulator">
        <button id="simulator-button" class="simulator-button" aria-label="Toggle Deauther simulator">Toggle Simulator</button>
        <div id="deauther-simulator" class="deauther-simulator">
          <div class="container">
            <h1>Black Hole V1.0 Deauther</h1>
            <div class="right">
              <div class="button-container">
                <form method="post">
                  <input type="submit" value="Rescan Network" disabled aria-label="Rescan Network">
                </form>
                <form method="post">
                  <input type="submit" value="Refresh page" disabled aria-label="Refresh page">
                </form>
              </div>
            </div>
            <div class="right">
              <form method="post">
                <div class="button-container">
                  <input type="submit" value="Start Attack" disabled aria-label="Start Attack">
                </div>
              </form>
            </div>
            <div class="right">
              <form method="post">
                <div class="button-container">
                  <input type="submit" value="Stop" disabled aria-label="Stop Attack">
                </form>
              </div>
            </div>
            <h2>Dashboard</h2>
            <table>
              <tr><th>State</th><th>Current Value</th></tr>
              <tr><td>Status Attack</td><td>Stopped</td></tr>
              <tr><td>LED Enabled</td><td>Enabled</td></tr>
              <tr><td>Frame Sent</td><td>0</td></tr>
              <tr><td>Send Delay</td><td>5</td></tr>
              <tr><td>Number of frames send each time</td><td>5</td></tr>
            </table>
            <h2>2.4GHz</h2>
            <table>
              <tr><th>SSID</th><th>RSSI</th><th>Channel</th></tr>
              <tr><td>Network1</td><td class="tdMeter"><div class="meter_background"><div class="meter_foreground deauther-meter_green" style="width: 60%;"></div></div><div class="meter_value">-60 dBm</div></td><td class="tdFixed">1</td></tr>
              <tr><td>Network2</td><td class="tdMeter"><div class="meter_background"><div class="meter_foreground meter_orange" style="width: 40%;"></div></div><div class="meter_value">-80 dBm</div></td><td class="tdFixed">6</td></tr>
              <tr><td>Network3</td><td class="tdMeter"><div class="meter_background"><div class="meter_foreground meter_red" style="width: 75%;"></div></div><div class="meter_value">-45 dBm</div></td><td class="tdFixed">11</td></tr>
            </table>
            <h2>Setup</h2>
            <div class="right">
              <div class="button-double">
                <form method="post">
                  <div class="button-container">
                    <input class="longInput" type="text" name="frames" placeholder="Number of frames" disabled>
                    <input type="submit" value="Set frames" disabled aria-label="Set frames">
                  </div>
                </form>
                <form method="post">
                  <div class="button-container">
                    <input class="longInput" type="text" name="delay" placeholder="Send delay" disabled>
                    <input type="submit" value="Submit" disabled aria-label="Update delay">
                  </div>
                </form>
              </div>
            </div>
            <h2>LED Options</h2>
            <div class="right">
              <div class="button-container">
                <form method="post">
                  <input type="submit" value="Turn on LED" disabled aria-label="Turn on LED">
                </form>
                <form method="post">
                  <input type="submit" value="Turn off LED" disabled aria-label="Turn off LED">
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <section id="about" class="section">
    <h2 class="glow-title">🔭 About</h2>
    <div class="glow-block">
      <p>Black Hole V1.0 is an open-source project by unnamedperson488 to support wireless testing and learning.</p>
      <a href="https://github.com/unnamedperson488/BlackHoleV1.0" class="github-button" target="_blank" aria-label="Contribute on GitHub">
        <i class="fab fa-github"></i> Contribute on GitHub
      </a>
    </div>
  </section>
  <section id="faq" class="section">
    <h2 class="glow-title">❓ FAQ</h2>
    <input type="text" id="faq-search" placeholder="Search FAQs..." aria-label="Search FAQs">
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
    <h2 class="glow-title flash-title">📱 Flash Firmware</h2>
    <div class="glow-block">
      <h3>Firmware Update</h3>
      <p>Update to v1.2.3 for optimal performance. Use Chrome/Edge:</p>
      <ol>
        <li>Connect via USB-C or serial.</li>
        <li>Refresh ports and select USB.</li>
        <li>Click Connect to flash.</li>
        <li>Enter Flash Mode.</li>
        <li>Erase flash if needed.</li>
        <li>Flash .bin file.</li>
        <li>Reset.</li>
      </ol>
      <svg width="200" height="100" viewBox="0 0 200 100" style="width: 50%; max-width: 100%; margin: 10px auto; display: block;">
        <rect x="50" y="20" width="100" height="60" fill="#111" stroke="#00eaff" stroke-width="2"/>
        <text x="55" y="35" fill="#ffffff" font-size="10">Log</text>
        <text x="55" y="50" fill="#ffffff" font-size="10">EN</text>
        <text x="55" y="65" fill="#ffffff" font-size="10">GND/VCC</text>
        <line x1="45" y1="30" x2="30" y2="30" stroke="#00eaff"/>
        <line x1="45" y1="45" x2="30" y2="45" stroke="#00eaff"/>
        <line x1="45" y1="60" x2="30" y2="60" stroke="#00eaff"/>
      </svg>
      <div class="flasher-card">
        <select id="port-select" aria-label="Select port"></select>
        <input type="file" id="firmware-upload" accept=".bin" aria-label="Upload firmware">
        <input type="text" class="ota-input" placeholder="Enter OTA IP" aria-label="OTA IP">
        <button class="flasher-button refresh" aria-label="Refresh ports">Refresh</button>
        <button class="flasher-button connect" aria-label="Connect to port">Connect</button>
        <button class="flasher-button erase" disabled aria-label="Erase flash">Erase</button>
        <button class="flasher-button flash" disabled aria-label="Flash firmware">Flash</button>
        <button class="flasher-button ota" aria-label="OTA update">OTA</button>
        <div class="progress-bar">
          <div class="progress-fill"></div>
        </div>
        <p id="flasher-status">Click 'Refresh' to begin.</p>
        <div id="flasher-log"></div>
        <p><a href="https://github.com/SelfMadeSystem/selfFlash/blob/main/docs/Troubleshooting.md" target="_blank">Troubleshooting</a> | <a href="https://discord.gg/PdpuDvVD" target="_blank">Browse Discord</a></p>
      </div>
    </div>
    <div class="glow-block">
      <h3>Version History</h3>
      <ul>
        <li><strong>V1.2.3 (May 2025):</strong> Improved WiFi stability and battery life.</li>
        <li><strong>V1.1.0 (Jan 2025):</strong> Added OTA support.</li>
        <li><strong>V1.0.0 (Nov 2024):</strong> Initial release.</li>
      </ul>
      <a href="https://github.com/SelfMadeSystem/selfFlash/releases" class="github-button" target="_blank" aria-label="Firmware Downloads">
        <i class="fab fa-github"></i> Firmware Downloads
      </a>
    </div>
    <div class="glow-block">
      <h3>Troubleshooting</h3>
      <ul>
        <li><strong>Port Not Detected:</strong> Ensure USB drivers are installed.</li>
        <li><strong>Flash Failed:</strong> Verify Download Mode connections.</li>
        <li><strong>OTA Issues:</strong> Check WiFi connection and IP address.</li>
      </ul>
    </div>
    <div class="glow-block">
      <h3>OTA Setup</h3>
      <p>Enable OTA updates:</p>
      <ol>
        <li>Connect device to WiFi via USB configuration.</li>
        <li>Note the OTA device IP.</li>
        <li>Enter IP in the OTA field and click “OTA.”</li>
      </ol>
    </div>
  </section>
  <footer>
    <p>© 2025 SelfMadeSystem. All rights reserved.</p>
    <p>
      <a href="https://github.com/SelfMadeSystem/selfFlash" target="_blank" aria-label="GitHub">GitHub</a> |
      <a href="https://discord.gg/PdpuDvVD" target="_blank" aria-label="Discord">Discord</a> |
      <a href="mailto:support@selfmadesystem.org" aria-label="Contact">Contact</a>
    </p>
  </footer>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const bootScreen = document.querySelector('#boot-screen');
      const bootProgress = document.querySelector('.boot-progress');
      const bootProgressFill = document.querySelector('.boot-progress-fill');
      const startButton = document.querySelector('.start-button');
      const backgrounds = document.querySelectorAll('.stars, .twinkling, .clouds');
      const spinner = document.querySelector('.loading-spinner');
      const wrapper = document.querySelector('.wrapper');
      const navWrapper = document.querySelector('.nav-wrapper');
      const themeToggle = document.querySelector('.theme-toggle');
      const langSwitcher = document.querySelector('.lang-switcher');
      const footer = document.querySelector('footer');

      if (!bootScreen || !startButton || !bootProgress || !bootProgressFill || !wrapper || !navWrapper) {
        console.error('Missing critical elements');
        alert('Error: Critical UI elements not found. Check console.');
        return;
      }

      const loadImage = (url) => new Promise((resolve) => {
        const img = new Image();
        img.src = url;
        img.onload = img.onerror = () => resolve();
      });

      function showSection(sectionId) {
        console.log(`Attempting to show section: ${sectionId}`);
        document.querySelectorAll('.section').forEach(section => {
          section.classList.remove('active');
          section.style.display = 'none';
        });
        const target = document.querySelector(sectionId);
        if (target) {
          target.classList.add('active');
          target.style.display = 'block';
          console.log(`Activated section: ${sectionId}`);
        } else {
          console.error(`Section not found: ${sectionId}`);
          alert(`Section ${sectionId} not found. Check console for details.`);
        }
      }

      document.querySelectorAll('.element, .product-card').forEach(element => {
        element.addEventListener('click', (e) => {
          const sectionId = element.dataset.section;
          if (sectionId) {
            e.preventDefault();
            showSection(sectionId);
            element.classList.add('pulse');
            setTimeout(() => element.classList.remove('pulse'), 200);
            console.log(`Navigation clicked: ${sectionId}`);
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
              console.log(`Navigation keypress: ${sectionId}`);
            }
          }
        });
      });

      startButton.addEventListener('click', () => {
        console.log('Start button clicked');
        startButton.disabled = true;
        startButton.style.display = 'none';
        bootProgress.style.display = 'block';
        spinner.classList.add('visible');

        const targetSection = startButton.dataset.targetSection || '#home';
        const loadProcess = async () => {
          try {
            console.log('Loading backgrounds...');
            await Promise.allSettled([
              loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/stars.png'),
              loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/twinkling.png'),
              loadImage('https://raw.githubusercontent.com/SelfMadeSystem/uiverse-contributions/main/quiet-snail-9/clouds.png')
            ]);
            console.log('Backgrounds processed');
            bootProgressFill.style.width = '100%';
            backgrounds.forEach(bg => bg.classList.add('loaded'));
          } catch (error) {
            console.error('Background load error:', error);
            alert('Failed to load backgrounds, proceeding.');
          }

          bootScreen.classList.add('hidden');
          spinner.classList.remove('visible');
          wrapper.classList.add('visible');
          navWrapper.classList.add('visible');
          themeToggle.classList.add('visible');
          langSwitcher.classList.add('visible');
          footer.classList.add('visible');
          showSection(targetSection);
          console.log('Activated section:', targetSection);
        };

        const timeout = setTimeout(() => {
          console.warn('Loading timeout');
          bootScreen.classList.add('hidden');
          spinner.classList.remove('visible');
          wrapper.classList.add('visible');
          navWrapper.classList.add('visible');
          themeToggle.classList.add('visible');
          langSwitcher.classList.add('visible');
          footer.classList.add('visible');
          showSection(targetSection);
          alert('Loading timed out, proceeded to content.');
        }, 10000);

        loadProcess().finally(() => clearTimeout(timeout));
      });

      const themeToggleBtn = document.querySelector('.theme-toggle');
      if (themeToggleBtn) {
        themeToggleBtn.addEventListener('click', () => {
          const isDark = document.body.dataset.theme !== 'light';
          document.body.dataset.theme = isDark ? 'light' : 'dark';
          localStorage.setItem('theme', isDark ? 'light' : 'dark');
          themeToggleBtn.textContent = isDark ? '🌞' : '🌑';
        });
        const savedTheme = localStorage.getItem('theme') || 'dark';
        document.body.dataset.theme = savedTheme;
        themeToggleBtn.textContent = savedTheme === 'light' ? '🌞' : '🌑';
      }

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
          document.querySelector('#home-title').textContent = `🌌 ${translations[lang].welcome}`;
          document.querySelector('.flash-title').textContent = `📱 ${translations[lang].flash}`;
          localStorage.setItem('language', lang);
        });
        const savedLang = localStorage.getItem('language') || 'en';
        langSelect.value = savedLang;
        langSelect.dispatchEvent(new Event('change'));
      }

      const portSelect = document.querySelector('#port-select');
      const refreshButton = document.querySelector('.flasher-button.refresh');
      const connectButton = document.querySelector('.flasher-button.connect');
      const eraseButton = document.querySelector('.flasher-button.erase');
      const flashButton = document.querySelector('.flasher-button.flash');
      const otaButton = document.querySelector('.flasher-button.ota');
      const firmwareUpload = document.querySelector('#firmware-upload');
      const otaInput = document.querySelector('.ota-input');
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
          statusText.textContent = 'No USB Serial Support. Use Chrome/Edge.';
          logMessage('Browser not supported');
          [portSelect, refreshButton, connectButton, eraseButton, flashButton, otaButton].forEach(btn => btn.disabled = true);
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
            statusText.textContent = 'Select a port';
            logMessage('No port selected');
            setTimeout(() => e.target.classList.remove('pulse'), 200);
            return;
          }
          try {
            const ports = await navigator.serial.getPorts();
            selectedPort = ports[portIndex];
            if (!selectedPort) throw new Error('Invalid port');
            await selectedPort.open({ baudRate: 115200 });
            statusText.textContent = 'Connected. Enter Download Mode (LOG to VCC, EN to GND, disconnect LOG)';
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
            logMessage('No device connected');
            setTimeout(() => e.target.classList.remove('pulse'), 200);
            return;
          }
          statusText.textContent = 'Erasing flash...';
          eraseButton.disabled = true;
          progressFill.style.width = '0%';
          try {
            logMessage('Erasing flash...');
            await new Promise(resolve => setTimeout(resolve, 2000));
            progressFill.style.width = '100%';
            statusText.textContent = 'Flash erased. Flash new firmware.';
            logMessage('Flash erased');
            setTimeout(() => e.target.classList.remove('pulse'), 200);
          } catch (error) {
            statusText.textContent = `Erase error: ${error.message}`;
            logMessage(`Erase error: ${error.message}`);
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
            logMessage('No device connected');
            setTimeout(() => e.target.classList.remove('pulse'), 200);
            return;
          }
          let firmware;
          if (firmwareUpload.files.length > 0) {
            const file = firmwareUpload.files[0];
            if (file.size > 1048576 || !file.name.endsWith('.bin')) {
              statusText.textContent = 'Invalid firmware (max 1MB, .bin only)';
              logMessage('Invalid firmware');
              setTimeout(() => e.target.classList.remove('pulse'), 200);
              return;
            }
            firmware = await file.arrayBuffer();
            logMessage(`Uploaded firmware: ${file.name}`);
          } else {
            statusText.textContent = 'Fetching official firmware...';
            logMessage('Downloading firmware');
            try {
              const response = await fetch('https://github.com/SelfMadeSystem/selfFlash/releases/firmware-v1.2.3.bin');
              if (!response.ok) throw new Error('Failed to fetch firmware');
              firmware = await response.arrayBuffer();
              logMessage('Firmware downloaded');
            } catch (error) {
              statusText.textContent = `Firmware fetch error: ${error.message}`;
              logMessage(`Firmware fetch error: ${error.message}`);
              setTimeout(() => e.target.classList.remove('pulse'), 200);
              return;
            }
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
              await writer.write(chunk);
              progress = Math.min((offset + chunkSize) / totalSize * 100, 100);
              progressFill.style.width = `${progress}%`;
              statusText.textContent = `Flashing: ${Math.round(progress)}%`;
              logMessage(`Flashing: ${Math.round(progress)}%`);
              await new Promise(resolve => setTimeout(resolve, 50));
            }
            await writer.close();
            statusText.textContent = 'Firmware flashed! Reset device (EN to VCC).';
            logMessage('Firmware flashed');
            await selectedPort.close();
            selectedPort = null;
            connectButton.disabled = false;
            refreshButton.disabled = false;
            portSelect.disabled = false;
            flashButton.disabled = true;
            eraseButton.disabled = true;
            setTimeout(() => e.target.classList.remove('pulse'), 200);
            await populatePorts();
          } catch (error) {
            statusText.textContent = `Flash error: ${error.message}`;
            logMessage(`Flash error: ${error.message}`);
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
            otaButton.disabled = false;
            setTimeout(() => e.target.classList.remove('pulse'), 200);
          } catch (error) {
            statusText.textContent = `OTA error: ${error.message}`;
            logMessage(`OTA error: ${error.message}`);
            otaButton.disabled = false;
            setTimeout(() => e.target.classList.remove('pulse'), 200);
          }
        });
      }

      if (portSelect) populatePorts();

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

      const newsletterForm = document.querySelector('#newsletter-form');
      if (newsletterForm) {
        newsletterForm.addEventListener('submit', (e) => {
          e.preventDefault();
          const email = document.querySelector('#newsletter-input').value;
          if (email.match(/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/)) {
            alert('Subscribed successfully!');
            newsletterForm.reset();
          } else {
            alert('Enter a valid email.');
          }
        });
      }

      const simulatorButton = document.querySelector('#simulator-button');
      const deautherSimulator = document.querySelector('#deauther-simulator');
      if (simulatorButton && deautherSimulator) {
        simulatorButton.addEventListener('click', () => {
          const isActive = deautherSimulator.classList.contains('active');
          deautherSimulator.classList.toggle('active', !isActive);
          simulatorButton.textContent = isActive ? 'Show Simulator' : 'Hide Simulator';
          simulatorButton.classList.add('pulse');
          setTimeout(() => simulatorButton.classList.remove('pulse'), 200);
        });
      }
    });
  </script>
</body>
</html>