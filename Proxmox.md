# Proxmox
[locutus.thismuch.net](https://locutus.thismuch.net:8006)

## Software
[Proxmox](https://proxmox.com)

## Installation
### Naming convention
Nodes in the proxmox cluster will be named after good Borg.

### Bootstrapping the Home Lab
See [[Bootstrapping]] for setting up the minimal services needed for the home network.

### Bare Metal Install
Follow the standard installation for Proxmox

The boot ssd will be available as a resource as part of the standard installation.  Additional storage will be served by TrueNAS through a VM on proxmox.

Create the `hivemind` cluster.

### SSL Certificates
Near the end of the bootstrapping process (e.g. after following the instructions in [[Certificate and Key Management]] to create a wildcard SSL certification for `thismuch.net`), add the certificate to Proxmox.``

On `keys.thismuch.net`:
```
acme.sh --install-cert -d '*.thismuch.net' --key-file proxmox/pveproxy-ssl.key --fullchain-file proxmox/pveproxy-ssl.pem
```

On `locutus.thismuch.net`:
```
pct pull 109 /root/proxmox/pveproxy-ssl.pem /etc/pve/local/pveproxy-ssl.pem
pct pull 109 /root/proxmox/pveproxy-ssl.key /etc/pve/local/pveproxy-ssl.key
systemctl restart pveproxy
```

## Provisioning Containers
Make sure to be up-to-date with [ansible-workspace-home](https://github.com/troy-jacobson/ansible-workspace-home.git).

On the `local` storage, select a containter template or select a new one.  `Templates` provides a source for known good templates, many from the Turnkey Linux project, and is the typical source for  templates.

Add an entry to `inventory/my_hosts.yml` and choose appropriate values for the machine ID, hostname, IP address, and other options.

Add the hostname and IP address to [[IP Address Allocations]] and [[pihole]].

In `inventory/proxmox-cluster.yml`, add the hostname to `proxmox_lxc` and the group for the node (e.g. `pmx_locutus`)

Run the `create-container.yml` playbook to create the container:
`ansible-playbook -i inventory -l <inventory entry> create-container.yml

At this time, go to the Proxomox UI and start the container.  Then log in as `root`.  Several of the containers will need manual steps at this point in the process before moving on.

