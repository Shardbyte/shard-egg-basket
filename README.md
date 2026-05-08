<!--
#
#
###########################
#                         #
#  Saint @ Shardbyte.com  #
#                         #
###########################
# Author: Shardbyte (Saint)
#
#
-->

<div id="header" align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="logo-shardbyte" width="150"/>
</div>

---

Pelican Panel egg definitions maintained by [Shardbyte](https://github.com/Shardbyte).

All eggs in this repository use images from [`ghcr.io/shardbyte/yolks`](https://github.com/Shardbyte/shard-yolk-basket) — a modern, Debian 13-first yolk image set built for Pelican Panel.

## Available Eggs

### Games

| Name | Path | Runtime Image |
|---|---|---|
| Project Tarkov: Fika Edition | [`games/eft/egg-eft-fika.yaml`](games/tarkov/egg-tarkov-fika.yaml) | `ghcr.io/shardbyte/yolks:debian` |

## Installing an Egg

1. In the Pelican Panel admin area, go to **Eggs**.
2. Click **Import Egg** and upload the `.yaml` file, or paste the raw GitHub URL into the **URL** field.

## Image Namespace

| Registry | Purpose |
|---|---|
| `ghcr.io/shardbyte/yolks` | Runtime and SDK bases |
| `ghcr.io/shardbyte/games` | Game-specific runtimes |
| `ghcr.io/shardbyte/installers` | Installation script helpers (`debian`, `dotnet_10`, `java_21`) |

## License

Copyright (c) 2023-2026 Shardbyte. All rights reserved.
