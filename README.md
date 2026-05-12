# DC to 3-Phase EV Traction Inverter using SPWM
## Overview
This project presents the design and simulation of a DC–AC three-phase traction inverter for Electric Vehicle (EV) applications. The system converts battery DC power into controlled three-phase AC output for driving a traction motor.

The inverter is implemented using a six-switch Voltage Source Inverter (VSI) topology with SPWM (Sinusoidal Pulse Width Modulation) based gate control. The project focuses on motor speed regulation through output frequency variation, DC-link stabilization, and inverter switching analysis.

The power-stage inverter and switching behavior were developed in LTspice, while motor-drive validation using a PMSM model was performed in MATLAB Simulink.

---

# Project Objectives
- Design a three-phase DC–AC traction inverter for EV applications
- Generate controlled three-phase AC output using SPWM
- Control motor speed by varying inverter output frequency
- Analyze inverter switching behavior and harmonic response
- Study DC-link capacitor performance and voltage ripple
- Validate inverter-driven PMSM operation

---

# Working Principle

## DC to AC Conversion
The inverter converts DC power from the battery into three-phase AC power using six MOSFET switches arranged in a three-phase bridge configuration.

The switches are controlled using Sinusoidal Pulse Width Modulation (SPWM), where sinusoidal reference signals are compared with a high-frequency triangular carrier waveform to generate PWM gate pulses.

---

# Motor Control using Frequency Variation

The speed of an AC traction motor primarily depends on the frequency of the applied three-phase voltage.

For synchronous machines:

```math
N_s = \frac{120f}{P}
```

Where:
- \(N_s\) = synchronous speed (RPM)
- \(f\) = supply frequency (Hz)
- \(P\) = number of poles

By varying the inverter output frequency through SPWM control, the motor speed can be increased or decreased.

### Low Frequency Operation
- Lower inverter frequency
- Lower motor speed
- Used during startup and low-speed driving

### High Frequency Operation
- Higher inverter frequency
- Higher motor speed
- Used during acceleration and cruising

The modulation index and switching frequency can also be adjusted to regulate output voltage and motor torque.

---

# SPWM Control Technique

Three sinusoidal reference signals separated by 120° are compared with a high-frequency triangular carrier waveform.

This generates six PWM gate pulses for the MOSFET switches of the inverter.

## Advantages of SPWM
- Reduced harmonic distortion
- Smooth motor operation
- Adjustable output voltage and frequency
- Better switching control

---

# RL Load as Motor Representation in LTspice

Since LTspice is primarily focused on power electronics and circuit-level simulation, a three-phase RL load was used to represent the electrical characteristics of a traction motor.

The RL load emulates:
- Motor winding resistance
- Motor phase inductance
- Current dynamics during inverter switching

This approach enables analysis of:
- Inverter output current
- Switching transients
- PWM behavior
- Phase voltage response
- DC-link ripple effects

The RL load model provides a simplified approximation of motor behavior suitable for inverter-focused power electronics analysis.

---

# DC-Link Capacitor

A DC-link capacitor is connected between the battery and inverter stages to:
- Reduce voltage ripple
- Supply transient current demand
- Stabilize the DC bus voltage
- Improve inverter performance during switching

---

# LTspice Implementation

The LTspice model includes:
- DC source/battery model
- DC-link capacitor
- Three-phase MOSFET inverter
- SPWM pulse generation
- Three-phase RL motor-equivalent load
- Output voltage and current analysis

## Simulated Results
- Three-phase output voltages
- PWM gate signals
- Phase currents
- DC-link voltage ripple
- Harmonic response

---

# MATLAB Simulink Validation

A simplified PMSM-based traction drive model was developed in MATLAB Simulink to validate:
- Motor speed response
- Torque characteristics
- Frequency-based speed control
- Inverter-driven motor operation

The Simulink model demonstrates traction-drive behavior under varying speed and load conditions.

---

# Applications
- Electric Vehicle Traction Systems
- EV Motor Drives
- Industrial Variable Frequency Drives (VFDs)
- Renewable Energy Conversion
- High-Power Motor Control

---

# Future Improvements
- Space Vector PWM (SVPWM)
- Field Oriented Control (FOC)
- Regenerative Braking
- SiC MOSFET-based inverter design
- Real-time DSP/Microcontroller implementation
- Hardware prototype development

---

# Software Used
- LTspice
- MATLAB Simulink
- Simscape Electrical

---

# Key Concepts
- Voltage Source Inverter (VSI)
- SPWM
- Traction Inverter
- PMSM Motor Drive
- Frequency-Based Speed Control
- DC-Link Stabilization
- Power Electronics for EVs

---
