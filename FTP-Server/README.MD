Required Devices

1. Required number of PCs -> 4 (In this case, minimum number of PC's taken)
	- You can use maximum of 254 Computers for a class C Network, Class B (2^16-2 computers), Class C (2^24-2 Computers). 
2. Networking Devices - Switch is used here..
3. FTP Server.

Steps to Configure DHCP Server

1. Connect PC0 with switch0 with Copper-Straight through cable.

PC0 Configuration
	- IP Address - 192.168.1.3
	- Subnet Mask - 255.255.255.0

PC1 Configuration
	- IP Address - 192.168.1.5
	- Subnet Mask - 255.255.255.0

PC2 Configuration
	- IP Address - 192.168.1.4
	- Subnet Mask - 255.255.255.0

PC3 Configuration
	- IP Address - 192.168.1.6
	- Subnet Mask - 255.255.255.0

2. Connect switch with FTP Server using Copper-Straight through cable.
3. Now Click on FTP server and navigate to Services -> FTP.
4. Turn On the service.
5. Now Save, And if you want to add users or change permissions to files present.
	- Then, Create Username & Password and set permissions.
	- You can add files down there, otherwise a few demo files are present.

Here you go! PCs are configured according to provided ip address.

Now, Click on any PC Client to connect to the FTP Service.

PC3 > Desktop > Command Prompt >>
C:\> FTP 192.168.1.2 (ftp server ip address)
Trying to connect...192.168.1.2
Connected to 192.168.1.2
220- Welcome to PT Ftp server
Username: cisco (Configured username)
331- Username ok, need password
Password: 
230- Logged in
(passive mode On)
ftp>quit
C:\> 

Use Question mark (?), for Help in Command Prompt for FTP Server here......