# Week 04 – Multi-Stage Amplifier & Power Output System

## Objective

This week focuses on building a complete analogue signal chain instead of isolated circuits.

The goal was to design a system that can:

- Amplify a weak signal  
- Stabilise it across stages  
- Deliver usable power to a load

### PCB – Multi stage amplifier and power control system
| 3D View            |  PCB Layout  |
| :-------------------------: | :-------------------------: |
| ![3dview](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4_3D.png)| ![PCB Lyout](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_04_Multi-Stage_Amplifier_Board/PCB/PCB4.png)|

## System Overview

The amplifier is implemented as three cascaded stages:

### Stage 1 — Swamped CE Amplifier  
Provides voltage gain while maintaining stability using emitter degeneration.

### Stage 2 — Emitter Follower (Buffer)  
Reduces output impedance and prevents loading of the first stage.

### Stage 3 — Class AB Power Stage  
Delivers current to the load with improved efficiency and reduced crossover distortion.

## What This Board Represents

This is not just another circuit.

It is a complete signal chain:

**Signal → Amplify → Buffer → Drive Load**

Compared to previous work:

- PCB 2 → signal shaping  
- PCB 3 → control and switching  
- PCB 4 → full analogue system  

## Practical Relevance

This architecture is directly used in:

- Audio amplifier systems (preamp → buffer → power stage)  
- Sensor signal chains (sensor → amplifier → buffer → output)  
- Analogue front-end (AFE) design  

This is the level where circuits start becoming real systems.

## LTspice Work

### 1. Individual Stage Simulations

- Swamped CE amplifier  
- Emitter follower (CC)  
- Common base (CB)  
- Cascaded CE + CC amplifier  
- Darlington configuration  
- Zener follower  

Used to understand behaviour of each building block.

### 2. Full System Simulation

- Complete multi-stage amplifier simulated together  
- Verified signal flow across all stages  
- Observed gain, buffering and output drive capability  

## PCB Implementation

- All three stages integrated into a single board  
- Clear signal flow: input → gain → buffer → power stage  
- Separate sections for each stage  
- Test points for debugging  
- Power and I/O block for easy interfacing  

## Key Learning Outcomes

- Gain alone is not sufficient → buffering is required  
- Cascading stages introduces loading effects  
- Emitter follower is critical for impedance matching  
- Class AB stage improves efficiency and reduces distortion  
- System behaviour changes when stages are combined  

## Limitations (Current Stage)

- No detailed impedance matching optimisation  
- No frequency response tuning  
- No full gain distribution design across stages  
- Thermal performance of output stage not analysed  

## Summary

This board represents the transition from circuit-level understanding to system-level design.

It establishes the foundation for:

- Analogue front-end design  
- Audio systems  
- Sensor signal processing chains  
- Mixed-signal and embedded hardware systems  
