# Black Hole V1.0

**Black Hole V1.0** is a high-performance, dual-band WiFi deauther built for power, stealth, and modular upgrades. It utilizes the BW16 module with the RTL8720DN chip to disrupt WiFi networks on both **2.4GHz** and **5GHz** bands.

---

## 💣 Features

- Dual-band WiFi deauthing (2.4GHz + 5GHz)
- Based on [RTL8720DN-Deauther Firmware](https://github.com/tesa-klebeband/RTL8720dn-Deauther)
- Reset + Power (Boot) buttons
- Dual SMA antenna connectors for max signal output
- Compact, black 4-layer PCB design
- No OLED (stealth mode)
- Field-tested with aggressive performance

---

## 🧠 Specs

| Component         | Details                          |
|------------------|----------------------------------|
| Chipset          | RTL8720DN (BW16 Module)          |
| PCB              | 4-layer, black solder mask       |
| Antennas         | 2x SMA (2.4GHz + 5GHz)           |
| Power            | Micro USB / LiPo compatible      |
| Buttons          | Reset (Red) + Power (Black)      |
| Firmware         | RTL8720dn-Deauther (Web UI)      |

---

## 📸 Photos
_(Add images of your PCB, final build, UI, LEDs in use, etc.)_

---

## ⚡ Getting Started

1. Clone the firmware from:
   [RTL8720dn-Deauther Repo](https://github.com/tesa-klebeband/RTL8720dn-Deauther)

2. Flash instructions available in `/docs/FlashGuide.md`

3. Connect via browser to `192.168.1.1` and launch attacks.

---

## 📁 Repository Structure

```bash
BlackHoleV1.0/
├── hardware/            # Gerber files, BOM, KiCad/Altium source
├── firmware/            # Latest release or forked deauther firmware
├── docs/                # Flashing guide, install manual, photos
├── images/              # Board renders, LED indicators
└── README.md            # You are here
