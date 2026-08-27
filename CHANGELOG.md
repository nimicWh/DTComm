# Changelog
## [v0.2.0] - 27/8/26

# OPC UA Integration

Added OPC UA communication capability to DTComm. 

## OPC UA Server (DTComm as a server)
- Test with console. No GUI yet.
- Using UA Expert (A product from Unified Automation)  to connect.
- Certificates authorization between server and client with DTComm as server and UA Expert as client
- All certificates loaded are for testing only
- All data are simulated for testing now.

1) Password before connect. Authorize the communication.
<img width="1902" height="981" alt="dtcomm_opcua1" src="https://github.com/user-attachments/assets/f64486bc-1808-4fff-bc27-947da8619546" />

2) Authorization to connect to DTComm with certificates verification between server and client. User authorization accepted.
<img width="1912" height="988" alt="Screenshot 2026-08-27 135551" src="https://github.com/user-attachments/assets/2265f724-fdcd-4325-84f6-cf4d7587c05e" />

3) Lets subscribe and send some data...
<img width="1899" height="993" alt="Screenshot 2026-08-27 135744" src="https://github.com/user-attachments/assets/f80d5d50-6887-4b10-82e7-856f132ffc2e" />

3) Some data.
<img width="1622" height="974" alt="dtcomm_ua_nodes_values" src="https://github.com/user-attachments/assets/ad6885fc-31a0-43f6-a7df-39706eacc06c" />












## OPC UA Client (server and client test program. The server uses above program)
- Test with console. No GUI yet.
- Certificates authorization between server and client.
- All certificates loaded are for testing only
- All data are simulated for testing now.
- * Password and username hard coded into the programs.

1)Client and server. Certifications authorization.
<img width="1916" height="845" alt="dtcomm_opcua_clt_svr" src="https://github.com/user-attachments/assets/2c8658bb-b137-4630-86ca-747df2c8557c" />











### DTComm Communication

The following communication functions have been successfully tested:

* TCP connection.
* Client/server communication.
* Session establishment.
* Subscription mechanism.



### Security

The authentication and authorization framework has been tested, including access control and account security behaviour.

* Monitoring applications.
* Engineering applications.
* Digital twin systems.



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

## [v0.1.0] - 12/08/2026

### Overview

DTComm progressed from its core communication foundation into an industrial communication platform supporting  multi-client communication and OPC UA integration**.

The current development platform uses a **simulated industrial chiller** as the equipment model for demonstrating communication and monitoring capabilities.

Testing done with local console.

## Added

### DTComm Core Communication

* TCP transport layer.
* DTComm frame protocol.
* `CONNECT` handshake.
* Session management.
* Ping/Pong heartbeat.
* Connection management.
* Subscription mechanism.
* Sensor data packet.

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
* Password.
* Account access.
* User roles.
* Permissions.
* Authorization enforcement.

---
