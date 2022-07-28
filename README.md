# proxmox-zfs-postinstall-v2

This script merges proxmox-zfs-postinstall (https://github.com/bashclub/proxmox-zfs-postinstall) and proxmox-autosnap (https://github.com/apprell/proxmox-autosnap)

## proxmox-zfs-postinstall

This script installs and configures basic tools for running a Proxmox Server.
Following settings are made:
- Disable `pve-enterprise` repo
- Add `pve-no-subscription` repo
- Upgrade system to latest version
- Install basic tools: `sudo vim ifupdown2 net-tools dnsutils ethtool git curl unzip screen iftop lshw smartmontools nvme-cli lsscsi sysstat zfs-auto-snapshot htop mc rpl`
- Configure snapshot retention for ZFS with `proxmox-autosnap` non-interactively
- `zfs_arc_[min|max]` will be calculated by size sum of all zpools in 512 MB steps
- Configure `vm.swappiness` interactively
- Install checkmk Agent with optional encryption and registration
- Added Support for Proxmox VE 7.0
- Added Proxmox SDN features

# Usage

Just download and execute the script, all settings are made interactively.
```
wget https://github.com/cef-informatique/proxmox-zfs-postinstall-v2/raw/main/proxmox-zfs-postinstall.sh
bash ./proxmox-zfs-postinstall.sh
```
