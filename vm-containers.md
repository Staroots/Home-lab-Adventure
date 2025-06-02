# Virtual Machines and Containers
** Planned VM/Container Stack

| Name           | Type     | OS           | Purpose                         |
|----------------|----------|--------------|----------------------------------|
| `plex-vm`      | VM       | Ubuntu       | Plex Media Server                |
| `minecraft-vm` | VM       | Ubuntu       | Modded Minecraft Server          |
| `nextcloud`    | LXC      | Ubuntu       | Self-hosted cloud storage        |
| `so-vm`        | VM       | Security Onion | Network security monitoring     |
| `docker-host`  | LXC      | Alpine       | General container playground     |

## Notes
- GPU Passthrough under investigation (for transcoding)
- Separate network bridges for isolated traffic (SO, Docker)
