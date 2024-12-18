# 🕵️‍♂️ Evil Twin Attack

⚠️ A simulation of an Evil Twin Wi-Fi attack using Cisco Packet Tracer.

---

## 📖 Overview

This project demonstrates an Evil Twin Attack, a wireless network attack where a rogue access point (AP) impersonates a legitimate one to trick users into connecting. Using Cisco Packet Tracer, this simulation visually represents how unsuspecting devices connect to the "Evil Twin," compromising their data security.

---

## 🌐 Network Topology

### ✅ Legitimate Access Point
- **Name:** Legitimate_Wireless_Router
- **SSID:** Legitimate_AP
- **Security:** WPA2-PSK (Password: 123123123)

**Connected Devices:**
- 📱 Smartphone1
- 💻 Laptop1
- 🖥️ PC0
- 🖥️ PC1
- 🖥️ Server1

### ❌ Evil Twin Access Point
- **Name:** Evil_Twin_Wireless_Router
- **SSID:** Same as Legitimate AP (Legitimate_AP)
- **Security:** No Password (Open Network)

**Connected Devices:**
- 💻 Laptop0
- 📱 Smartphone0

---

## 📸 Evil Twin Network Diagram
![Evil Twin Network Diagram](https://github.com/21Lalit/Networking-projects/blob/main/Evil-Twin-Attack/Evil-Twin-Attack.png)

---

## 🕵️ What is an Evil Twin Attack?

An Evil Twin Attack is a Wi-Fi attack where a hacker sets up a rogue wireless router mimicking a legitimate access point (same SSID). Devices connect to this AP thinking it’s safe, giving the hacker access to their network traffic.

---

## 🔍 How It Works:
- The rogue access point is configured with the same SSID as the legitimate one.
- No security (open network) is used to attract unsuspecting devices.
- Devices connect to the Evil Twin, exposing sensitive data.
- Attackers can intercept traffic, steal credentials, or launch further attacks.

---
### The Attack in Action:
1. **Laptop0** and **Smartphone0** were originally connected to the legitimate access point (Legitimate_Wireless_Router) when they were near it.
2. The attacker, setting up the rogue **Evil Twin** AP, broadcasted the same SSID as the legitimate AP, tricking nearby devices into thinking it was the same network.
3. Since **Evil Twin** had no security (open network), the devices, unaware of the attack, automatically connected to it, believing it was the legitimate network.
4. **Laptop0** and **Smartphone0** were now connected to the **Evil Twin** instead of the legitimate access point, exposing their sensitive data to the attacker.

![Access_Points](https://github.com/21Lalit/Networking-projects/blob/main/Evil-Twin-Attack/Wireless-Access-Points.png)

### The Result:
- The attacker could now monitor all the traffic coming from **Laptop0** and **Smartphone0**.
- The devices' sensitive data, including usernames, passwords, and browsing activity, could be intercepted, and further attacks could be launched, such as credential theft or man-in-the-middle attacks.

This highlights the vulnerability of devices that automatically connect to open Wi-Fi networks and the risks of connecting to networks without verifying their authenticity.

---

## ⚙️ Simulation Steps

### 1. Setup Legitimate Access Point:
- Configure WPA2-PSK security with password `123123123`.
- Connect legitimate devices (Laptop1, PC0, PC1, Smartphone1, and Server1).

### 2. Setup Evil Twin Access Point:
- Configure the same SSID (Legitimate_AP) with no security.
- Allow open connections.

### 3. Device Connections:
- Laptop0 and Smartphone0 automatically connect to the rogue AP due to the open configuration.

### 4. Monitor Behavior:
- Observe which devices connect to the fake AP and analyze the impact.

---

## 🚨 Impact of the Attack
- **Data Interception 🕵️‍♀️**: Sensitive data can be captured by the attacker.
- **Credential Theft 🔑**: Users might unknowingly expose passwords and private information.
- **MITM (Man-In-The-Middle) Attacks 🌐**: Traffic can be intercepted, altered, or redirected.
- **Malware Injection 🐍**: Devices may download malicious payloads.

---

## 🛡️ Prevention Measures
- 🔒 **Verify SSIDs** before connecting to any Wi-Fi network.
- 🛡️ **Use a VPN** to encrypt your traffic on public Wi-Fi.
- 🚫 **Disable automatic connection** to open networks.
- 🔍 **Deploy Wireless Intrusion Detection Systems (WIDS)**.
- 🪪 **Use certificate-based authentication** for trusted networks.

---

## 🛠️ Tools Used
- 🧰 **Cisco Packet Tracer**: For network simulation.
- 📶 **Wireless Routers**: Configured as legitimate and rogue APs.
- 💻 **End Devices**: Laptops, smartphones, PCs, and servers.

---

## 🎯 Key Learnings
- How an Evil Twin Attack works.
- The risks associated with unsecured public Wi-Fi.
- Measures to identify and mitigate rogue APs in real-world networks.

---

## 📢 Conclusion

This simulation illustrates how vulnerable devices can connect to malicious networks when proper Wi-Fi security practices aren't followed. Understanding the attack helps in raising awareness and adopting secure networking habits.

> _"Trust takes years to build, seconds to break, and forever to repair. Protect your networks."_

🛡️ Stay Secure, Stay Aware.
