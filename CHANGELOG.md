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

## OPC UA Client (server and client test program)
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
