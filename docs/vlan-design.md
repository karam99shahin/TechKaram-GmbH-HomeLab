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
| IT (VLAN10) | Management (VLAN40) | ACCEPT |
| Management (VLAN40) | IT (VLAN10) | ACCEPT |
| IT (VLAN10) | Accounting (VLAN30) | ACCEPT |
| IT (VLAN10) | Sales (VLAN50) | ACCEPT |
| Accounting (VLAN30) | Any | DROP |
| Sales (VLAN50) | Any | DROP |
| Development (VLAN20) | Accounting/Sales | DROP |
| Management (VLAN40) | Accounting/Sales | DROP |

## Design Rationale

- IT has full access to all departments as it is responsible for technical support and infrastructure management across the entire company.
- Development and Management can communicate with IT for support, but have no access to Accounting or Sales to protect sensitive financial and customer data.
- Accounting and Sales cannot initiate connections to any other department — they can only respond to IT requests.
- All inter-VLAN traffic is enforced at the Ubuntu Server (acting as router) via iptables FORWARD chain rules with a default DROP policy.
- This design follows the Principle of Least Privilege — each department has only the access it operationally requires.
