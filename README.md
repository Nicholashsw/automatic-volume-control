# Automatic Volume Control for Audio Amplifier System

This is my embedded systems project. It demonstrates the design and implementation of an **automatic volume control (AVC)** system using analog audio circuitry, a microcontroller, and digital feedback.

> **Goal:** Maintain consistent audio loudness regardless of input level using a closed-loop control system.

---

## System Overview

The AVC system is composed of 4 major subsystems:

| Subsystem | Description |
|-----------|-------------|
|  **VCA (Voltage Controlled Amplifier)** | Core gain control using THAT2180C |
|  **PA (Power Amplifier)** | Fixed gain output stage using LM380N |
|  **VU Meter** | Analog peak detector for loudness sensing |
|  **Microcontroller (STM32 + MicroPython)** | Automates gain adjustments via feedback loop |

---

## Labs & Methodology

The project was built across 9 lab sessions:

1. **Microcontroller Setup**
2. **Data Acquisition & Signal Generation**
3. **Waveform Modulation + FFT**
4. **Automation & Instrument Control**
5. **VCA Characterization**
6. **PA Frequency Response**
7. **VU Meter Sensitivity**
8. **Subsystem Integration (Manual Volume Control)**
9. **Automatic Volume Control Algorithm**

---

## Control Algorithm

Implemented in Python using the VScope API to:

- Read analog volume (`Vvolume`) from VU meter
- Compare to a user-defined setpoint
- Adjust control voltage `Va` (via DAC) every 10ms
- Maintain smooth and stable output volume

Simple proportional logic with optional moving average smoothing and step size tuning.

---

## Results

| Test | Observation |
|------|-------------|
| Manual Control | Output volume successfully tracked VCA voltage changes |
| Auto Control | Maintained target loudness with dynamic input signals |
| FFT Analysis | AM sidebands confirmed; spectra matched theory |
| Clipping Protection | System reduced gain when PA saturation was detected |
| Listening Tests | Reduced need for manual adjustment; consistent output level |

---

## Files

| File | Description |
|------|-------------|
| `Automatic Volumn Control Amplifier.ipynb` | Final control code with feedback loop |
| `Report.pdf` | Full 40+ page technical report with lab breakdowns, analysis, and conclusions |

---

**Nicholas Hong**  
B.Eng. (EEE), NTU Singapore  
[LinkedIn](https://www.linkedin.com/in/nicholas-hong001) • [GitHub](https://github.com/Nicholashsw)
