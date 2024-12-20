# 🚀 Departments of a Company Network

_"The strength of a company lies in the strength of its network."_  
— Anonymous

## 🌟 Project Overview
This project reimagines a **corporate network** by simulating secure, efficient, and scalable communication across three departments: **Sales**, **Executive**, and **Production**. Leveraging **subnetting**, **VLANs**, and **innovative network design**, the infrastructure ensures seamless operations while maximizing security and resource optimization. 

📍 **Complete Network Overview**:  
![Complete Network](https://github.com/21Lalit/Networking-projects/blob/main/Company-Networks/Departments-of-a-Company-Network/Three-Departments.png)

---

## 📖 Definitions You Should Know

### 🔐 Subnetting
- **Definition**: Subnetting divides a large network into smaller, more manageable sub-networks, optimizing IP address utilization and enhancing security.
- **Why It's Used**: To reduce network congestion and manage resources effectively.

### 🌐 VLAN (Virtual Local Area Network)
- **Definition**: VLANs allow the creation of multiple virtual networks within the same physical infrastructure, isolating traffic for better performance and security.
- **Why It's Used**: To logically separate departments, reduce broadcast traffic, and enhance scalability.

### 🧠 Innovation in Design
1. **Dynamic Subnet Class Allocation**: Efficiently assigning Class A, B, and C IP ranges based on department size and needs.
2. **Precise Subnetting via VLSM**: Ensuring minimal wastage of IP addresses while maintaining flexibility.
3. **VLAN-Driven Security**: Leveraging VLANs to isolate sensitive operations like raw materials (Production) from general workflows.
4. **Scalability by Design**: Networks designed to accommodate future growth without major overhauls.

---

## 🏢 Departments and Network Design

### 1. 📊 Sales Department
The **Sales** department blends Class B and Class C IP addressing to optimize team-based networking:  
- **Class B**: Primary network range **172.16.2.1 - 172.16.2.2**.  
- **Class C**: Subnetted for smaller teams: **192.168.3.1 - 192.168.3.3**.

📍 **Visual Representation**:  
![Sales Department](https://github.com/21Lalit/Networking-projects/blob/main/Company-Networks/Departments-of-a-Company-Network/Sales-Department.png)

---

### 2. 💼 Executive Department
The **Executive** team uses **Class A subnetting** to create three secure sub-departments:  
- **Starting Address**: 10.0.0.1  
- **Subnet Mask**: /29 (255.255.255.248)  
- **IP Ranges**:  

| Sub-department | Subnet Range      | Usable IP Range       |
|----------------|-------------------|-----------------------|
| Sub-department 1 | 10.0.0.0/29       | 10.0.0.1 - 10.0.0.6   |
| Sub-department 2 | 10.0.0.8/29       | 10.0.0.9 - 10.0.0.14  |
| Sub-department 3 | 10.0.0.16/29      | 10.0.0.17 - 10.0.0.22 |

📍 **Visual Representation**:  
![Executive Department](https://github.com/21Lalit/Networking-projects/blob/main/Company-Networks/Departments-of-a-Company-Network/Executive-Department.png)

---

### 3. ⚙️ Production Department
The **Production** department employs **VLAN technology** to manage operations:  
- **Sub-departments**:
  - **Sell**: Manages finished goods.
  - **Raw**: Oversees raw material inventory.  
- **IP Range**: 192.168.20.0/24.  

📍 **Visual Representation**:  
![Production Department](https://github.com/21Lalit/Networking-projects/blob/main/Company-Networks/Departments-of-a-Company-Network/Production-Department.png)

---

## 🧮 Subdivision Techniques

### 1. Different IP Classes 🏷️
- **Use Case**: Used in the Sales department to separate primary and sub-networks.  
- **Outcome**: Easy management of team-level communications.

### 2. Subnetting with VLSM ✂️
- **Use Case**: Applied in the Executive department for precise resource allocation.  
- **Outcome**: Efficient IP usage with minimal wastage.

### 3. VLAN Technology 🔌
- **Use Case**: Used in the Production department for logical segmentation.  
- **Outcome**: Enhanced security and reduced broadcast traffic.

---

## 🌟 Key Benefits
- **🔒 Security**: Logical segmentation ensures data protection.  
- **📈 Scalability**: Design supports future growth.  
- **🎯 Efficiency**: Optimized IP utilization through VLSM and VLANs.  
- **🚦 Traffic Management**: VLANs reduce unnecessary broadcast traffic.

---

## 🛠️ Tools Used
- **Cisco Packet Tracer**: To simulate and test the network topology.  
- **Subnet Calculator**: For precise subnet planning and IP allocation.

---

## 🔮 Future Improvements
- Deploy **centralized routing** for seamless inter-VLAN communication.  
- Integrate **DHCP** to automate IP assignments.  
- Implement **QoS** policies to prioritize critical data traffic.

---

## 🌈 Fun Fact!
"An optimized network doesn't just connect devices; it connects **people** and empowers **innovation**."

---

> _"Innovation lies in simplicity, and simplicity is at the heart of this network."_
