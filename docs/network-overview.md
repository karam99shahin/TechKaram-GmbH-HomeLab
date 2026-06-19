# Network Overview — TechKaram GmbH

## Project Overview

Full simulation of a company IT infrastructure built in VirtualBox.
Includes network segmentation (VLANs), server administration (Linux & Windows),
Active Directory, Group Policy, firewall rules, and RAID storage.

## Network Diagram
Internet[Internet]
    Ubuntu["Ubuntu Server<br>192.168.10.10<br>Gateway / Router / DHCP / DNS / Firewall"]
    
    Internet --> Ubuntu
    
    Ubuntu --> VLAN10["VLAN10 - IT<br>192.168.10.0/24"]
    Ubuntu --> VLAN20["VLAN20 - Development<br>192.168.20.0/24"]
    Ubuntu --> VLAN30["VLAN30 - Accounting<br>192.168.30.0/24"]
    Ubuntu --> VLAN40["VLAN40 - Management<br>192.168.40.0/24"]
    Ubuntu --> VLAN50["VLAN50 - Sales<br>192.168.50.0/24"]
    
    VLAN10 --> WinServer["Windows Server<br>192.168.10.20"]
    VLAN10 --> Client1["Client1<br>192.168.10.50"]
    VLAN10 --> WinClient1["WinClient1<br>192.168.10.30"]
    
    VLAN20 --> Client2["Client2<br>192.168.20.50"]
    VLAN30 --> Client3["Client3<br>192.168.30.50"]
    VLAN40 --> Client4["Client4<br>192.168.40.50"]
    VLAN50 --> Client5["Client5<br>192.168.50.50"]
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
