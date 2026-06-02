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

  # Shard Egg Basket

  **Current Pelican Panel eggs maintained by Shardbyte**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
</div>

---

All eggs use images from [shard-yolk-basket](https://github.com/Shardbyte/shard-yolk-basket) -- a Debian 13-first yolk image set built for Pelican Panel.

## Available Eggs

### Games

| Name | Egg File | Runtime Image | Install Image |
|---|---|---|---|
| Minecraft Vanilla | [`games/mc/vanilla/egg-minecraft-vanilla.yaml`](games/mc/vanilla/egg-minecraft-vanilla.yaml) | `ghcr.io/shardbyte/yolks:java_8` -- `java_25` | `ghcr.io/shardbyte/installers:debian` |
| Minecraft Forge | [`games/mc/forge/egg-minecraft-forge.yaml`](games/mc/forge/egg-minecraft-forge.yaml) | `ghcr.io/shardbyte/yolks:java_8` -- `java_25` | `ghcr.io/shardbyte/installers:java_21` |
| Project Tarkov: Fika Edition | [`games/eft/egg-eft-fika.yaml`](games/eft/egg-eft-fika.yaml) | `ghcr.io/shardbyte/yolks:debian` | `ghcr.io/shardbyte/installers:dotnet_10` |
| Project Zomboid | [`games/pz/egg-project-zomboid.yaml`](games/pz/egg-project-zomboid.yaml) | `ghcr.io/shardbyte/steamcmd:debian` | `ghcr.io/shardbyte/installers:debian` |

## Installing an Egg

### Via import URL (recommended)

Each egg contains an `update_url` pointing to its raw GitHub URL. In the Pelican admin area:

1. Go to **Eggs** -- **Import Egg**.
2. Paste the raw GitHub URL from the table below into the **URL** field.

| Egg | Import URL |
|---|---|
| Minecraft Vanilla | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/vanilla/egg-minecraft-vanilla.yaml` |
| Minecraft Forge | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/forge/egg-minecraft-forge.yaml` |
| Project Tarkov: Fika Edition | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/eft/egg-eft-fika.yaml` |
| Project Zomboid | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/pz/egg-project-zomboid.yaml` |

### Via file upload

Download the `.yaml` file and upload it directly in **Eggs** -- **Import Egg**.

## Image Namespace

Images are published to GHCR under `ghcr.io/shardbyte/`.

| Image | Purpose |
|---|---|
| `ghcr.io/shardbyte/yolks:java_25` | Java 25 runtime (MC 26.1+) |
| `ghcr.io/shardbyte/yolks:java_21` | Java 21 runtime (MC 1.20.5 -- 1.21.x) |
| `ghcr.io/shardbyte/yolks:java_17` | Java 17 runtime (MC 1.17 -- 1.20.4) |
| `ghcr.io/shardbyte/yolks:java_11` | Java 11 runtime (MC 1.12.1 -- 1.16.5) |
| `ghcr.io/shardbyte/yolks:java_8` | Java 8 runtime (MC 1.7.10 -- 1.12) |
| `ghcr.io/shardbyte/yolks:debian` | Generic Debian 13 runtime |
| `ghcr.io/shardbyte/steamcmd:debian` | Debian 13 runtime with SteamCMD pre-installed |
| `ghcr.io/shardbyte/installers:java_21` | Debian 13 installer with Java 21 (Forge installs) |
| `ghcr.io/shardbyte/installers:debian` | Debian 13 installer base (runs as root) |
| `ghcr.io/shardbyte/installers:dotnet_10` | Debian 13 installer with .NET 10 SDK |

Source: [shard-yolk-basket](https://github.com/Shardbyte/shard-yolk-basket)

## License

Copyright (c) 2023-2026 [Shardbyte](https://github.com/Shardbyte). Released under the [MIT License](LICENSE).

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
