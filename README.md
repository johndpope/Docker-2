# Description

This is the updated docker-compose repo of all the media and home server apps

### Traefik 2 (CURRENT - GENERIC LINUX)

- docker-compose-t2.yml
- docker-compose-t2-vpn.yml
- docker-compose-t2-obsolete.yml (Apps that I do not use anymore)


## What apps are included in this stack?

We will try to keep this repo up-to-date. For now, here are the apps currently included in our stack:

### FRONTENDS

- Traefik - Reverse Proxy
- OAuth - Forward Authentication (Google OAuth 2.0)
- Authelia - Private Forward Authentication (Default)
- Portainer - Container Management
- Organizr - Unified Frontend
- Heimdall - Unified Frontend Alternative
- Autoindex - Plain text Index to All Files

### SMART HOME

- Home Assistant Core - Home Automation (OBSOLETE - since Home Assistant Supervised now works on Docker)
- HA-Dockermon - Manage Docker containers in Home Assistant
- Mosquitto - MQTT Broker
- MotionEye - Video Surveillance
- ZoneMinder - Video Surveillance
- MiFlora - MiFlora MQTT Daemon (MiFlora Plant Sensors) (OBSOLETE)

### DATABASE

- MariaDB - MySQL Database
- phpMyAdmin - Database management
- InfluxDB - Database for sensor data
- Postgres - Database
- Grafana - Graphical data visualization for InfluxDB data
- Varken - Monitor Plex, Sonarr, Radarr, and Other Data (OBSOLETE)
- Redis - Key value store
- Redis Commander - Redis management

### DOWNLOADERS

- jDownloader - Download management
- TransmissionBT with VPN - Torrent Downloader with [IPVanish](https://www.smarthomebeginner.com/go/ipvanish) VPN.
- SABnzbd - Binary newsgrabber (NZB downloader)
- qBittorrent with VPN - Torrent downloader (OBSOLETE)

### INDEXERS

- NZBHydra2 - NZB meta search
- Jackett - Torrent proxy

### PVRS

- Lidarr - Music Management
- Radarr - Movie management
- Sonarr - TV Shows management
- LazyLibrarian - Books Management

### MEDIA SERVER

- AirSonic - Music Server
- Calibre - Ebook/Audiobook Server
- Calibre-Web - Ebook/Audiobook Reader
- Plex - Media Server
- Emby - Media Server
- Jellyfin - Media Server
- Ombi - Media Requests
- Tautulli - Previously PlexPy. Plex statistics and monitoring
- Plex-Sync - For Syncing watched status between plex servers
- PhotoShow - Personal Photo Gallery and viewer
- TellyTv- IPTV proxy for Plex (OBSOLETE)
- xTeve- IPTV proxy for Plex (OBSOLETE)

### MEDIA FILE MANAGEMENT

- Bazarr - Subtitle Management
- Picard - Music Library Tagging and Management
- Handbrake - Video Conversion (Transcoding and compression)
- MKVToolNix - Video Editing (Remuxing - changing media container while keeping original source quality)
- MakeMKV - Video Editing (Ripping from Disks)
- FileBot - File renamer

### SYSTEM

- Firefox - Web Broswer
- Glances - System Information
- APCUPSD - APC UPS Management
- Guacamole - Remote desktop, SSH, on Telnet on any HTML5 Browser
- Guacamole Daemon - Needed for Guacamole
- Dozzle - Docker logs viewer
- qDirStat - Directory Statistics
- StatPing - Status Page & Monitoring Server
- SmokePing - Network Latency Monitoring
- VS Code Server - Code Editor
- Logarr - Log Management (OBSOLETE)
- Monitorr - Webfront to display the status of any webapp or service (OBSOLETE)
- Cloud Commander - Web File Manager (OBSOLETE)
- Cloud9 - Cloud IDE (OBSOLETE)

### MAINTENANCE

- Ouroboros - Automatic Docker Container Updates
- Docker-GC - Automatic Docker Garbage Collection
- Traefik Certificate Dumper - Extract Traefik SSL Certs
- Cloudflare DDNS - Dynamic IP Updater
- Cloudflare Companion - Automatic CNAME creation for services

## MariaDB

Even though I have included a MariaDB container, I use an external MariaDB host (my Synology NAS).
