# Services Overview — TechKaram GmbH

| Service | Server | Port | Description |
|---------|--------|------|--------------|
| DHCP | Ubuntu Server | 67/UDP | Automatic IP assignment for all VLANs |
| DNS (Internal) | Ubuntu Server | 53 | Resolves karam.local zone, forwards external queries to 8.8.8.8 |
| DNS (AD) | Windows Server | 53 | Active Directory DNS — required for domain services (SRV records, Kerberos, LDAP) |
| SSH | Ubuntu Server | 22 | Remote management via VS Code Remote-SSH (restricted to VLAN10 and Host-Only network) |
| Active Directory | Windows Server | 389 | Domain: karam.local — user/computer management, GPOs |
| Firewall (iptables) | Ubuntu Server | — | Default-deny INPUT policy, inter-VLAN routing control |
| RAID 1 (mdadm) | Ubuntu Server | — | Mirrored storage at /mnt/raid for data redundancy |
