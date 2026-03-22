# PCB Design Details – Week 03  
BJT Driver & Small Signal Amplifier Board  

## 1. Design Objective

![Week03_Schematic](Images/week03_schematic.png)

This board was designed to move from signal-level circuits to practical transistor-based control and amplification.

It implements:

- DC biasing for stable transistor operation  
- Transistor switch driver for real load control  
- Small signal CE amplifier  

All blocks operate from a +12 V supply and are structured for testing and understanding transistor behaviour in real conditions.

## 2. PCB Layout

![Week03_PCB_Layout](Images/week03_pcb_layout.png)

The PCB is organised into three main functional blocks with clear separation:

- Switch driver placed near output side for load connection  
- Amplifier section kept compact to reduce noise  
- Biasing block isolated for measurement  

Power traces are wider than signal traces, and test points are provided at key nodes (base, collector, emitter).

## 3. Block B — Switch Driver (Main Block)

This is the most important part of the board.

### Design Conditions

- Input: 5 V logic (MCU)  
- Input current: < 10 mA  
- Load supply: up to 12 V  
- Load current: up to ~300 mA  

### Operation

- Input HIGH → transistor ON (saturation) → load ON  
- Input LOW → transistor OFF → load OFF  

The transistor is used as a **switch (cut-off / saturation mode)**.

### Base Drive

IB ≈ (5 − 0.7) / 470 ≈ 9 mA  

Using forced beta:

β = 10 → IB ≈ IC / 10  

For ~100 mA load → IB ≈ 10 mA → design is acceptable.

### Protection

- Schottky flyback diode across load  
- Protects transistor from inductive voltage spikes  

### Key Insight

This block converts:

**Low-power logic signal → high-current load control**

This is directly usable in embedded systems.

## 4. Block A — DC Biasing

Voltage divider bias is used to set a stable operating point.

- Base voltage set using resistor divider  
- Emitter resistor stabilises current  
- Reduces dependence on transistor β  

This block is used to observe and verify Q-point stability in active region.

## 5. Block C — CE Amplifier

Voltage Divider Bias CE amplifier for small signal amplification.

### Features

- Coupling capacitors for AC signal  
- Optional emitter bypass capacitor  
- Standard CE configuration  

### Behaviour

- With bypass capacitor → high gain  
- Without bypass → lower gain, better stability  
- Output is inverted  

### Notes

- Low input impedance (~kΩ range)  
- Sensitive to loading  

## 6. Capacitors (Essential)

- Input capacitor → blocks DC, passes AC  
- Emitter bypass → increases gain  
- Output capacitor → isolates DC  
- Supply decoupling → reduces noise  

Values selected to support low-frequency signals (~20 Hz).

## 7. Layout Considerations

- Wide traces for +12 V supply  
- Short signal paths  
- Clear block separation  
- Test points for debugging  
- Clean ground return paths  

## Real World Application

- MCU-based relay / motor driver  
- Actuator control circuits  
- Basic analogue signal amplification  
- Pre-stage for sensor signal conditioning  
- Embedded hardware driver stage  

## Design Summary

- Block A → sets stable operating point  
- Block B → enables real-world load control  
- Block C → provides signal amplification  

This board represents the transition from understanding transistor behaviour to actually using it in practical systems.
