
## MY SETUP

- MAIN - Dell T550 Proxmox Server with Ubuntu 20.10
- WEB - Digital Ocean Virtual Private Server with Ubuntu 20.10

## What apps are included in this stack?

The apps I use are scattered around in five different docker-compose files (on five hosts listed above). Some apps are used in more than one host and some on only one.

### FRONTENDS

- Traefik - Reverse Proxy
- Docker Socket Proxy - Secure Proxy for Docker API
- Authelia - Private Forward Authentication
- Portainer - Container Management
- Organizr - Unified Frontend
- Heimdall - Unified Frontend Alternative

### SMART HOME

- Home Assistant Core - Home Automation

### INDEXERS

- NZBHydra2 - NZB meta search
- Jackett - Torrent proxy

### PVRS

- Lidarr - Music Management
- Radarr - Movie management
- Sonarr - TV Shows management
- LazyLibrarian - Books Management
- Readarr - Books Management

### MEDIA SERVER

- AirSonic - Music Server
- Calibre - Ebook/Audiobook Server
- Calibre-Web - Ebook/Audiobook Reader
- Plex - Media Server
- Emby - Media Server (OBSOLETE)
- Jellyfin - Media Server
- Ombi - Media Requests (OBSOLETE)
- Tautulli - Previously PlexPy. Plex statistics and monitoring
- Plex-Sync - For Syncing watched status between plex servers
- PhotoShow - Personal Photo Gallery and viewer
- TellyTv- IPTV proxy for Plex (OBSOLETE)
- xTeve- IPTV proxy for Plex (OBSOLETE)

### MEDIA FILE MANAGEMENT

- Bazarr - Subtitle Management
- Picard - Music Library Tagging and Management
- Handbrake - Video Conversion, Transcoding, and Compression
- MKVToolNix - Video Editing, Remuxing (changing media container while keeping original source quality)
- MakeMKV - Video Editing (Ripping from Disks)
- FileBot - File renamer
- Tiny Media Manager - Media Files Management

### UTILITIES

- UniFi Controller - Controller for Ubiquiti UniFi Network Gear
