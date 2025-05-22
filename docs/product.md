---
layout: default
title: Black Hole V1.0
permalink: /product/
---

<div class="product-page bg-black text-white min-h-screen px-6 py-12">

  <div class="max-w-4xl mx-auto">
    <h1 class="text-5xl font-bold text-center mb-10">Black Hole V1.0</h1>

    <!-- Product Card -->
    <div class="bg-gray-900 rounded-2xl p-6 shadow-xl mb-12">
      <h2 class="text-3xl font-semibold mb-4">Ultimate Dual-Band Deauther</h2>
      <p class="text-lg mb-4">
        The Black Hole V1.0 is a compact, high-performance dual-band deauther for both 2.4GHz and 5GHz Wi-Fi frequencies. Designed for ethical testing, education, and advanced hobbyist use, this board combines precision engineering with user control.
      </p>
      <p class="text-md text-gray-400 mb-6">Engineered by <strong>unnamedperson</strong></p>

      <ul class="list-disc list-inside mb-6">
        <li>ESP32 + BW16 dual chip support</li>
        <li>External SMA antenna ports for maximum signal power</li>
        <li>Custom power button, reset button, and LiPo battery charging</li>
        <li>Minimalist design, compact black 4-layer PCB</li>
        <li>Fully open-source with detailed flashing instructions</li>
      </ul>

      <a href="#firmware" class="inline-block bg-white text-black font-semibold px-4 py-2 rounded hover:bg-gray-200 transition">Jump to Firmware</a>
    </div>

    <!-- Technical Specs -->
    <div class="bg-gray-900 rounded-2xl p-6 shadow-lg mb-12">
      <h2 class="text-2xl font-semibold mb-4">Tech Specs</h2>
      <ul class="list-disc list-inside">
        <li>PCB: 4-layer, black, rectangular</li>
        <li>ESP32 (2.4GHz) with SMA antenna port</li>
        <li>BW16 (5GHz) with separate SMA antenna port</li>
        <li>Power button: black, centered</li>
        <li>Reset button: red tip, top-right corner</li>
        <li>LiPo battery charger integrated</li>
        <li>Case-ready design with protruding buttons</li>
      </ul>
    </div>

    <!-- Firmware Section -->
    <div id="firmware" class="bg-gray-900 rounded-2xl p-6 shadow-lg mb-12">
      <h2 class="text-2xl font-semibold mb-4">Firmware & Flashing</h2>

      <p class="mb-4">
        The Black Hole V1.0 runs on custom firmware designed to deliver precise control over deauth/jamming functions across dual bands. It supports real-time command execution, USB updating, and OTA (over-the-air) flashing.
      </p>

      <ol class="list-decimal list-inside mb-4">
        <li>Download the latest firmware from our <a href="https://github.com/unnamedperson488/BlackHoleV1.0/releases" class="text-blue-400 underline">GitHub releases</a>.</li>
        <li>Use <code>ESPHome-Flasher</code> or <code>esptool.py</code> to flash to the ESP32.</li>
        <li>Ensure the BW16 binary is also flashed using a compatible uploader.</li>
        <li>Power on the board using the center power button.</li>
      </ol>

      <p class="mb-2">Detailed guide: <a href="https://github.com/unnamedperson488/BlackHoleV1.0/blob/main/docs/flashing.md" class="text-blue-400 underline">Flashing Instructions</a></p>
    </div>

    <!-- Purchase -->
    <div class="bg-gray-900 rounded-2xl p-6 shadow-lg mb-12">
      <h2 class="text-2xl font-semibold mb-4">Buy Now</h2>
      <p class="mb-4">Price: <strong>$140 USD</strong></p>
      <a href="https://discord.gg/YOURSERVER" class="inline-block bg-green-500 text-white font-semibold px-4 py-2 rounded hover:bg-green-600 transition">Order via Discord</a>
    </div>

    <!-- Social Buttons -->
    <div class="bg-gray-900 rounded-2xl p-6 shadow-lg mb-12">
      <h2 class="text-2xl font-semibold mb-4">Follow & Support</h2>
      <div class="flex gap-4 flex-wrap">
        <a href="https://github.com/unnamedperson488" class="bg-white text-black px-4 py-2 rounded hover:bg-gray-200">GitHub</a>
        <a href="https://instagram.com/unnamedperson488" class="bg-pink-600 text-white px-4 py-2 rounded hover:bg-pink-700">Instagram</a>
        <a href="https://youtube.com/@unnamedperson488" class="bg-red-600 text-white px-4 py-2 rounded hover:bg-red-700">YouTube</a>
        <a href="https://tiktok.com/@unnamedperson488" class="bg-black text-white px-4 py-2 rounded hover:bg-gray-800">TikTok</a>
        <a href="https://discord.gg/YOURSERVER" class="bg-indigo-600 text-white px-4 py-2 rounded hover:bg-indigo-700">Discord</a>
      </div>
    </div>

    <!-- Back to Home -->
    <div class="text-center mt-12">
      <a href="/" class="text-blue-400 underline">← Back to Home</a>
    </div>

  </div>
</div>
