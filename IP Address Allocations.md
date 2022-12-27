
# IP Address Allocations

### Core Networking
Range: 192.168.0.**1 - 29**

IP address for:
* Router and firewall
* Pi Hole/DNS/DHCP
* Wireless Access Points

May use static DHCP or manual configuration depending on the device.

| IP | Hostname | Documentation | Notes |
| ----- | ----- | -----| ----- |
| 192.168.0.1 | [pfsense.thismuch.net](https://192.168.0.1) | [[pfSense]] | |
| 192.168.0.5 | [ap-asus01.thismuch.net](http://ap-asus01.thismuch.net) | | Asus Wireless access point |
| 192.168.0.10 | [pihole.thismuch.net](http://pihole.thismuch.net/admin) | [[pihole]] | |
| 192.168.0.25 | keys.thismuch.net | | |




### Static IP and DNS
192.168.0.**30-149**
Hosts where IP address and DNS entries are managed manually or with other tools such as Ansible.

| IP | Hostname | Documentation | Notes |
| ----- | ----- | -----| ----- |
| 192.168.0.30 | [locutus.thismuch.net](https://192.168.0.30:8006) | [[Proxmox]] | |
| 192.168.0.31 |    | [[TrueNAS]] | |
| 192.168.0.32 | [ldap.thismuch.net](https://ldap.thismuch.net) | | |



### Named Hosts with Static IPs via DHCP
192.168.0.**150-199**
Hosts that are garnted a static IP via DHCP.

### General Devices
192.168.0.**200-254**
IP address for:
* Phones
* Computers
* Misc devices that don't need additinal DNS or networking configuration