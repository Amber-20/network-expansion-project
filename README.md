# Network Expansion Project – Remote Office Integration

This repository contains a complete remote office network expansion lab that integrates a new branch site into an existing enterprise network using a secure IPsec VPN. It showcases practical skills in network design, infrastructure planning, device configuration, security, and professional IT project documentation. [web:12][web:13]

## Overview

The remote office connects to headquarters (HQ) over the public Internet using a site‑to‑site IPsec VPN, with pfSense serving as the edge firewall and VPN gateway and Cisco devices providing routing and switching. [web:12][web:8]  
The design supports 25 initial users, scales up to 50, and uses VLAN segmentation to separate corporate, voice, guest, and management traffic. [web:12][web:11]

## Objectives

- Capture and document user and business requirements for the new branch office. [web:12]  
- Assess application usage and bandwidth needs for Microsoft 365, VoIP, and video conferencing. [web:9]  
- Design a scalable, secure network topology with VLANs and IPsec VPN between HQ and branch. [web:12][web:13]  
- Configure routers, switches, and pfSense firewall for routing, NAT, and security enforcement. [web:11][web:8]  
- Provide clear documentation for deployment, testing, and future maintenance.

## Topology

High‑level design:

- HQ edge firewall connects to the Internet and terminates the HQ side of the VPN. [web:12]  
- Site‑to‑site IPsec VPN tunnel between HQ and the remote pfSense firewall. [web:13]  
- Remote pfSense connects to a Cisco branch router, which uplinks to a Layer 2 switch providing access to VLANs 10/20/30/40. [web:11]  

# Network Expansion Project – Remote Office Integration

This repository contains a complete remote office network expansion lab that integrates a new branch site into an existing enterprise network using a secure IPsec VPN. It showcases practical skills in network design, infrastructure planning, device configuration, security, and professional IT project documentation. [web:12][web:13]

## Overview

The remote office connects to headquarters (HQ) over the public Internet using a site‑to‑site IPsec VPN, with pfSense serving as the edge firewall and VPN gateway and Cisco devices providing routing and switching. [web:12][web:8]  
The design supports 25 initial users, scales up to 50, and uses VLAN segmentation to separate corporate, voice, guest, and management traffic. [web:12][web:11]

## Objectives

- Capture and document user and business requirements for the new branch office. [web:12]  
- Assess application usage and bandwidth needs for Microsoft 365, VoIP, and video conferencing. [web:9]  
- Design a scalable, secure network topology with VLANs and IPsec VPN between HQ and branch. [web:12][web:13]  
- Configure routers, switches, and pfSense firewall for routing, NAT, and security enforcement. [web:11][web:8]  
- Provide clear documentation for deployment, testing, and future maintenance.

## Topology

High‑level design:

- HQ edge firewall connects to the Internet and terminates the HQ side of the VPN. [web:12]  
- Site‑to‑site IPsec VPN tunnel between HQ and the remote pfSense firewall. [web:13]  
- Remote pfSense connects to a Cisco branch router, which uplinks to a Layer 2 switch providing access to VLANs 10/20/30/40. [web:11]  

# Network Expansion Project – Remote Office Integration

This repository contains a complete remote office network expansion lab that integrates a new branch site into an existing enterprise network using a secure IPsec VPN. It showcases practical skills in network design, infrastructure planning, device configuration, security, and professional IT project documentation. [web:12][web:13]

## Overview

The remote office connects to headquarters (HQ) over the public Internet using a site‑to‑site IPsec VPN, with pfSense serving as the edge firewall and VPN gateway and Cisco devices providing routing and switching. [web:12][web:8]  
The design supports 25 initial users, scales up to 50, and uses VLAN segmentation to separate corporate, voice, guest, and management traffic. [web:12][web:11]

## Objectives

- Capture and document user and business requirements for the new branch office. [web:12]  
- Assess application usage and bandwidth needs for Microsoft 365, VoIP, and video conferencing. [web:9]  
- Design a scalable, secure network topology with VLANs and IPsec VPN between HQ and branch. [web:12][web:13]  
- Configure routers, switches, and pfSense firewall for routing, NAT, and security enforcement. [web:11][web:8]  
- Provide clear documentation for deployment, testing, and future maintenance.

## Topology

High‑level design:

- HQ edge firewall connects to the Internet and terminates the HQ side of the VPN. [web:12]  
- Site‑to‑site IPsec VPN tunnel between HQ and the remote pfSense firewall. [web:13]  
- Remote pfSense connects to a Cisco branch router, which uplinks to a Layer 2 switch providing access to VLANs 10/20/30/40. [web:11]  

[ HQ Firewall ]
|
Internet
|
IPsec VPN Tunnel
  |
[ Remote pfSense ]
|
[ Branch Router ]
|
+-------------------+
| |
[L2 Switch] Guest WiFi APs
|
+-- VLAN 10: Corporate
+-- VLAN 20: Voice
+-- VLAN 30: Guests
+-- VLAN 40: Management

text

For a detailed, diagram‑generator‑ready description, see `diagrams/network-topology-description.txt`.

## Tools and Technologies

- **pfSense** – Branch firewall, NAT gateway, site‑to‑site VPN endpoint, and IDS/IPS platform. [web:8][web:17]  
- **Cisco IOS Router** – Inter‑VLAN routing, DHCP for VLANs, and IPsec integration towards HQ. [web:11][web:12]  
- **Cisco IOS L2 Switch** – VLAN creation, 802.1Q trunking, and access port assignments. [web:11]  
- **Cisco Packet Tracer (or similar)** – Lab emulation and validation environment. [web:11]  

## Key Features

- **VLAN segmentation**
  - VLAN 10 – Corporate data
  - VLAN 20 – Voice
  - VLAN 30 – Guest
  - VLAN 40 – Management  

- **Secure WAN/VPN**
  - Site‑to‑site IPsec tunnel between HQ and branch using AES‑256 and SHA‑256. [web:13]  
  - Clear Phase 1 and Phase 2 configuration template in `configs/vpn-tunnel-config.txt`. [web:13]  

- **Routing and services**
  - Router subinterfaces for each VLAN with inter‑VLAN routing. [web:11]  
  - DHCP scopes for all VLANs with appropriate default gateways and DNS options. [web:11]  

- **Security controls**
  - pfSense firewall rules for WAN, LAN, guest, and VPN segments, including guest isolation. [web:8]  
  - IDS/IPS (Suricata/Snort) guidelines for WAN/LAN monitoring and blocking. [web:8]  

- **Capacity planning**
  - Bandwidth analysis for Microsoft 365, VoIP, and video conferencing with a 100 Mbps symmetrical link recommendation. [web:9][web:16]  

## Repository Structure

network-expansion-project/
│
├── README.md # Project overview and usage
│
├── configs/
│ ├── router-config.txt # Cisco branch router config (VLANs, DHCP, IPsec, NAT)
│ ├── switch-config.txt # Cisco L2 switch config (VLANs, trunk, access ports)
│ ├── pfsense-firewall-rules.txt# pfSense rules, NAT, IDS/IPS guidelines
│ ├── vpn-tunnel-config.txt # IPsec Phase 1/2 parameters and routing integration
│ └── vlans.txt # VLAN IDs, subnets, and purposes
│
├── diagrams/
│ └── network-topology-description.txt # Text description for diagram tools

│
└── docs/
├── requirements.md # User, business, and security requirements
├── bandwidth-analysis.md # Application and bandwidth calculations
├── deployment-guide.md # Deployment steps with pfSense & Packet Tracer
├── security-policy.md # Branch office security policy
└── testing-and-validation.md # Test and validation plan


## How to Clone and Use

git clone https://github.com/Amber-20/network-expansion-project.git
cd network-expansion-project


- Review `docs/requirements.md` and `docs/bandwidth-analysis.md` to understand the scenario.  
- Load router and switch configs from `configs/` into Cisco Packet Tracer or lab devices, adjusting interfaces as needed. [web:11]  
- Configure pfSense following `docs/deployment-guide.md` and `configs/pfsense-firewall-rules.txt`. [web:8]  
- Run through `docs/testing-and-validation.md` to verify connectivity, segmentation, VPN, and QoS.
