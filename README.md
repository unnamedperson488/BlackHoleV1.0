# Black Hole V1.0
### Dual-Band Wi-Fi Deauther (2.4GHz + 5GHz)

**Black Hole V1.0** is an advanced Wi-Fi deauther and wireless auditing tool that supports both 2.4GHz and 5GHz frequencies. Built with both an ESP32 and BW16 (RTL8720DN) module, this device offers unmatched signal disruption capability for professional penetration testers and wireless researchers.

---

## 🧠 Features

- **Dual-Band Interference:** Supports both 2.4GHz (ESP32) and 5GHz (BW16)
- **Modular Antennas:** Two SMA ports for external foldable antennas
- **LiPo Battery Powered:** Rechargeable via USB-C using TP4056 with protection
- **Reset + Power Buttons:** Onboard controls for full manual operation
- **Premium Design:** 4-layer black PCB with custom silkscreen and protruding buttons
- **Open Source:** Full access to hardware design files and flashing tools

---

## 🧹 Parts List

| Part Name                         | Description                                         |
|----------------------------------|-----------------------------------------------------|
| **ESP32 Module**                 | 2.4GHz Wi-Fi + Bluetooth SoC                        |
| **BW16 Module (RTL8720DN)**      | 5GHz Wi-Fi + Bluetooth 5.0 module                   |
| **TP4056 Charging Board**        | USB-C LiPo charging and protection circuit          |
| **3.7V 300mAh LiPo Battery**     | Rechargeable lithium polymer battery                |
| **SMA Foldable Antennas**        | One for ESP32 (2.4GHz), one for BW16 (5GHz)         |
| **Red Momentary Button**         | Reset; protrudes slightly at top-right corner       |
| **Black Push Button**            | Power on/off; centered on PCB                       |
| **UL1571 Wire (26-32 AWG)**      | Internal connection wiring                          |
| **Rosin Core Solder Wire**       | For assembly and solder joints                      |
| **Heat Shrink Tubing**           | For insulation and securing battery/wires           |

---

## 📀 PCB Design Summary

- **Board Layers:** 4
- **Color:** Matte black
- **Size:** Rectangular, compact layout
- **Connectors:** 2 × SMA (external)
- **Buttons:**  
  - **Reset Button:** Red, small, top-right  
  - **Power Button:** Black, center of board
- **Silkscreen Label:**  
  ```
  BLACK HOLE V1.0  
  ENGINEERED BY unnamedperson
  ```

---

## ⚡ How to Flash Firmware

### 🔹 ESP32 Flashing

1. Hold the **boot button** (center) while pressing **reset**.
2. Connect to PC via USB-C.
3. Flash using [esptool.py](https://github.com/espressif/esptool), [PlatformIO](https://platformio.org/), or Arduino IDE.

Example:
```bash
esptool.py --chip esp32 --port COM3 write_flash 0x1000 firmware.bin
```

### 🔸 BW16 Flashing

1. Connect BW16's UART pins to a USB-to-TTL adapter.
2. Use [ambd_flash_tool](https://github.com/ambiot/ambd_flash_tool) or Ameba SDK to upload firmware.
3. Follow specific BW16 bootloader sequence instructions in [FLASHING.md](FLASHING.md).

---

## 📁 Project Structure

```
BlackHole-V1.0/
├── assets/                 # Images, renders, diagrams
├── firmware/               # ESP32 and BW16 firmware binaries
├── hardware/               # KiCAD files, schematics, gerbers
├── case/                   # STL/STEP for 3D-printable custom case
├── .github/workflows/      # CI/CD pipelines for auto builds
├── FLASHING.md             # Extended flashing instructions
├── LICENSE
├── README.md
└── .gitignore
```

---

## ⚠️ Legal & Ethical Use

**This project is intended solely for educational and authorized security testing purposes.**  
Do **NOT** use this tool on networks you do not own or have explicit permission to audit. Misuse of this tool may violate local, state, or federal laws.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Credits

- Designed and engineered by `unnamedperson`
- Community-sourced feedback and testing
- Powered by open-source hardware philosophy

---

## 💬 Contact & Community

Questions or feedback? Join our Discord server:  
👉 [https://discord.gg/YOUR-SERVER](https://discord.gg/YOUR-SERVER)
