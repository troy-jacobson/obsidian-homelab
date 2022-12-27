# TrueNAS
[truenas-01.thismuch.net](https://truenas-01.thismuch.net)

## Purpose
TrueNAS 

## Hardware
Proxmox VM #101
- 2 Cores
- 8GB RAM
- 50 GB system volume
- 4 8TB drives, in pass-through mode from Proxmox


## Software
[TrueNAS Scale](https://www.truenas.com/truenas-scale/)

Get the URL for the current version TrueNAS SCALE from their [download page/](https://www.truenas.com/download-truenas-scale/)
Go to `local` storage on the `locutus` node
Select `ISO Images`
Use the `Download from URL` button to get the ISO from TrueNAS and make it available on Proxmox.

## Configuration
Adding the hard drives:
Configure PCI passthrough on `locutus`

In the `Hardware`  section of the TrueNAS VM, 

In the `Hardware` section of the TrueNAS VM, add a CD/DVD Drive loaded with the TrueNAS ISO.

Install TrueNAS into the VM.

Configure a static IP address and add an entry on the pihole.

Create the `helium-1` ZFS pool with the four hard drives.

