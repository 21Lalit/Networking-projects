# 📡 DHCPv6 Configuration in Cisco Packet Tracer

### 📖 Overview

This project demonstrates how to configure **DHCPv6 (Dynamic Host Configuration Protocol for IPv6)** using a server in Cisco Packet Tracer. The DHCPv6 server dynamically assigns IPv6 addresses and other configuration information to client devices.

---

## 🖧 Topology Components

* **Server0** (DHCPv6 Server)
* **PC0** (Client)

---

## ⚙️ Router Configuration

```bash
enable
config t
ipv6 unicast-routing

ipv6 dhcp pool test
 address prefix 2001:DB8:1::/64
 dns-server 2001:4860:4860::8888
 domain-name website.com
exit

interface gig0/0/0
 ipv6 address 2001:DB8:1::1/64
 ipv6 enable
 ipv6 dhcp server test
 ipv6 nd managed-config-flag
 no shutdown
exit
exit
write memory
```

### 🔍 Verify Binding

```bash
show ipv6 dhcp binding
```

---

## 🖥️ DHCPv6 Server Configuration

1. **Go to Server0 → Services → DHCPv6**
2. **Create Pool**:

   * Pool Name: `test`
   * DNS Server: `2001:4860:4860::8888`
   * Domain Name: `example.com`
  

![AAA RADIUS Network](https://github.com/21Lalit/Networking-projects/blob/main/DHCPv6-Configuration/DHCP-POOL.png)

3. **IPv6 Address Prefix**:

   * Prefix: `2001:DB8:1::`
   * Prefix Length: `64`
![AAA RADIUS Network](https://github.com/21Lalit/Networking-projects/blob/main/DHCPv6-Configuration/DHCPv6-Server.png)
---

## 💻 Client Configuration (PC0)

1. Go to **Desktop → IP Configuration**
2. Under **IPv6 Configuration**:

   * Select: `Automatic`
   * Wait for the **"IPv6 request successful"** message
  

![AAA RADIUS Network](https://github.com/21Lalit/Networking-projects/blob/main/DHCPv6-Configuration/DHCPv6-Client.png)

---

## ✅ Verification

1. Open **Command Prompt** on PC0:

```bash
ipconfig       # Verify IP address assignment
ping <Router IPv6 Address>   # e.g., ping 2001:DB8:1::1
```

---

## 🎯 Key Learnings

* How to configure DHCPv6 server using GUI
* How to configure router with `ipv6 dhcp pool`
* Assign IPv6 addresses dynamically to client devices
* Importance of `ipv6 nd managed-config-flag`

---

> *"IPv6 is the future, and DHCPv6 makes managing it easier."*
