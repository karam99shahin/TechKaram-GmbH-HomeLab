# Network Overview — TechKaram GmbH

## Project Overview

Full simulation of a company IT infrastructure built in VirtualBox.
Includes network segmentation (VLANs), server administration (Linux & Windows),
Active Directory, Group Policy, firewall rules, and RAID storage.

## Network Diagram
[Internet]
   |
[Ubuntu Server - 192.168.10.10]
Gateway/Router/DHCP/DNS/Firewall
   |
   |--- VLAN10 - IT - 192.168.10.0/24
   |       |-- Windows Server - 192.168.10.20
   |       |-- Client1 - 192.168.10.50
   |       |-- WinClient1 - 192.168.10.30
   |
   |--- VLAN20 - Development - 192.168.20.0/24
   |       |-- Client2 - 192.168.20.50
   |
   |--- VLAN30 - Accounting - 192.168.30.0/24
   |       |-- Client3 - 192.168.30.50
   |
   |--- VLAN40 - Management - 192.168.40.0/24
   |       |-- Client4 - 192.168.40.50
   |
   |--- VLAN50 - Sales - 192.168.50.0/24
           |-- Client5 - 192.168.50.50
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
