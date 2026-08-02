# BedWars1058‑Inviter

[![Modrinth](https://img.shields.io/badge/1.15-Release-success?logo=modrinth)](https://modrinth.com/plugin/bedwars1058-inviter/versions)
[![Java](https://img.shields.io/badge/Java-11%2B-important)](https://adoptium.net/)
[![bStats](https://bstats.org/signatures/bukkit/BedWars1058-Inviter.svg)](https://bstats.org/plugin/bukkit/BedWars1058-Inviter/32091)

**Lightweight yet powerful addon for BedWars1058** that fills your arenas faster, keeps players connected, and puts communication entirely in your hands.

> This plugin is **closed source**. Redistribution, decompilation, or modification is prohibited.

---

## Features

- **Automatic Arena Announcements** – configurable interval, minimum player threshold, togglable
- **Manual Invite `/yq`** – personalised clickable invitations, cross‑world visibility, cooldown
- **Server‑wide Shout `/hh`** – broadcast to all players, separate cooldown
- **Quick Invite Item** – customisable item given in waiting/starting arenas, right‑click to invite
- **Quick Start `/bi startgame`** – force‑start a game (with temporary OP for `/bw start`)
- **Hide Commands** – `/bi hide yq` / `/bi hide hh` to toggle message visibility (experimental)
- **Multi‑Language** – editable YAML language files, switch with `/bi language <lang>`
- **Placeholder System** – `{arena}`, `{player}`, `{luckpermprefix}`, `{acceptbutton}`, `{rejectbutton}`, …
- **Config Auto‑Completion** – missing options and language keys are automatically added on startup
- **Clickable Messages** – accept/reject buttons, hover tooltips, direct join with smart `/leave` support
- **Proxy Support** – BungeeCord (BedWarsProxy) and Velocity (experimental)
- **bStats Integration** – anonymous usage statistics (can be disabled)
- **Update Checker** – notifies admins about new versions from Modrinth

## Requirements

- **BedWars1058** (BedWarsProxy optional for BungeeCord)
- **Java 11+**
- **Spigot / Paper 1.8.8 – 1.21**
- **LuckPerms** (optional, for `{luckpermprefix}`)

## Installation

1. Drop the `.jar` into your server’s `plugins/` folder.
2. Restart the server.
3. Add `/yq` and `/hh` to `allowed-commands` in `plugins/BedWars1058/config.yml`:
   ```yaml
   allowed-commands:
     - shout
     - bw
     - leave
     - yq
     - hh
   ```
4. Restart again for the changes to take effect.
5. Edit `plugins/BedWars1058-Inviter/config.yml` and the language files in `language/`.
6. Apply changes without restart: `/bi reload`

> **Important**: `/yq` and `/hh` **must** be added to BedWars1058’s `allowed-commands` list, otherwise they won’t work in‑game.

## Commands & Permissions

| Command | Description | Permission |
| :--- | :--- | :--- |
| `/yq` | Send a manual arena invitation | `bi.use` (default) |
| `/hh <msg>` | Server‑wide shout | `bi.use` (default) |
| `/bi reload` | Reload configuration (confirmation required) | `bi.admin` |
| `/bi language <lang>` | Switch server language (preserves config comments) | `bi.admin` |
| `/bi version` | Show plugin author and version | `bi.use` |
| `/bi update` | Manually check for updates | `bi.admin` |
| `/bi startgame` | Force‑start the current arena | `bi.start` |
| `/bi hide <yq\|hh>` | Toggle invitation or shout visibility | `bi.hide.yq` / `bi.hide.hh` |
| `/bi help` | Display customisable help menu | `bi.use` |

**Permission Nodes**
- `bi.use` – allows `/yq`, `/hh`, `/bi help` (default: true)
- `bi.admin` – allows `/bi reload`, `/bi language`, `/bi update` (default: op)
- `bi.start` – allows `/bi startgame` and the quick‑start item (default: op)
- `bi.hide.yq` – allows toggling invitation visibility (default: true, requires `experimental-features.enabled: true`)
- `bi.hide.hh` – allows toggling shout visibility (default: true, requires `experimental-features.enabled: true`)
- `bi.update` – receives update notifications (default: op)

## Configuration & Language

- All functional settings are in `config.yml`. Missing keys are automatically appended on startup, so upgrading is seamless.
- Player‑facing messages are stored in `language/en_us.yml` (default) and `language/zh_cn.yml`. You can create your own file and switch with `/bi language <lang>`. Language files also auto‑complete.

## Support

Found a bug or have a suggestion? Open an issue on the [issue tracker](https://github.com/xwasd48/Plugin-Issue-Reporting-Repository/issues).

