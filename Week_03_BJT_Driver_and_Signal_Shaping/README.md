# Week 03 – BJT Driver & Biasing Board

This week focuses on moving from basic signal conditioning to active control using transistors. The aim is to understand how signals can be used to control real hardware through proper biasing and amplification.

Unlike previous work which dealt mainly with shaping signals, this board is designed to drive loads and amplify signals in a controlled and practical way.

## Objectives

- Understand BJT operation in cut-off, active and saturation regions  
- Design stable biasing networks  
- Use a transistor as a switch for load driving  
- Implement small-signal amplification using voltage divider bias  
- Study the effect of coupling and bypass capacitors  
- Connect theory (load line, Q-point) with real circuits  

## System Overview

The board is divided into three functional blocks:

### Block A – DC Biasing Lab  
Used to study transistor biasing and observe operating point stability through test points.

### Block B – Switch Driver  
Implements the transistor as a switch to control loads.

- Suitable for relay, motor or actuator control  
- Includes base current limiting and protection diode  
- Demonstrates cut-off and saturation behaviour  

### Block C – VDB Amplifier  
Implements a small-signal common emitter amplifier.

- Voltage divider bias for stable operation  
- Input/output coupling capacitors  
- Optional emitter bypass for gain control  

## Why This Board Matters

This is not just a learning circuit. It represents a shift from passive electronics to active control systems.

- Signals are no longer just shaped — they are used to control outputs  
- Circuits are capable of driving real components  
- Transistor behaviour is applied in practical scenarios  

This type of design is directly relevant to embedded systems, robotics and hardware control applications.

## LTspice Work

Simulations were used to understand behaviour before implementation:

- BJT output characteristics  
- Transistor switching behaviour  
- Load line and Q-point analysis  
- Base-biased and VDB amplifiers  
- Effect of bypass capacitor on gain  
- Multi-stage amplification basics  

## PCB Implementation

- Modular block-based layout  
- Clear signal flow and easy probing  
- Test points at key nodes  
- Short routing for signal integrity  
- Designed for practical experimentation  

## Key Takeaways

- Biasing defines how a transistor behaves  
- Switching and amplification are fundamentally different modes  
- Proper base current control is critical for reliable switching  
- Emitter resistor improves stability but reduces gain  
- Real-world circuits require trade-offs between gain, stability and power

## Files Structure

- `README.md` – Overview and system explanation  
- `LTspice/Simulation_Details.md` – Simulation results and observations  
- `PCB/PCB_Design_Details.md` – Design reasoning and layout  

## Summary

This board marks the transition from understanding signals to controlling systems. It introduces practical transistor usage for switching and amplification, forming a strong foundation for real-world electronics and embedded hardware design.

