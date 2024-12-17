# 🌐 VLAN Configuration

This guide details the process of configuring VLANs for different departments on a network switch. The departments and their corresponding VLANs are as follows:

1. **HR Department** - VLAN 2
2. **Sales Department** - VLAN 3
3. **Production Department** - VLAN 4

---

## 📋 Requirements

- 🖥️ **Number of PCs**: Determine the total PCs in the LAN to decide the network class.
- 🛠️ **Static IP Range**: If DHCP is not implemented, assign a static IP range for each VLAN.
- 🔗 **Switch**: Use one or more switches as required.
- 📶 **Cables**: Use copper straight-through cables to connect Fast Ethernet ports.

---

## 🔧 Steps to Configure the VLANs

### 1. Connect All PCs
- Link all PCs to **Switch0** using straight-through cables.

### 2. Assign Static IP Addresses
- Configure each PC:
  - Navigate to **Desktop > IP Configuration**.
  - Set the **IP Address** and **Subnet Mask** fields.

### 3. Configure Switch0

#### a. Create VLANs

1. **HR Department (VLAN 2):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# vlan 2
    switch0(config-vlan)# name HR_Department
    ```

2. **Sales Department (VLAN 3):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# vlan 3
    switch0(config-vlan)# name Sales_Department
    ```

3. **Production Department (VLAN 4):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# vlan 4
    switch0(config-vlan)# name Production_Department
    ```

#### b. Assign Ports to VLANs

1. **HR Department (Ports: f0/1, f0/2, f0/3, f0/13, f0/14):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# int f0/1
    switch0(config-if)# switchport access vlan 2
    switch0(config)# exit

    switch0(config)# int f0/2
    switch0(config-if)# switchport access vlan 2
    switch0(config)# exit

    switch0(config)# int f0/3
    switch0(config-if)# switchport access vlan 2
    switch0(config)# exit

    switch0(config)# int f0/13
    switch0(config-if)# switchport access vlan 2
    switch0(config)# exit

    switch0(config)# int f0/14
    switch0(config-if)# switchport access vlan 2
    switch0(config)# exit
    ```

2. **Sales Department (Ports: f0/4, f0/5, f0/6, f0/11, f0/12):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# int f0/4
    switch0(config-if)# switchport access vlan 3
    switch0(config)# exit

    switch0(config)# int f0/5
    switch0(config-if)# switchport access vlan 3
    switch0(config)# exit

    switch0(config)# int f0/6
    switch0(config-if)# switchport access vlan 3
    switch0(config)# exit

    switch0(config)# int f0/11
    switch0(config-if)# switchport access vlan 3
    switch0(config)# exit

    switch0(config)# int f0/12
    switch0(config-if)# switchport access vlan 3
    switch0(config)# exit
    ```

3. **Production Department (Ports: f0/7, f0/8, f0/9, f0/10):**
    ```
    switch0>en
    switch0#config t
    switch0(config)# int f0/7
    switch0(config-if)# switchport access vlan 4
    switch0(config)# exit

    switch0(config)# int f0/8
    switch0(config-if)# switchport access vlan 4
    switch0(config)# exit

    switch0(config)# int f0/9
    switch0(config-if)# switchport access vlan 4
    switch0(config)# exit

    switch0(config)# int f0/10
    switch0(config-if)# switchport access vlan 4
    switch0(config)# exit
    ```

---

## ✅ Verification

1. Use the following command to check VLAN configurations:
    ```
    switch0>en
    switch0#show vlan
    ```
2. Ensure the ports and VLAN assignments match your requirements.

---

🎉 **Configuration Complete!** Departments have been successfully configured with VLANs.

> "Good configuration is the foundation of a secure and efficient network."

