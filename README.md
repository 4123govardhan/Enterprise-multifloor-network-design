# Enterprise Multi-Floor Network Design and Implementation

## Project Overview

This project demonstrates the design and implementation of an enterprise network using Cisco Packet Tracer. The network connects three floors through three routers and provides separate VLANs for different departments.

The project includes inter-VLAN routing, OSPF, DHCP, trunk links, SSH management, wireless connectivity, and switch port security.

## Network Design

- Three routers connected through serial links
- Three floor switches
- Separate VLANs for eight departments
- Router-on-a-stick inter-VLAN routing
- OSPF dynamic routing
- DHCP address allocation
- 802.1Q trunking
- SSH management configuration
- Sticky MAC port security
- Wireless access points and end devices

## VLAN and IP Address Plan

| Floor | Department | VLAN | Network | Gateway |
|---|---|---:|---|---|
| 1 | Reception | 80 | 192.168.8.0/24 | 192.168.8.100 |
| 1 | Store | 70 | 192.168.7.0/24 | 192.168.7.100 |
| 1 | Logistics | 60 | 192.168.6.0/24 | 192.168.6.100 |
| 2 | Finance | 50 | 192.168.5.0/24 | 192.168.5.100 |
| 2 | HR | 40 | 192.168.4.0/24 | 192.168.4.100 |
| 2 | Sales | 30 | 192.168.3.0/24 | 192.168.3.100 |
| 3 | Admin | 20 | 192.168.2.0/24 | 192.168.2.100 |
| 3 | IT | 10 | 192.168.1.0/24 | 192.168.1.100 |

## Routing Design

OSPF Area 0 is configured between the three routers to exchange routes between the floor networks.

The routers use serial point-to-point links with /30 addressing:

- 10.10.10.0/30
- 10.10.10.4/30
- 10.10.10.8/30

Router subinterfaces provide inter-VLAN routing for the departments connected to each floor switch.

## Verification Results

The following tests were performed in Cisco Packet Tracer:

- **OSPF:** All three routers showed two neighbors in the FULL state.
- **VLANs and trunking:** VLAN assignments and 802.1Q trunk links were verified on all three floor switches.
- **DHCP:** Address leases were observed in the DHCP pools across all three routers.
- **Port security:** The third-floor switch showed port security enabled on Fa0/2, one sticky MAC address learned, and zero violations.
- **Connectivity:** The IT Test-PC successfully pinged its default gateway (192.168.1.100) and an Admin-subnet device (192.168.2.1), with 0% packet loss in both tests.
- **SSH:** The R1 CLI reported SSH enabled. A successful remote SSH login has not yet been documented.

## Repository Structure

- `Enterprise-MultiFloor-Network.pkt` — Cisco Packet Tracer project file
- `configurations/` — Router and switch configuration files
- `topology/` — Network topology diagram and description
- `testing/` — Verification documentation and screenshots

## Technologies and Concepts

Cisco Packet Tracer, VLANs, IEEE 802.1Q trunking, router-on-a-stick, OSPF, DHCP, SSH, sticky MAC port security, IPv4 addressing, and network troubleshooting.

## How to Use

1. Download `Enterprise-MultiFloor-Network.pkt`.
2. Open the file using Cisco Packet Tracer.
3. Review the topology and device configurations.
4. Use the configuration files and testing documentation to explore the implementation.

## Project Purpose

This project was created to practice enterprise network design, configuration, verification, and troubleshooting in a multi-floor environment.
