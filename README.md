# ESP32-Based Health Monitoring System

An ESP32-based health monitoring system designed to monitor physiological parameters using the MAX30102, BMP280, and GSR sensors.

The system collects sensor data and provides a foundation for real-time health monitoring, physiological data analysis, and future IoT integration.
---
<img width="1357" height="628" alt="image" src="https://github.com/user-attachments/assets/8ccd251f-0da7-4c6e-ae6d-308f0e37c406" />

---

## Project Overview

This project uses multiple sensors connected to an ESP32 to monitor different health-related parameters.

The collected data can be processed by the ESP32 and displayed through a serial monitor, dashboard, or other compatible monitoring interface.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller for sensor data acquisition and processing |
| MAX30102 | Optical sensor for pulse rate and SpO₂ estimation |
| BMP280 | Environmental temperature and atmospheric pressure measurement |
| GSR Sensor | Measurement of galvanic skin response |
| Power Supply | Provides power to the system |
| Connecting Wires | Sensor and microcontroller connections |

## Sensors Used

### 1. MAX30102 — Heart Rate and SpO₂ Monitoring

The MAX30102 is an integrated optical sensor that uses red and infrared light to measure changes in blood volume through photoplethysmography (PPG).

**Parameters:**
- Heart Rate (BPM)
- Blood Oxygen Saturation (SpO₂) estimation

**Communication:** I²C

**Applications:**
- Heart rate monitoring
- Pulse waveform acquisition
- SpO₂ estimation

### 2. BMP280 — Temperature and Pressure Monitoring

The BMP280 is a digital barometric pressure sensor that measures atmospheric pressure and temperature.

**Parameters:**
- Temperature (°C)
- Atmospheric Pressure (hPa)

**Communication:** I²C or SPI

**Applications:**
- Environmental monitoring
- Ambient temperature measurement
- Atmospheric pressure monitoring

Note: The BMP280 measures ambient temperature, not core body temperature.

### 3. GSR Sensor — Galvanic Skin Response

The GSR sensor measures changes in the electrical conductance or resistance of the skin, which can vary with sweat gland activity.

**Parameters:**
- Skin conductance or resistance, depending on the sensor
- Raw analog sensor readings

**Communication:** Analog input

**Applications:**
- Electrodermal activity monitoring
- Physiological response observation
- Research and educational experiments

GSR measurements may be influenced by skin moisture, electrode contact, movement, and sensor calibration.

## System Architecture

```text
              ┌──────────────────┐
              │      ESP32       │
              │  Main Controller│
              └────────┬─────────┘
                       │
          ┌────────────┼────────────┐
          │            │            │
       I²C Bus      I²C Bus     Analog Input
          │            │            │
   ┌──────▼─────┐ ┌────▼─────┐ ┌────▼─────┐
   │ MAX30102   │ │ BMP280   │ │ GSR      │
   │            │ │          │ │ Sensor   │
   └────────────┘ └──────────┘ └──────────┘
          │            │            │
          ▼            ▼            ▼
     Heart Rate    Temperature   Skin Response
     SpO₂ Estimate Pressure      Raw / Conductance
```

## Features

- Heart rate monitoring using MAX30102
- SpO₂ estimation using MAX30102
- Ambient temperature measurement using BMP280
- Atmospheric pressure measurement using BMP280
- GSR sensor data acquisition
- ESP32-based sensor integration
- Real-time sensor data processing
- Expandable architecture for IoT integration

## Software Requirements

- Arduino IDE
- ESP32 Board Support Package
- MAX30102 sensor library
- BMP280 sensor library
- GSR sensor interface code

## Data Output

The system can provide the following sensor readings:

| Parameter | Unit |
|---|---|
| Heart Rate | BPM |
| SpO₂ | % |
| Ambient Temperature | °C |
| Atmospheric Pressure | hPa |
| GSR | Raw ADC / Conductance, depending on calibration |

## Applications

- Educational health monitoring projects
- Biomedical instrumentation experiments
- Wearable health monitoring prototypes
- Physiological signal acquisition
- IoT-based health monitoring research

## Limitations

- MAX30102 readings depend on proper finger placement, sensor contact, and signal quality.
- SpO₂ values are estimates and are not equivalent to medical-grade measurements.
- BMP280 measures ambient temperature and atmospheric pressure, not body temperature or blood pressure.
- GSR readings require calibration and are affected by skin contact and environmental conditions.
- The system is a prototype and is not intended for medical diagnosis.

## Future Improvements

- OLED display integration
- Wi-Fi-based data transmission
- MQTT-based IoT monitoring
- Web-based health dashboard
- Cloud data logging
- Sensor calibration and filtering
- Battery-powered portable operation
- Data visualization and historical analysis

## Disclaimer

This project is intended for educational, research, and prototyping purposes only.

It is not a certified medical device and must not be used for medical diagnosis, treatment, or emergency health decisions.

## Contributions:

Mahfuz Rahman - 3D designing
