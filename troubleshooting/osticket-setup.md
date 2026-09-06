# osTicket Setup — TechKaram GmbH

## Deployment Method
osTicket deployed via Docker on Ubuntu Server (192.168.10.10)
Accessible internally at: http://192.168.10.10

## Components
- osTicket (campbellsoftwaresolutions/osticket)
- MariaDB 10.5 (database backend)

## Departments Configured
- IT
- Development
- Accounting
- Management
- Sales

## Help Topics
- Network Issue
- Hardware Problem
- Software Request
- Account Access
- General Inquiry
- Feedback

## Agents
| Agent | Department | Access Level |
|-------|------------|--------------|
| it-admin | IT | Full Access |
| it-support | IT | Extended |
| dev-senior | Development | Extended |
| acc-accountant | Accounting | Limited |
| mgmt-hr | Management | Extended |
| sales-manager | Sales | Limited |

## Test Tickets
- Ticket #155886 — Cannot access Development share (Resolved)
- Ticket #605183 — Cannot login to domain (Resolved)
