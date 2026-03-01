# Week 02 – Diode Fundamentals & Signal Shaping

## Theory Scope Covered

This week focused on non-linear semiconductor behaviour and practical signal shaping techniques.

Topics studied and validated:

- Diode V–I characteristic
- Forward and reverse conduction behaviour 
- clipper (Biased clippers)
- Combination clipper (window limiter)
- Clamper circuits (DC level shifting)
- Zener diode breakdown behaviour
- Zener regulation principles
- LED current control
- Photodiode sensing behaviour
- Schottky vs silicon diode characteristics
- Basic optocoupler understanding

The emphasis was on waveform behaviour, conduction regions, and real-world signal conditioning applications.

## Practical Objective

The goal of this week was to understand how diodes are used beyond rectification:

- Voltage limiting
- Signal protection
- Level shifting
- Amplitude window control
- Basic sensing interfaces

a consolidated signal-conditioning PCB was designed to implement these behaviours in hardware.

## LTspice Validation

Simulations were performed to visualise:

- Diode exponential conduction curve
- Clipping behaviour 
- Biased clipping threshold shifting
- Window limiting using dual diodes ( comnbination clipper )
- Clamper DC level shifting
- Zener breakdown region behaviour

The simulations were used to develop waveform-level intuition before PCB implementation.

Detailed simulation observations are documented in:

→ `LTspice/Simulation_Details.md`

## Hardware Implementation

A dedicated **Diode & Signal Applications Board** was designed containing the following functional blocks:

### 1. Clipper Block
- Positive and negative clipping
- Biased clipping using reference voltage
- Combination clipper (window limiter)

### 2. Clamper Block
- Positive and negative clamper
- RC time-constant behaviour

### 3. Zener Limiter Block
- Zener-based voltage limiting
- Ripple interaction study

### 4. Photo Sensing Block
- Photodiode signal generation
- Basic light-to-voltage conversion concept

### 5. LED Block
- Current-limited LED driver
- Visual signal indication

### 6. Input / Power Block
- 5 V supply interface
- Modular header connections
- Test points for waveform probing

This board allows practical experimentation with non-linear devices and signal conditioning techniques.

Detailed schematic reasoning and layout considerations are documented in:

→ `PCB/PCB_Design_Details.md`

## Engineering Focus This Week

- Understanding Diode circuits and special purpose diodes 
- Identifying conduction thresholds
- Observing waveform distortion mechanisms
- Studying DC shifting and amplitude limiting
- Translating theoretical diode models into practical PCB implementation

This week established the foundation for signal conditioning, protection circuits, and sensor interface design.
