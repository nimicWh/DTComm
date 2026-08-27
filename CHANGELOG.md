# Changelog

## [v0.1.0] - 2026-08-27

### Overview

DTComm progressed from its core communication foundation into an industrial communication platform supporting  multi-client communication and OPC UA integration**.

The current development platform uses a **simulated industrial chiller** as the equipment model for demonstrating communication and monitoring capabilities.

---

## Added

### DTComm Core Communication

* TCP transport layer.
* DTComm frame protocol.
* Packet serialization and deserialization.
* Packet type definitions.
* `CONNECT` handshake.
* Session management.
* Ping/Pong heartbeat.
* Connection management.
* Subscription mechanism.
* Sensor data packet support.

### Real-Time Telemetry

Implemented the initial telemetry architecture for continuous equipment data:

```text
Simulated Chiller
       ↓
ChillerDevice
       ↓
Runtime Scan
       ↓
TagCache
       ↓
SubscriptionManager
       ↓
SensorData Packet
       ↓
DTComm Client
       ↓
Live Monitoring
```

The runtime architecture uses a **100 ms scan interval** as the current development target.

### Equipment Simulation

Added a simulated industrial chiller as the primary demonstration equipment.

The simulation provides continuously changing equipment and sensor values for communication and monitoring tests.

Current demonstration data includes:

* Chilled-water supply temperature.
* Device status.
* Sensor values.
* Equipment operating data.

### Multi-Client Communication

Added support for multiple simultaneous DTComm client connections.

The server can independently register and manage multiple client sessions.

Testing demonstrated:

* Multiple client connections.
* Independent client startup timing.
* Individual client connection handling.
* Client subscriptions.
* Continuous communication with multiple clients.

### Packet Integrity

Added **CRC-32C** packet integrity verification.

Implemented validation for:

* Valid packets.
* Tampered packets.
* Invalid packet magic.
* Truncated packets.
* Invalid packet lengths.
* Unexpected trailing data.

Example test results:

```text
PASS: Valid packet accepted.
PASS: Tampered packet rejected by CRC-32C.

PASS: Bad Magic rejected - Invalid DTComm packet.
PASS: Truncated packet rejected - Invalid DTComm packet length.
PASS: Unexpected trailing data rejected - Invalid DTComm packet length.
```

### Security

Implemented the initial DTComm authentication and authorization framework.

Added:

* Username/password authentication.
* Password hashing.
* Account management.
* Account lockout.
* User roles.
* Permissions.
* Authorization enforcement.

Authentication and authorization behaviour has been tested.

The security architecture is being developed with reference to **IEC 62443 industrial cybersecurity principles**.

DTComm does **not** claim IEC 62443 compliance or certification.

---

# OPC UA Integration

Added OPC UA communication capability to DTComm.

## OPC UA Server

Implemented:

* DTComm OPC UA server.
* OPC UA application instance.
* Application certificate handling.
* PKI certificate store.
* DTComm runtime data source integration.
* OPC UA equipment nodes.
* OPC UA monitored items.
* OPC UA subscriptions.

Example node:

```text
ns=2;s=Chiller01.Temperature
```

## OPC UA Client

Implemented a DTComm OPC UA client test application.

The client currently supports:

* Endpoint discovery.
* Application certificate loading.
* Certificate exchange.
* Secure channel establishment.
* Username/password authentication.
* OPC UA session creation.
* Monitored item creation.
* OPC UA subscription creation.

Example successful test state:

```text
CONNECTION SUCCESSFUL

OPC UA SUBSCRIPTION STARTED
Node : ns=2;s=Chiller01.Temperature
```

---

# Verified

### DTComm Communication

The following communication functions have been successfully tested:

* TCP connection.
* Client/server communication.
* Session establishment.
* Heartbeat.
* Subscription mechanism.
* Continuous telemetry architecture.
* Multiple client connections.

### Packet Integrity

CRC-32C integrity protection has been tested successfully against valid and deliberately invalid packet data.

### Security

The authentication and authorization framework has been tested, including access control and account security behaviour.

### OPC UA Connection

The OPC UA implementation has successfully demonstrated:

1. Endpoint discovery.
2. Certificate loading.
3. Certificate exchange.
4. Secure channel establishment.
5. User authentication.
6. Session creation.
7. Monitored item creation.
8. Subscription creation.

---

# In Progress

## OPC UA Live Telemetry

The remaining OPC UA development work is to verify the complete live data-change path from the simulated equipment through the OPC UA server to the client.

Target path:

```text
Simulated Chiller
       ↓
DTComm Runtime
       ↓
OPC UA Server Variable
       ↓
DataValue Update
       ↓
OPC UA DataChange Notification
       ↓
OPC UA Subscription
       ↓
DTComm OPC UA Client
       ↓
Live Value
```

The OPC UA connection, security, session and subscription layers are operational.

The **server-side variable update and end-to-end live data-change notification path remains under verification**.

---

# Architecture Direction

DTComm is evolving toward a layered industrial communication architecture:

```text
┌──────────────────────────────────────┐
│     Digital Twin / Applications      │
├──────────────────────────────────────┤
│   OPC UA / MQTT / Modbus Interfaces  │
├──────────────────────────────────────┤
│        DTComm Telemetry Layer        │
├──────────────────────────────────────┤
│    Session / Security Management     │
├──────────────────────────────────────┤
│       DTComm Packet Protocol         │
├──────────────────────────────────────┤
│            TCP Transport             │
└──────────────────────────────────────┘
```

The objective is to provide a communication foundation between:

* Industrial equipment.
* Equipment simulation.
* Real-time telemetry.
* Monitoring applications.
* Engineering applications.
* Digital twin systems.


DTComm is currently a development and demonstration project. The GitHub repository is provided as a public engineering project showcase and does not contain the DTComm source code.
