# ⚡ CyberCarve

A custom-built, Arduino-controlled laser engraver capable of cutting and engraving wood, leather, and acrylic. This system integrates hardware assembly, firmware configuration, and a complete software toolchain, developed as a 3rd-year Computer Engineering hardware project.

---

## 📋 Table of Contents
- [Features](#-features)
- [System Architecture](#️-system-architecture)
- [Bill of Materials (BoM)](#-bill-of-materials-bom)
- [Software Toolchain](#-software-toolchain)
- [Installation & Setup](#-installation--setup)
- [Safety Warnings](#️-safety-warnings)
---

## ✨ Features
* **Precision Routing:** Driven by NEMA 17 stepper motors for accurate XY-axis positioning.
* **Firmware:** Runs on custom-configured GRBL for real-time G-code execution.
* **Working Area:** [e.g., 300mm x 300mm]
* **Laser Module:** [e.g., 5.5W Optical Power Diode Laser]

---

## 🏗️ System Architecture


* **Controller:** Arduino Uno with a CNC Shield V3.
* **Motor Drivers:** A4988 / DRV8825 stepper drivers.
* **Firmware:** GRBL v1.1.
* **Communication:** Serial via USB.

---

## 🛒 Bill of Materials (BoM)

| Component | Quantity | Notes |
| :--- | :---: | :--- |
| Arduino Uno | 1 | Main microcontroller |
| CNC Shield V3 | 1 | Expansion board for motor drivers |
| NEMA 17 Stepper Motors | 3 | X and dual Y-axis |
| A4988 Stepper Drivers | 3 | Microstepping control |
| [Insert Wattage] Laser Diode | 1 | With TTL/PWM control board |
| 12V / 24V Power Supply | 1 | Ensure sufficient amperage (e.g., 10A) |
| Aluminum Extrusions | Lot | V-slot 2020/2040 for the frame |
| GT2 Timing Belts & Pulleys | Lot | For precision axis movement |

---

## 💻 Software Toolchain
1. **Design:** Inkscape / AutoCAD (Vector creation)
2. **CAM / G-Code Generation:** LaserGRBL or LightBurn
3. **Sender:** Universal G-Code Sender (UGS)

---

## 🚀 Installation & Setup
### Cloning the Repository

```
git clone [https://github.com/EngineerMapatac/CyberCarve.git](https://github.com/EngineerMapatac/CyberCarve.git)
cd CyberCarve

```

---
## Flashing the Firmware

1. Download the GRBL library.

2. Open the Arduino IDE, go to Sketch -> Include Library -> Add .ZIP Library, and select the downloaded file.

3. Open File -> Examples -> grbl -> grblUpload.

4. Connect the Arduino Uno and upload the sketch.

---

## ⚠️ Safety Warnings

READ BEFORE OPERATING:

- Eye Protection: ALWAYS wear laser safety goggles rated for your specific laser wavelength (e.g., 450nm OD4+).

- Ventilation: Melting and burning materials release toxic fumes. Operate in a well-ventilated area or build a fume extractor.

- Fire Hazard: Never leave an active laser unattended. Keep a fire extinguisher nearby.

---

> Documented and built by John Ramil Mapatac