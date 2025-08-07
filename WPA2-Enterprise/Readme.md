# 🔐 AAA with RADIUS Server Configuration in Cisco Packet Tracer

*"Authentication is the first step to trust in networking."*

---

## 📖 Overview

This project demonstrates the implementation of **AAA (Authentication, Authorization, Accounting)** using a **RADIUS server** in Cisco Packet Tracer. It showcases how devices like routers can delegate user authentication to a central server—adding security, control, and centralized credential management.

---

## 🖧 Network Topology

```
[PC] ─── [Switch] ─── [Router1]
               |
           [Server]
 AAA Client   RADIUS Server
```

![AAA RADIUS Network](https://github.com/21Lalit/Networking-projects/blob/main/AAA-Radius/aaa-radius.png)

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

![RADIUS Configuration Screenshot](https://github.com/21Lalit/Networking-projects/blob/main/AAA-Radius/radius-server-config.png)

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

---

# 📶 WPA2-Enterprise Wireless Authentication with RADIUS

### Topology

```
[Laptop]---[Switch]---[Wireless Router]~~~(Wireless)~~~[PC]
               |
           [Server (RADIUS)]
```

![WPA2-Enterprise Topology](https://github.com/21Lalit/Networking-projects/blob/main/WPA2-Enterprise/WPA2-Enterprise-Topology.png)

---

### 🖥️ RADIUS Server Configuration

* **Service**: Radius (Enabled)
* **Client Name**: SecureWifi
* **Client IP**: 192.168.0.1 (Wireless Router IP)
* **Key**: 123123

#### User Credentials:

* **Username**: lalit
* **Password**: 12312345

---

### 📡 Wireless Router Configuration

* **SSID**: SecureWifi
* **Authentication**: WPA2-Enterprise
* **RADIUS Server IP**: 192.168.0.2 (RADIUS Server IP)
* **Key**: 123123

---

### 💻 Client (Laptop/PC) Configuration

1. **Add Wireless Adapter**:

   * Physical Tab → Add **WMP300N** module

2. **Connect to SSID**:

   * Desktop → PC Wireless → Create Profile
   * **SSID**: SecureWifi
   * **Security Mode**: WPA2-Enterprise
   * **Username**: lalit
   * **Password**: 12312345

3. Wait for the connection to sync and authenticate.

---

## ✅ Verification Steps

* Check IP Address from DHCP
* Ping Wireless Router or Server

```bash
ipconfig
ping 192.168.0.1
```

---

## 🎯 Key Learnings

* Configure WPA2-Enterprise with centralized user authentication
* Understand difference between WPA2-PSK vs WPA2-Enterprise
* Role of RADIUS in secure wireless access

---

> *"Enterprise-grade security begins with authenticated access."*
