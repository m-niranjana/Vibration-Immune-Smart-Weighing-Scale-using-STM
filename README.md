<div align="center">

# ⚖️ VIBRATION-IMMUNE SMART DIGITAL WEIGHING SCALE

### Using STM32 & Digital Signal Processing

**An Intelligent Embedded Weighing System for Stable and Reliable Weight Measurement Under Vibration Conditions**

<br>

**GROUP 6 | DIGITAL SIGNAL PROCESSING PROJECT**

<br>

`STM32` · `Embedded C` · `DSP` · `FIR Filtering` · `FFT Analysis`

<br>

![Project](https://img.shields.io/badge/Project-Embedded%20Systems-0078D4?style=for-the-badge)
![Controller](https://img.shields.io/badge/Controller-STM32-03234B?style=for-the-badge)
![Technology](https://img.shields.io/badge/Technology-DSP-009688?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Development-orange?style=for-the-badge)

</div>

---

## 📌 1. Project Overview

Conventional digital weighing scales often experience unstable readings when subjected to external vibrations and mechanical disturbances.

The **Vibration-Immune Smart Digital Weighing Scale** aims to address this problem using Digital Signal Processing (DSP) techniques.

The proposed system integrates a load cell, HX711 24-bit ADC module, and STM32 NUCLEO-F411RE microcontroller to acquire and process weight measurements.

FIR low-pass filtering is used to reduce unwanted signal fluctuations, while Fast Fourier Transform (FFT) analysis examines the frequency components associated with vibrations.

The processed weight measurement is displayed on an SSD1306 OLED display, providing a clear and more stable weight estimate.

### 💡 Our Approach

**LOAD CELL → HX711 ADC → STM32 → DIGITAL SIGNAL PROCESSING → STABLE WEIGHT DISPLAY**

---

## 🎯 2. Problem Statement

Environmental vibrations can introduce unwanted fluctuations into load-cell signals, resulting in unstable weight measurements.

The project investigates:

**Can Digital Signal Processing and FFT-based analysis improve weight stability in an STM32-based weighing system under vibration conditions while maintaining measurement accuracy and response time?**

---

## 🚀 3. Project Objectives

* Develop a digital weighing system using a load cell, HX711 ADC, and STM32 NUCLEO-F411RE.
* Implement digital filtering to reduce vibration-related signal fluctuations.
* Perform FFT-based frequency analysis to identify dominant vibration components.
* Evaluate the system using reference masses under controlled vibration conditions.
* Display processed weight measurements through an OLED display.

---

## 🏗️ 4. System Architecture

### Block Diagram

```text
       ┌──────────────────────┐
       │    LOAD PLATFORM    │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │      LOAD CELL       │
       │  Mechanical to       │
       │  Electrical Signal   │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │       HX711          │
       │  Signal Conditioning │
       │  & 24-bit ADC        │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │   STM32 NUCLEO       │
       │      F411RE          │
       │  Data Acquisition    │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │    FIR FILTERING     │
       │  Signal Stabilization│
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │     FFT ANALYSIS     │
       │ Vibration Frequency  │
       │     Detection        │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │  WEIGHT CALCULATION  │
       │    & CALIBRATION     │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │    SSD1306 OLED      │
       │  Processed Weight    │
       │      Display         │
       └──────────────────────┘
```

---

## 🔧 5. Hardware Components

| Sl. No. | Component          | Specification       |
| :-----: | ------------------ | ------------------- |
|    1    | Microcontroller    | STM32 NUCLEO-F411RE |
|    2    | Load Cell          | 3 kg                |
|    3    | ADC Module         | HX711 24-bit        |
|    4    | Display            | SSD1306 OLED        |
|    5    | Display Resolution | 128 × 64 pixels     |
|    6    | Connecting Wires   | Jumper Wires        |

---

## 💻 6. Software & Technologies

| Technology    | Application                              |
| ------------- | ---------------------------------------- |
| Embedded C    | Microcontroller programming              |
| STM32CubeIDE  | Firmware development                     |
| MATLAB        | Digital signal processing and simulation |
| Wokwi         | Virtual hardware simulation              |
| Tera Term     | Serial monitoring                        |
| FIR Filtering | Signal fluctuation reduction             |
| FFT           | Frequency-domain analysis                |
| UART          | Serial communication                     |
| I2C           | OLED communication                       |

---

## ⚙️ 7. Working Principle

The system operates through the following stages:

**01. Weight Sensing**

The load cell detects the applied force and converts it into a proportional electrical signal.

**02. Signal Conditioning**

The HX711 module amplifies the weak load-cell signal and converts it into digital data using its 24-bit ADC.

**03. Data Acquisition**

The STM32 NUCLEO-F411RE acquires the digital measurements at approximately 80 samples per second.

**04. FIR Filtering**

A Finite Impulse Response (FIR) low-pass filter is used to reduce unwanted fluctuations in the measured signal.

**05. FFT Analysis**

Fast Fourier Transform analysis examines the frequency components of the sampled signal and identifies dominant vibration frequencies.

**06. Weight Calculation**

Calibration using known reference masses converts the sensor readings into meaningful weight measurements.

**07. OLED Display**

The processed weight measurement is displayed on the SSD1306 OLED screen.

---

## 📊 8. Digital Signal Processing

DSP is the core technology behind this project.

### A. FIR Low-Pass Filtering

A 40th-order FIR low-pass filter with a 5 Hz cutoff frequency is used in the MATLAB simulation.

| Parameter                   |        Value |
| --------------------------- | -----------: |
| Sampling Frequency          |        80 Hz |
| Cutoff Frequency            |         5 Hz |
| Filter Order                |           40 |
| Number of Coefficients      |           41 |
| Normalized Cutoff Frequency |        0.125 |
| Group Delay                 |   20 samples |
| Time Delay                  | 0.25 seconds |

The FIR filter helps attenuate unwanted higher-frequency variations in the measured signal.

### B. Fast Fourier Transform (FFT)

FFT is used to examine the frequency-domain characteristics of the sampled signal.

| Parameter                    |       Value |
| ---------------------------- | ----------: |
| Sampling Frequency           |       80 Hz |
| FFT Size                     | 256 samples |
| Observation Time             | 3.2 seconds |
| Frequency Resolution         |   0.3125 Hz |
| Nyquist Frequency            |       40 Hz |
| Simulated Dominant Frequency |       20 Hz |

The simulation identifies a dominant frequency component of 20 Hz and associates it with a packaging press through predefined source-classification logic.

---

## 📈 9. Simulation Results

The MATLAB simulation evaluates the effectiveness of FIR filtering by comparing raw and filtered signals against a reference weight profile.

### RMS Error Comparison

| Parameter          |  Raw Signal | FIR Filtered Signal |
| ------------------ | ----------: | ------------------: |
| RMS Error          | 0.036239 kg |         0.003285 kg |
| RMS Error in Grams |    36.239 g |             3.285 g |

### Key Simulation Result

**Approximately 90.93% reduction in RMS error was observed after FIR filtering in the MATLAB simulation.**

This demonstrates improved agreement between the filtered signal and the reference weight profile under the simulated conditions.

> Note: The 90.93% improvement is a MATLAB simulation result, not a verified physical hardware performance measurement.

### Result Visualization

Add your MATLAB result images here:

| Raw Signal           | FIR Filtered Signal       |
| -------------------- | ------------------------- |
| Add raw signal graph | Add filtered signal graph |

| FFT Spectrum  | MATLAB Simulation            |
| ------------- | ---------------------------- |
| Add FFT graph | Add MATLAB output screenshot |

---

## 🔬 10. Experimental Testing

The physical prototype integrates:

* STM32 NUCLEO-F411RE
* 3 kg Load Cell
* HX711 ADC Module
* SSD1306 OLED Display

The experimental procedure considers:

1. Baseline measurements without intentionally applied vibration.
2. Measurements under controlled vibration conditions.
3. Comparison of raw and processed readings.
4. Evaluation using known reference masses.
5. Analysis of measurement stability and accuracy.

The project report describes testing at selected vibration frequencies, including 18 Hz and 26 Hz conditions.

Further repeatable hardware measurements are required to establish quantitative vibration-rejection performance.

---

## ✨ 11. Advantages

**Improved Signal Stability**

Digital filtering helps reduce unwanted fluctuations in load-cell measurements.

**Frequency Analysis**

FFT helps investigate dominant frequency components associated with vibrations.

**Embedded Processing**

The STM32 microcontroller performs the required signal acquisition and processing.

**Real-Time Display**

The OLED provides a direct view of the processed weight.

**Modular Architecture**

The system allows future integration of advanced filtering and vibration compensation techniques.

---

## ⚠️ 12. Limitations

* Filtering may introduce delay and slow the response to changes in weight.
* A fixed filter may not suppress every vibration frequency effectively.
* The approximately 80 Hz sampling rate limits the measurable frequency range.
* Current testing covers selected vibration frequencies and reference masses.
* Quantitative performance claims require recorded measurements, calibration details, and repeatable testing.

---

## 🔮 13. Future Scope

The project can be extended through the following improvements:

**Adaptive Filtering**

Adjust filter characteristics according to changing vibration conditions.

**Advanced Frequency Analysis**

Explore frequency-dependent filtering and adaptive notch filters.

**Vibration Sensing**

Integrate an accelerometer for direct measurement of mechanical vibrations.

**Data Logging & Connectivity**

Enable long-term storage of measurements and remote monitoring.

**Extended Experimental Testing**

Evaluate different loads, vibration frequencies, and mechanical configurations.

---

## 💰 14. Project Expenditure

| Sl. No. | Component                      |   Cost (₹) |
| :-----: | ------------------------------ | ---------: |
|    1    | STM32 NUCLEO-F411RE            |       2000 |
|    2    | 3 kg Load Cell                 |        200 |
|    3    | HX711 Amplifier Module         |         40 |
|    4    | OLED Display (128 × 64)        |        180 |
|    5    | Connecting Wires & Accessories |         80 |
|    6    | Miscellaneous                  |        100 |
|         | **Total**                      | **₹2,600** |

---

## 📷 15. Project Gallery

### Hardware Implementation

Add photographs of the actual prototype here.

| Hardware Setup          | OLED Display        |
| ----------------------- | ------------------- |
| Add hardware photograph | Add OLED photograph |

### Simulation & Analysis

| MATLAB Results    | Experimental Setup     |
| ----------------- | ---------------------- |
| Add MATLAB graphs | Add testing photograph |

---

## 👨‍💻 16. Project Team

**GROUP 6 – Electronics and Communication Engineering**

| Name          | Institution                |
| ------------- | -------------------------- |
| Devakrishna R | TKM College of Engineering |
| M Niranjana   | TKM College of Engineering |
| Arya K S      | TKM College of Engineering |
| Karthik S     | TKM College of Engineering |

**Institution:** TKM College of Engineering, Kollam

**Department:** Electronics and Communication Engineering

**Course:** 24ECJ502 – Digital Signal Processing

**University:** APJ Abdul Kalam Technological University

**Project Year:** 2026

---

## 📚 17. References

1. J. Fraden, *Handbook of Modern Sensors: Physics, Designs, and Applications*, 4th Edition, Springer, 2010.
2. R. G. Lyons, *Understanding Digital Signal Processing*, 3rd Edition, Prentice Hall, 2011.
3. S. W. Smith, *The Scientist and Engineer's Guide to Digital Signal Processing*, 2nd Edition, 1999.
4. STMicroelectronics, STM32F411xC/E Microcontroller Reference Manual.
5. AVIA Semiconductor, HX711 24-Bit Analog-to-Digital Converter Datasheet.
6. Texas Instruments, Digital Filter Design Reference Notes.

---

<div align="center">

# ⚡ ENGINEERING MEETS INTELLIGENCE ⚡

### Building Smarter Measurement Systems Through Digital Signal Processing

**Vibration-Immune Smart Digital Weighing Scale**

*Designed & Developed by Group 6*

**TKM COLLEGE OF ENGINEERING | 2026**

</div>
