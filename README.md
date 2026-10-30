# ⚖️ VIBRATION-IMMUNE SMART DIGITAL WEIGHING SCALE
<p align="center">
Using STM32 & Digital Signal Processing
<p align="center">
  <b>An Intelligent Embedded Weighing System for Improved Measurement Stability Under Vibration Conditions</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Project-Completed-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Platform-STM32-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-Embedded%20C-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Technology-DSP-purple?style=for-the-badge" />
</p>

---

## 📌 About The Project

The **Vibration-Immune Smart Digital Weighing Scale** is an embedded systems project developed as part of the Digital Signal Processing (24ECJ502) course at TKM College of Engineering.

Conventional digital weighing scales may produce unstable readings when exposed to external vibrations and mechanical disturbances. These disturbances introduce unwanted fluctuations into load-cell signals, affecting measurement stability.

This project explores the application of **Digital Signal Processing (DSP)** techniques to improve the stability and reliability of weight measurements.

The system integrates a 3 kg load cell, HX711 24-bit ADC module, and STM32 NUCLEO-F411RE microcontroller. FIR low-pass filtering is investigated to reduce unwanted signal fluctuations, while Fast Fourier Transform (FFT) analysis is used to identify dominant vibration frequency components.

The measured weight is displayed on an SSD1306 OLED display, providing a convenient real-time monitoring interface.

## 🎯 Project Objectives

* Develop a digital weighing system using STM32 NUCLEO-F411RE.
* Interface a load cell with the HX711 24-bit ADC module.
* Investigate FIR filtering techniques for reducing vibration-induced fluctuations.
* Perform FFT-based frequency analysis to identify dominant vibration components.
* Evaluate the system using reference masses under selected vibration conditions.
* Display weight measurements through an SSD1306 OLED display.

## 🏗️ System Architecture

### Block Diagram

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/4c20b23a-30dd-41e7-8c01-79dff61542bb" />


## 🔧 Hardware Components

| Sl. No. | Component          | Specification       |
| :-----: | ------------------ | ------------------- |
|    1    | Microcontroller    | STM32 NUCLEO-F411RE |
|    2    | Load Cell          | 3 kg                |
|    3    | ADC Module         | HX711 (24-bit)      |
|    4    | Display            | SSD1306 OLED        |
|    5    | Display Resolution | 128 × 64 pixels     |
|    6    | Connecting Wires   | Jumper Wires        |

## 💻 Software & Technologies

| Technology    | Application                  |
| ------------- | ---------------------------- |
| Embedded C    | Microcontroller programming  |
| STM32CubeIDE  | Firmware development         |
| MATLAB        | DSP simulation and analysis  |
| Wokwi         | Hardware simulation          |
| Tera Term     | Serial monitoring            |
| FIR Filtering | Signal fluctuation reduction |
| FFT           | Frequency-domain analysis    |
| I2C           | OLED communication           |
| UART          | Serial communication         |

## ⚙️ Working Principle

### 1. Weight Sensing

The load cell detects the applied mechanical force and converts it into a proportional electrical signal.

### 2. Signal Conditioning

The HX711 module amplifies the weak electrical signal from the load cell and converts it into digital data using its integrated 24-bit ADC.

### 3. Data Acquisition

The STM32 NUCLEO-F411RE receives the digital measurements from the HX711 module at approximately 80 samples per second.

### 4. FIR Low-Pass Filtering

A Finite Impulse Response (FIR) low-pass filter is investigated to attenuate unwanted higher-frequency signal variations and obtain smoother weight readings.

### 5. FFT Analysis

Fast Fourier Transform (FFT) analysis examines the frequency components of the sampled signal to identify dominant vibration frequencies.

### 6. Weight Calculation and Calibration

The sensor readings are calibrated using known reference masses to obtain meaningful weight measurements.

### 7. Output Display

The measured weight is displayed on the SSD1306 OLED screen for real-time monitoring.

## 📊 Digital Signal Processing

Digital Signal Processing is the core concept explored in this project.

### A. FIR Low-Pass Filtering

A 40th-order FIR low-pass filter with a cutoff frequency of 5 Hz is used in the MATLAB simulation.

| Parameter                   |        Value |
| --------------------------- | -----------: |
| Sampling Frequency          |        80 Hz |
| Cutoff Frequency            |         5 Hz |
| Filter Order                |           40 |
| Number of Coefficients      |           41 |
| Normalized Cutoff Frequency |        0.125 |
| Group Delay                 |   20 Samples |
| Time Delay                  | 0.25 Seconds |

The FIR filter helps attenuate unwanted higher-frequency variations in the measured signal.

### B. Fast Fourier Transform (FFT)

FFT analysis is used to examine the frequency-domain characteristics of the sampled signal.

| Parameter                    |       Value |
| ---------------------------- | ----------: |
| Sampling Frequency           |       80 Hz |
| FFT Size                     | 256 Samples |
| Observation Time             | 3.2 Seconds |
| Frequency Resolution         |   0.3125 Hz |
| Nyquist Frequency            |       40 Hz |
| Simulated Dominant Frequency |       20 Hz |

The MATLAB simulation identifies a dominant vibration frequency of 20 Hz.

The simulation associates this frequency with a packaging press using predefined source-classification logic.

## 📈 Simulation Results

MATLAB simulation was conducted to evaluate the performance of FIR filtering by comparing raw and filtered signals against a reference weight profile.

### RMS Error Comparison

| Parameter      | Raw Signal | FIR Filtered Signal |
| -------------- | ---------: | ------------------: |
| RMS Error (kg) |   0.036239 |            0.003285 |
| RMS Error (g)  |     36.239 |               3.285 |

### Key Result

**Approximately 90.93% reduction in RMS error was observed after FIR filtering in the MATLAB simulation.**

This indicates improved agreement between the filtered signal and the reference weight profile under the simulated conditions.

## 🔬 Hardware Implementation & Testing

The physical prototype was developed and tested using the following components:

* STM32 NUCLEO-F411RE microcontroller.
* 3 kg load cell.
* HX711 amplifier and ADC module.
* SSD1306 OLED display.

The practical implementation demonstrates the operation of the hardware components and the weight measurement process.

### Experimental Testing

The testing procedure included:

* Baseline measurements without intentionally applied vibration.
* Weight measurements using reference masses.
* Testing under selected external vibration conditions.
* Observation of OLED readings under different conditions.
* Analysis of measurement stability.

The project report describes selected vibration conditions, including 18 Hz and 26 Hz.

Further repeatable measurements are necessary to establish quantitative hardware performance.

## ✨ Advantages

* **Improved Signal Stability:** Digital filtering helps reduce unwanted fluctuations in load-cell measurements.
* **Frequency Analysis:** FFT helps investigate frequency components associated with vibrations.
* **Embedded Processing:** STM32 provides a platform for sensor acquisition and embedded signal processing.
* **Real-Time Display:** OLED provides a convenient interface for viewing weight measurements.
* **Modular Architecture:** The system allows future integration of advanced filtering and compensation techniques.

## ⚠️ Limitations

* Filtering may introduce delay and slow the response to changes in weight.
* A fixed filter may not suppress every vibration frequency effectively.
* The approximately 80 Hz sampling rate limits the measurable frequency range.
* Current testing covers selected vibration frequencies and reference masses.
* Quantitative performance claims require recorded measurements, calibration details and repeatable testing.

## 🚀 Future Scope

The project can be further enhanced through the following developments:

1. **Adaptive Filtering:** Adjust filter characteristics according to changing vibration conditions.
2. **Advanced Frequency Analysis:** Explore frequency-dependent filtering and adaptive notch filters.
3. **Vibration Sensing:** Integrate an accelerometer for direct vibration measurement.
4. **Data Logging:** Enable long-term storage and analysis of weight measurements.
5. **Wireless Connectivity:** Introduce remote monitoring and IoT-based data visualization.
6. **Extended Testing:** Evaluate different loads, vibration frequencies and mechanical configurations.

## 💰 Project Expenditure

| Sl. No. | Component                      |   Cost (₹) |
| :-----: | ------------------------------ | ---------: |
|    1    | STM32 NUCLEO-F411RE            |       2000 |
|    2    | 3 kg Load Cell                 |        200 |
|    3    | HX711 Amplifier Module         |         40 |
|    4    | OLED Display (128 × 64)        |        180 |
|    5    | Connecting Wires & Accessories |         80 |
|    6    | Miscellaneous                  |        100 |
|         | **Total**                      | **₹2,600** |


## 📚 References

1. J. Fraden, *Handbook of Modern Sensors: Physics, Designs, and Applications*, 4th Edition, Springer, 2010.
2. R. G. Lyons, *Understanding Digital Signal Processing*, 3rd Edition, Prentice Hall, 2011.
3. S. W. Smith, *The Scientist and Engineer's Guide to Digital Signal Processing*, 2nd Edition, 1999.
4. STMicroelectronics, *STM32F411xC/E Advanced ARM-Based 32-Bit MCU Reference Manual*, RM0383.
5. AVIA Semiconductor, *HX711 24-Bit Analog-to-Digital Converter for Weigh Scales Datasheet*.
6. Texas Instruments, *Digital Filter Design Reference Notes*, SLAA114, 2001.

---

<p align="center">
