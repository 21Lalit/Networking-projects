# 🔐 AAA with RADIUS Server Configuration in Cisco Packet Tracer

*"Authentication is the first step to trust in networking."*

---

## 📖 Overview

This project demonstrates the implementation of **AAA (Authentication, Authorization, Accounting)** using a **RADIUS server** in Cisco Packet Tracer. It showcases how devices like routers can delegate user authentication to a central server—adding security, control, and centralized credential management.

---

## 🖧 Network Topology

![AAA RADIUS Network](https://github.com/21Lalit/Networking-projects/blob/main/AAA-Radius-Server/Topology.png)

### Components:

* **Router1 (ISR4331)** – 192.168.1.1/24
* **Switch1** – Central connection hub
* **PC2 (Client)** – 192.168.1.2/24
* **Server (Radius Server)** – 192.168.1.3/24

All devices are connected via a switch.

---

## ⚙️ RADIUS Server Configuration

### ✅ Server Details:

* **Service**: AAA (Enabled)
* **RADIUS Port**: 1645
* **Client (Router)**:

  * IP: `192.168.1.1`
  * Server Type: `Radius`
  * Key: `12312345`

### 👤 User Credentials:

* **Username**: `lalit`
* **Password**: `12312345`

![RADIUS Configuration Screenshot](https://github.com/21Lalit/Networking-projects/blob/main/AAA-Radius-Server/Radius-Server.png)

---

## 🔑 Concept: What is AAA and RADIUS?

### AAA (Authentication, Authorization, Accounting):

* **Authentication**: Who are you?
* **Authorization**: What can you access?
* **Accounting**: What did you do?

### RADIUS (Remote Authentication Dial-In User Service):

* Centralized protocol that provides AAA services over IP-based networks.
* Encrypts only the password (not the entire payload).

---

## 🧪 Simulation Steps

### 🛠️ Router Configuration

```
enable
conf t
hostname R1
interface g0/0/0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
exit
```

### 🔐 Configure AAA on the Router

```
aaa new-model
radius server host
 address ipv4 192.168.1.3
 key 12312345
exit
aaa authentication login AAA group radius local
```

### 🌐 Configure VTY Lines for Telnet Access

```
line vty 0 4
login authentication AAA
transport input telnet
```

### 🖥️ Server Configuration

* Navigate to **Services → AAA**
* Turn ON AAA service
* Server Type: **RADIUS**
* Under **Network Configuration**:

  * **Client Name**: Router
  * **Client IP**: 192.168.1.1
  * **Secret**: 12312345
  * Click **Add**
* Under **User Setup**:

  * **Username**: lalit
  * **Password**: 12312345
  * Click **Add**

![Client Login Verification](https://github.com/21Lalit/Networking-projects/blob/main/AAA-Radius-Server/AAA-Client.png)

---


## 🎯 Key Learnings

* How to set up a basic RADIUS server in Cisco Packet Tracer.
* Use of AAA model to improve network authentication security.
* Testing router login via **Telnet** with centralized credentials.

---

## 🚀 Future Scope

* Integrate **TACACS+** for encryption of full payload.
* Use **802.1X** for port-based network access control.
* Add **accounting** to log user activity.

---

> *"Centralized authentication builds decentralized trust."*

🛡️ Secure your network, one login at a time.
