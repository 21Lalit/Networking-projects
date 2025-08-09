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


![aa-radius](https://github.com/21Lalit/Networking-projects/blob/main/WPA2-Enterprise/aaa-radius.png)
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
