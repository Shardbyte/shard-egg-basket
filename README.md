<!--
###########################
#                         #
#  Saint @ Shardbyte.com  #
#                         #
###########################
# Author: Shardbyte (Saint)
-->

<div id="header" align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte logo" width="150"/>
</div>

---

Pelican Panel egg definitions maintained by [Shardbyte](https://github.com/Shardbyte).

All eggs use images from [shard-yolk-basket](https://github.com/Shardbyte/shard-yolk-basket) — a Debian 13-first yolk image set built for Pelican Panel.

## Available Eggs

### Games

| Name | Egg File | Runtime Image | Install Image |
|---|---|---|---|
| Project Tarkov: Fika Edition | [`games/eft/egg-eft-fika.yaml`](games/eft/egg-eft-fika.yaml) | `ghcr.io/shardbyte/yolks:debian` | `ghcr.io/shardbyte/installers:dotnet_10` |
| Project Zomboid | [`games/pz/egg-project-zomboid.yaml`](games/pz/egg-project-zomboid.yaml) | `ghcr.io/shardbyte/steamcmd:debian` | `ghcr.io/shardbyte/installers:debian` |

## Installing an Egg

### Via import URL (recommended)

Each egg contains an `update_url` pointing to its raw GitHub URL. In the Pelican admin area:

1. Go to **Eggs** → **Import Egg**.
2. Paste the raw GitHub URL from the table below into the **URL** field.

| Egg | Import URL |
|---|---|
| Project Tarkov: Fika Edition | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/eft/egg-eft-fika.yaml` |
| Project Zomboid | `https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/pz/egg-project-zomboid.yaml` |

### Via file upload

Download the `.yaml` file and upload it directly in **Eggs** → **Import Egg**.

## Image Namespace

Images are published to GHCR under `ghcr.io/shardbyte/`.

| Image | Purpose |
|---|---|
| `ghcr.io/shardbyte/yolks:debian` | Generic Debian 13 runtime |
| `ghcr.io/shardbyte/steamcmd:debian` | Debian 13 runtime with SteamCMD pre-installed |
| `ghcr.io/shardbyte/installers:debian` | Debian 13 installer base (runs as root) |
| `ghcr.io/shardbyte/installers:dotnet_10` | Debian 13 installer with .NET 10 SDK |

Source: [shard-yolk-basket](https://github.com/Shardbyte/shard-yolk-basket)

## License

Copyright (c) 2023-2026 [Shardbyte](https://github.com/Shardbyte). Released under the [MIT License](LICENSE).
