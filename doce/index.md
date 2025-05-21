<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Black Hole V1.0</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background-color: #0b0b0b;
      color: #f8f8f8;
      font-family: 'Courier New', monospace;
    }
    .bios {
      font-size: 0.95rem;
      line-height: 1.6;
      white-space: pre-line;
      color: #00ff95;
      padding: 1rem;
      background: #000;
      border: 1px solid #333;
      border-radius: 0.5rem;
      margin-bottom: 2rem;
    }
    button:hover .text2 {
      display: inline;
    }
    .text2 {
      display: none;
    }
  </style>
</head>
<body class="px-4 sm:px-8 py-6">
  <!-- Header -->
  <header class="text-center mb-12">
    <h1 class="text-4xl md:text-6xl font-bold text-white">Black Hole V1.0</h1>
    <p class="text-gray-400 mt-2">Dual-Band Deauther by unnamedperson</p>
  </header>

  <!-- BIOS Boot Sim -->
  <section class="bios">
    Booting Black Hole V1.0...
    
    Initializing dual-band modules...
    ✓ 2.4GHz ESP32 module: OK
    ✓ 5GHz BW16 module: OK
    ✓ Power system: Online
    ✓ SMA Antennas: Connected
    ✓ Reset / Boot Buttons: Functional

    System Ready.
    Entering command terminal...
  </section>

  <!-- Media Section with TikTok Button -->
  <section class="text-center mb-16">
    <h2 class="text-3xl font-semibold mb-4">Connect with Me</h2>
    <div class="flex justify-center">
      <button class="flex items-center gap-2 px-4 py-2 bg-gray-900 border border-gray-700 rounded-lg hover:border-white transition">
        <span class="icon">
          <!-- TikTok SVG from your input -->
          <svg xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg" width="30" viewBox="0 0 120 120" height="30" fill="none">
            <!-- SVG paths from your snippet -->
            <defs>
              <linearGradient y2=".304922" y1="120.316" x2="119.695" x1="-.315704" gradientUnits="userSpaceOnUse" id="a">
                <stop stop-color="#111" offset="0"></stop>
                <stop stop-color="#111111" offset="1"></stop>
              </linearGradient>
            </defs>
            <circle cx="60" cy="60" r="60" fill="url(#a)"/>
            <!-- Simplified, full paths will be in final version -->
          </svg>
        </span>
        <span class="text-white">Follow me</span>
        <span class="text2 text-sm text-pink-500">1,2k</span>
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="text-center text-sm text-gray-600">
    <p>© 2025 Black Hole V1.0 — Engineered by unnamedperson</p>
    <p><a href="https://unnamedperson488.github.io/BlackHoleV1.0/" class="underline">Visit GitHub Pages</a></p>
  </footer>
</body>
</html>
