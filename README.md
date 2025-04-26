# Flight-Computer

A compact, custom-designed PCB (Printed Circuit Board) for a Flight Computer, aimed at aerospace applications like model rockets, UAVs, and experimental aircrafts. The design integrates essential sensors and microcontroller connections to provide reliable flight data acquisition and processing.

## Overview
The Flight Computer is powered by an STM32F405RG microcontroller, enabling real-time data acquisition from multiple environmental and motion sensors. It also supports wireless data transmission using the NRF24L01-PA radio module, and precise location tracking through the NEO-M9N GPS receiver. This project is currently at the prototype stage, aimed at validating the PCB layout, hardware interfacing, and initial sensor readings.

## Major Components

| Component | Description |
|:---|:---|
| **STM32F405RG** | High-performance ARM Cortex-M4 Microcontroller |
| **LM20BIM7** | Precision Temperature Sensor |
| **Si7020-A20** | Humidity Sensor with I²C Interface |
| **MPU6050** | 6-axis IMU (Accelerometer + Gyroscope) |
| **NEO-M9N** | High-Precision GPS Module |
| **NRF24L01-PA** | Long-Range Wireless Radio Module |

## Features

- **High-Speed Processing**: 168 MHz ARM Cortex-M4 with hardware floating-point unit (FPU).
- **Environmental Monitoring**: Temperature and humidity sensing for atmospheric studies.
- **Precise Navigation**: Real-time position and velocity data from GPS.
- **Wireless Telemetry**: Long-range data transmission using NRF24L01-PA module.
- **Motion Tracking**: 3-axis acceleration and 3-axis rotational velocity sensing.
- **Noise Filtering and Protection**: Power-line ferrite beads, fuses, and transient protection.
- **Modular Design**: Easy to add additional sensors or modules if needed.
- **Lightweight and Compact**: Optimized for minimal payload impact in flight applications.

## System Architecture


The Flight Computer follows a layered and modular system design, ensuring clear data flow and easy expandability. The architecture can be understood in three main layers:

### Sensor Layer
This layer is responsible for collecting environmental and motion data in real-time.
- **Temperature Sensor (LM20BIM7):**
    Measures ambient temperature and sends analog data to the STM32's ADC.

- **Humidity Sensor (Si7020-A20):**
    Captures precise humidity levels via the I2C interface.

- **IMU (MPU6050):**
    Provides 6-axis motion data (acceleration and gyroscope) over I2C communication.

### Processing Layer
The STM32F405RG acts as the central controller, performing the following:
- Reads sensor inputs (ADC, I2C, UART).
- Filters and processes sensor data.
- Combines multiple sensor readings for better situational awareness (sensor fusion).
- Prepares formatted data packets for transmission.

### Communication Layer
Handles external data transmission and navigation data retrieval.

- **GPS Module (NEO-M9N):**
    Interfaces over UART to provide real-time positioning information.

- **Wireless Radio (NRF24L01-PA):**
    Uses SPI communication to send collected flight data wirelessly to a ground receiver or base station.

## Repository Structure

| Folder/File	| Description |
|:---|:---|
| **Flight_Computer.net**	| Netlist file describing PCB connections |
| **Schematics/** |	Electrical schematics (to be added) |
| **Gerber_Files/** |	PCB fabrication files (optional for production) |
| **README.md** |	Project documentation |

## Applications

- High-Altitude Balloons
- Model Rocket Avionics
- Experimental UAV Flight Computers
- Remote Atmospheric Data Collection

## Future Enhancements

- Integration of SD card storage for redundant flight logging
- Addition of LoRaWAN communication for ultra-long range telemetry
- Redundant GPS modules for enhanced navigation reliability
- Automatic recovery and emergency shutdown systems

## License
This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for more details.


