# Departments of a Company Network

## Project Overview
This project demonstrates a simulated network infrastructure for a company with three main departments: **Sales**, **Executive**, and **Production**. The network is designed to optimize communication, enhance security, and efficiently allocate private IP addresses using various subnetting techniques and VLAN technology.

---

## Departments and Network Design

### 1. Sales Department
The Sales department utilizes two different classes of private IP addresses to create sub-networks:

- **Class B Network**: Used for the primary network within the Sales department with the IP range **172.16.2.1 - 172.16.2.2**.
- **Class C Network**: Sub-networks are created to manage smaller teams within the Sales department with the IP range **192.168.3.1 - 192.168.3.3**.

By employing different IP classes, the Sales department efficiently manages resources based on team size and connectivity needs.

---

### 2. Executive Department
The Executive department uses **Class A Private IP Addressing** with subnetting:

- The network begins with the **IP Address 10.0.0.1**.
- Three sub-departments are created using a **/29 netmask** (255.255.255.248), which provides 6 usable host addresses per subnet.
- Subnetting is done while taking care of minimum wastage of IP addresses.

| Sub-department | Subnet Range      | Usable IP Range       |
|----------------|-------------------|-----------------------|
| Sub-department 1 | 10.0.0.0/29       | 10.0.0.1 - 10.0.0.6   |
| Sub-department 2 | 10.0.0.8/29       | 10.0.0.9 - 10.0.0.14  |
| Sub-department 3 | 10.0.0.16/29      | 10.0.0.17 - 10.0.0.22 |

This approach ensures optimal usage of the Class A address space for the smaller sub-departments.

---

### 3. Production Department
The Production department employs **VLAN (Virtual Local Area Network) Technology**:

- The department is divided into two sub-departments:
  - **Sell Sub-department**: Manages the sale of finished goods.
  - **Raw Sub-department**: Handles raw materials and their management.
- The VLANs use the **Class C private IP range 192.168.20.0/24**.

By using VLANs, communication is logically segmented even though the physical network may be shared. This enhances security and reduces broadcast traffic.

---

## Subdivision Techniques

### Method 1: Different IP Classes
- **Explanation**: Assigning different classes of private IP addresses (Class B and Class C) allows for a hierarchical approach to addressing. This is useful in environments with varying device density or connectivity requirements.
- **Use Case**: Applied in the Sales department to differentiate primary and sub-networks.

### Method 2: Subnetting with Variable Length Subnet Mask (VLSM)
- **Explanation**: By applying a **/29 subnet mask** on a Class A network, smaller sub-networks are created with precisely the required number of host addresses.
- **Use Case**: Used in the Executive department to allocate IPs efficiently for three sub-departments.

### Method 3: VLAN Technology
- **Explanation**: VLANs logically divide a single physical network into multiple virtual networks. Devices in one VLAN cannot communicate directly with devices in another VLAN unless explicitly routed.
- **Use Case**: Utilized in the Production department to separate Sell and Raw sub-departments.

---

## Benefits of the Design
- **Efficient Resource Utilization**: Optimal use of private IP address space.
- **Enhanced Security**: Logical segmentation using VLANs prevents unauthorized access between sub-departments.
- **Scalability**: Supports future growth with minimal reconfiguration.
- **Reduced Broadcast Traffic**: VLANs minimize unnecessary traffic within the network.

---

## Tools Used
- **Cisco Packet Tracer**: For network simulation and topology design.
- **Subnet Calculator**: To calculate subnets and ensure efficient IP usage.

---

## Future Improvements
- Implement a centralized routing table for better inter-VLAN communication.
- Integrate DHCP for automatic IP assignment.
- Explore QoS (Quality of Service) policies for prioritizing critical traffic.

---

## Conclusion
This project illustrates a practical application of subnetting and VLAN technologies to create a structured and efficient network design for a company's departments. The design ensures security, scalability, and resource optimization.
