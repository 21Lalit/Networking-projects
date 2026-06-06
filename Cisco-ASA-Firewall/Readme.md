# Cisco ASA Firewall Configuration in Cisco Packet Tracer

"Firewalls do not just block traffic; they enforce trust boundaries."

---

## Overview

This project demonstrates the configuration of a Cisco ASA firewall in Cisco Packet Tracer. The lab includes an inside network, an outside network, an internal web server, static NAT, and access-control rules to allow only specific traffic from an outside client to an internal server.

The main objective of this project is to understand how a firewall separates trusted and untrusted networks, publishes an internal server using NAT, and filters traffic using ACL rules.

---

## Network Topology

![Cisco ASA Firewall Topology](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/Topology.png)

### Components

* Cisco ASA 5506-X Firewall
* Inside Switch
* Outside Switch
* Router0 representing the outside/ISP side
* Server0 as the internal web server
* PC0 and PC1 as inside clients
* PC2 as the outside testing client

---

## IP Addressing Scheme

| Device  | Interface          | IP Address        | Purpose                    |
| ------- | ------------------ | ----------------- | -------------------------- |
| ASA     | GigabitEthernet1/1 | 192.168.10.1/24   | Inside gateway             |
| ASA     | GigabitEthernet1/2 | 203.0.113.2/24    | Outside firewall interface |
| Server0 | Fa0                | 192.168.10.100/24 | Internal web server        |
| PC0     | Fa0                | 192.168.10.10/24  | Inside client              |
| PC1     | Fa0                | 192.168.10.20/24  | Inside client              |
| PC2     | Fa0                | 203.0.113.10/24   | Outside client             |
| Router0 | Gi0/0/0            | 203.0.113.1/24    | Outside router             |

---

## ASA Interface Configuration

The ASA firewall has two main zones:

* `inside` with security level `100`
* `outside` with security level `0`

![ASA Interface Configuration](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/ASA-Interfaces.png)

```cisco
interface GigabitEthernet1/1
 nameif inside
 security-level 100
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet1/2
 nameif outside
 security-level 0
 ip address 203.0.113.2 255.255.255.0
```

The `inside` interface acts as the gateway for the internal network, while the `outside` interface connects the ASA firewall to the external network.

---

## NAT Configuration

Static NAT is configured to publish the internal web server to the outside network.

Internal web server:

```text
192.168.10.100
```

Mapped public IP:

```text
203.0.113.100
```

NAT configuration:

```cisco
object network WEB-SERVER
 host 192.168.10.100
 nat (inside,outside) static 203.0.113.100
```

![NAT Configuration](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/NAT-Configuration.png)

This NAT rule maps the internal server IP `192.168.10.100` to the outside-accessible IP `203.0.113.100`.

---

## ACL Configuration

The outside ACL allows only HTTP traffic from PC2 to the published web server IP.

Allowed traffic:

```text
Source: 203.0.113.10
Destination: 203.0.113.100
Service: HTTP / TCP 80
```

Denied traffic:

```text
All other IP traffic
```

Final ACL:

```cisco
access-list OUTSIDE-INSIDE extended permit tcp host 203.0.113.10 host 203.0.113.100 eq www
access-list OUTSIDE-INSIDE extended deny ip any any
access-group OUTSIDE-INSIDE in interface outside
```

![ACL Configuration](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/ACL-Configuration.png)

The ACL is applied inbound on the ASA outside interface. This means traffic entering the firewall from the outside network is checked against these rules.

---

## Testing and Verification

### Test 1: Allowed HTTP Traffic

From PC2 browser:

```text
http://203.0.113.100
```

Result: The internal web server page opened successfully.

![HTTP Allowed Test](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/HTTP-Allowed.png)

This confirms that HTTP traffic from the outside client was allowed through the ASA firewall and translated to the internal web server using static NAT.

---

### Test 2: Denied Traffic

Traffic other than HTTP was denied by the ASA ACL.

Examples of denied traffic:

```text
https://203.0.113.100
ping 203.0.113.100
SSH to 203.0.113.100
```

![Denied Traffic Test](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/Traffic-Denied.png)

The deny rule hit count increased, confirming that unwanted traffic was blocked by the firewall.

---

## Verification Commands

Useful commands used during the lab:

```cisco
show interface ip brief
show nat
show access-list
show arp
show running-config
write memory
```
---

## ARP Verification

The ARP table was checked to verify Layer 2 connectivity between the ASA firewall and the outside network devices.

![ARP Table Verification](https://github.com/21Lalit/Networking-projects/blob/main/Cisco-ASA-Firewall/ARP-Table.png)
Command used:

```cisco
show arp

The `show access-list` output confirmed that HTTP traffic was allowed and other traffic was denied using hit counts.

Example final ACL verification:

```cisco
access-list OUTSIDE-INSIDE extended permit tcp host 203.0.113.10 host 203.0.113.100 eq www
access-list OUTSIDE-INSIDE extended deny ip any any
```

---

## Project Files

| File                    | Description                                   |
| ----------------------- | --------------------------------------------- |
| `ASA-Firewall.pkt`      | Cisco Packet Tracer project file              |
| `Topology.png`          | Final network topology                        |
| `ASA-Interfaces.png`    | ASA inside and outside interface verification |
| `NAT-Configuration.png` | Static NAT verification                       |
| `ACL-Configuration.png` | ACL rules and hit count verification          |
| `HTTP-Allowed.png`      | Successful HTTP access from outside PC        |
| `Traffic-Denied.png`    | Denied traffic verification                   |
| `Readme.md`             | Project documentation                         |

---

## Key Learnings

* Configured Cisco ASA inside and outside interfaces.
* Understood ASA security levels.
* Implemented static NAT for internal server publishing.
* Created ACL rules to allow only required traffic.
* Verified allowed and denied traffic using ACL hit counts.
* Practiced firewall troubleshooting in Cisco Packet Tracer.
* Learned how NAT and ACLs work together in ASA firewall traffic flow.

---

## Future Scope

* Add a DMZ network for public-facing servers.
* Configure separate rules for HTTPS traffic.
* Add logging for denied traffic.
* Add multiple outside clients and test source-based filtering.
* Implement VPN or secure remote management access.
* Add more internal services and apply least-privilege firewall rules.

---

## Final Result

The lab successfully demonstrates a working Cisco ASA firewall setup where:

* The inside network is protected.
* The internal web server is published using static NAT.
* The outside PC can access only the HTTP service.
* All other traffic is denied by firewall ACL.
* ASA hit counts verify both allowed and denied traffic.

---

> "A firewall is effective only when its rules are clear, tested, and minimal."

Secure the boundary. Allow only what is required.
