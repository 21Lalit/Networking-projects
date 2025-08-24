# 🛠️ EIGRP Configuration

## 📌 Overview

**EIGRP (Enhanced Interior Gateway Routing Protocol)** is a **distance vector** routing protocol developed by Cisco, designed to be more efficient and faster than RIP.
It supports **classless routing**, uses **DUAL (Diffusing Update Algorithm)** for loop-free paths, and is **only supported on Cisco devices**.

---

## 🌐 Network Topology

![EIGRP Topology Diagram](https://github.com/21Lalit/Networking-projects/blob/main/EIGRP-Configuration/eigrp-topology.png)

```
        ┌───────────────┐                   ┌───────────────┐
        │     R1        │                   │     R2        │
        │---------------│                   │---------------│
        │192.168.12.1   │ 192.168.12.0/24   │192.168.12.2   │
        │1.1.1.1        │ <---------------> │2.2.2.2        │
        └───────────────┘                   └───────────────┘
```

> Both routers are in **EIGRP Autonomous System 100**.

---

## ⚙️ Configuration

### 📍 Router R1

```bash
enable
configure terminal

hostname R1

interface FastEthernet0/0
 ip address 192.168.12.1 255.255.255.0
 no shutdown

interface Loopback0
 ip address 1.1.1.1 255.255.255.255

router eigrp 100
 network 192.168.12.0 0.0.0.255
 network 1.1.1.1 0.0.0.0
 no auto-summary

end
write memory
```

---

### 📍 Router R2

```bash
enable
configure terminal

hostname R2

interface FastEthernet0/0
 ip address 192.168.12.2 255.255.255.0
 no shutdown

interface Loopback0
 ip address 2.2.2.2 255.255.255.255

router eigrp 100
 network 192.168.12.0 0.0.0.255
 network 2.2.2.2 0.0.0.0
 no auto-summary

end
write memory
```

---

## 🔍 Verification Commands

```bash
show ip eigrp neighbors     # Check EIGRP adjacency
show ip route eigrp         # View routes learned via EIGRP
show ip protocols           # Confirm EIGRP settings
```

---

## 💡 Notes

* All routers in the same EIGRP domain **must share the same AS number**.
* `no auto-summary` disables classful routing and enables VLSM.
* Wildcard masks are **inverse** of subnet masks.
* Use `write memory` to save configuration permanently.

---

> *"In networking, every connection matters – in security, every connection is suspect."* – Anonymous
