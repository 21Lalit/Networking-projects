# 🔒 Access Mode Security - Network Security Configuration

## 📌 Overview
This project focuses on securing network access modes by implementing Console, VTY, and Privilege mode passwords on network switches. Proper access control is crucial to prevent unauthorized configuration changes and ensure network integrity.

## 📜 Table of Contents
- [📌 Overview](#-overview)
- [🎯 Objectives](#-objectives)
- [🛠️ Network Topology](#️-network-topology)
- [🔑 Security Configurations](#-security-configurations)
  - [1️⃣ Console & VTY Configuration](#1️⃣-console--vty-configuration)
  - [2️⃣ Privilege Mode Security](#2️⃣-privilege-mode-security)
- [📸 Project Screenshots](#-project-screenshots)
- [📂 Repository Structure](#-repository-structure)
- [🚀 How to Use](#-how-to-use)
- [📌 Conclusion](#-conclusion)

---

## 🎯 Objectives
✅ Configure console and VTY passwords to restrict unauthorized access.
✅ Secure privileged EXEC mode with a strong encrypted password.
✅ Implement user authentication for switch access.
✅ Apply best practices for password management in network security.

---

## 🛠️ Network Topology
The network consists of:
- A **switch** connected to multiple **PCs** and a **laptop**.
- Configured security access using Console, VTY, and Enable mode passwords.

![Network Topology](https://github.com/21Lalit/Networking-projects/blob/main/Access-Mode-Security/Access-Mode-Security.png)

---

## 🔑 Security Configurations
### 1️⃣ Console & VTY Configuration
To prevent unauthorized access to the switch, we configured:
```bash
line con 0
 password Console@123
 login
!
line vty 0 4
 password Vty@123
 login
!
line vty 5 15
 password Vty@123
 login
```
✅ **Console password:** `Console@123`
✅ **VTY password:** `Vty@123`

### 2️⃣ Privilege Mode Security
The privileged EXEC mode is secured with an encrypted password:
```bash
enable secret 5 $1$mERr$CJwqOh3WnG/b.aT8NV1J0.
username Lalit secret 5 Password@123
```
✅ **Enable password (encrypted)** ensures only authorized users can access privileged mode.
✅ **User authentication** with a secure password.

---

## 📸 Project Screenshots and Privileged Mode Security
### Console & VTY Configuration
![Console & VTY](https://github.com/21Lalit/Networking-projects/blob/main/Access-Mode-Security/Running-Configurations.png)

---

## 📂 Repository Structure
```
/Networking-projects
  ├── Access-Mode-Security.png  # Network topology diagram
  ├── Running-Configurations.png # CLI configuration outputs
  ├── README.md                 # Project documentation
```

---

## 🚀 How to Use
1️⃣ Open **Cisco Packet Tracer** or any network simulator.
2️⃣ Load the provided topology and access the switch CLI.
3️⃣ Apply the given configurations.
4️⃣ Verify secure access by logging in via console and VTY.

---

## 📌 Conclusion
This project demonstrates fundamental network security measures for securing switch access. By configuring console, VTY, and privilege mode passwords, unauthorized access can be prevented, ensuring a robust network infrastructure.

🚀 **Stay Secure & Happy Networking!** 🔥
> _ "Network security is a tapestry woven not just with firewalls and encryption, but with the threads of vigilance, adaptability, and collective resolve—each layer a testament to the art of defending what connects us."
---
