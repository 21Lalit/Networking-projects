# DHCP Server Configuration Project

This project demonstrates how to configure a DHCP server to dynamically allocate IP addresses to connected devices in a network. The setup uses a Class C network as an example.

## Required Devices

1. **PCs**
   - **Number of PCs**: 6 (in this example)
   - Maximum devices supported per class:
     - **Class C**: Up to 254 computers
     - **Class B**: 2<sup>16</sup> - 2 computers
     - **Class A**: 2<sup>24</sup> - 2 computers
2. **Central Networking Device**: Switch
3. **DHCP Server**

---

## Steps to Configure the DHCP Server

1. **Network Connections**:
   - Connect all PCs to the switch using copper straight-through cables.
   - Connect the switch to the DHCP server using a copper straight-through cable.

2. **DHCP Server Configuration**:
   - Access the DHCP server and navigate to **Services** > **DHCP**.
   - Create a new pool and name it (e.g., `serverPool`).
   - Provide the following details for the pool:
     - **Starting IP Address**: `192.168.1.2`
     - **Subnet Mask**: `255.255.255.0`
     - **Gateway Address**: `192.168.1.1`
     - (Optional) Add **DNS**, **TFTP**, or **WLC** addresses if required.

3. **Client Configuration**:
   - On each PC, set the IP configuration mode to **DHCP** instead of **Static**.

---

## Outcome

Once the setup is complete, all connected PCs will automatically receive IP addresses from the DHCP server based on the provided configuration.

---

## Notes

- This project focuses solely on DHCP IP configuration.
- Ensure that the network topology and connections are correct to avoid misconfigurations.

Enjoy setting up your dynamic IP allocation system!
