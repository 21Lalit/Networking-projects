Required Devices

1. Required number of PCs -> 6 (In this case)
	- You can use maximum of 254 Computers for a class C Network, Class B (2^16-2 computers), Class C (2^24-2 Computers). 
2. Central Networking Device -> Switch (In this Case)
3. DHCP Server

Steps to Configure DHCP Server

1. Connect all PC's with switch with Copper-Straight through cable.
2. Connect switch with server using Copper-Straight through cable.
3. Now Click on DHCP server and navigate to Services -> DHCP.
4. In this menu, write a pool name (serverPool - In this case)
5. Now Provide basic details about the pool.
6. This project only focuses on the DHCP IP Configuration.
	- Starting Ip Address - 192.168.1.2
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.1.1
	- You can also give DNS, TFTP and WLC Address here.
7. Now Select IP Configuration on each PC by DHCP instead of Static.

Here you go! PCs are configured according to provided ip address.
