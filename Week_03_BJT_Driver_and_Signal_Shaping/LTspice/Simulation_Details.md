# LTspice Simulation Details – Week 03  
BJT Behaviour & Amplifier Design

The simulations performed this week focused on understanding transistor operation in both switching and amplification modes.  

Each circuit was analysed to study biasing behaviour, operating regions, gain characteristics, and signal amplification.

## 1. BJT Output Characteristics (Common Emitter)

![BJT Output Characteristics](bjt_output_characteristics.png)

### Observations

- Collector current increases with collector–emitter voltage initially, then becomes nearly constant.
- Each curve represents a different base current level.
- At low VCE, the transistor operates in saturation.
- At higher VCE, it enters the active region where IC is controlled by base current.

### Learning Outcome

This simulation clarified how a transistor transitions between saturation and active regions, and how base current controls collector current.

## 2. Transistor as a Switch

![Transistor as Switch](transistor_switch.png)

### Observations

- At low base voltage, the transistor remains in cut-off and collector voltage stays high.
- As base voltage increases beyond ~0.7 V, the transistor turns ON.
- Collector voltage drops sharply, indicating saturation.
- Transition between OFF and ON is rapid.

### Learning Outcome

This demonstrated how a transistor behaves as a digital switch, operating between cut-off and saturation regions.

## 3. Voltage Divider Bias (VDB) Load Line

![VDB Load Line](vdb_load_line.png)

### Observations

- The load line shows the relationship between IC and VCE for a given RC.
- Intersection of load line with transistor characteristics defines the Q-point.
- Changing emitter resistance shifts the operating point.
- Higher RE reduces collector current and improves stability.

### Learning Outcome

This simulation reinforced how biasing components set the operating point and control amplifier stability.

## 4. Base Biased Amplifier (With Coupling Capacitor)

![Base Biased Amplifier](base_biased_amp.png)

### Observations

- Output signal is amplified and inverted relative to input.
- Coupling capacitor blocks DC and passes AC signal.
- Output is centred around a DC operating point.
- Some distortion may appear if biasing is not optimal.

### Learning Outcome

This showed how coupling capacitors isolate DC levels while allowing AC amplification.

## 5. VDB Amplifier (Without Bypass Capacitor)

![VDB Amplifier Without Bypass](vdb_no_bypass.png)

### Observations

- Output is amplified but gain is limited.
- Emitter resistor introduces negative feedback.
- Signal remains stable with reduced distortion.
- Output amplitude is smaller compared to bypass case.

### Learning Outcome

This demonstrated how emitter degeneration improves stability at the cost of gain.

## 6. VDB Amplifier (With Bypass Capacitor)

![VDB Amplifier With Bypass](vdb_with_bypass.png)

### Observations

- Gain increases significantly compared to without bypass.
- AC signal bypasses emitter resistor through capacitor.
- Output amplitude is higher while DC bias remains unchanged.
- Slight increase in distortion may be observed.

### Learning Outcome

This showed how bypass capacitors increase AC gain while maintaining DC stability.

## 7. Multistage Amplifier

![Multistage Amplifier](multistage_amp.png)

### Observations

- Overall gain increases due to cascading stages.
- Output amplitude is significantly higher than input.
- Each stage contributes additional amplification.
- Coupling capacitors maintain DC isolation between stages.

### Learning Outcome

This demonstrated how multiple amplifier stages can be combined to achieve higher gain and signal conditioning.

These simulations established a clear understanding of transistor behaviour, biasing techniques, and practical amplifier design before implementing them on the PCB.
