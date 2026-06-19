# TechKaram-GmbH-HomeLab
HomeLab project for IT infrastructure simulation

## 📌 Overview
This project simulates a small-to-medium enterprise IT infrastructure designed and implemented in a virtual lab environment using VirtualBox.

The goal is to demonstrate practical skills relevant to the German apprenticeship (Ausbildung) for:

> Fachinformatiker Systemintegration

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

- Gateway/Router: Ubuntu Server
- Domain Controller: Windows Server 2022
- Clients: Ubuntu 24.04 / Windows 11
- Virtualization: Oracle VirtualBox

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

- DNS resolution issues and fixes
- DHCP misconfiguration handling
- VLAN routing debugging
- AD join failures and solutions

---

