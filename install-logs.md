#Installation Log

### 2025-05-31
- Assembled Hardware
- Installed Ubuntu 12
- Installed Casa OS
- Installed Nginx and configured proxy to use HTTPS for broswer connections
- Installed Crafty Controller, configured and set up minecraft server for internal network.
- Wasnt happy with the level of control through Casa OS and Crafty controller researching Proxmox

### 2025-06-01
- Creating this repository to document my journey
##  Flashing the Installer
- Initially used BalenaEtcher to flash Proxmox VE 8.4 ISO → flash completed, but boot failed ("switching root" hang)
- Flash drive appeared in Windows as two drives—suspected hybrid ISO weirdness
- Reflashed using Rufus with DD mode → success

##  BIOS Configuration
- Switched motherboard boot mode to **UEFI + Legacy**
- Disabled Secure Boot
- Booted successfully into Proxmox installer

## 🖥 Proxmox Installation
- Chose **ext4** as file system for SSD
- Installed Proxmox VE 8.4 successfully
- Set static IP: `192.168.1.100`
- Verified Web UI login at: `https://192.168.1.100:8006`
- Logged in as `root` under Linux PAM

###  Post-Install Cleanup
- Removed the "No Subscription" Nag Screen:
  ```bash
  sed -i.bak "s/data.status !== 'Active'/false/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js
