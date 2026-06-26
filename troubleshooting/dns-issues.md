## Issue : "bad name" warning on BIND9 startup

Symptom:  
BIND9 showed "bad name" warnings during startup for internal hostnames.

Root Cause:  
BIND9 enforces strict RFC hostname validation by default.  
Internal lab hostnames like karam99 did not fully comply with these standards.

Fix:  
Added check-names master ignore; to named.conf.options to allow  
internal naming conventions in the lab environment.  
This is standard practice for internal DNS zones that use  
custom naming schemes not intended for public DNS.

Note:  
In a production environment, hostnames would be renamed to fully  
comply with RFC standards instead of adjusting the validation setting.
