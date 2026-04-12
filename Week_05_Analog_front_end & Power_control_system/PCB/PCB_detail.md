# Analog Front-End and Power Control Board

## Overview

This PCB integrates analog signal processing and power control into a unified system.  
It combines low-noise JFET amplification, MOSFET-based switching, and SCR-based protection.

The design follows a structured engineering workflow:
- Circuit design and theory
- LTspice simulation
- Mathematical validation
- PCB implementation with layout-level considerations
---
## 3D View

![3D PCB](pcb_3d.png)

---
## PCB Layout
| Dimensions            |  PCB layout  |
| :-------------------------: | :-------------------------: |
| ![Upside Down Labs BioAmp EXG Pill dimensions](graphics/board/v1.0/BioAmp-EXG-Pill-v1.0-dimensions.png)  | ![Upside Down Labs BioAmp EXG Pill schematic](graphics/docs/BioAmp-EXG-Pill-v1.0b-schematic.png) |

---
## Schematic

![Schematic](pcb_schematic.png)

---
# System Architecture

The PCB is divided into five functional blocks:

1. JFET Common Source Amplifier  
2. JFET Source Follower  
3. MOSFET Power Switching Block  
4. SCR Crowbar Protection  
5. Input/Output and Power Conditioning  

---
# 🔌 Power Architecture (IMPORTANT DESIGN DECISION)

## Split +12V Power Planes

The front copper layer contains **two separate +12V zones**:

### 1️⃣ Power Zone (High Current)
- Used by:
  - MOSFET switching block  
  - SCR protection block  
- Carries:
  - High current
  - Switching noise

---
### 2️⃣ Analog Zone (Low Noise)
- Used by:
  - JFET amplifier stages  
- Carries:
  - Small-signal analog currents

---
## Why separation is required

Switching circuits generate:
- Voltage spikes  
- High di/dt noise  
- Ground bounce  

If shared directly:

Noise_switching → Analog_signal

→ Results in distortion and unstable biasing

---
## Engineering Solution

- Two isolated +12V copper zones  
- Connected through controlled path (via filtering / routing)

---
## Result

✔ Reduced noise coupling  
✔ Stable analog operation  
✔ Improved signal integrity  

---
# 1️⃣ Analog Front-End (JFET)

## Common Source Amplifier

Provides voltage amplification.

### Gain

Av ≈ gm × RD

Where:
- gm = transconductance of JFET  
- RD = 1.8kΩ
---

### Biasing

VGS = VG − VS  
VS = ID × RS  

Condition:
VGS < 0  (required for N-channel JFET operation)

---
## Source Follower

- Output buffer  
- Low output impedance  
Av ≈ 1  (no voltage gain, acts as buffer)

---
# 2️⃣ MOSFET Switching Block

## Function

- Controls external load using MOSFET + 555 timer
Gate current:
I = V / R
Switching speed:
t ≈ R × C
- Gate resistor limits current  
- Prevents oscillation  

---

# 3️⃣ SCR Crowbar Protection

## Trigger Condition

Vtrigger ≈ Vzener + VBE  
Vtrigger ≈ 14V + 0.7V ≈ 14.7V

---

## Behaviour

- SCR turns ON  
- Shorts supply  
- Fuse blows  

✔ Protects entire system from overvoltage  

---

# 4️⃣ Power Conditioning

## Decoupling Network

### High-frequency

Capacitive reactance:

Xc = 1 / (2π f C)

Example:
100nF capacitor → low impedance at high frequency → filters noise

---

### Bulk

- 10µF, 47µF → transient handling  

---

## Result

✔ Stable supply  
✔ Reduced ripple  

---

# 5️⃣ PCB Layout Engineering

## Trace Width

Designed for ~1A:

| Type         | Width        |
|--------------|-------------|
| Power traces | 1–1.5 mm    |
| Signal traces| 0.2–0.3 mm  |

---

## Voltage Drop

Voltage drop:

Vdrop = I × R

For short PCB traces:
Vdrop < 50 mV  (negligible)

---
## Grounding Strategy

- Continuous ground plane  
- Short return paths  

✔ Minimises noise  

---
## Component Placement

- Analog and power sections physically separated  
- High-current loops minimised  
- Decoupling capacitors placed close to ICs  

---
## EMI Control

- Ferrite bead filtering  
- Reduced loop area  
- Controlled switching paths  

---
# 6️⃣ Link to Simulation

All functional blocks validated in LTspice:

- JFET amplifier  
- MOSFET switching  
- Biasing behaviour  

Refer:
👉 [simuation detial.md](Week_05_Analog_front_end & Power_control_system/LTspice/Simulation details.md)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_05_Analog_front_end%20%26%20Power_control_system/LTspice/Simulation%20details.md)

---

# Conclusion

This PCB demonstrates:

- Functional analog front-end design  
- Practical power switching implementation  
- Robust overvoltage protection  
- Intentional power domain separation  

The split power plane design ensures that switching noise does not degrade analog performance, making the system reliable for mixed-signal applications.
