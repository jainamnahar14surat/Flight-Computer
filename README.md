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
