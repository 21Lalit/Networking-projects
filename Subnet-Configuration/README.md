# Subnet Configuration

## 🌐 Introduction
This document provides an overview of the subnet configuration for a network using the IP address range `192.168.1.0-255`. The network has been divided into multiple subnets for different departments to enhance organization, improve security, and ensure efficient utilization of IP addresses. Each department operates in an isolated environment, preventing direct communication with other departments.

---

## 📋 Network Details

### IP Address Range
- **Overall Range**: 192.168.1.0-255
- **Subnetting Purpose**: To divide the network into smaller, manageable segments for different departments while maintaining isolation and security.
![Subnetting](https://github.com/21Lalit/Networking-projects/blob/main/Subnet-Configuration/Subnetting.png)
### 🛠️ Subnet Mask Definitions
- **Subnet Mask**: Defines the division of the IP address into network and host portions.
- **CIDR Notation**: Compact representation of the subnet mask (e.g., `/28` or `/29`).

| **Subnet Mask** | **CIDR** | **Hosts Per Subnet** |
|------------------|----------|----------------------|
| 255.255.255.240  | /28      | 14                   |
| 255.255.255.248  | /29      | 6                    |

---

## 🏢 Subnets Created

### Department A
- **IP Address Range**: 192.168.1.0-15
- **Subnet Mask**: 255.255.255.240 (/28)

| **💻 Device** | **IP Address**   | **Gateway Address** |
|------------|------------------|---------------------|
| PC0        | 192.168.1.1/28   | 192.168.1.254       |
| PC1        | 192.168.1.2/28   | 192.168.1.254       |
| PC2        | 192.168.1.7/28   | 192.168.1.254       |
| PC3        | 192.168.1.8/28   | 192.168.1.254       |
| PC4        | 192.168.1.3/28   | 192.168.1.254       |
| PC5        | 192.168.1.9/28   | 192.168.1.254       |
| PC6        | 192.168.1.4/28   | 192.168.1.254       |
| PC7        | 192.168.1.10/28  | 192.168.1.254       |
| PC8        | 192.168.1.5/28   | 192.168.1.254       |
| PC9        | 192.168.1.11/28  | 192.168.1.254       |
| PC10       | 192.168.1.6/28   | 192.168.1.254       |
| PC11       | 192.168.1.12/28  | 192.168.1.254       |

### Department B
- **IP Address Range**: 192.168.1.16-23
- **Subnet Mask**: 255.255.255.248 (/29)

| **💻 Device** | **IP Address**   | **Gateway Address** |
|------------|------------------|---------------------|
| PC12       | 192.168.1.17/29  | 192.168.1.254       |
| PC13       | 192.168.1.20/29  | 192.168.1.254       |
| PC14       | 192.168.1.18/29  | 192.168.1.254       |
| PC15       | 192.168.1.21/29  | 192.168.1.254       |
| PC16       | 192.168.1.19/29  | 192.168.1.254       |
| PC17       | 192.168.1.22/29  | 192.168.1.254       |

### Department C
- **IP Address Range**: 192.168.1.24-31
- **Subnet Mask**: 255.255.255.248 (/29)

| **💻 Device** | **IP Address**   | **Gateway Address** |
|------------|------------------|---------------------|
| PC18       | 192.168.1.25/29  | 192.168.1.254       |
| PC19       | 192.168.1.28/29  | 192.168.1.254       |
| PC20       | 192.168.1.26/29  | 192.168.1.254       |
| PC21       | 192.168.1.29/29  | 192.168.1.254       |
| PC22       | 192.168.1.27/29  | 192.168.1.254       |
| PC23       | 192.168.1.30/29  | 192.168.1.254       |

---

## 📖 Key Definitions

### 🔍 Subnet
A logical subdivision of an IP network that helps segment a large network into smaller parts, improving management and security.

### 🌐 Gateway
A network node that serves as an access point to another network, often connecting local devices to external networks.

### 🧮 CIDR (Classless Inter-Domain Routing)
A method for allocating IP addresses and routing that allows for more flexible and efficient use of IP address space compared to traditional classful addressing.

---

## 🛠️ Configuration Notes
- **🔒 Isolation**: Each department has been assigned a unique subnet to ensure isolation and prevent inter-department communication.
- **📌 Gateway Configuration**: All devices use `192.168.1.254` as the gateway address for external communication.
- **🧾 Subnet Masks**: Ensure the appropriate subnet mask is used for accurate IP address allocation and routing.

---

## 🌟 Benefits of Subnetting
- **🔐 Enhanced Security**: Limits communication between different subnets.
- **📈 Efficient Address Management**: Avoids wastage of IP addresses.
- **🚀 Improved Performance**: Reduces network congestion by limiting broadcast domains.

---

## 🛡️ Troubleshooting Tips
1. ✅ Verify IP address and subnet mask configurations on each device.
2. ✅ Ensure the gateway address is consistent across devices in the same subnet.
3. ✅ Check for conflicts or overlapping IP addresses within subnets.

---

> "Subnetting is not just about dividing networks; it's about uniting devices in a structured and secure manner." 
