# VLAN Configuration
Here vlans are configured by creating different vlans in switch using the following names:
1. HR Department - VLAN 2
2. Sales Department - VLAN 3
3. Production Department - VLAN 4

## Requirements
- Number of PC's required in the LANs deciding Class of Network.
- If DHCP is not implemented, Range of Static IP address is required.
- A switch or more as per requirement is needed.
- Copper-Straight Through Cable is required to connected Fast-Ethernet ports.

## Steps to Configure Different Departments
According to this Network......
1. Connect all PC's to the Switch0
2. Providing Static IP addresses to Computers. (Desktop > IP Configuration > IP and Subnet Mask fields)
3. Now Configure Switch0

### Steps to Configure Switch0
1. Create 3 new Vlans 
    a. Vlan 2 - HR Department
        switch0>en 
        switch0#config t 
        switch0(config)#
        switch0(config)# vlan 2
        switch0(config-vlan)# name HR_Department
    b. Vlan 3 - Sales Department
        switch0>en 
        switch0#config t 
        switch0(config)#
        switch0(config)# vlan 3
        switch0(config-vlan)# name Sales_Department
    c. Vlan 4 - Production Department
        switch0>en 
        switch0#config t 
        switch0(config)#
        switch0(config)# vlan 4
        switch0(config-vlan)# name Production_Department
2. In each Department Check the ports to which PCs Connected.
3. In HR Department Ports (f0/1, f0/2, f0/3, f0/13, f0/14) are Connected.
    switch0>en
    switch0#config t 
    switch0(config)#int f0/1
    switch0(config)#switchport access vlan 2
    switch0(config)#exit

    switch0(config)#int f0/2
    switch0(config)#switchport access vlan 2
    switch0(config)#exit

    switch0(config)#int f0/3
    switch0(config)#switchport access vlan 2
    switch0(config)#exit

    switch0(config)#int f0/13
    switch0(config)#switchport access vlan 2
    switch0(config)#exit

    switch0(config)#int f0/14
    switch0(config)#switchport access vlan 2
    switch0(config)#exit

4. In Sales Department Ports (f0/4, f0/5, f0/6, f0/11, f0/12) are Connected.
    switch0>en
    switch0#config t 
    switch0(config)#int f0/4
    switch0(config)#switchport access vlan 3
    switch0(config)#exit

    switch0(config)#int f0/5
    switch0(config)#switchport access vlan 3
    switch0(config)#exit

    switch0(config)#int f0/6
    switch0(config)#switchport access vlan 3
    switch0(config)#exit

    switch0(config)#int f0/11
    switch0(config)#switchport access vlan 3
    switch0(config)#exit

    switch0(config)#int f0/12
    switch0(config)#switchport access vlan 3
    switch0(config)#exit

5. In Production Department Ports (f0/7, f0/8, f0/9, f0/10) are Connected.
    switch0>en
    switch0#config t 
    switch0(config)#int f0/7
    switch0(config)#switchport access vlan 4
    switch0(config)#exit

    switch0(config)#int f0/8
    switch0(config)#switchport access vlan 4
    switch0(config)#exit

    switch0(config)#int f0/9
    switch0(config)#switchport access vlan 4
    switch0(config)#exit

    switch0(config)#int f0/10
    switch0(config)#switchport access vlan 4
    switch0(config)#exit

6. Here you go ! All Set, Departments are Configured Manually.
7. To Check all Department
    switch0>en
    switch0#show vlan
    Refer to Image Vlan-Departments-Networking.png 
