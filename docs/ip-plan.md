# IP Plan — TechKaram GmbH

| Device | Interface | IP Address | Role |
|--------|-----------|------------|------|
| Ubuntu Server | enp0s3 | 192.168.10.10 | Gateway, DHCP, DNS, Firewall |
| Ubuntu Server | enp0s8 | 10.0.3.15 | NAT - Internet |
| Ubuntu Server | enp0s9 | 192.168.56.101 | Host-Only - Management |
| Ubuntu Server | enp0s10 | 192.168.20.1 | VLAN20 Gateway |
| Ubuntu Server | enp0s3.40 | 192.168.40.1 | VLAN40 Gateway |
| Ubuntu Server | enp0s10.30 | 192.168.30.1 | VLAN30 Gateway |
| Ubuntu Server | enp0s10.50 | 192.168.50.1 | VLAN50 Gateway |
| Windows Server | Ethernet | 192.168.10.20 | Active Directory, DNS |
| Client1 (Ubuntu) | enp0s3 | 192.168.10.50 | IT Workstation |
| Client2 (Ubuntu) | enp0s3 | 192.168.20.50 | Dev Workstation |
| Client3 (Ubuntu) | enp0s3 | 192.168.30.50 | Accounting Workstation |
| Client4 (Ubuntu) | enp0s3 | 192.168.40.50 | Management Workstation |
| Client5 (Ubuntu) | enp0s3 | 192.168.50.50 | Sales Workstation |
| WinClient1 | Ethernet | 192.168.10.30 | Domain Client (IT) |
