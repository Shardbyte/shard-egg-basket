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

  # Project Tarkov: Fika Edition

  **A current Pelican egg for private SPT and Fika co-op servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../LICENSE)
</div>

---

A self-hosted co-op server for Escape from Tarkov using SPT (Single Player Tarkov) and the
Fika mod. Lets you and your friends run private raids together without the official servers.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/eft/egg-eft-fika.yaml
```

In Pelican admin: **Eggs** -- **Import Egg** -- paste the URL above.

---

## Requirements

| Item | Value |
|------|-------|
| Runtime image | `ghcr.io/shardbyte/yolks:debian` |
| Install image | `ghcr.io/shardbyte/installers:dotnet_10` |
| Minimum install RAM | 4096 MB |
| Minimum runtime RAM | 4096 MB |

The install process compiles SPT from source using the .NET 10 SDK. It requires at least 4 GB
of RAM during installation -- the container will be killed by the OOM killer if given less.

---

## Variables

| Name | Env | Default | Description |
|------|-----|---------|-------------|
| SPT Version | `SPT_BRANCH` | `4.0.13` | Git branch or tag on `sp-tarkov/server-csharp` to compile. Use a version tag (e.g. `4.0.13`) for a stable release, or `main` for the latest development build. |
| Install Fika | `SPT_FIKA` | `0` | Set to `1` to automatically download and install the latest Fika co-op mod release alongside SPT. Set to `0` for a standard single-player SPT server. |

---

## Notes

- Fika requires each connecting client to also have the Fika client mod installed -- the server
  mod alone is not enough. Check the [Fika project](https://github.com/project-fika) for client setup.
- Changing `SPT_BRANCH` after installation requires a full reinstall to rebuild from the new
  source. The existing server data is wiped on reinstall.
- If the install fails with an OOM error (exit 137), increase the install container memory
  to at least 4 GB and trigger a reinstall.
- The Fika config at `user/mods/fika-server/assets/configs/fika.jsonc` is seeded during
  install so Pelican can manage the backend IP and port settings correctly on first boot.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
