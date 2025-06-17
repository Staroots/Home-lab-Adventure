# Proxmox Setup (To-Do)

## Installation
- Installed Proxmox 
- Installed to dedicated SSD
- Created separate ZFS pool for VMs and containers usin:
  - 6TB Toshiba MG08 HDD (Media/Data)
  - SSD for high-performance VMs

** Configuration
- Created Static IP for Proxmox host
- Enabled SSH and web UI access
- Updated repositories to remove enterrise subscrition nag
- Created backup schedule to Cold Storage (planned)

## Next Steps
- Create initial LXC templates for Ubuntu & Alpine
- Set up cloud-init
- Install Terraform provider for Proxmox (DevOps practice)
