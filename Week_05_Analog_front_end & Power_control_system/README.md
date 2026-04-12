# Week 5 – Analog Front end & Power Control Systems

## Overview
This week focused on a comprehensive study and practical implementation of active semiconductor devices, covering:

- JFET: device characteristics, biasing, and amplifier configurations  
- MOSFET: enhancement/depletion modes, amplifier design, and switching applications  
- Thyristor family: SCR, DIAC, TRIAC, IGBT and protection circuits  

The objective was to move beyond isolated concepts and build an understanding of how these devices are used in real electronic systems.

---

## Hardware Implementation

### PCB – Analog Front-End & Power Control Board
| 3D View            |  PCB Layout  |
| :-------------------------: | :-------------------------: |
| ![Upside Down Labs BioAmp EXG Pill dimensions](graphics/board/v1.0/BioAmp-EXG-Pill-v1.0-dimensions.png)  | ![Upside Down Labs BioAmp EXG Pill schematic](graphics/docs/BioAmp-EXG-Pill-v1.0b-schematic.png) |

## Practical Implementation

The concepts were validated through:

- LTspice simulations of amplifier and switching behaviour  
- Design and development of a **combined Analog Front-End and Power Control PCB**

---

## System-Level Design

A complete hardware system was designed integrating:

- Analog signal amplification (JFET-based stage)  
- Buffering and signal conditioning  
- MOSFET-based switching and control  
- SCR-based over-voltage protection  

This represents a transition from individual circuit blocks to **integrated analog + power system design**.

---

## Key Outcomes

- Developed understanding of voltage-controlled vs current-controlled devices  
- Analysed amplification, switching, and protection in a unified framework  
- Implemented a full signal-to-power chain on PCB  
- Strengthened practical design skills in simulation, component selection, and layout  

---

## Repository Structure

- `/LTspice` → device-level simulations and analysis  
- `/PCB` → schematic, layout, and hardware implementation  

---
