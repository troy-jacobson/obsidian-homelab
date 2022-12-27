# ThisMuch Home Lab
## Purpose
The purpose of computing resources for our family and household are to:
- Provide wired and wireless networking infrastructure for immediate family and guests
- Host services for day-to-day activities, recreation, and nice-to-have resources
- Host file storage for family needs
- Provide resources for tech based hobbies
- Implement backups and applicable security safeguards

## WAN
We currently have Charter for our ISP and own our cable modem.

[[pfSense]] provides firewall and routing services.

## LAN
See also [[IP Address Allocations]].

[[pihole]] provides DNS and DHCP services for our LAN, along with add blocking and other services.


## Proxmox
A [[Proxmox]] cluster hosts various services and applications.

## TrueNAS
[[TrueNAS]] is used for managing storage.  It is installed as a VM in Proxmox.  ZFS is used to provide a layer of redundancy.

