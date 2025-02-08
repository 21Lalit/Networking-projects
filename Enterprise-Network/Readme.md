# 🌐 Enterprise Network Project

## 📌 Overview
This project showcases the implementation of an **Enterprise Network** using **VLANs (Virtual Local Area Networks)** to efficiently manage and segment different departments within an organization. The network topology integrates multiple VLANs, access points, printers, and an internet gateway to enhance **security, scalability, and performance**.

---
## 🏗️ Network Design
The network is structured into distinct VLANs to segregate departments, ensuring optimal communication and data flow.
---
### Enterprise Network Topology
![Enterprise Network Topology](https://github.com/21Lalit/Networking-projects/blob/main/Enterprise-Network/Enterprise-Network-Topology.png)
---
### 🔹 VLAN 2: Sales Department
- **🖥 Devices:**
  - 💻 Laptop (192.168.1.5)
  - 📱 Smartphone (192.168.1.4)
  - 🖥️ PC (192.168.1.2)
  - 🖨 Printer (192.168.1.3)
- **🌍 Gateway:** 192.168.1.1
- **📡 Connected via:** Access Point & Switch

### 🔹 VLAN 3: Marketing Department
- **🖥 Devices:**
  - 💻 Laptop (192.168.1.5)
  - 🖥️ PC (192.168.1.6)
  - 🖨 Printer (192.168.1.7)
- **🌍 Gateway:** 192.168.1.1
- **📡 Connected via:** Access Point & Switch

### 🔹 VLAN 4: Machine Department
- **🖥 Devices:**
  - 💻 Laptop (192.168.1.7)
  - 🖥️ PC (192.168.1.8)
  - 📟 Tablet (192.168.1.9)
  - 🖨 Printer (192.168.1.10)
- **🌍 Gateway:** 192.168.1.1
- **📡 Connected via:** Access Point & Switch

---
## 🔧 Switch Configuration
![Switch VLAN Configuration](https://github.com/21Lalit/Networking-projects/blob/main/Enterprise-Network/Switch-VLAN-Configuration.png)

The switch is configured to manage VLANs efficiently, assigning specific interfaces to different VLANs:
- **VLAN 2 (Sales)**: Ports **Fa0/1, Fa0/2, Fa0/3**
- **VLAN 3 (Marketing)**: Ports **Fa0/5, Fa0/6, Fa0/7**
- **VLAN 4 (Machine)**: Ports **Fa0/8, Fa0/9, Fa0/10**
- **Default VLAN (1)**: Reserved for management purposes

---
## 🚦 Routing and Internet Access
- **🛜 Router:** Connected to the **Enterprise Network** via **Gig0/0/0**
- **🌍 ISP:** Ensuring **internet access**
- **🔁 Inter-VLAN Routing:** Managed via a **Layer 3 switch** or a **router** to enable communication between VLANs

---
## 🛠 Implementation Tools
- **🔧 Cisco Packet Tracer** for simulation
- **⚙️ VLAN configuration** via CLI on switches
- **📌 Static IP addressing** for structured device management

---
## 🌟 Key Features
✅ **Network Segmentation**: Improves security & efficiency
✅ **Access Control**: Restricts communication to relevant devices
✅ **Scalability**: Easy expansion with additional VLANs
✅ **Centralized Routing**: Facilitates smooth inter-VLAN communication

---
## 🚀 Future Improvements
🔹 Implement **Dynamic VLAN Assignment** via **RADIUS Server**
🔹 Introduce **Quality of Service (QoS)** for bandwidth management
🔹 Configure **Firewall Rules** to enhance inter-VLAN security

---
## 🎯 Conclusion
This **Enterprise Network** is structured to efficiently manage communication between departments while ensuring **security, scalability, and high performance**. The **VLAN implementation** reduces unnecessary traffic, increases overall network efficiency, and enhances data management. 

> "Technology is best when it brings people together." – Matt Mullenweg

