# LTspice Simulation Details – Week 01  
Rectification, Filtering and Regulation Behaviour

The purpose of simulation this week was not to design the final PCB directly, but to develop practical and graphical understanding of the concepts studied in theory.

Each simulation focused on observing waveform behaviour, voltage relationships, conduction intervals, and ripple characteristics.

## 1. Centre-Tap Full-Wave Rectifier

![Centre-tap full-wave rectifier output]()

This simulation was used to understand how full-wave rectification operates using a centre-tapped transformer.

### Observations

- Output frequency doubled to 100 Hz.
- Alternate diode conduction clearly visible.
- Ripple frequency = 2 Fin ( input frequency)
- rectifer input = 0.5Vp2 ( peak secondry volatge)
- Peak output ( ideal ) = 0.5 Vp2 ( peak secondry volatge)
- Dc output = 2Vp(out) / 𐍀
- Higher diode voltage stress observed.

### Learning Outcome

This clarified:

- The difference between half-wave and full-wave rectification.
- How current paths change between positive and negative cycles.

## 2. Bridge Rectifier

📷 *Insert bridge rectifier waveform screenshot here.*

This simulation compared bridge rectification against the centre-tap configuration.

### Observations

- Both half-cycles are utilised.
- Ripple frequency = 2 Fin ( input frequency)
- rectifer input = Vp2 ( peak secondry volatge)
- Peak output ( ideal ) = Vp2 ( peak secondry volatge)
- Output ripple frequency remains 100 Hz.
- Two diodes conduct in series during each half-cycle.
- Lower PIV requirement per diode compared to centre-tap.

### Learning Outcome

This made it clear why bridge rectifiers are more common in practical designs:

- Better transformer utilisation.
- Simplified transformer requirement (no centre tap).
- More uniform conduction behaviour.

---

## 3. Bridge Rectifier with Capacitor Input Filter

📷 *Insert filtered output waveform here.*  
📷 *Insert diode current waveform showing charging pulses here.*

This simulation introduced bulk capacitance and load current.

### Observations

- DC level increased towards peak voltage ( peak to peak filtering)
- Conduction occurred only near waveform peaks.
- Diode current appeared as narrow, high-amplitude pulses.
- Increasing capacitance reduced ripple but increased peak charging current.

### Learning Outcome

This was critical for practical understanding:

- Ripple depends on load current and capacitance and frequency.
- Large capacitors reduce ripple but stress the rectifier.
- Conduction angle reduces significantly with capacitor-input filters.
- Average load current is very different from peak diode current.

This directly influenced capacitor and rectifier selection in the PCB design.

## 4. Zener Regulator Under Ripple Conditions

📷 *Insert Zener regulation waveform under ripple here.*

This simulation was used to understand how ripple affects regulation.

### Observations

- Zener clamps voltage only when sufficient current flows.
- During ripple valley, regulation weakens first.
- Output stability depends on input minimum voltage.
- Dynamic resistance of Zener affects ripple rejection.

### Learning Outcome

This clarified:

- Regulation depends on maintaining minimum Zener current.
- Ripple directly impacts regulation stability.
- Valley voltage is more critical than peak voltage.

## 5. Zener with Additional Smoothing Capacitor

📷 *Insert Zener + capacitor waveform here.*

An additional capacitor was introduced to observe ripple reduction.

### Observations

- Output ripple reduced significantly.
- Voltage waveform became more stable.
- Transient response slowed slightly.

### Learning Outcome

This demonstrated:

- Capacitive smoothing improves ripple performance.
- Filtering can support regulation.
- There is always a trade-off between response speed and stability.

## Overall Simulation Insights

Across all simulations, the following practical understandings were developed:

- Full-wave rectification doubles ripple frequency.
- Capacitor-input filters create narrow, high-current conduction intervals.
- Peak diode current can be significantly higher than average load current.
- Ripple magnitude is determined by load current and capacitance.
- Regulation stability depends on minimum input voltage.
