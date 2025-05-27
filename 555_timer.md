# Monostable Multivibrator Using 555 Timer IC

## 📌 Objective
To design and simulate a monostable multivibrator circuit using the 555 Timer IC that generates an output pulse of 0.5 milliseconds duration when triggered.

---

## 🧠 Theory

A monostable multivibrator is a pulse-generating circuit that has only one stable state. Upon receiving a trigger input, it transitions to a temporary quasi-stable state and stays in that state for a predetermined time before returning to its original stable state.

In a 555 timer configured in monostable mode:
- The output remains LOW until a trigger pulse (active LOW) is applied.
- Once triggered, the output goes HIGH for a specific duration defined by the RC time constant.
- The duration of the HIGH output (pulse width) is given by:

\[
T = 1.1 \times R \times C
\]

Where:
- T = pulse width (seconds)
- R = resistance (ohms)
- C = capacitance (farads)

This configuration is useful for applications like timer circuits, pulse generation, switch debouncing, and delay circuits.

---

## 🔧 Components Required

| Component         | Specification        |
|------------------|----------------------|
| 555 Timer IC      | Standard DIP package |
| Resistor (R)      | 454.54 Ω (approx.)   |
| Capacitor (C)     | 1 µF                 |
| Power Supply      | 5V DC                |
| Signal Generator  | Trigger pulse source |
| Output Indicator  | LED/Oscilloscope     |
| Breadboard/Wires  | For circuit setup    |

---

## 📐 Design Calculation

Given:
- Desired pulse width (T) = 0.5 ms = 0.0005 s
- Capacitance (C) = 1 µF = 1×10⁻⁶ F

Using the monostable formula:
\[
R = \frac{T}{1.1 \times C} = \frac{0.0005}{1.1 \times 10^{-6}} \approx 454.54\ \Omega
\]

A resistor value of 470 Ω (nearest standard value) can be used.

---

## 🔌 Circuit Diagram

![Circuit Diagram](https://github.com/user-attachments/assets/f09d2014-f234-4cf1-947f-79f882f99862)

Wiring Summary:
- Pin 1 → GND
- Pin 2 → Trigger (active LOW)
- Pin 3 → Output
- Pin 4 → Reset (tie to Vcc)
- Pin 5 → Control Voltage (optional: connect 10nF capacitor to GND)
- Pin 6 → Threshold
- Pin 7 → Discharge
- Pin 8 → Vcc (5V)

---

## 🧪 Procedure

1. Assemble the circuit as shown in the diagram.
2. Use a 470 Ω resistor and 1 µF capacitor to set the timing.
3. Connect a pulse generator or push-button to provide a trigger to pin 2.
4. Observe the output at pin 3 on an oscilloscope or LED.
5. Verify that the pulse duration is approximately 0.5 milliseconds.
6. Repeat triggering to observe repetitive one-shot pulses.

---

## 📊 Output Waveform

![Waveform](https://github.com/user-attachments/assets/141243cc-a94a-4485-b145-532742e47138)

- First waveform: Trigger signal
- Second waveform: Capacitor charging voltage
- Third waveform: Output pulse (HIGH for 0.5 ms)

---

## 📈 Observations

- The circuit remains in a LOW state until a trigger is received.
- On receiving a trigger, the output switches to HIGH and remains HIGH for a time determined by the RC constant.
- After the capacitor voltage exceeds 2/3 of Vcc, the timer resets and the output returns to LOW.
- With C = 1 µF and R ≈ 454.54 Ω, the output pulse width measured was close to 0.5 ms.

---

## ✅ Conclusion

The 555 timer IC successfully operated in monostable mode, generating a single output pulse of 0.5 milliseconds in response to each input trigger. The timing was accurately determined by the formula:

\[
T = 1.1 \times R \times C
\]
# ASTABLE MULTIVIBRATOR


## Objective

To design and implement a circuit that generates a pulse waveform of 0.5 ms duration using an astable multivibrator, differentiator, clipper, and monostable multivibrator.

---

## Introduction

Pulse generation is a fundamental task in digital and analog electronics, widely used in timing circuits, control systems, and communication modules. This project demonstrates how a basic analog circuitry can be designed to generate a fixed-width pulse of 0.5 ms using common building blocks like multivibrators and signal shaping circuits.

---

## Theory

### 1. Astable Multivibrator

An astable multivibrator continuously switches between high and low states without external triggering. It is used to generate a square waveform. A 555 timer in astable mode uses two resistors (R1 and R2) and a capacitor (C) to define its time period:

- Time period:  
  T = 0.693 × (R1 + 2 × R2) × C  
- Frequency:  
  f = 1.44 / ((R1 + 2 × R2) × C)

This square wave serves as the base signal for pulse shaping.

### 2. Differentiator Circuit

A differentiator converts the edges of the square wave into spike pulses by using a capacitor and resistor:

- Time constant: τ = R × C

A small time constant ensures the output is a narrow voltage spike at each rising and falling edge of the input signal.

### 3. Clipper Circuit

A clipper (using a diode) allows only positive spikes to pass through and blocks or clips negative spikes. This results in clean, single-direction pulses suitable to trigger the next stage.

### 4. Monostable Multivibrator

A monostable multivibrator has one stable state and one temporary state. Triggered by a positive spike, it switches to the unstable state for a fixed time:

- Pulse duration: T_pulse = 1.1 × R × C

For 0.5 ms output, suitable R and C are selected accordingly.

---

## Design and Components

| Block             | Component Type | Example Values                   |
|------------------|----------------|----------------------------------|
| Astable          | 555 Timer IC   | R1 = 4.7 kΩ, R2 = 10 kΩ, C = 0.01 µF |
| Differentiator   | R and C        | R = 1 kΩ, C = 0.01 µF            |
| Clipper          | Diode          | 1N4148 Silicon Diode             |
| Monostable       | 555 Timer IC   | R = 4.7 kΩ, C = 0.1 µF           |

---

## Circuit Operation

1. The astable multivibrator produces a continuous square wave.
2. The differentiator generates spike pulses at each transition.
3. The clipper circuit removes the negative pulses, keeping only the positive spikes.
4. Each positive spike triggers the monostable multivibrator, producing a 0.5 ms pulse output.

---

## Procedure

1. Assemble the 555 astable multivibrator circuit with calculated R and C.
2. Connect its output to the differentiator (series C, shunt R).
3. Use a diode in clipper configuration to remove negative spikes.
4. Feed the clipped output to the trigger input of the monostable multivibrator (another 555 timer).
5. Use an oscilloscope or simulator to verify waveforms at each stage.
6. Adjust component values if required to obtain precise timing.

---

## Output

- Input: Square wave from astable multivibrator (~1 kHz)
- Intermediate: Narrow spike train (positive and negative)
- Clipped: Positive spikes only
- Final Output: 0.5 ms pulse at each spike, from monostable multivibrator

---

## Applications

- Pulse generators
- Signal conditioning
- IR sensor systems
- Microcontroller triggering

---

## Conclusion

The project successfully demonstrates the use of basic analog building blocks to generate a consistent and accurate 0.5 ms pulse waveform. It integrates timing circuits and signal shaping to produce a reliable and repeatable output pulse in response to a square wave input.

"""




