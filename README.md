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

# Usage

## Installation

First, install Docker and Docker Compose, as described in our <a href="https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/">Docker Media Server guide</a>.

1. Clone the repo.
2. Configure `traefik.toml`

- Rename `traefik\traefik.toml.example` to `traefik\traefik.toml`
- Edit it to reflect your situation
- Edit domain name.
- DNS Challenge (for LetsEncrypt verification) is enabled by default for cloudflare. Use the [Traefik Reverse Proxy guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/) for help with this.
- For other providers other than cloudflare, [check here](https://docs.traefik.io/v2.0/https/acme/#providers).

3. (Optional) Enable or use HTTP Basic Authentication by renaming `shared\.htpasswd.example` to `shared\.htpasswd` in the folder and adding username and hashed password to it.
4. Configure environmental variables (`.env` file)

- Rename the included `.env.example` to `.env`.
- Edit variables in `.env` file.
- All variables (ie. `${XXX}`) in docker-compose.yml come from `.env` file stored in the same place as docker-compose.yml.
- Ensure good permissions for the `.env` file (recommended: 640).

5. Edit `docker-compose.yml` to include only the services you want or add additional services to it. Be sure to read the comments for each app and create any required files.
6. Start and stop your docker stack as described in our [Docker Media Server guide](https://www.smarthomebeginner.com/docker-home-media-server-2018-basic/).
7. (Optional) Put non-docker apps behind Traefik proxy by renaming `traefik\rules\app.toml.example` to `traefik\rules\app.toml` and editing its contents.

## Starting and Stopping

I use bash_aliases to simplify starting and stopping containers/stack. Included in the repo is an example of bash_aliases I use (replace USER with your Linux username). Here are some example alias commands:

- <strong>dc1up</strong> or <strong>dc2up</strong> - Create network and start Docker Traefik 1 or 2 stack
- <strong>dc1down</strong> or <strong>dc2down</strong> - Stop Docker Traefik 1 or 2 stack
- <strong>dcup1</strong> or <strong>dcup2</strong> - Start Docker Traefik 1 or 2 stack
- <strong>dcup1v</strong> or <strong>dcup2v</strong> - Start Docker Trafik 1 or 2 VPN stack
- <strong>dcdown1</strong> or <strong>dcdown2</strong> - Stop Docker Traefik 1 or 2 stack
- <strong>dcdown1v</strong> or <strong>dcdown2v</strong> - Stop Docker Traefik 1 or 2 VPN stack
- <strong>dcrec1</strong> or <strong>dcrec2</strong> - Start or recreate a specific service
- <strong>dcstop1</strong> or <strong>dcstop2</strong> - Stop a specific service
- <strong>dcrestart1</strong> or <strong>dcrestart2</strong> - Restart a specific service
- <strong>dclogs1</strong> or <strong>dclogs1v</strong> or <strong>dclogs2</strong> or <strong>dclogs2v</strong> - See real-time logs for the corresponding stack or service
- <strong>dcpull1</strong> or <strong>dcpull1v</strong> or <strong>dcpull2</strong> or <strong>dcpull2v</strong> - Pull new images for the corresponding stack or service
