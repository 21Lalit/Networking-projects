# Network Device Port Security Configuration

## 📌 Overview
This project demonstrates how to configure and manage **port security** on a network switch. The goal is to secure the switch ports by controlling the MAC addresses allowed on each port and defining actions for security violations.

## 🛠️ Configurations
The following configurations have been implemented:

1. **Maximum Secure Addresses**: Each port is configured with a limit on the number of MAC addresses allowed.
2. **Violation Actions**:
   - **Shutdown**: The port is disabled upon a security violation.
   - **Protect**: The port drops packets from unauthorized MAC addresses but does not log violations.
   - **Restrict**: The port drops packets and logs security violations.
3. **MAC Address Table**: Displays static and dynamic MAC addresses assigned to ports.
##Topology
Here’s the network topology used in this project:

![Network Topology](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/External-non-user-01.png)  

### Legitimate and External Users  
- **Legitimate Users:**  
  ![Legitimate User 1](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Legitimate-User-01.png)  
  ![Legitimate User 2](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Legitimate-User-02.png)  

- **External Unauthorized User:**  
  ![External User](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/External-non-user-01.png)  

## Port Security Configuration Output  
### MAC Address Table  
![MAC Address Table](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Mac-Address-Table-01.png)  

### Port Security Verification  
- **Configuration 1:**  
  ![Port Security Config 1](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Mac-and-Port-Security-Running-Conf-01.png)  

- **Configuration 2:**  
  ![Port Security Config 2](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Mac-and-Port-Security-Running-Conf-02.png)  

- **Configuration 3:**  
  ![Port Security Config 3](https://github.com/21Lalit/Networking-projects/blob/main/Port-Security-Configuration/Mac-and-Port-Security-Running-Conf-03.png)  

## 🔍 Port Security Status
The table below summarizes the port security configurations applied:

| Port  | Max Secure Addr | Current Addr | Security Violation | Security Action |
|-------|----------------|--------------|---------------------|-----------------|
| Fa0/1 | 2              | 1            | 1                   | Shutdown        |
| Fa0/2 | 2              | 0            | 1                   | Protect         |
| Fa0/3 | 1              | 0            | 0                   | Restrict        |

## 📄 MAC Address Table
The following MAC addresses have been recorded on different ports:

| VLAN | MAC Address       | Type     | Port  |
|------|------------------|----------|-------|
| 1    | 0001.4397.2434   | STATIC   | Fa0/3 |
| 1    | 000c.cf65.1321   | DYNAMIC  | Fa0/4 |
| 1    | 0030.a360.d096   | STATIC   | Fa0/1 |

## 📜 Commands Used
### Show Port Security
```shell
Switch# show port-security
```
### Show MAC Address Table
```shell
Switch# show mac-address-table
```

## 📌 How to Apply Port Security
1. **Enable port security on an interface:**
   ```shell
   Switch(config-if)# switchport port-security
   ```
2. **Set the maximum number of MAC addresses allowed:**
   ```shell
   Switch(config-if)# switchport port-security maximum 2
   ```
3. **Specify a violation action:**
   ```shell
   Switch(config-if)# switchport port-security violation shutdown
   ```
4. **Manually assign a MAC address (Optional):**
   ```shell
   Switch(config-if)# switchport port-security mac-address 0001.4397.2434
   ```
5. **Save the configuration:**
   ```shell
   Switch# write memory
   ```

> "Hackers don’t break in, they log in. Secure your credentials."

