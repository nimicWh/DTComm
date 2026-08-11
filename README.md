# DTComm

### Industrial Communication for Real-Time Equipment Monitoring

*Engineering Simulation • HVAC • Industrial Automation • Digital Twin • Industry 4.0*

</p>

<p align="center">
<img src="https://img.shields.io/badge/Status-Active%20Development-success" />
</p>

**DTComm** is an industrial communication platform being developed for **real-time equipment monitoring, industrial digitalisation and digital twin applications**.

From the beginning of the project, DTComm with the intention of evolving toward an architecture **aligned with IEC 62443 industrial cybersecurity principles**.

The current development platform uses a **simulated industrial chiller** to demonstrate live equipment communication and monitoring.


---

## What can DTComm do?

DTComm to demonstrates:

* Real-time equipment data monitoring
* Live sensor values
* Device connection management
* Data subscriptions
* Continuous telemetry updates
* Equipment simulation
* Client/server communication
* Automatic device scanning
* Multiple data points from a device
* Responsive communication under continuous data traffic

The current demonstration uses a simulated industrial chiller.

---

## Industrial Chiller Demonstration

The current DTComm demonstration models a chiller with live operating data.

Example:

| Equipment              | Data       |
| ---------------------- | ---------- |
| Main Chiller           | Connected  |
| CHW Supply Temperature | Live       |
| Device Status          | Live       |
| Sensor Updates         | Continuous |
| Communication          | Real-time  |

The simulated equipment continuously generates operating values which are transmitted to the monitoring application.

This provides a controlled environment for developing and testing DTComm before connecting it to physical industrial equipment.

---

## Live Monitoring

The DTComm client provides a live view of connected equipment and its operating data.

Example workflow:

```text
Industrial Equipment
        ↓
     DTComm
        ↓
   Live Data
        ↓
 Monitoring Application
```

The intention is to make equipment data available to applications without requiring the application to directly manage the underlying communication process.

---

## Designed for Industrial Applications

DTComm is being developed with applications such as:

### Equipment Monitoring

Monitor operating parameters from industrial equipment in real time.

### Digital Twins

Provide the communication layer between physical equipment, simulation models and digital-twin applications.

### Condition Monitoring

Collect continuous operating data that can be used for equipment condition assessment.

### Industrial Training

Use simulated equipment to demonstrate industrial communication, monitoring and equipment behaviour without requiring physical machinery.

### Engineering Applications

Provide a lightweight communication mechanism for engineering software and equipment models.

---

## Current Demonstration

The current development system consists of:

**DTComm Server**

↓

**Simulated Industrial Chiller**

↓

**Live Sensor Data** (simulated)

↓

**DTComm Client**

The demonstration is intentionally built around an industrial equipment scenario rather than a generic messaging example.

---

## Performance Goals

DTComm is being developed with the following targets:

| Objective             |           Target |
| --------------------- | ---------------: |
| Communication latency |         < 100 ms |
| Runtime scan interval |           100 ms |
| Sensor scalability    | 100+ data points |
| Continuous telemetry  |        Supported |
| Equipment simulation  |        Supported |
| Client monitoring     |        Supported |

These are development targets and test objectives, not certification claims.

---

## Why DTComm?

The DTComm is to be designed for the project, Physic based digital twin. IT explores a lightweight approach to the environment of communication.

---

## Industrial Cybersecurity

The long-term security direction of DTComm is intended to align with the **IEC 62443 family of standards**, which provides a framework for cybersecurity in industrial automation and control systems.

Security is being considered alongside the development of:

* Equipment communication
* Application interaction
* Device and session management
* Access control
* Authentication and authorization
* Protection of the communication pipeline

DTComm is **not intended to claim IEC 62443 compliance or certification**. Instead, the project aims to adopt security practices and principles that are consistent with the IEC 62443 approach, with the objective of reducing the risk of unauthorized access, malicious activity and other threats to the communication pipeline within industrial automation environments.

The intention is to make **security part of the communication platform from the beginning**, rather than treating cybersecurity as an additional layer after the communication system has been developed.


---

## Demonstration

## Screenshots
1) Server to client interaction
   <img width="1919" height="1048" alt="dtcomm1" src="https://github.com/user-attachments/assets/6978cd2a-bd78-4fab-97cc-09f4ec5c34f7" />

2) Subscription
   <img width="1919" height="1062" alt="dtcomm_sub" src="https://github.com/user-attachments/assets/090977c8-013c-4a55-b73a-5311be2411dc" />

3) Connection example, 3 client connections, authenticated, acknowledged and subscribed.
   <img width="1919" height="1062" alt="dtcomm_multi" src="https://github.com/user-attachments/assets/1b85e580-270c-425a-896d-736f6c3072ce" />




The project is being developed using an industrial chiller as the primary demonstration platform.

---

## Project Status

**Active Development**
On going
1) Security on communication transmission.
2) Provide communication interface or socket for MQTT, OPC UA, Modbus or other protocols.

DTComm is currently a development and demonstration project.

The implementation is **closed source**. This repository is provided as a public project showcase and does not contain the DTComm source code.

---

## Applications

DTComm is intended for applications involving:

**Industrial Automation · Equipment Monitoring · Digital Twins · IIoT · Condition Monitoring · Engineering Applications · Technical Training**

---

### DTComm

**Turning industrial equipment data into usable real-time information.**

