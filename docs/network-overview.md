# Network Overview — TechKaram GmbH

## Project Overview

Full simulation of a company IT infrastructure built in VirtualBox.
Includes network segmentation (VLANs), server administration (Linux & Windows),
Active Directory, Group Policy, firewall rules, and RAID storage.

## Network Diagram

[Internet]
    |
    v
[Ubuntu Server - 192.168.10.10]
(Gateway / Router / DHCP / DNS / Firewall)
    |
    +------------------+------------------+------------------+------------------+
    |                  |                  |                  |                  |
    v                  v                  v                  v                  v
[VLAN10 - IT]    [VLAN20 - Dev]    [VLAN30 - Acc]    [VLAN40 - Mgmt]    [VLAN50 - Sales]
192.168.10.0/24  192.168.20.0/24  192.168.30.0/24  192.168.40.0/24   192.168.50.0/24
    |                  |                  |                  |                  |
    +--+--+            |                  |                  |                  |
    |  |  |            |                  |                  |                  |
    v  v  v            v                  v                  v                  v
[WS] [C1] [WC1]      [C2]               [C3]               [C4]               [C5]
10.20 10.50 10.30    20.50              30.50              40.50              50.50


## Technologies Used

- Virtualization: Oracle VirtualBox
- OS (Server): Ubuntu Server 24.04 LTS
- OS (Domain): Windows Server 2022
- OS (Clients): Ubuntu 24.04, Windows 11 Pro
- Networking: netplan, iptables, BIND9, isc-dhcp-server
- Storage: mdadm (RAID 1)
- Directory Services: Active Directory Domain Services (AD DS)
- Remote Access: OpenSSH, VS Code Remote-SSH
``
