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

  # Minecraft NeoForge

  **A current Pelican egg for NeoForge modded Minecraft servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../../LICENSE)
</div>

---

A modern modded Minecraft server powered by NeoForge. Use it for packs built on
NeoForge, including newer Forge-style mod packs that need the NeoForge loader.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/neoforge/egg-minecraft-neoforge.yaml
```

In Pelican admin: **Eggs** -- **Import Egg** -- paste the URL above.

---

## Requirements

| Item | Value |
|------|-------|
| Runtime image | See Java Version table below |
| Install image | `ghcr.io/shardbyte/installers:java_21` |
| Minimum install RAM | 512 MB |
| Minimum runtime RAM | 2048 MB (varies by mod pack) |

### Java Version by Minecraft Version

| Minecraft Version | Required Java | Runtime Image |
|-------------------|---------------|---------------|
| 26.1+ (2026, year-based) | Java 25 | `ghcr.io/shardbyte/yolks:java_25` |
| 1.20.5 -- 1.21.x | Java 21 | `ghcr.io/shardbyte/yolks:java_21` |
| 1.20.1 -- 1.20.4 | Java 17 | `ghcr.io/shardbyte/yolks:java_17` |

Your mod pack's download page will list the required Java version.

---

## Variables

| Name | Env | Default | Description |
|------|-----|---------|-------------|
| Minecraft Version | `MC_VERSION` | `latest` | Minecraft version to install NeoForge for (e.g. `1.21.1`). Use `latest` to auto-resolve the newest version with a NeoForge build. |
| NeoForge Version | `NEOFORGE_VERSION` | _(empty)_ | Full NeoForge version string (e.g. `21.1.200` or `1.20.1-47.1.106`). When set, skips auto-resolution from `MC_VERSION`. |
| JVM Flags | `JVM_FLAGS` | G1GC flags | JVM arguments injected at startup. For Java 21+ consider ZGC. Invalid flags crash on start. |
| Extra Startup Arguments | `EXTRA_ARGS` | _(empty)_ | Optional server arguments appended after the launch invocation. Leave blank for default server behavior. |

---

## Notes

- NeoForge 1.20.1 uses the legacy `forge` artifact on the NeoForged Maven repository.
  The install script handles this automatically.
- NeoForge launches through `unix_args.txt`. Do not remove that file after install.
- If the server crashes immediately on start, check the Java version dropdown on the
  Startup tab and match the Java version listed by your mod pack.
- The default JVM flags omit `-XX:+AlwaysPreTouch` intentionally -- this flag causes
  crashes in containerized environments.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
