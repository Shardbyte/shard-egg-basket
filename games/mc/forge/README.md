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

  # Minecraft Forge

  **A current Pelican egg for modded Minecraft servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../../LICENSE)
</div>

---

A modded Minecraft server powered by Forge. Install mod packs so you and your friends can
play together -- from tech mods like Create to adventure packs like RLCraft.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/forge/egg-minecraft-forge.yaml
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
| Server Jar File | `SERVER_JARFILE` | `server.jar` | Jar filename used on Forge versions below 1.17. On 1.17+ this is unused because Forge launches via `unix_args.txt`. Must end in `.jar`. |
| Minecraft Version | `MC_VERSION` | `latest` | Minecraft version to install Forge for (e.g. `1.20.1`, `26.1.2`). Use `latest` to auto-resolve the newest version with a Forge build. |
| Build Type | `BUILD_TYPE` | `recommended` | Forge build channel. `recommended` = latest stable release. `latest` = includes release candidates. Ignored when `FORGE_VERSION` is set. |
| Forge Version | `FORGE_VERSION` | _(empty)_ | Full Forge version string (e.g. `1.20.1-47.3.0`). When set, skips auto-resolution entirely. Leave blank to auto-resolve from `MC_VERSION` and `BUILD_TYPE`. |
| JVM Flags | `JVM_FLAGS` | Aikar's G1GC flags | JVM arguments injected at startup. Defaults to Aikar's tuned G1GC flags for Minecraft servers. For Java 21+ consider ZGC: `-XX:+UseZGC -XX:+ZGenerational`. Invalid flags crash the server on start. |
| Extra Startup Arguments | `EXTRA_ARGS` | _(empty)_ | Optional server arguments appended after the launch invocation. Useful for Forge/FML flags like `--universe` or `--world`. |

---

## Notes

- If the server crashes immediately on start, the Java version is almost always the cause.
  Check your mod pack's download page for the required Java version and update the runtime
  dropdown on the server's Startup tab to match.
- Minecraft switched to year-based versioning in 2026 (26.1, 26.2, ...). These versions
  require Java 25. Both old (1.x.x) and year-based (26.x.x) versions are fully supported.
- The install container uses `java_21` and cannot run very old Forge installers (MC 1.12.2
  and older require a Java 8 installer). A `java_8` installer image is planned.
- Forge 1.17+ uses JPMS (`--add-opens` flags) via `unix_args.txt`. The startup command
  handles this automatically -- do not remove the `unix_args.txt` logic from the command.
- The default JVM flags omit `-XX:+AlwaysPreTouch` intentionally -- this flag causes crashes
  in containerized environments even though it appears in the official Aikar's flags reference.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
