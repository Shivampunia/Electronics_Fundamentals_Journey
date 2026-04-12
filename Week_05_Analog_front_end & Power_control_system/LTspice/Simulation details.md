# LTspice Simulations – Week 5

## Overview
This section documents the simulation work performed to understand and validate the behaviour of JFETs, MOSFETs, and their practical circuit applications.

The simulations directly support the design and implementation of the **Analog Front-End and Power Control PCB**.

---

## 1. JFET Device Characteristics

### Transfer Characteristics (Id vs Vgs)

![JFET Transfer](jfet_transfer.png)

- Shows relationship between gate voltage and drain current  
- Confirms cutoff and active region behaviour  
- Used to estimate operating bias point  

---

### Output Characteristics (Id vs Vds)

![JFET Output](jfet_output.png)

- Demonstrates ohmic and saturation regions  
- Validates constant current behaviour in saturation  

---

## 2. JFET Biasing

### Self-Bias Configuration

![JFET Bias](jfet_self_bias.png)

- Establishes stable operating point without external gate supply  
- Verified:
  - Vg = 0V
  - Vs = 1.8mA ⤬ 1k = 1.8V
  - Vgs = -1.8V

- Ensures operation in saturation region for amplification  

---

## 3. JFET Amplifier Design

### Common Source Amplifier

![JFET CS](jfet_cs.png)

- Provides voltage amplification  
- Observations:
  - Output is inverted  
  - Voltage gain of cs amplifer: Av = gm*rd

---

### Cascaded Amplifier (CS + Source Follower)

![JFET Cascade](jfet_cascade.png)

- Stage 1: Voltage amplification (CS)  
- Stage 2: Buffering (Source follower)  

✔ High gain + low output impedance  
✔ Directly implemented in PCB analog front-end  

---

## 4. MOSFET Device Characteristics

### Id vs Vgs

![MOSFET VGS](mosfet_vgs.png)

- Shows threshold voltage behaviour  
- Identifies cutoff and active region  

---

### Id vs Vds

![MOSFET VDS](mosfet_vds.png)

- Confirms linear and saturation regions  
- Used for switching vs amplification decisions  

---

## 5. MOSFET Amplifier

![MOSFET Amplifier](mosfet_amp.png)

- Common source MOSFET amplifier  
- Similar behaviour to JFET CS stage  
- Used for understanding gain and biasing differences  

---

## 6. MOSFET as Switch (555 Timer Control)

![MOSFET Switch](mosfet_switch.png)

- MOSFET driven by 555 timer  
- Demonstrates digital switching behaviour  

✔ ON/OFF operation  
✔ Gate control via pulse signal  
✔ Matches PCB power switching block  

---

## Key Learnings

- JFET: High input impedance, stable analog amplification  
- MOSFET: Strong switching capability and scalable power control  
- Biasing is critical for stable operation  
- Cascaded stages improve signal quality and drive capability  
- Simulation validated before PCB implementation  

---

## Conclusion

The simulations provided a clear understanding of device physics and circuit behaviour, enabling confident transition from theory to practical PCB design.

All major functional blocks used in the PCB were first verified through LTspice.
