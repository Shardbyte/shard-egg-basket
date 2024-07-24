# Escape from Tarkov

## Singleplayer COOP Tarkov Server

**Fika** is a mod for **SPT** that allows you to play COOP with your friends. It utilizes a P2P-UDP connection for a modern and performant experience. The main goals of Fika are: performance, accuracy and mod-support. Fika is currently maintained by the Fika team.

## Egg Information

- This egg will build the requested version of SPT Tarkov from source.
  - This egg also has an option to build the requested version of FIKA Tarkov from source.

## Prerequisites

- Access to the Pterodactyl admin panel.
- General knowledge of computers, networking and SPT.

### Hosting

- Router and ISP that supports either **Port Forwarding** or **UPnP**
- TCP port 6969 open for the SPT Server
- UDP Port open for P2P traffic, default 25565 (if using UPnP this is not required)
- Internet speed of at least 20 Mbit/s up and down is recommended. Each client averages around 400 kbit/s.

#### Server Ports

Default ports required to run the server.

| Port     | default |
|----------|---------|
| Game     | 6969    |
| FIKA UDP | 25565   |

If you can not port forward, you can use a VPN like `ZeroTier` or `Radmin` or a proxy like ``Playit.gg``.

---

### Client

- Router and ISP that supports either **Port Forwarding** or **UPnP** | **NOTE**: This is only required if you will be hosting in-game
- UDP Port open for P2P traffic, default 25565 (if using UPnP this is not required) | **NOTE**: Same as above
- SPT installed and working, matching the version of Fika you are going to use
- Access to your Windows Firewall
- Internet speed of at least 20 Mbit/s up and down is recommended

#### Client for connecting to the server

[FIKA Client Latest Release](https://github.com/project-fika/Fika-Plugin/releases/latest)

### Both

- The latest **MATCHING** Fika files

---

For more information about the project you can view the [Fika Docs](https://github.com/project-fika/Fika-Documentation)
