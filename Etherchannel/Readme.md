# 🔗 EtherChannel with LACP Configuration in Cisco Packet Tracer

*"Stronger together: EtherChannel binds bandwidth and resilience."*

---

## 📖 Overview

This project demonstrates the configuration of **EtherChannel using LACP (Link Aggregation Control Protocol)** between two Cisco switches. EtherChannel bundles multiple physical links into a single logical link to enhance bandwidth, provide redundancy, and improve fault tolerance.

---

## 🖧 Network Topology

![EtherChannel Topology](https://github.com/21Lalit/Networking-projects/blob/main/EtherChannel/EtherChannel-Topology.png)

### Components:

* **Switch0** – 2960-24TT
* **Switch1** – 2960-24TT
* **Connections**: Two Ethernet cables (Fa0/1 and Fa0/2) between the switches

---

## 🔍 Key Concepts

### 🧠 What is EtherChannel?

EtherChannel combines multiple Ethernet links between devices to act as a single logical link.

### 🔗 What is LACP?

* **LACP (Link Aggregation Control Protocol)** is an IEEE 802.3ad standard.
* Dynamically establishes EtherChannel.
* Works between multiple vendor devices (e.g., Cisco ↔ HP).

### ✅ Why Use EtherChannel with LACP?

* **Increased Bandwidth**: Aggregate capacity of multiple links.
* **Redundancy**: One link fails, traffic still flows through others.
* **STP Optimization**: Prevents STP from blocking ports.
* **Congestion Reduction**.
* **Simplified Management**.

---

## ⚙️ Switch Configurations

### 🔧 Switch1 Configuration

```bash
enable
conf t
interface range fa0/1 - 2
 channel-group 1 mode active
exit

interface port-channel 1
 switchport mode trunk
exit
```

### 🔧 Switch0 Configuration

```bash
enable
conf t
interface range fa0/1 - 2
 channel-group 1 mode passive
exit

interface port-channel 1
 switchport mode trunk
exit
```

> 💡 Note: You can also use `active` mode on both switches for dynamic negotiation.

---

## 🔍 Verification

### Run the following command:

```bash
show etherchannel summary
```

**Output Explanation:**

* **Po1(SU)**:

  * **S** = Layer 2 (Switching)
  * **U** = Up (Operational)
  * Indicates ports Fa0/1 and Fa0/2 are bundled in EtherChannel

---

## 🎯 Key Learnings

* Configuration of LACP-based EtherChannel between two switches
* Verification using `show etherchannel summary`
* How EtherChannel improves both speed and fault tolerance

---

> *"EtherChannel isn't just faster; it's smarter networking."*

🚀 Combine for strength, connect for resilience!
