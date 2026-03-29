<div align="center">

# arcade

### the family's game room

**game server manager for [halo-ai](https://github.com/bong-water-water-bong/halo-ai) — fork of [LinuxGSM](https://github.com/GameServerManagers/LinuxGSM) with a web GUI**

</div>

---

## what is arcade?

a web-based game server manager that runs on your [halo-ai](https://github.com/bong-water-water-bong/halo-ai) stack. spin up dedicated game servers with one click from the [man-cave](https://github.com/bong-water-water-bong/man-cave) dashboard.

built on top of [LinuxGSM](https://linuxgsm.com/) — the battle-tested game server manager that supports 120+ games.

## what it does

- **one-click deploy** — pick a game, click deploy, server is live
- **auto port forwarding** — configures your router via UPnP or ASUS router API
- **auto DDNS** — players connect via `yourname.asuscomm.com:port`
- **auto caddy** — reverse proxy configured automatically
- **man-cave integration** — manage everything from the dashboard
- **stream deck** — start/stop game servers from a button

## how it works

```
man-cave dashboard
  > arcade API (FastAPI)
      - LinuxGSM (server management)
          SteamCMD (download server files)
          systemd (service management)
          game configs (auto-generated)
      - port manager
          UPnP (automatic)
          ASUS router API (fallback)
      - DDNS manager
          ASUS DDNS (asuscomm.com)
```

## supported games (via LinuxGSM)

| Game | Server | Status |
|------|--------|--------|
| Counter-Strike 2 | cs2server | planned |
| Valheim | vhserver | planned |
| Minecraft (Java) | mcserver | planned |
| ARK: Survival Evolved | arkserver | planned |
| Rust | rustserver | planned |
| Terraria | terraria | planned |
| 7 Days to Die | sdtdserver | planned |
| Project Zomboid | pzserver | planned |
| Palworld | pwserver | planned |
| ... and 110+ more | | |

## quick start

```bash
# install as part of halo-ai
# enable "arcade game servers" during install

# standalone
git clone https://github.com/bong-water-water-bong/arcade.git /srv/ai/arcade
cd /srv/ai/arcade
/opt/python3.13/bin/python3.13 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python arcade.py
```

access at `https://strixhalo/arcade`

## the family

| member | role |
|---|---|
| [halo ai](https://github.com/bong-water-water-bong/halo-ai) | the father — bare-metal ai stack |
| [echo](https://github.com/bong-water-water-bong/echo) | the mother — voice of the family |
| [meek](https://github.com/bong-water-water-bong/meek) | the eldest — security overseer |
| [man-cave](https://github.com/bong-water-water-bong/man-cave) | the control center |
| [arcade](https://github.com/bong-water-water-bong/arcade) | the game room |

## license

Apache 2.0
