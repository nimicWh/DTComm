# Changelog
## [v0.2.0] - 27/8/26

# OPC UA Integration

Added OPC UA communication capability to DTComm. 

## OPC UA Server (DTComm as a server)
- Test with console. No GUI yet.
- Using UA Expert (A product from Unified Automation)  to connect.
- Certificates authorization between server and client with DTComm as server and UA Expert as client
- All certificates loaded are for testing only

1) Password before connect
<img width="1902" height="981" alt="dtcomm_opcua1" src="https://github.com/user-attachments/assets/f64486bc-1808-4fff-bc27-947da8619546" />









## OPC UA Client 

Implemented a DTComm OPC UA client test application.









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

* Monitoring applications.
* Engineering applications.
* Digital twin systems.


DTComm is c

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

The OPC UA development to complete live data-change path from the simulated equipment through the OPC UA server to the client.

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

## [v0.1.0] - 12/08/2026

### Overview

DTComm progressed from its core communication foundation into an industrial communication platform supporting  multi-client communication and OPC UA integration**.

The current development platform uses a **simulated industrial chiller** as the equipment model for demonstrating communication and monitoring capabilities.

Testing done with local console.

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

Implemented validation for:

* Valid packets.
* Tampered packets.
* Invalid packet magic.
* Truncated packets.
* Invalid packet lengths.

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

---
