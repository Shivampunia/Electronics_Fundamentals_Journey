# LTspice Simulation Details – Week 02  
Diode Behaviour & Signal Shaping

The simulations performed this week were intended to build graphical and behavioural understanding of non-linear diode circuits.  

Each circuit was analysed to observe conduction regions, threshold behaviour, and waveform modification effects.

## 1. Diode V–I Characteristic (1N4148)

![[Diode V-I Curve](diode_iv_curve.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_02_Diode_Signal_Shaping/LTspice/diode%20I-V%20curve.png)

### Observations

- Forward conduction begins near 0.6–0.7 V.
- Current increases rapidly with small increases in forward voltage.
- Reverse region shows negligible current before breakdown.

### Learning Outcome

This simulation clarified the exponential nature of diode conduction and reinforced the concept of threshold voltage in practical circuits.

## 2. Positive Clipper

![Positive Clipper](positive_clipper.png)

### Observations

- When the input voltage goes positive, the diode becomes forward-biased. It acts like a closed switch (with a small forward voltage drop, typically ~0.7V for a 1N4148)
- negative half-cycle remains largely unaffected.
- Clipper will not work properly unless the series resistance Rs is much greater then bulk resistance and much smaller than load resistance Rl.

### Learning Outcome

- useful for signal shaping , circuit protection and communication

## 3. Biased Clipper

![[Biased Clipper](biased_clipper.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_02_Diode_Signal_Shaping/LTspice/biased%20clipper.png)

### Observations

- Clipping threshold shifts due to added DC reference.
- Conduction begins only after (V_bias + V_diode).
- Output waveform becomes asymmetrical.

### Learning Outcome

This showed how clipping levels can be controlled precisely using a reference voltage, enabling selective amplitude limiting.

## 4. Combination Clipper (Window Limiter)

![[Combination Clipper](combination_clipper.png)](https://github.com/Shivampunia/Electronics_Fundamentals_Journey/blob/main/Week_02_Diode_Signal_Shaping/LTspice/Combination%20clipper.png)

### Observations

- Signal is constrained between upper and lower voltage limits.
- Two diodes establish a defined voltage window.
- Output signal is Square wave
- Central portion of waveform remains undistorted.

### Learning Outcome

This simulation demonstrated practical window limiting used in signal protection and conditioning applications.

## 5. Clamper Circuit

![Clamper](clamper.png)

### Observations

- A clamper add a dc voltage to ac , it shifts ac refernce voltage level upto dc level
- Capacitor charges during one half-cycle and sets new DC level.
- For clamper to work properly : Rl × C > 100T

### Learning Outcome

This clarified the difference between clipping (amplitude limiting) and clamping (DC level shifting), and highlighted the role of capacitor charging behaviour.

## 6. Zener Diode V–I Characteristic (1N750)

![Zener V-I Curve](zener_curve.png)

### Observations

- Sharp breakdown region near rated Zener voltage.
- Reverse voltage remains approximately constant in breakdown region.
- Forward region behaves similarly to a standard silicon diode.

### Learning Outcome

This simulation visualised controlled reverse breakdown and reinforced the principle of voltage limiting using Zener diodes.

These simulations built waveform-level intuition prior to implementation on the signal conditioning PCB.
