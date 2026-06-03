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

  # Minecraft Vanilla

  **A current Pelican egg for vanilla Minecraft servers**

  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](../../../LICENSE)
</div>

---

A vanilla Minecraft server downloaded directly from the official Mojang manifest.
No third-party sources, no mods -- just a clean survival or creative world for
you and your friends.

---

## Import

```
https://raw.githubusercontent.com/Shardbyte/shard-egg-basket/refs/heads/main/games/mc/vanilla/egg-minecraft-vanilla.yaml
```

In Pelican admin: **Eggs** -- **Import Egg** -- paste the URL above.

---

## Requirements

| Item | Value |
|------|-------|
| Runtime image | See Java Version table below |
| Install image | `ghcr.io/shardbyte/installers:debian` |
| Minimum install RAM | 256 MB |
| Minimum runtime RAM | 1024 MB (2048+ MB recommended for most versions) |

### Java Version by Minecraft Version

| Minecraft Version | Required Java | Runtime Image |
|-------------------|---------------|---------------|
| 26.1+ (2026, year-based) | Java 25 | `ghcr.io/shardbyte/yolks:java_25` |
| 1.20.5 -- 1.21.x | Java 21 | `ghcr.io/shardbyte/yolks:java_21` |
| 1.17 -- 1.20.4 | Java 17 | `ghcr.io/shardbyte/yolks:java_17` |
| 1.12.1 -- 1.16.5 | Java 11 | `ghcr.io/shardbyte/yolks:java_11` |
| 1.7.10 -- 1.12 | Java 8 | `ghcr.io/shardbyte/yolks:java_8` |

Using a lower Java version than required will crash the server on start.
Higher is usually fine -- prefer the newest Java that your version supports.

---

## Variables

| Name | Env | Default | Description |
|------|-----|---------|-------------|
| Server Jar File | `SERVER_JARFILE` | `server.jar` | Jar filename. The install script downloads and names the server jar to this value. Must end in `.jar`. |
| Minecraft Version | `MC_VERSION` | `latest` | `latest` for newest release, `snapshot` for latest dev snapshot, or an exact version (e.g. `1.21.4`, `26.1.2`). Changing version requires a reinstall. |
| JVM Flags | `JVM_FLAGS` | G1GC flags | JVM arguments injected at startup. For Java 21+ consider ZGC. Invalid flags crash on start. |
| Extra Startup Arguments | `EXTRA_ARGS` | _(empty)_ | Optional arguments appended after the jar invocation (e.g. `--bonusChest`, `--eraseCache`). |

---

## Notes

- If the server crashes immediately on start, check the Java version dropdown
  on the Startup tab. Each Minecraft version has a minimum Java requirement --
  running an older JVM will fail before the world loads.
- Minecraft switched to year-based versioning in 2026 (26.1, 26.2, ...). These
  versions require Java 25. Both old (1.x.x) and year-based (26.x.x) versions
  are supported.
- Very old versions (before 1.2.5) do not have a dedicated server jar in the
  Mojang manifest. The install script will abort with an error for these.
- Changing `MC_VERSION` after first start requires a reinstall to replace the
  jar file. World data in `world/` is not deleted by reinstall.
- The default JVM flags omit `-XX:+AlwaysPreTouch` intentionally -- this flag
  causes crashes in containerized environments.

---

<div align="center">
  <img src="https://raw.githubusercontent.com/Shardbyte/Shardbyte/main/img/logo-shardbyte-master-light.webp" alt="Shardbyte" width="22"/>
  <br/>
  <sub>Built by <a href="https://github.com/Shardbyte">Shardbyte</a></sub>
</div>
