# PCB Design Details – Week 04  
Multi-Stage BJT Amplifier & Power Output Board

## 1. Objective

Design a complete analog signal chain:
Input → Amplify → Buffer → Power Output → Load  
Demonstrates conversion of a small signal into usable output power.

## 2. Application

- Audio amplifiers  
- Sensor front-end systems  
- Analog signal processing  

## 3. System Architecture
- Vin → CE Amplifier → Emitter Follower → Class-AB → Load

## 4. Schematic

![[Schematic](schematic.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4_sch.png)

## 5. PCB Layout

![[PCB Layout](pcb_layout.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4.png)

## 6. 3D View

![[PCB 3D](pcb_3d.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4_3D.png)

## 7. LTspice Simulation (Full Chain)

![[LTspice Full System](ltspice_simulation.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4_sim.png)

- Green → Input signal  
- Red → Final output  

👉 Confirms full signal amplification across all stages  

## 8. Stage Design

### Stage 1 — Swamped CE Amplifier

- IC ≈ 1 mA, mid-point bias  
- RC ≈ 4.7kΩ  
- RE: 470Ω (unbypassed) + 680Ω (bypassed)  
- Av ≈ RC / RE(unbypassed) ≈ 10

→ Stable voltage amplification  

### Stage 2 — Emitter Follower

- Gain ≈ 1  
- High input impedance  
- Low output impedance  

→ Buffer stage, prevents loading  

### Stage 3 — Class-AB Power Stage

- BD139 + BD140  
- Diode bias ≈ 1.4V  
- Ipeak ≈ 5V / 8Ω ≈ 0.6A

- Output capacitor ≈ 470µF  

→ Drives load with sufficient current  

## 9. Capacitors

- Input / coupling: 10µF  
- Emitter bypass: 100µF  
- Output: 470µF  

## 10. I/O and Test Points

- +12V supply ( from two pin screw terminal ) 
- Vin ( 100mV - 500mV peak , freq= 100Hz - 10KHz) from two pin header
- Vout ( 4 - 6V peak) from two pin header

## 11. Key Points

- Gain staged across blocks  
- Buffer ensures signal integrity  
- Class-AB enables power delivery  

## 12. Limitation

- No thermal compensation  
- No feedback network  
- No frequency optimization  

## Conclusion

This PCB implements a complete multi-stage amplifier system, demonstrating practical signal amplification and power delivery.
