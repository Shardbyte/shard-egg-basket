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

  # Minecraft Fabric

  **A current Pelican egg for Fabric modded Minecraft servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../../LICENSE)
</div>

---

A lightweight modded Minecraft server powered by Fabric. Use it for performance
mod packs, smaller mod lists, snapshots, and packs that update quickly.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/fabric/egg-minecraft-fabric.yaml
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
| 1.17 -- 1.20.4 | Java 17 | `ghcr.io/shardbyte/yolks:java_17` |
| 1.12.1 -- 1.16.5 | Java 11 | `ghcr.io/shardbyte/yolks:java_11` |
| 1.7.10 -- 1.12 | Java 8 | `ghcr.io/shardbyte/yolks:java_8` |

Your mod pack's download page will list the required Java version.

---

## Variables

| Name | Env | Default | Description |
|------|-----|---------|-------------|
| Server Jar File | `SERVER_JARFILE` | `server.jar` | Fabric launcher jar filename. The startup command launches this file. Must end in `.jar`. |
| Minecraft Version | `MC_VERSION` | `latest` | `latest` for newest release, `snapshot` for latest dev snapshot, or an exact version required by your mod pack. |
| Fabric Installer Version | `FABRIC_INSTALLER_VERSION` | `latest` | Fabric installer version. Leave as `latest` unless support instructions require an exact installer version. |
| Fabric Loader Version | `FABRIC_LOADER_VERSION` | `latest` | Fabric Loader version. Use `latest`, `snapshot`, or an exact version required by your mod pack. |
| JVM Flags | `JVM_FLAGS` | G1GC flags | JVM arguments injected at startup. For Java 21+ consider ZGC. Invalid flags crash on start. |
| Extra Startup Arguments | `EXTRA_ARGS` | _(empty)_ | Optional server arguments appended after the jar invocation. Leave blank for default server behavior. |

---

## Notes

- Fabric packs are strict about versions. Match Minecraft, Fabric Loader, and Java to
  the mod pack's install instructions when the pack provides them.
- Changing `MC_VERSION` or `FABRIC_LOADER_VERSION` after first install requires a reinstall
  to replace the launcher and Minecraft server jar. World data is not deleted by reinstall.
- The default JVM flags omit `-XX:+AlwaysPreTouch` intentionally -- this flag causes
  crashes in containerized environments.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
