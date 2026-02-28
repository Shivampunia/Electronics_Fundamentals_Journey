# PCB Design Details – Week 01  

AC–DC Linear Power Supply Board

## 1. Output Specification

- Output voltage: 12 V DC (regulated by MP1584 buck converter)  
- Maximum load current: 1 A  
- Input: 230 V AC, 50 Hz  

## 2. Transformer Selection

Secondary voltage: 12 V AC (RMS)

Peak secondary voltage:

```
V_peak = V_rms × 1.414
V_peak = 12 × 1.414
V_peak ≈ 17 V
```

This defines the maximum rectified voltage before diode drops.

Transformer rating selected:

- 12 V AC  
- ≥ 20 VA  

Output power requirement:

```
P_out = 12 V × 1 A
P_out = 12 W
```

20 VA provides sufficient thermal and regulation margin.

## 3. Bridge Rectifier Selection

Two diodes conduct per half-cycle.

```
V_drop ≈ 0.7 V × 2
V_drop ≈ 1.4 V
```

Peak DC after rectification:

```
V_DC_peak = 17 V − 1.4 V
V_DC_peak ≈ 15.6 V
```

### PIV Requirement

```
PIV ≈ 17 V
```

A rectifier rated ≥ 100 V was selected for safety margin.  
Current rating ≥ 2 A to tolerate capacitor charging pulses.

## 4. Bulk Capacitor Sizing

Capacitance: 10,000 µF  
Ripple frequency: 100 Hz (full-wave)

```
V_ripple = I / (f × C)
V_ripple = 1 A / (100 Hz × 0.01 F)
V_ripple ≈ 1 V
```

Minimum DC voltage after ripple:

```
V_min = 15.6 V − 1 V
V_min ≈ 14.6 V
```

This voltage feeds the buck converter input.

## 5. Buck Converter Regulation (MP1584)

The MP1584 is a high-efficiency DC–DC step-down converter rated up to 3 A.

Input voltage range (typical module):  
4.5 V – 28 V

Since the rectified voltage ranges approximately from 14.6 V to 15.6 V, it lies well within the operating range of the converter.

Unlike a linear regulator, the buck converter:

- Does not require dropout headroom calculation  
- Does not dissipate large power as heat  
- Operates with high efficiency (typically 85–92%)

Estimated power dissipation at 90% efficiency:

```
P_loss ≈ P_out × (1 / efficiency − 1)
P_loss ≈ 12 W × (1 / 0.9 − 1)
P_loss ≈ 1.3 W
```

Significantly lower than a linear regulator.

## 6. Bleeder Resistor (10 kΩ)

Purpose:

- Discharge bulk capacitor after power-off  
- Provide minimum load stability  

```
I = 12 V / 10000 Ω
I ≈ 1.2 mA
```

```
P = V² / R
P = 12² / 10000
P ≈ 0.014 W
```

0.25 W resistor selected for margin.

## 7. LED Indicator Resistor (2.2 kΩ)

Assuming LED forward voltage ≈ 2 V:

```
I_LED = (12 V − 2 V) / 2200 Ω
I_LED ≈ 4.5 mA
```

## 8. Surge Current Consideration

At power-up:

- Capacitor initially uncharged  
- High peak charging current  
- Limited primarily by transformer impedance  

Protection included:

- Input fuse  
- Series NTC thermistor  

## 9. Decoupling and Layout Considerations

- Large bulk capacitor placed close to bridge rectifier  
- Short high-current loop between transformer, rectifier and capacitor  
- Buck converter module positioned to minimise input loop area  
- Adequate copper width for 1 A current path  

## Key Design Conclusions

- 10,000 µF produces approximately 1 V ripple at 1 A load.  
- Rectified voltage remains well within MP1584 operating range.  
- Switching regulation significantly reduces thermal dissipation compared to linear regulation.  
- Bridge rectifier must tolerate high peak charging current.  
- Inrush and fault protection implemented.  
