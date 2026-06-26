# DNS Troubleshooting — TechKaram GmbH

## Issue 1: "bad name" warning on BIND9 startup

**Symptom:**  
BIND9 service started but showed warnings about invalid hostnames.  
`sudo systemctl status bind9` displayed "bad name" errors.

**Root Cause:**  
BIND9 by default enforces strict hostname validation (RFC compliance).  
Some internal hostnames did not meet strict DNS naming standards.

**Fix:**  
Added the following line to `/etc/bind/named.conf.options`:
check-names master ignore;

**Lesson Learned:**  
In internal/lab environments, strict name checking can be safely disabled.  
In production, fix the hostnames instead of disabling the check.

---

## Issue 2: Typo in zone file causing SOA record failure

**Symptom:**  
BIND9 failed to load the `karam.local` zone correctly.

**Root Cause:**  
Comma used instead of dot in SOA record:
@ IN SOA ns1,Fix:cal.   ← wrong

**Fix:**  
Corrected to:
@ IN SOA ns1.karam.local.   ← correct
Also incremented the Serial number after the fix.

**Lesson Learned:**  
Zone file syntax is strict — a single wrong character can prevent the entire zone from loading. Always run `sudo named-checkzone karam.local /etc/bind/db.karam.local` after editing zone files to catch errors before restarting the service.
