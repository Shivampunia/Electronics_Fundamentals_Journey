# LTspice Simulation Details – Week 04  
Multi-Stage Amplifier & Building Blocks

The simulations this week were focused on understanding both individual amplifier stages and their behaviour when cascaded into a complete signal chain.

## 1. Swamped CE Amplifier

![Swamped Amplifier](swamped_amp.png)

### Observations

- Output is amplified and inverted (180° phase shift)  
- Emitter resistance stabilises gain  
- Partial bypass capacitor increases gain without losing stability  

### Learning Outcome

- Emitter degeneration improves linearity  
- Gain becomes predictable and less dependent on transistor β  

## 2. Emitter Follower (Common Collector)

![Emitter Follower](cc_amp.png)

### Observations

- Output follows input (no phase inversion)  
- Voltage gain ≈ 1  
- Current capability increases significantly  

### Learning Outcome

- Acts as buffer stage  
- Reduces loading effect on previous stage  

## 3. Common Base Amplifier

![Common Base](cb_amp.png)

### Observations

- No phase inversion  
- High voltage gain  
- Very low input impedance  

### Learning Outcome

- Suitable for high-frequency and low-impedance sources  
- Not ideal for general cascading due to input loading  

## 4. Cascaded CE + CC Amplifier

![Cascading CE CC](ce_cc_cascade.png)

### Observations

- CE stage provides voltage gain  
- CC stage buffers output  
- Overall signal is amplified and stabilised  

### Learning Outcome

- Demonstrates proper stage combination  
- Shows importance of buffering between stages  

## 5. Darlington Configuration

![Darlington](darlington.png)

### Observations

- Very high current gain  
- Base current requirement significantly reduced  
- Slower response compared to single transistor  

### Learning Outcome

- Useful for driving high-current loads from weak signals  
- Trade-off between gain and speed  

## 6. Zener Follower (Voltage Regulation)

![Zener Follower](zener_follower.png)

### Observations

- Output voltage remains nearly constant  
- Vout ≈ Vz − VBE  
- Stable against input variations  

### Learning Outcome

- Simple voltage regulation using Zener + transistor  
- Acts as emitter follower with fixed reference  

## 7. Key Understanding (System Level)

- CE stage → provides voltage gain  
- CC stage → provides current gain and buffering  
- Cascading → introduces loading effects  
- Proper stage order is critical for performance  

## Final Insight

These simulations were not isolated experiments.

They directly form the building blocks of the final multi-stage amplifier:

**Swamped CE → Emitter Follower → Power Stage**

Understanding each block individually made it possible to design and simulate the complete system effectively.
