# 🎭 MAC Spoofing Attack

⚠️ A simulation of a MAC Spoofing attack using Cisco Packet Tracer.

---

## 📖 Overview

This project demonstrates a MAC Spoofing attack, where an attacker alters their device's MAC address to impersonate a legitimate device on a network. This technique is commonly used to bypass access controls, evade tracking, or conduct Man-in-the-Middle (MITM) attacks. Using Cisco Packet Tracer, this simulation visually represents how MAC addresses can be spoofed to manipulate network behavior.

---

## 🌐 Network Topology

### ✅ Legitimate Devices
- **PC 1** (Legitimate_PC_1)  
  - **MAC Address:** `00E0.B014.2164`
- **PC 2** (Legitimate_PC_2)  
  - **MAC Address:** `000A.4163.AE6B`

### ❌ Spoofing Device
- **Attacker PC** (Spoofed_Mac_Address)  
  - **Before Spoofing MAC:** `000A.4143.2882`  
  - **After Spoofing MAC:** `00E0.B014.2164`

### 🔀 Network Components
- **Switch** (Centralized network control)
- **Gateway** (192.168.1.1)

---

## 📸 MAC Spoofing Network Diagram
![MAC Spoofing Network Diagram](https://github.com/21Lalit/Networking-projects/blob/main/Mac-Spoof.png)

---

## 🕵️ What is MAC Spoofing?

MAC Spoofing is an attack where a malicious actor changes their device's Media Access Control (MAC) address to impersonate another legitimate device on the network. This technique is often used for:
- Bypassing network security measures like MAC address filtering.
- Evading tracking mechanisms.
- Launching Man-in-the-Middle (MITM) attacks.
- Gaining unauthorized access to restricted networks.

---

## 🔍 How It Works:
1. **Attacker identifies the target MAC address.**
2. **Attacker changes their device's MAC address** to match the legitimate device.
3. **Network switch recognizes the spoofed MAC as legitimate.**
4. **Attacker can intercept, manipulate, or disrupt network traffic.**

---

## ⚙️ Simulation Steps

### 1. Initial Setup:
- Configure the legitimate devices (PC 1 & PC 2) with their respective MAC addresses.
- Connect them to a centralized switch.

### 2. Attacker Setup:
- Configure the attacker's PC with its original MAC address (`000A.4143.2882`).
- Use MAC spoofing techniques to change the MAC to `00E0.B014.2164`.

### 3. Observe Network Behavior:
- The network switch now recognizes the attacker's device as `Legitimate_PC_1`.
- Any traffic intended for `Legitimate_PC_1` is now directed to the attacker's device.

---

## 🚨 Impact of the Attack

- **Unauthorized Network Access 🔓**: Attacker can gain access to restricted areas of the network.
- **Identity Theft 🎭**: The attacker's device is treated as a legitimate device.
- **Man-in-the-Middle Attack 🕵️**: The attacker can intercept and alter data packets.
- **Session Hijacking 🔄**: Ongoing sessions of the legitimate user can be taken over.

---

## 🛡️ Prevention Measures

- 🔒 **Enable Port Security:** Restrict MAC addresses on switch ports.
- 🔍 **Monitor Network Traffic:** Use intrusion detection systems to detect anomalies.
- 🔄 **Use Dynamic ARP Inspection (DAI):** Prevent ARP spoofing.
- 🪪 **Implement 802.1X Authentication:** Authenticate devices before granting access.
- 🚫 **Regularly Audit MAC Addresses:** Detect and block unauthorized MAC address changes.

---

## 🛠️ Tools Used

- 🧰 **Cisco Packet Tracer**: Network simulation tool.
- 💻 **PCs & Switches**: To simulate the attack environment.
- ⚡ **MAC Spoofing Techniques**: Used to alter the MAC address.

---

## 🎯 Key Learnings

- Understanding how MAC Spoofing attacks work.
- How attackers manipulate MAC addresses to bypass security.
- How to implement network security measures to mitigate such attacks.

---

## 📢 Conclusion

This simulation highlights the risks associated with MAC Spoofing attacks and the importance of network security measures. By implementing proper security mechanisms like MAC filtering, port security, and network monitoring, organizations can significantly reduce the risk of unauthorized access and data breaches.

> _"Security isn’t a product, it’s a process. Stay aware, stay protected."_

🛡️ Stay Secure, Stay Aware.