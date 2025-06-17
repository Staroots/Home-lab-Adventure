# Home-lab-Adventure
This repository documents the build, configurations, and evolition of my personal home server. This is being created from a previous gaming computer I built years ago.

## Purpose
- DevOps
- Automation
- Self-hosting services
- Ifrastructure & Security Tools

## Goals
- Learn Proxmox for virtualization and containerization
- Host services like:
  - Security Tools (Security Onion, Fail2Ban, ect.)
  - Plex or Jellyfin (Media Server)
  - Modded Minecraft Server
- Practice DevOps Concepts and infrastructure management

## Base System
- **Hypervisor**: Proxmox VE (installed over Ubuntu Server)
- ** Primary VM/container stack**
  - Plex or Jellyfin in LXC or VM
  - Minecraft In dedicated Docker container
  - Security Onion in VM monitoring the services
  - Reverse proxy (Ngix or traefik)
  - Docker host for experimentation

See 'proxmox-setup.md' and vm-containers.md' for technical details.
 
## Status
See 'install-logs.md' for timeline and changes.
