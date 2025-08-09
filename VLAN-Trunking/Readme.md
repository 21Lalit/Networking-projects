# 🌐 VLAN Trunking with Multiple Departments in Cisco Packet Tracer

*"Segmentation brings clarity. VLANs bring control."*

---

## 📖 Overview

This project demonstrates **VLAN Trunking** in a multi-department setup using **Cisco Packet Tracer**. VLANs are used to logically segment a network, improve performance, and enhance security. Trunking enables VLAN communication across switches.

---

## 🖧 Network Topology

![VLAN Trunking Topology](https://github.com/21Lalit/Networking-projects/blob/main/VLAN-Trunking/VLAN-Trunking.png)

### 🏢 Departments and VLAN Mapping:

* **Department 1 (MP)** – VLAN 2
* **Department 2 (Assam)** – VLAN 3
* **Department 3 (Delhi)** – VLAN 4
* **Department 4 (Haryana)** – VLAN 5

### 🔌 Topology Summary:

* **Two Switches** (Switch2 and Switch3)
* **End Devices** connected to specific VLANs based on departments
* **Trunk link** between switches to carry multiple VLANs
* **Server and Laptops** for extended testing

---

## ⚙️ VLAN Configuration Steps

### 🚀 To Enable Trunk Mode

```bash
enable
configure terminal
interface fa0/3
switchport mode access
switchport mode trunk
```

### 🧱 To Create VLANs

```bash
enable
configure terminal
vlan 2
name MP
vlan 3
name Assam
vlan 4
name Delhi
vlan 5
name Haryana
```

### 🔧 To Assign Ports to VLANs

```bash
interface fa0/x
switchport mode access
switchport access vlan <vlan_id>
```

---

## 📟 Switch Configurations

### 📘 Switch 2:

![Switch2 Config](https://github.com/21Lalit/Networking-projects/blob/main/VLAN-Trunking/Switch2-Configurations.png)

* VLANs created: 2 (MP), 3 (Assam), 4 (Delhi), 5 (Haryana)
* Ports mapped accordingly to VLANs

### 📙 Switch 3:

![Switch3 Config](https://github.com/21Lalit/Networking-projects/blob/main/VLAN-Trunking/Switch3-Configurations.png)

* Identical VLAN configuration to Switch2
* Consistent port-to-VLAN mapping

---

## 🧪 Key Learnings

* **VLAN Trunking** allows multiple VLANs to be carried over a single physical link.
* **Logical segmentation** of network using VLANs reduces broadcast domains and improves security.
* **Trunk ports** must be configured on both sides to ensure VLAN data is correctly tagged and understood.

---

## 📌 Troubleshooting Tips

* Ensure VLAN IDs match across switches
* Verify trunk ports are correctly configured
* Use `show vlan` and `show interface trunk` commands for debugging

---

## 🎯 Future Scope

* Add **Router-on-a-Stick** to enable inter-VLAN routing
* Use **VTP** (VLAN Trunking Protocol) to propagate VLANs automatically
* Implement **Port Security** for enhanced control

---
# Another Example
![VLAN Trunking Topology](https://github.com/21Lalit/Networking-projects/blob/main/VLAN-Trunking/Another-Example.png)
---
> *"A well-segmented network is a well-managed network."*

📡 Keep your network clean, controlled, and secure with VLANs!
