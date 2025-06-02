graph TD
  Internet --> Router
  Router --> |LAN| Proxmox
  Proxmox --> VM1[Security Onion]
  VM1 --> TAP0[Monitoring NIC]
  Proxmox --> VM2[Minecraft]
  Proxmox --> VM3[Plex]
  
