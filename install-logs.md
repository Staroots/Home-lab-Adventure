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

##  Proxmox Installation
- Chose **ext4** as file system for SSD
- Installed Proxmox VE 8.4 successfully
- Set static IP: `192.168.1.100`
- Verified Web UI login at: `https://192.168.1.100:8006`
- Logged in as `root` under Linux PAM

##  Post-Install Cleanup
- Removed the "No Subscription" Nag Screen:
  ```bash
  sed -i.bak "s/data.status !== 'Active'/false/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js

### 2025-06-02

## 1. **Proxmox VM Setup**
- Installed Ubuntu Server in a VM via Proxmox
- Assigned 4 vCPUs, 16GB RAM, and 100GB disk
- Created `/opt/minecraft` as working directory

## 2. **Docker Setup**
- Encountered issues due to *Snap version of Docker*
- Removed Snap Docker (`snap remove docker`)
- Installed Docker Engine and Compose Plugin using official Docker APT repo:
  ```bash
  sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin
## 3. **Dcoker Compose**
- Created docker-compose.yaml for Forge Minecraft server.
- launched and successfully connected to server through Minecraft client.

### 2025-06-12 

## 1. **Reverse Proxy VM Setup**

- Uploaded Debian 12 cloud image (`debian-12-genericcloud-amd64.qcow2`) to Proxmox via SCP  
- Imported image as a disk to storage location `/mnt/sdb1/images/`  
- Created new VM (ID: 102) and attached imported disk  
- Successfully configured and booted the VM into Debian 12 login prompt  
- Installed and configured UFW firewall  
- Installed and configured Caddy with a test `Caddyfile` for `daemonroots.dev`  
- Installed `acme.sh` as root for future DNS validation and certificate automation  
- Set up secondary user account (`demroots`) for SSH access  
