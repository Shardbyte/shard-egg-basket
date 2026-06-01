<!--
###########################
#                         #
#  Saint @ Shardbyte.com  #
#                         #
###########################
# Author: Shardbyte (Saint)
-->

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="90"/>

  # Project Zomboid

  **A current Pelican egg for Project Zomboid servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../LICENSE)
</div>

---

A survival horror server for Project Zomboid -- run a private world for you and your friends
to survive the zombie apocalypse together.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/pz/egg-project-zomboid.yaml
```

In Pelican admin: **Eggs** -- **Import Egg** -- paste the URL above.

---

## Requirements

| Item | Value |
|------|-------|
| Runtime image | `ghcr.io/shardbyte/steamcmd:debian` |
| Install image | `ghcr.io/shardbyte/installers:debian` |
| Minimum runtime RAM | 2048 MB base + ~500 MB per player |
| Ports required | Two UDP ports (game port + game port + 1) |

---

## Variables

| Name | Env | Default | Description |
|------|-----|---------|-------------|
| Server Name | `SERVER_NAME` | `PelicanPZ` | Internal name for save and config files. Alphanumeric and underscores only. Changing this after first start creates a new world. |
| Auto Update | `AUTO_UPDATE` | `1` | `1` to update server files on each container start via SteamCMD. `0` to skip updates and start faster. |
| Admin Username | `ADMIN_USER` | `admin` | In-game admin account username. |
| Admin Password | `ADMIN_PASSWORD` | _(empty)_ | In-game admin account password. Required; use a strong password -- it controls full server access. |
| Game Port (UDP) | `GAME_PORT` | `16261` | Primary UDP port clients connect to. Must match your Pelican port allocation. |
| Steam / NAT Port (UDP) | `STEAM_PORT` | `16262` | Secondary UDP port for Steam networking. Typically game port + 1. Must also be open in your firewall. |
| Max Players | `MAX_PLAYERS` | `16` | Maximum concurrent players. Written to the server ini on install; edit the ini via SFTP to change after first start. |
| Steam App ID | `SRCDS_APPID` | `380870` | Project Zomboid dedicated server App ID. Do not modify. |
| JVM Flags | `JVM_FLAGS` | _(G1GC + headless)_ | Extra JVM flags injected at startup. Invalid flags will crash the server. |
| Steam Beta Branch | `SRCDS_BETAID` | `unstable` | SteamCMD beta branch. `unstable` installs Build 42. Leave empty for Build 41 (stable). Requires a reinstall to switch branches. |
| Beta Branch Password | `SRCDS_BETAPASS` | _(empty)_ | Password for a private beta branch. Leave empty for public branches. |
| Additional Startup Parameters | `ADDITIONAL_ARGS` | _(empty)_ | Extra parameters appended to the server startup command. |

---

## Notes

- Two UDP ports must be open and allocated in Pelican: `GAME_PORT` (default 16261) and
  `STEAM_PORT` (default 16262). Both are required for clients to connect.
- Build 42 (set via `SRCDS_BETAID=unstable`) requires significantly more RAM than Build 41.
  Allocate at least 4 GB for a small server running Build 42.
- Build 42 performs a one-time cache rebuild on first boot that can take 2-3 minutes. The
  server is not stuck -- wait for "SERVER STARTED" in the console before connecting.
- Server settings beyond what the panel exposes (sandbox rules, spawn rates, etc.) are in
  `Zomboid/Server/<ServerName>.ini`. Edit this file via SFTP and restart to apply changes.
- Saves persist under `Zomboid/Saves/Multiplayer/<ServerName>/`. Back this up before
  reinstalling or changing the server name.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
