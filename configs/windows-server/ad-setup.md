# Active Directory Setup — TechKaram GmbH

## Domain Info
- Domain Name: karam.local
- NetBIOS Name: KARAM
- Domain Controller: Windows Server 2022 — 192.168.10.20

## Organizational Units (OUs)

| OU | Users |
|----|-------|
| IT | it-admin, it-support |
| Development | dev-senior, dev-junior, dev-ops |
| Accounting | acc-accountant, acc-finance |
| Management | mgmt-hr, mgmt-ceo |
| Sales | sales-manager |

## Group Policy Objects (GPOs)

| GPO Name | Linked to OU | Policy |
|----------|--------------|--------|
| Password Policy | karam.local (Domain) | Min length 8, complexity enabled, max age 90 days, min age 1 day |
| Block USB | Accounting | Deny all Removable Storage access |
| Block Software Install | Development | Software Restriction Policy — block for all except local admins |
| Block Shutdown | Management | Remove Shutdown/Restart/Sleep/Hibernate options |
| Prevent Control Panel | Sales | Block access to Control Panel |

## Domain-joined Clients

| Computer | IP | OU/Group |
|----------|----|---------|
| WinClient1 | 192.168.10.30 | IT |
