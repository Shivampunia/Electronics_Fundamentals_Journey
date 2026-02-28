# Week 01 – Rectification & Linear Power Supply

## Theory Scope Covered

This week focused on AC–DC conversion and basic linear regulation:

* Full-wave rectification (center-tap and bridge)
* RMS to peak voltage conversion
* Peak Inverse Voltage (PIV)
* Capacitor input filtering
* Ripple estimation and load dependence
* Surge current during startup
* Zener regulation fundamentals
* Dropout condition and regulation limits

## LTspice Validation

The following circuits were simulated before hardware implementation:

* Center-tap full-wave rectifier
* Bridge rectifier
* Bridge + capacitor input filter
* Surge current behavior at startup
* Zener regulator under ripple conditions
* Zener + additional smoothing capacitor

Detailed simulation analysis and waveform screenshots are provided in:

→ LTspice/Simulation_Details.md

### Key Technical Observations

* Full-wave rectification doubled ripple frequency (2 × line frequency).
* Bridge topology reduced PIV requirement per diode compared to center-tap configuration.
* Capacitor input filter reduced ripple magnitude but introduced narrow high-current charging pulses.
* Ripple magnitude varied with load resistance and capacitance value.
* Zener regulation failed when the input valley voltage dropped below ( VZ + I Z(min)*RZ ).

Simulation results were used to size the bulk capacitor and evaluate regulation behavior before PCB design.

## Hardware Implementation

A 230V AC to regulated DC linear power supply board was designed and implemented.

### System Architecture

230V AC
→ Fuse protection
→ NTC inrush limiter
→ Step-down transformer
→ Bridge rectifier (KBU6A)
→ 10000µF bulk capacitor
→ Linear regulator stage
→ Regulated DC output

## Schematic Design Rationale

### 1. Bridge Rectifier (KBU6A)

* Selected for appropriate current rating and PIV margin.
* Chosen over center-tap configuration to eliminate center-tapped transformer requirement.
* Two-diode conduction path considered in voltage drop calculation.

### 2. Bulk Capacitor (10000µF)

* Sized to reduce ripple under expected load.
* Ripple estimated using:
* Tradeoff considered: lower ripple vs higher inrush current.

### 3. Inrush Current Control (NTC)

* Added to limit startup surge caused by large capacitor charging.
* Prevents excessive stress on bridge rectifier and transformer.

### 4. Linear Regulator Stage

* Implemented to improve load regulation beyond simple Zener-based control.
* Dropout headroom verified from rectified minimum voltage.
* Local decoupling capacitors placed near regulator pins.

### 5. Protection and Debugging

* Fuse included for primary-side protection.
* Test points added for measuring rectified voltage, ripple, and regulated output.

## PCB Design Considerations

The PCB layout translated theoretical design into practical constraints:

* High-current rectifier loop minimized to reduce parasitic inductance.
* Bulk capacitor placed physically close to bridge output.
* Clear separation between primary (mains) and secondary sides.
* Ground routing optimized for low impedance return in regulator section.
* Adequate trace width provided for charging current pulses.
* Thermal clearance considered around regulator.

Detailed calculations, margin analysis, and layout reasoning are provided in:

→ PCB/PCB_Design_Details.md

## Practical Use Case

This design represents a foundational linear power supply suitable for:

* Low-voltage analog circuit development
* Microcontroller supply (with proper heat management)
* Laboratory testing setups

It demonstrates the complete path from AC mains to regulated DC with isolation, filtering, and protection.

## Engineering Limitations Identified

* Linear regulation reduces efficiency under higher load currents.
* Thermal dissipation of regulator must be evaluated for sustained operation.
* Large bulk capacitance increases peak diode stress.
* No transient suppression (MOV) currently implemented on mains input.

## Next Improvements

* Add MOV for surge protection.
* Perform thermal analysis of regulator under load.
* Compare ripple and efficiency against SMPS topology.
* Add current sensing for load characterization.
