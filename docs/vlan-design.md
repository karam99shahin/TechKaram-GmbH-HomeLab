# VLAN Design — TechKaram GmbH

## VLAN Table

| VLAN ID | Name | Subnet | Gateway | Department |
|---------|------|--------|---------|------------|
| VLAN10 | IT | 192.168.10.0/24 | 192.168.10.10 | IT Department |
| VLAN20 | Development | 192.168.20.0/24 | 192.168.20.1 | Development |
| VLAN30 | Accounting | 192.168.30.0/24 | 192.168.30.1 | Accounting |
| VLAN40 | Management | 192.168.40.0/24 | 192.168.40.1 | Management |
| VLAN50 | Sales | 192.168.50.0/24 | 192.168.50.1 | Sales |

## Inter-VLAN Routing Rules

| From | To | Action |
|------|----|--------|
| IT (VLAN10) | Development (VLAN20) | ACCEPT |
| Development (VLAN20) | IT (VLAN10) | ACCEPT |
| Management (VLAN40) | IT (VLAN10) | ACCEPT |
| IT (VLAN10) | Management (VLAN40) | ACCEPT |
| Accounting (VLAN30) | Any | DROP |
| Sales (VLAN50) | Any | DROP |

## Design Rationale

- IT has broad access (Development, Management) since it manages infrastructure and support across departments.
- Development and Management can communicate directly with IT for support and oversight, but not with each other unless explicitly required.
- Accounting and Sales are fully isolated from other VLANs as a security measure, since they handle sensitive financial and customer data with no operational need to reach other departments.
- All inter-VLAN traffic is enforced at the Ubuntu Server (acting as router) via iptables FORWARD chain rules.
