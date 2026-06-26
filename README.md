# TechKaram-GmbH-HomeLab

> Author: Karam 

HomeLab project for IT infrastructure simulation

## 📌 Overview
This project simulates a small-to-medium enterprise IT infrastructure designed and implemented in a virtual lab environment using VirtualBox.

---

## 🎯 Objectives

- Design and implement a segmented corporate network
- Configure centralized authentication using Active Directory
- Deploy network services (DHCP, DNS, Firewall)
- Apply security policies using Group Policy Objects (GPO)
- Implement Linux server administration and automation
- Simulate real-world IT operations in a company environment

---

## 🏢 Simulated Company Structure

TechKaram GmbH consists of:

- IT Department
- Development Team
- Accounting Department
- Management
- Sales Department

Each department is isolated using VLAN segmentation.

---

## 🌐 Network Architecture

| Device | IP | Role |
|--------|----|------|
| Ubuntu Server | 192.168.10.10 | Gateway, DHCP, DNS, Firewall |
| Windows Server | 192.168.10.20 | Active Directory, DNS |
| Client1 (Ubuntu) | 192.168.10.50 | IT Workstation |
| Client2 (Ubuntu) | 192.168.20.50 | Development Workstation |
| Client3 (Ubuntu) | 192.168.30.50 | Accounting Workstation |
| Client4 (Ubuntu) | 192.168.40.50 | Management Workstation |
| Client5 (Ubuntu) | 192.168.50.50 | Sales Workstation |
| WinClient1 | 192.168.10.30 | Domain Client (IT) |

Network includes:
- VLAN segmentation
- Inter-VLAN routing
- DHCP service
- DNS (internal domain: karam.local)
- Firewall rules (iptables)

---

## 🧠 Key Features

### Networking
- VLAN-based network segmentation
- Inter-VLAN routing
- Static and dynamic IP management

### Windows Server
- Active Directory Domain Services (AD DS)
- Organizational Units (OU) per department
- Group Policy Objects (GPO):
  - Password policy enforcement
  - USB access restriction
  - Software installation control
  - Control Panel restrictions

### Linux Server
- DHCP server (ISC DHCP)
- DNS server (BIND9)
- Firewall configuration (iptables)
- RAID 1 storage configuration (mdadm)

---

## 🔐 Security Implementation

- Role-based access control
- Department-level network isolation
- Firewall filtering rules
- Password complexity enforcement
- Device usage restrictions via GPO

---

## 💾 Storage

- RAID 1 mirror configuration using mdadm
- Ext4 filesystem
- Designed for redundancy and fault tolerance

---

## ⚙️ Tools & Technologies

- Ubuntu Server 24.04 LTS
- Windows Server 2022
- Windows 11 / Ubuntu Clients
- VirtualBox
- BIND9
- ISC DHCP Server
- Active Directory
- Group Policy Management
- iptables
- mdadm

---

## 📚 Learning Outcomes

This project demonstrates:

- Real-world IT system administration skills
- Enterprise network design
- Server management (Linux + Windows)
- Security policy implementation
- Problem-solving in network environments

---

## ⚠️ Troubleshooting Examples

- BIND9 "bad name" warning — resolved via check-names configuration
- DHCP subnet declaration commented out by default — fixed manually
- Zone file SOA record typo (comma instead of dot)
- VLAN routing debugging

---

## 📁 Repository Structure

- configs/ — Server configuration files (Ubuntu + Windows)
- docs/ — Network diagrams, IP plan, VLAN design, services overview
- screenshots/ — Proof-of-concept evidence
- troubleshooting/ — Real issues encountered and solutions
