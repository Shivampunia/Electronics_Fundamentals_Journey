# PCB Design Details – Week 02  
Diode & Signal Applications Board  

## 1. Design Objective

![Week02_Schematic](Images/week02_schematic.png)

This board was designed to implement and experimentally validate the diode-based signal conditioning circuits studied during Week 02.

The PCB integrates:

- Fixed clippers  
- Biased and combination clippers  
- Positive and negative clampers  
- Zener limiter  
- LED indication stage  
- Photodiode sensing stage  
- Local negative rail generation using TC7662A  

All functional blocks operate from a +5 V supply. A local negative rail is generated where required.

Signal paths are intentionally current-limited to ensure safe laboratory experimentation.

## 2. PCB Layout

![Week02_PCB_Layout](Images/week02_pcb_layout.png)

The PCB is organised into clearly defined functional blocks to reflect the schematic structure. Each signal-conditioning stage (clipper, clamper, Zener limiter, photodiode and LED blocks) is physically separated to minimise interference and allow independent testing.

High-impedance analogue nodes are kept short and isolated from the charge pump section to reduce switching noise coupling. The TC7662A negative rail generator is placed away from sensitive signal paths, with decoupling capacitors positioned close to its pins.

Power traces are wider than signal traces to ensure low impedance distribution of the +5 V rail. Input and output headers are aligned along the board edges to simplify laboratory probing and configuration. Silkscreen labelling clearly identifies each block and jumper to support repeatable experimentation.

## 3. Power Architecture

### Main Supply  
+5 V external input.

### Negative Rail Generation  
A TC7662A charge pump generates approximately −5 V from the +5 V rail.

- Input capacitor: 10 µF  
- Output capacitor: 10 µF  
- Local 0.1 µF decoupling  

The negative rail is used only for biased and combination clipping configurations.

The charge pump section is placed away from high-impedance analogue nodes to reduce switching noise coupling.

datasheet of charge pump in : !(charge_pump.pdf)

## 3. Clipper Block

The clipper block supports:

- Negative clipper  
- Positive clipper  
- Combination clipper  
- Biased clipping using ± rails  

### Component Values

- Series resistors: 10 kΩ  
- Load resistors: 100 kΩ  
- Diodes: 1N4148  

### Current Limiting

For a 10 V peak laboratory input:

I_max = 10 V / 10 kΩ = 1 mA

This remains well within safe operating limits for the 1N4148.

High-value load resistors minimise waveform distortion due to loading.

Jumpers (JP1–JP3) allow configuration selection without modifying the PCB.

## 4. Clamper Block

The clamper section performs DC level shifting of AC signals.

### Component Values

- Capacitors: 1 µF  
- Load resistors: 100 kΩ  
- Diodes: 1N4148  

### Time Constant

τ = R × C  
τ = 100 kΩ × 1 µF  
τ = 0.1 s  

For a 1 kHz signal:

T = 1 ms  

Since τ (100 ms) is significantly greater than T (1 ms), the capacitor retains charge between cycles, enabling stable clamping behaviour( stiff clamper).

JP4 allows selection of positive or negative clamping.

## 5. Zener Limiter Block

The Zener block demonstrates voltage limiting behaviour.

### Component Values

- Zener diode: 1N750 (≈ 5.1 V)  
- Series resistor: 2.2 kΩ  
- Load resistor: 10 kΩ  
- Capacitors: 10 µF and 0.1 µF(bypass cap)  

### Current Consideration

For a 10 V input:

I_Z ≈ (10 V − 5.1 V) / 2.2 kΩ ≈ 2.2 mA  

This allows safe Zener operation within the breakdown region under laboratory conditions.

The parallel capacitors provide low- and high-frequency filtering.

## 6. LED Block

The LED stage provides visual indication and demonstrates basic current limiting.

- Series resistor: 1 kΩ  
- Supply: 5 V  
- Typical LED forward voltage ≈ 2 V  

I_LED ≈ (5 − 2) / 1 kΩ ≈ 3 mA  

This ensures visible illumination without excessive current.

## 7. Photodiode Sensing Block

Photodiode: SFH205FA  

Configuration: reverse-biased detection.

- Load resistor: 100 kΩ  
- Small capacitor for noise filtering  

Output relationship:

V_out = I_photo × R  

The high-value resistor improves sensitivity for low-light conditions, while the capacitor reduces high-frequency noise.

## 8. Layout Considerations

- Functional blocks clearly separated on PCB.  
- Short signal paths in clipping networks.  
- Decoupling capacitors placed close to IC and Zener nodes.  
- Charge pump isolated from sensitive analogue nodes.  
- Clear silkscreen labelling for laboratory use.  
- Header-based I/O allows independent block testing.

## Real world application

- Analogue front-end development platform
- Educational hardware lab board
- Rapid prototyping board for signal conditioning
- Protection block tester before integrating into bigger systems
- Embedded system input protection validation tool

## Design Summary

This board translates theoretical diode behaviour into practical, testable hardware.

It demonstrates:

- Controlled current limiting  
- Safe laboratory operating margins  
- Local bias generation without dual external supply  
- Modular experimentation capability  
- Integration of multiple analogue diode applications on a single platform  

The design prioritises clarity, safety, and repeatable testing.
