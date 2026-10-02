# BMR Fleet Manager

Fleet tools and a local browser dashboard for **Railroader**, by BMR.

Manage equipment, numbering, groups, destinations and exports from the game or a browser on your game PC. 
Plan trains with the train calculator, read and add timetable services, and view a printable Train Graph.

**First public release: 0.21.4** | **Requires: Railroader 2025.1 and Unity Mod Manager 0.27.10 or later**

[GitHub downloads](https://github.com/BMR-Modding/BMR-Fleet-Manager-Releases/releases) | [Nexus Mods](https://www.nexusmods.com/games/railroader/mods/1787) | [User guide](USER_GUIDE.md) | [Help and bug reports](SUPPORT.md) | [Release notes](CHANGELOG.md) | [Discord support](https://discord.com/channels/795878618697433097/1316066545352577145)


The 0.21.4 download is prepared as a draft for final publication.

## Install or update

1. Close Railroader.
2. Download **BMR.FleetManager-0.21.4.zip** from GitHub Releases or the Nexus Files tab. Use the named mod ZIP, rather than GitHub's automatically generated source archives.
3. Remove standalone **BMR Equipment Delivery** and legacy **BMR Purchase Interchange** if installed; delivery is included in Fleet Manager.
4. Install the ZIP through Unity Mod Manager, replacing any previous Fleet Manager version.
5. Load a railroad and open **Company > Equipment**. Confirm **Fleet Manager 0.21.4**.
6. Reload any open Fleet Manager browser tabs after updating.

## Features

- Search, category/car-type filters, maintenance information and saved equipment groups.
- Reviewed bulk numbering, purchase numbering rules and attached-tender handling.
- Repair, sale and compatible automatic Load/Unload waybill destinations.
- A resizable game window and local browser dashboard, with dark mode and company logos.
- Train calculations with MU traction, coupled or planned helpers, starting/running grade estimates, Imperial/Metric units and printable train sheets.
- Persistent numbering/company history with reviewed restoration, plus in-game Undo last change.
- Timetable reading and new services, with a printable Train Graph.
- CSV export, optional timed/save/exit exports and local files organized by game save.

Open the browser through **UMM > BMR Fleet Manager > Open web interface** or the game's **Export** tab. Its default address is [127.0.0.1:18766](http://127.0.0.1:18766/); run it on the same PC as the game.

For multiplayer, host and participating clients need matching **0.21.4**. Officers and Presidents may request host-validated fleet management edits. Other operational edits follow native game permissions. **Company Recharter and company identity restoration remain host-only.** See the [multiplayer guide](USER_GUIDE.md#multiplayer-access).

## Compatibility and limits

The build targets Railroader **2025.1.0b**. Compatibility with the forthcoming MOW update has not been established. Scrapalachia and Lego's Used Locomotive Market are optional integrations, not required dependencies.

Train calculations are estimates; the Train Graph is a timetable view and does not predict collisions or automate dispatch. See [known limits](SUPPORT.md#known-limits).

This repository provides mod downloads and player documentation.
