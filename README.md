# Distributed ICU Patient Monitoring Network

## 1. Project Overview

The **Distributed ICU Patient Monitoring Network** is an embedded systems project designed to monitor multiple patient health and environmental parameters using distributed microcontroller nodes and CAN (Controller Area Network) communication.

The system collects sensor readings such as temperature, oxygen level, and light intensity through Node A. The collected data is transmitted to Node B using the CAN protocol. Node B communicates with an on-premise computer server through UART, where the patient monitoring information is displayed.

The project demonstrates distributed embedded communication, sensor interfacing, CAN-based data transmission, and local server integration.

## 2. Objectives

- Monitor patient-related parameters in real time.
- Interface multiple sensors with a microcontroller.
- Implement node-to-node communication using the CAN protocol.
- Transfer collected sensor data to a computer server using UART.
- Demonstrate distributed monitoring using multiple microcontroller nodes.
- Support local patient data monitoring without depending on continuous internet connectivity.

## 3. System Architecture

The system consists of two microcontroller nodes:

### Node A – Sensor Monitoring Node

Node A is responsible for collecting sensor data.

Connected sensors:
- **Temperature Sensor:** Measures the surrounding temperature.
- **LDR Sensor:** Measures light intensity.
- **Oxygen Sensor:** Monitors oxygen-related measurements.

The sensor outputs are connected to the analog input channels AIN1, AIN2, and AIN3, respectively.

Node A processes the sensor readings and transmits the collected information to Node B through the CAN interface.

### Node B – Server Communication Node

Node B receives the sensor information transmitted by Node A through the CAN interface.

Its responsibilities include:
- Receiving CAN messages.
- Extracting the sensor readings.
- Sending the processed data to the computer through UART.
- Enabling real-time patient data monitoring on the server.

### Computer – Local Server

The computer acts as the local monitoring server.

It receives sensor data through UART and displays the patient information, including:

- Temperature Level
- Light Level
- Oxygen Level

Example monitoring output:

```text
******** PATIENT DATA ********

TEMP LEVEL : 28 C
LIGHT LEVEL: 60%
OXY LEVEL  : 99%
```

## 4. Communication Protocols

| Protocol | Purpose |
|---|---|
| ADC | Reads analog sensor outputs |
| CAN | Communication between Node A and Node B |
| UART | Communication between Node B and the computer server |

## 5. System Data Flow

1. Sensors continuously provide measurements to Node A.
2. Node A reads the analog sensor values through ADC channels.
3. Sensor readings are processed and organized into CAN messages.
4. CAN communication transfers the messages from Node A to Node B.
5. Node B receives and extracts the transmitted data.
6. Node B sends the sensor information to the computer using UART.
7. The computer displays the patient monitoring parameters.

## 6. Why an On-Premise Server?

Hospitals use local servers to maintain reliable access to critical patient information.

Key advantages include:

- **Low Latency:** Data is transferred within the hospital's local network.
- **Internet Independence:** Monitoring and data logging can continue during external internet outages.
- **Data Privacy:** Sensitive patient information remains under the hospital's local control.
- **Real-Time Integration:** Local infrastructure supports communication with multiple monitoring devices.

## 7. Technologies Used

- Embedded C
- Microcontroller-based distributed architecture
- ADC sensor interfacing
- CAN Protocol
- UART Communication
- Local Computer Server
- Temperature Sensor
- LDR Sensor
- Oxygen Sensor

## 8. Key Features

- Distributed sensor monitoring architecture.
- Multiple sensor interfacing using ADC.
- CAN-based communication between embedded nodes.
- UART-based communication with a computer.
- Centralized patient parameter display.
- Local server-based monitoring architecture.

## 9. Applications

- ICU patient monitoring systems.
- Hospital environmental monitoring.
- Distributed healthcare monitoring networks.
- Embedded sensor networks.
- Localized medical data acquisition systems.

## 10. Future Enhancements

- Support multiple patient monitoring nodes.
- Implement patient identification and individual data logging.
- Develop a graphical monitoring dashboard.
- Add threshold-based alerts for abnormal readings.
- Implement data storage and historical monitoring.
- Introduce secure communication and access control.

## 11. Conclusion

The Distributed ICU Patient Monitoring Network demonstrates how multiple embedded nodes can communicate using the CAN protocol to collect and transfer sensor information to a centralized local server.

By combining ADC-based sensor interfacing, CAN communication, and UART-based server integration, the project provides a foundation for distributed patient monitoring systems that can operate independently of continuous internet connectivity.
