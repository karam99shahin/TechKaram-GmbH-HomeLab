# DHCP Troubleshooting — TechKaram GmbH

## Issue: DHCP server running but not assigning IP addresses

**Symptom:**  
Client connected to VLAN10 but received no IP address.  
`ip a` showed only link-local IPv6, no IPv4 address.

**Root Cause:**  
The subnet declaration in `/etc/dhcp/dhcpd.conf` was commented out by default.  
The service started successfully but had no active subnet configured.

**Fix:**  
Uncommented and configured the subnet block:

subnet 192.168.10.0 netmask 255.255.255.0 {
  range dynamic-bootp 192.168.10.50 192.168.10.100;
  option routers 192.168.10.10;
  option domain-name-servers 192.168.10.10;
}


**Lesson Learned:**  
Always verify `/etc/dhcp/dhcpd.conf` after installation — default config ships with all subnets commented out. Use `sudo systemctl status isc-dhcp-server` to confirm service is active, then test with a client.
