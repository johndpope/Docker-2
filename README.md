
## MY SETUP

- MAIN - Dell T550 Proxmox Server with Ubuntu 20.10
- WEB - Digital Ocean Virtual Private Server with Ubuntu 20.10

## What apps are included in this stack?

The apps I use are scattered around in five different docker-compose files (on five hosts listed above). Some apps are used in more than one host and some on only one.

### Backend Services

- Traefik - Reverse Proxy
- Authelia - Private Forward Authentication
- Portainer - Container Management
- Organizr - Unified Frontend
- Heimdall - Unified Frontend Alternative

### Webfronts

- Organizr
- Heimdall

### Web Services

- FreshRSS
- WikiJS
- Vaultwarden
- Joplin

### Media Services

- Tautulli - Previously PlexPy. Plex statistics and monitoring

### MEDIA FILE MANAGEMENT

- Bazarr - Subtitle Management
- Picard - Music Library Tagging and Management
- Handbrake - Video Conversion, Transcoding, and Compression
- MKVToolNix - Video Editing, Remuxing (changing media container while keeping original source quality)
- MakeMKV - Video Editing (Ripping from Disks)
- FileBot - File renamer
- Tiny Media Manager - Media Files Management

### Databases

- Postgres

### UTILITIES

- UniFi Controller - Controller for Ubiquiti UniFi Network Gear

### SMART HOME

- Home Assistant Core - Home Automation
