# SCP: ReEnter — Pterodactyl Egg

Official Pterodactyl egg for hosting **SCP: ReEnter Dedicated Servers**.

This egg installs and manages the SCP: ReEnter Dedicated Server through **SteamCMD** and includes support for automatic updates, basic server configuration, additional startup arguments, and the optional **SCP WebPanel**.

## Features

- SteamCMD installation
- Automatic game updates on server startup
- Optional file validation
- Configurable server name and description
- Configurable maximum player count
- Friendly fire toggle
- Optional SCP WebPanel support
- Custom Steam branch support
- Additional startup arguments
- Pterodactyl `PTDL_v2` format

## Requirements

- Pterodactyl Panel
- Pterodactyl Wings
- Linux-compatible node
- Network allocation for the game server
- Additional TCP allocation if SCP WebPanel is enabled

## Installation

1. Download `egg-scp-reenter.json`.
2. Open your Pterodactyl admin panel.
3. Go to **Nests**.
4. Create or select a suitable nest.
5. Click **Import Egg**.
6. Upload `egg-scp-reenter.json`.
7. Create a new server using the imported egg.
8. Configure the required ports and server variables.
9. Start the server.

The egg will install the SCP: ReEnter Dedicated Server automatically using SteamCMD.

## Steam App ID

The dedicated server uses Steam App ID:

```text
4211100
```

## Default Docker Image

```text
ghcr.io/ptero-eggs/steamcmd:ubuntu_24.04
```

## Configuration

The egg exposes the following configuration options:

| Variable | Description |
|---|---|
| `GAME_AUTO_UPDATE` | Automatically update the game before startup |
| `VALIDATE` | Validate server files through SteamCMD |
| `SERVER_NAME` | Server name shown in the server browser |
| `SERVER_DESCRIPTION` | Server description / MOTD |
| `MAX_PLAYERS` | Maximum player count |
| `FRIENDLY_FIRE` | Enable or disable friendly fire |
| `ENABLE_WEB_PANEL` | Enable the optional SCP WebPanel |
| `WEB_PANEL_MODE` | WebPanel HTTPS / HTTP mode |
| `WEB_PANEL_PORT` | Port used by SCP WebPanel |
| `SRCDS_BETAID` | Optional Steam branch |
| `SRCDS_BETAPASS` | Optional Steam branch password |
| `EXTRA_ARGS` | Additional server startup arguments |

## SCP WebPanel

The optional SCP WebPanel can be enabled with:

```text
ENABLE_WEB_PANEL=1
```

Before enabling it, assign an additional TCP allocation to the server and set the same port in:

```text
WEB_PANEL_PORT
```

The default WebPanel port is:

```text
8080
```

## Updates

Automatic updates are enabled by default.

When `GAME_AUTO_UPDATE` is set to `1`, SteamCMD checks for updates before every server start.

For troubleshooting, `VALIDATE` can be enabled to verify the installed server files.

## Server Files

The egg expects the SCP: ReEnter server launcher at:

```text
SCPReEnterServer.sh
```

The optional web panel executable is:

```text
SCPWebPanel
```

## Support

For questions related to this egg or SCP: ReEnter server hosting:

**contact@scpreenter.com**

## License

Refer to the SCP: ReEnter project and game licensing terms for usage of SCP: ReEnter server files and related assets.
