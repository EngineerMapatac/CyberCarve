### GRBL Configuration and Calibration

Here is the step-by-step solution to configure the GRBL firmware for the laser engraver setup. Open the console in your G-code sender (like LaserGRBL or UGS) and input these commands.

---

**Step 1: Enable Laser Mode**

By default, GRBL pauses momentarily when changing spindle speeds. For a laser, this causes burn marks at the corners of a design. Enable laser mode to make the power changes continuous.

Input: `$32=1`

---

**Step 2: Set Maximum and Minimum Spindle Speed (Laser Power)**

This maps the G-code `S` values to the PWM output on Pin 11. The standard maximum is 1000.


Input: `$30=1000`

Input: `$31=0`

---

**Step 3: Calculate and Set Steps per Millimeter**

For a standard NEMA 17 motor (1.8-degree step angle = 200 steps/revolution), using A4988 drivers with 1/16 microstepping, a GT2 timing belt (2mm pitch), and a 20-tooth pulley:

Steps per revolution = 200 * 16 = 3200 steps

Distance per revolution = 20 * 2 = 40.0000 mm

Steps per mm = 3200 / 40.0000 = 80.0000 steps/mm


Input X-axis: `$100=80.0000`

Input Y-axis: `$101=80.0000`

---

**Step 4: Set Maximum Feed Rate**

This defines the top speed of your X and Y axes in mm/min. For V-slot extrusions and belts, 5000 mm/min is a safe starting point.


Input X-axis: `$110=5000.0000`

Input Y-axis: `$111=5000.0000`

---

**Step 5: Set Acceleration**


This determines how fast the motors reach the maximum feed rate in mm/sec^2.


Input X-axis: `$120=500.0000`

Input Y-axis: `$121=500.0000`