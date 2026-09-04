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

Notes: All information sources, coding and findings and researches from internet. They contributes to the build up of this  project.


---

## DTComm System Overview

The current DTComm demonstration uses a simulated industrial chiller to represent equipment operating in an industrial environment.

```text
             ┌─────────────────────┐
             │   Simulated Chiller │
             │                     │
             │  Live Equipment     │
             │  Sensor Data        │
             │  Operating Status   │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │       DTComm        │
             │                     │
             │ Communication Layer │
             │ Security            │
             │ Sessions            │
             │ Telemetry           │
             │ Subscriptions       │
             └──────────┬──────────┘
                        │
              ┌─────────┴──────────────────────────────┐
              │                   │                    │
              ▼                   ▼                    ▼
       ┌─────────────┐     ┌─────────────┐      ┌─────────────┐
       │   DTComm    │     │    OPC UA   │      │ Blockchain  │
       │   Client    │     │  Interface  │      │  Interface  │
       │             │     │             │      │  Persisted  │
       │ Monitoring  │     │ Industrial  │      │  Storage    │
       │ Application │     │ Integration │      │             │
       └──────┬──────┘     └─────────────┘      └─────────────┘
              │
              ▼
       ┌─────────────┐
       │    Live     │
       │  Monitoring │
       │             │
       │ Equipment   │
       │ Status      │
       │ Sensor Data │
       └─────────────┘
```

### Communication Flow

**Industrial Equipment**

The simulated chiller continuously generates equipment operating data.

↓

**DTComm**

DTComm manages equipment communication, sessions, security, telemetry and data subscriptions.

↓

**Communication Interfaces**

DTComm data can be exposed to applications through communication interfaces such as DTComm and OPC UA. MQTT and Modbus are part of the planned development direction.

↓

**Monitoring Application**

The client receives equipment data and presents the information as a real-time monitoring view.

### End-User Perspective

The intended concept is straightforward:

```text
Equipment
    ↓
Equipment Data
    ↓
DTComm
    ↓
Communication
    ↓
Application
    ↓
Usable Information
```

DTComm is intended to provide the communication layer between industrial equipment and higher-level engineering or monitoring applications.

The simulated chiller provides a controlled environment for demonstrating this architecture before integration with physical industrial equipment.


## What DTComm do?

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

## Industrial Cybersecurity

The long-term security direction of DTComm is intended to align with the **IEC 62443 family of standards**, which provides a framework for cybersecurity in industrial automation and control systems.

Security is being considered alongside the development of:

* Equipment communication
* Application interaction
* Device and session management
* Access control
* Authentication and authorization
* Protection of the communication pipeline

The project aims to adopt security practices and principles that are consistent with the IEC 62443 approach, with the objective of reducing the risk of unauthorized access, malicious activity and other threats to the communication pipeline within industrial automation environments.

The intention is to make **security part of the communication platform from the beginning**, rather than treating cybersecurity as an additional layer after the communication system has been developed.


---

## Demonstration

## Screenshots
1) Server to client interaction
   <img width="1919" height="1048" alt="dtcomm1" src="https://github.com/user-attachments/assets/6978cd2a-bd78-4fab-97cc-09f4ec5c34f7" />

2) Subscription
   <img width="1919" height="1062" alt="dtcomm_sub" src="https://github.com/user-attachments/assets/090977c8-013c-4a55-b73a-5311be2411dc" />

3) Connection example, 3 client connections, authenticated, acknowledged and subscribed.
   Different timing startup for each client and connect to server. Server registered 3 connections individually.
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

