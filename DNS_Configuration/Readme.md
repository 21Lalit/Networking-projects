Required Devices

1. Required number of PCs -> 2 (In this case, minimum number of PC's taken)
	- You can use maximum of 254 Computers for a class C Network, Class B (2^16-2 computers), Class C (2^24-2 Computers). 
2. Networking Devices - Router and Switches are used here..
3. DNS and HTTP Server.

Steps to Configure DHCP Server

1. Connect PC0 with switch0 with Copper-Straight through cable.

PC0 Configuration
	- IP Address - 192.168.1.4
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.1.1
	- DNS Server - 192.168.1.2

2. Connect switch with DNS and HTTP Server using Copper-Straight through cable.
3. Now Click on DNS server and navigate to Services -> DNS.
4. In this menu, write Domain Name, Domain IP Address and Address Type (website.com -- 192.168.1.3 - In this case)
As Shown in DNS-Configuration.png
5. Now Save, And if you want to add more addresses then changes values and add further.
6. DNS Configuration.
	
	DNS Service Configuration
	- HTTP Server Ip Address - 192.168.1.3 (Address of HTTP Server Where Website.com is Hosted)
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.1.1
	
	DNS Server Configuration
	- IP Address - 192.168.1.2
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.1.1
	- DNS Server - 192.168.1.2
7. HTTP Configuration.
	
	HTTP Service Configuration
	- Click on HTTP Server > Services > HTTP
	- Turn on the required protocol HTTP or HTTPS to host the website
	- You can add files down there, otherwise a few demo files are present.

	HTTP Server Configuration
	- IP Address - 192.168.1.3
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.1.1
	- DNS Server - 192.168.1.2

7. Router Configuration

Configure the port Gig0/0/0 for internal network (192.168.1.1-255)

Router>enable
	Router#
	Router#configure terminal
	Enter configuration commands, one per line.  End with CNTL/Z.
	Router(config)#interface GigabitEthernet0/0/0
	Router(config-if)#ip address 192.168.1.1 255.255.255.0
	Router(config-if)#

Configure the port Gig0/0/0 for internal network (192.168.2.1-255)

	Router>enable
	Router#
	Router#configure terminal
	Enter configuration commands, one per line.  End with CNTL/Z.
	Router(config)#interface GigabitEthernet0/0/0
	Router(config-if)#ip address 192.168.2.1 255.255.255.0
	Router(config-if)#

Connect PC1 with switch1 with Copper-Straight through cable.
	- IP Address - 192.168.2.2
	- Subnet Mask - 255.255.255.0
	- Gateway Address - 192.168.2.1
	- DNS Server - 192.168.1.2

Here you go! PCs are configured according to provided ip address.
You can Check the domain website.com on PC1.
Click on PC1 > Desktop > Web Browser > website.com
