# Help and bug reports

## Quick checks

- Confirm Fleet Manager **0.21.3** in **Company > Equipment** and Unity Mod Manager.
- After an update, reload the browser tab and use **Refresh from game**. The dashboard displays a snapshot.
- If the web page does not open, start it in UMM or the Export tab and use **http://127.0.0.1:18766/** on the game PC.
- If an edit is rejected, refresh and review it again. Equipment state, permissions or the loaded railroad may have changed.
- In multiplayer, check matching mod versions on host and clients. Officers/Presidents need host acknowledgement before shared bulk edits. If a request times out, inspect the result before retrying; it is not automatically repeated.
- Save the game after shared changes. Fleet Manager's local files, history and CSV exports do not save the game.

## Known limits

- The build targets Railroader **2025.1.0b**. MOW compatibility has not been established.
- Single-player bulk numbering, browser History/Undo, in-game Undo and the save-folder workflow have been confirmed in game. Live multiplayer synchronization, role changes and save/reload still need validation.
- History covers numbering and company identity. Destination, group, rule, purchase and timetable edits have no history restoration in this version.
- Timetables can be read and new services added. Editing/deleting existing services and live train positions are not included. Adding a service does not assign a crew.
- The Train Graph uses schematic station spacing. Intersections show planned schedule overlaps, not collision or track-capacity predictions.
- Traction calculations are estimates. Steam estimates use current boiler pressure and do not predict sustained steam production; they are not braking or coupler limits.
- Detailed Save As, autosave, file-access failure and multiplayer edge cases have not all been separately checked in game. Keep an important save backed up before bulk edits.

## Report a problem

[Open a bug report](https://github.com/BMR-Modding/BMR-Fleet-Manager-Releases/issues/new?template=bug_report.yml) and include:

- Fleet Manager, Railroader and Unity Mod Manager versions.
- Single-player or multiplayer, host/client and role.
- Steps to reproduce, the expected result and what happened.
- Other relevant mods, plus a screenshot if useful.
- **Player.log**, captured after the problem and before restarting the game.

Find Player.log by pasting this folder into Windows Explorer:

```text
%USERPROFILE%\AppData\LocalLow\Giraffe Lab LLC\Railroader
```

Logs can contain local paths, player names and session details. Review them before attaching them to a public issue.

## Local files

Fleet Manager stores each host save's exports, rules, history, logos and recovery files under:

```text
%USERPROFILE%\AppData\LocalLow\Giraffe Lab LLC\Railroader\BMR.FleetManager\<save name>
```

Autosaves use the parent save's folder. Save As copies local data forward and separates later changes. Multiplayer clients use a local Multiplayer fallback because the host's save filename is not available. The [user guide](USER_GUIDE.md#csv-exports-and-umm-settings) explains migration and spreadsheet paths.

## Verify a download

The release includes a SHA-256 checksum beside the installation ZIP. In PowerShell, run this from the download folder and compare the Hash with the checksum file:

```powershell
Get-FileHash -LiteralPath '.\BMR.FleetManager-0.21.3.zip' -Algorithm SHA256
```
