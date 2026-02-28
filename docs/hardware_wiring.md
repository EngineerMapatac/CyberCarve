## 🔌 Hardware Wiring & Pinout Guide

To bring CyberCarve to life, the Arduino Uno and CNC Shield V3 handle all the logic and power distribution. Make sure the power is completely disconnected before wiring anything.

# 1. Stepper Motor Drivers (A4988 or DRV8825)
Insert the drivers into the X, Y, and A slots on the CNC Shield.

Important: Pay close attention to the orientation! The EN (Enable) pin on the driver must align with the EN pin on the shield. Plugging these in backward will instantly destroy the driver.

Dual Y-Axis Cloning: Since laser engravers typically use two motors for the Y-axis (one on each side), you need to clone the Y-axis to the A-axis. Place two jumper caps on the Y pins of the blue axis-cloning block located in the center of the shield.

# 2. Stepper Motor Connections
Connect your NEMA 17 stepper motors to the four-pin headers next to each driver.
| Axis | Motor | CNC Shield Header |
| :--- | :--- | :--- |
| X-Axis | Laser Head Carriage | X |
| Y-Axis 1 | Left Gantry Motor | Y |
| Y-Axis 2 | Right Gantry Motor | A (Cloned from Y) |
| Z-Axis | Optional (for motorized focus) | Z |

# 3. Laser Module (PWM / TTL Control)
This is the most critical connection for a laser engraver. GRBL v1.1 uses Variable Spindle Speed to control the laser's power intensity via PWM (Pulse Width Modulation).

GRBL v1.1 Update: In GRBL v1.1, the PWM output was moved to Arduino Pin 11.

Where to plug it in: On the standard CNC Shield V3, Pin 11 is labeled as Z+ or Z-Endstop (in the white endstop block). Connect your laser's PWM/TTL wire to the Z+ signal pin, and the laser's GND to the adjacent ground pin.

Do not use the SpnEn (Spindle Enable) pin for the laser if you want variable power (grayscale engraving).

# 4. Limit Switches (Endstops)
Limit switches are highly recommended for the "Homing" feature, allowing CyberCarve to know its exact physical boundaries.
| Switch | CNC Shield Pins (White Block) |
| :--- | :--- |
| X-Min | X+ or X- and GND |
| Y-Min | Y+ or Y- and GND |

# 5. Power Supply
Logic Power: The Arduino Uno gets its 5V logic power via the USB cable connected to your computer.

Motor Power: Connect your 12V or 24V power supply directly to the large blue screw terminal on the CNC Shield labeled 12-36V. Never attempt to power the stepper motors through the Arduino's barrel jack or USB.