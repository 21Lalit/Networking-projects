# 📶 WPA2-PSK Wireless Network Setup in Cisco Packet Tracer

*"Secure connectivity is the foundation of safe networking."*

---

## 📖 Overview

This project demonstrates the configuration of a **WPA2-PSK (Wi-Fi Protected Access 2 - Pre-Shared Key)** wireless network using a **WRT300N wireless router** and a **laptop**. WPA2-PSK ensures encrypted wireless communication for secure client access.

---

## 🖧 Network Topology

```
[Wireless Router]---(Wireless)---[Laptop]
     WRT300N                       Laptop0
```

![WPA2-PSK Topology](https://github.com/21Lalit/Networking-projects/blob/main/WPA2-PSK/WPA2-PSK.png)

---

## ⚙️ Configuration Details

### 🔧 Wireless Router (WRT300N)

1. Click on the **Wireless Router**
2. Navigate to the **GUI tab** > **Wireless**
3. Set the following:

   * **SSID**: `SecureNet`
   * **Wireless Security**: `WPA2-PSK`
   * **Passphrase**: `cyber@123`
4. Click **Save Settings**

### 🧭 DHCP Configuration (Optional)

* Go to **Setup tab → Basic Setup**
* Ensure **DHCP Server** is enabled

### 💻 Laptop Configuration

1. Click on the **Laptop** > Go to **Desktop** tab > Open **PC Wireless**
2. Click the **Connect** tab
3. Select SSID: `SecureNet`
4. Enter the **Passphrase**: `cyber@123`
5. Click **Connect**

---

## ✅ Verification Steps

### 📡 IP Assignment

* Go to **Desktop > IP Configuration**
* Ensure IP is assigned via DHCP

### 🧪 Connectivity Test

Open **Command Prompt** from Laptop:

```bash
ipconfig          # Verify IP address
ping 192.168.0.1  # Ping the Wireless Router
```

---

## 🎯 Key Learnings

* Configuration of WPA2-PSK wireless security
* Wireless device connectivity in Packet Tracer
* Verification using DHCP and ICMP tools (ping)

---

## 🚀 Future Scope

* Add multiple clients for network load testing
* Implement MAC filtering for enhanced security
* Explore WPA3 if supported

---

> *"Encryption is your first line of defense in wireless networks."*

🛡️ Stay secure, stay wireless.
