# Amplitude Modulation and Demodulation Design

This repository contains my project on Printed Circuit Board deisgn The project involves designing an **Amplitude Modulator and Demodulator** on a single PCB, demonstrating the principles of amplitude modulation (AM) and demodulation.

## Objective
To design and simulate a circuit that performs:
- **Amplitude Modulation (AM)**: Modulates a message signal onto a carrier signal, with adjustable modulation index.
- **Amplitude Demodulation**: Extracts the original message signal from the modulated AM signal, with a customizable low-pass filter (LPF) cutoff frequency.

## Overview
The design process involved the following steps:
1. **Circuit Simulation**: The circuit was simulated in LTspice software.
2. **PCB Design**: Schematic and layout routing were completed using PCB design tools. Design Rule Check (DRC) shows zero errors.
3. **Validation**: Both modulation and demodulation functionalities were verified under ideal simulation conditions.

## Circuit Description
### Purpose
The circuit demonstrates the modulation of an input message signal onto a carrier signal and the recovery of the message signal through demodulation. It allows for parameter adjustments, such as the modulation index and LPF cutoff frequency, for better understanding and optimization.

### Working Conditions
- **Simulation Environment**: LTspice
- **Inputs**:
  - Carrier Signal: Sine wave, frequency 100 kHz to 1 MHz, amplitude 1–5 V p-p.
  - Message Signal: Sine wave, frequency 20 Hz to 20 kHz, amplitude 0.5–5 V p-p.
- **Outputs**:
  - Modulated AM signal.
  - Demodulated message signal (post-LPF).
- **Power Supply**: 
  - +12V and -12V DC for circuit components.
  - Ground (GND) common for all interconnected circuits.

### Constraints
- **Load Impedance**:
  - Modulator output: Ideal resistive load (>1 kΩ). Used 3.9 kΩ in the design.
  - Demodulator output: Resistor-capacitor (R-C) network satisfying the relation $f_c = \frac{1}{2\pi RC}$ for LPF.

## Power Consumption
### AM Modulator
- Load Resistor (R<sub>L</sub>): 3.9 kΩ
  - Power dissipation: $P_{R_L} = \frac{V^2}{R} \approx 36.9$ mW
- Modulator IC (MC1496):
  - Power consumption: $P_{IC} = V_{CC} \cdot I_{CC} \approx 24$ mW
- **Total Modulator Power**: $P_{modulator} \approx 60.9$ mW

### AM Demodulator
- Power dissipation depends on the modulated wave's amplitude ($V_m$) and resistor value ($R$). Capacitors do not dissipate power directly.

### Modulation Index
The modulation index (μ) affects the total power of the AM signal:
\[
P_{AM} = P_c \left( 1 + \frac{\mu^2}{2} \right)
\]
where $P_c$ is the carrier power.

## PCB Design
The PCB design includes:
1. **Modulator Block**: Accepts carrier and message signals. Outputs an AM signal with adjustable modulation index.
2. **Demodulator Block**: Accepts the modulated AM signal. Outputs the demodulated message signal post-LPF.

The schematic and PCB layout were completed with no errors in the DRC.

## PCB Schematic and Layout

Below are the images of the designed PCB schematic and layout:

### PCB Schematic
![PCB Schematic]()

### PCB Layout
![PCB Layout](https://github.com/BRshreya29/AM-Modulator-PCB-design/blob/main/PCB%20Layout.png)

## Repository Structure
```
.
├── PCB_Design            # PCB schematic and layout files
├── Documentation         # Detailed report and circuit explanations
├── CAM Outputs           # Gerber Files for PCB Printing
└── README.md             # This file
```

## Key Features
- Adjustable modulation index in the modulator block.
- Customizable LPF cutoff frequency in the demodulator block.
- Accurate simulation results using LTspice.
- Zero-error PCB design verified using DRC.

## Conclusion
This project included circuit design, implementation on bread-board, circuit simulation results, and circuit diagram included in the report. 
