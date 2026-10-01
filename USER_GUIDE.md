# BMR Fleet Manager user guide

Fleet Manager expands Railroader's equipment tools with fleet search, numbering, saved groups, destination assignments, CSV exports and a local web interface.

**Version 0.21.3.** This guide covers installation, fleet tools, the local web interface, multiplayer access and local files.

[Downloads](https://github.com/BMR-Modding/BMR-Fleet-Manager-Releases/releases) | [Help and bug reports](SUPPORT.md) | [Release notes](CHANGELOG.md)

## Install or update

Requires **Railroader 2025.1 and Unity Mod Manager**. The current build targets the installed 2025.1.0b game API. Compatibility with the forthcoming MOW update has not been established.

1. Close Railroader.
2. Remove standalone **BMR Equipment Delivery** and the legacy **BMR Purchase Interchange** if installed. Delivery is included in Fleet Manager.
3. Install **BMR.FleetManager-0.21.3.zip** through UMM, replacing the previous Fleet Manager version.
4. Start the game and load a railroad. Open **Company > Equipment** and confirm **Fleet Manager 0.21.3**.
5. Reload any open Fleet Manager browser tabs after updating.

Existing saved rules and groups are retained. Exports and company logos are stored outside the mod installation folder. Keep a backup of an important save before changing equipment in bulk.

## Fleet tools in the game

Open **Company > Equipment**. **Open in own window** at the bottom opens a larger, resizable Fleet Manager window.

| Tab | What it does |
| --- | --- |
| Overview | Search equipment, filter by category, saved group and maintenance state, sort within categories, and inspect the selected vehicle. Native crew, freight Operations and passenger controls remain available. |
| Numbering | Select equipment and a number range, review the proposed identities, then Apply. Attached tenders follow their locomotive. Undo restores the last numbering operation while its expected state remains unchanged. |
| Rules | Save ranges for individual or grouped models, including models not yet owned. Enable **Use for new purchases** for automatic numbering of supported host purchases. |
| Groups | Save named sets of equipment, keep selections while filtering, and use groups across fleet tools. A vehicle can belong to several groups. |
| Destinations | Review bulk repair and sale assignments. Optional scrapping appears with supported Scrapalachia installed. |
| Export | Export the company fleet, choose separator and tender rows, open the export folder, or start the web interface. |

Selecting **Freight** reveals an additional car-type filter in Overview, Numbering, Rules, Groups and Destinations. Filters do not change saved equipment or narrow whole-fleet CSV exports.

Save a rule or group in its editor, then have the host save the game to retain it after reloading. Unsaved editor drafts are not exported as saved group membership. Number-range counts and overlap warnings help plan capacity; they do not reserve numbers or renumber equipment by themselves.

The regular equipment catalog includes **Deliver to**. Saved purchase rules support native host purchases, compatible Lego's Used Locomotive Market purchases and Sandbox placement. Previous-owner lettering is optional in the supported used market. Unsupported or unassigned models retain native numbering.

**Company Recharter** is under **Company > Settings > Advanced**. It previews company name/reporting-mark changes and optionally updates owned equipment carrying the old mark. **Company Recharter is always host-only.**

## Web interface

Use **UMM > BMR Fleet Manager > Open web interface**, or the button in the game's Export tab. Open **http://127.0.0.1:18766/** on the same PC as the game.

The sidebar provides:

- **Overview / Equipment register:** fleet totals, maintenance, search and filters, with separate Crew and Destination / Waybill columns. Distance travelled, total service distance and overhaul remaining are shown in miles or kilometres. The service odometer is used for maintenance and can differ from actual distance travelled; overdue overhauls are marked. The register remembers its unit choice.
- **Equipment groups / Numbering:** reviewed edits using the same existing tools as the game.
- **Destinations:** repair, sale, optional scrapping, and automatic **Load** and **Unload** waybill destinations.
- **Train calculator:** a captured consist, helper planning, traction estimates and a printable train sheet.
- **History / Undo:** recorded numbering and company identity changes, with reviewed restoration.
- **Timetables:** saved services, new-service creation and a printable Train Graph.
- **CSV export:** local files for spreadsheets and records.

Bulk numbering applies the reviewed identities immediately. Vehicle lettering/models refresh gradually over the following frames to avoid repeated model teardown during temporary numbering; allow that visual refresh to finish.

The browser shows a snapshot. Use **Refresh from game** after game changes. Review an edit before confirming it; stale selections, changed data or lost permissions can require another preview. The host must save shared changes in the game.

For fuel, repair parts and captive freight, choose the automatic Load or Unload mode, select company-owned freight cars, then **Find eligible destinations**. Locations must accept every selected car under the game's freight, contract and progression rules. **None** clears only the chosen automatic destination. Existing active waybills and the other automatic destination are preserved; the game creates a missing bill when appropriate. Repair replaces an overhaul instruction with routine repair. Sale and scrapping replace active waybills. Bulk destination changes have no Undo.

Use **Dark mode** beside Refresh to switch the dashboard theme. The browser remembers the choice; printed train sheets use a light background.

Use **Add company logo** below the railroad name to upload a PNG, JPEG or WebP up to 10 MB. Review and save the image. Logos are stored locally per railroad, preserve their proportions, and can be replaced or removed. They are not uploaded to a cloud service.

### Train calculator

Select a company locomotive to read its coupled train, including foreign rolling stock. The selected engine's native control/MU group supplies the initial active traction. Independent helpers can be added explicitly, either already coupled or planned at the rear; their linked tenders are included without counting any vehicle twice.

Choose a grade, running speed and traction reserve. The calculator displays **starting from standstill** and **maintaining speed** separately, plus gross/trailing weight, engine/tender/car counts, length and tractive effort. Unavailable engines contribute weight without usable traction.

**US Imperial** is the default: lb of force, short tons (2,000 lb), feet and mph. **Metric** uses kN, tonnes, metres and km/h. The choice is remembered and applies to calculations, the grade table and the printed sheet.

Planned helpers add their weight and power to the estimate without adding other cars coupled to them. Selecting helpers does not couple equipment, enable MU or operate their controls. Read the train again after changing its consist.

Enter train details and use **Print / Save PDF** for the consist sheet and grade/weight table. Estimates are not braking or coupler limits, and do not predict sustained steam production. Recheck after changing the train or operating conditions.

### History / Undo

The web **History / Undo** page lists the newest 100 recorded numbering and Company Recharter operations for this save. Officers and Presidents read the host's history; the host reads its local history. Expand an entry to see its before/after values, choose **Review restoration**, then apply the reviewed change.

History survives restarting the game. Equipment restoration is available to the host, Officer and President, and requires the affected equipment to retain its recorded identity, model, ownership and tender relationship. Conflicting numbers, unavailable cars, changed company details or changes since review stop the restoration. **Recharter restoration remains host-only** and also refuses to remark newly acquired vehicles. A completed restoration becomes another history entry; failed or unconfirmed operations cannot be restored.

The existing in-game **Undo last change** remains available for the last numbering operation in that session. History begins with changes recorded by Fleet Manager; earlier unrecorded changes are not reconstructed. It covers numbering and company identity, not groups, rules, destinations, automatic purchases or timetables. Save the game after applying or restoring a change.

Records are stored under `BMR.FleetManager/<save name>/History` in the game's LocalLow folder. Save As copies the existing local files; later changes remain separate for each save, even when their saved railroad IDs match. Every restoration still checks the current values. History and recovery records are not save backups.

### Timetables and Train Graph

Enable **Timetables** in **Company > Settings > Features**, then open **Timetables** in the browser. The list reads the complete saved timetable, including stations currently hidden by progression. It shows train symbol, direction, class/type, arrivals, departures and meets.

To add a service as host, Officer or President:

1. Select **Add service**, enter a unique train symbol, direction, class and Passenger/Freight type.
2. Select at least two available stations. The form follows the game's travel order.
3. Give the first timed stop an absolute time such as `08:00`. Later times can be absolute or relative, such as `+10` minutes or `+00:10`. Arrival is optional; departure is required. Meets accept comma-separated train symbols.
4. Choose **Review new service**. **View draft on graph** shows the unapplied service as a dotted line; choose Review again to return to the confirmation.
5. Apply, then save the game. Existing services and source comments are retained. Apply or discard any unsaved native timetable-editor draft first.

Native permissions, branch rules, source, station availability and the loaded railroad are checked before applying. An invalid existing timetable must be corrected in the game. Timetable recovery files contain the before/after source under `BMR.FleetManager/<save name>/TimetableRecovery`; there is no timetable Undo button in this version.

Switch **View** to **Train Graph** for time horizontally and stations vertically. Filter by route, train type or symbol; change the time window, zoom or pan, and select a line or timed point for details. Horizontal sections show station dwell. D+1 labels identify an inferred crossing of midnight; daily game times have no calendar date.

Graph station spacing is schematic, with separate branch panels. Solid lines are passenger services, dashed lines freight, and dotted lines unapplied drafts. Lines between timed points are interpolation. Crossings are planned schedule overlaps, not signalling, track-capacity or collision checks. **Print / Save PDF** uses a light background, time-window sheets and repeated station labels; long routes split into overlapping station sections.

Adding a service does not assign a crew. Passenger crews retain the game's timetable behavior; this does not automate freight dispatch. Editing/deleting existing services and live train positions are not included.

## Multiplayer access

Install **0.21.3 on both the host and participating clients**. Each player runs Fleet Manager and, if wanted, its local browser interface on their own game PC. Operations use that player's native game permissions, including applicable crew restrictions; Fleet Manager does not grant a higher role.

| Feature | Current access |
| --- | --- |
| Fleet browsing, train calculations and manual local CSV exports | Available to connected clients. The host must open Fleet Manager web or export once to create the shared export identity, then save the railroad. |
| Freight Operations, automatic waybills and passenger stops | Native property/message permissions are checked before changes. |
| Bulk repair, sale, automatic Load/Unload and optional scrap destination assignments | Every selected car must pass native permission and state checks at preview and application. |
| Bulk numbering/Undo and saved group/rule edits | Host, Officer and President. Client changes are validated and applied by the host. |
| Timetable reading / additions | Clients may read; host, Officer and President may add services after host-side native validation. |
| History restoration | Host, Officer and President for equipment; company identity restoration remains host-only. |
| Company Recharter | **Host-only by design.** |
| Automatic purchase numbering, custom delivery routing and automatic CSV triggers | Host-side features. |

Permissions can change during a session. Reopen or refresh controls after a role change; an already-open control cannot apply an edit after access is revoked. An allowed local request still travels through the game's normal multiplayer validation.

Shared bulk tools wait for the host to acknowledge the matching Fleet Manager version. The host checks the authenticated connection and current Officer/President role, validates changes and rejects stale previews. A request is never automatically repeated after a timeout: refresh and inspect the result before trying again. The host saves all shared changes.

This update covers fleet numbering, rules, groups, timetable additions and equipment history restoration. Catalog delivery selection, optional used-market lettering and automatic purchase/export processing remain host-side; this handler does not forward purchase transactions.

Live host/client synchronization, role changes and save/reload still need validation. See [known limits](SUPPORT.md#known-limits).

## CSV exports and UMM settings

Fleet Manager stores local files together under the actual game save name:

```text
%USERPROFILE%\AppData\LocalLow\Giraffe Lab LLC\Railroader\BMR.FleetManager\<save name>
```

Each save folder contains **Exports**, **History**, **Rules**, **TimetableRecovery**, **WebLogos** and **Recovery**, plus a small ownership file. CSVs are directly under Exports. Company renaming keeps the save folder unchanged. Autosaves use the parent save name. A successful **Save As** copies existing local files to the new name and keeps future writes separate; existing destination files are preserved. Use **Copy file path** to update spreadsheet connections after migration or Save As.

Invalid filename characters are replaced; long names are shortened. A short ID suffix resolves collisions with another save or pre-existing folder. Unsaved railroads use an Unsaved folder until first save. Multiplayer clients cannot read the host's local save filename, so their local exports/logos use a separate Multiplayer folder keyed to the railroad; shared history requests still use the host's save.

On first access, matching old history, latest CSVs and logos are copied into the save folder. Original files remain available. Older shared Rules, TimetableRecovery and mod-installation Recovery files have no reliable save identifier and remain at their original paths. **Open old shared rules** opens the previous Rules folder; copy wanted JSON files into the current save's Rules folder to use them. Moving local files does not modify the game save.

Exports include all retained company equipment, with off-railroad equipment flagged. Separate tenders are optional; locomotive rows retain their linked tender ID. Choose comma or semicolon separators. Each export replaces the corresponding latest file, so spreadsheet queries can refresh from the same path. Identity columns should be imported as text to retain leading zeroes.

UMM options include:

- Show/hide group controls in vehicle inspection Operations.
- Auto-start the web interface, with a separate option to open the browser.
- Automatic CSV export on a 1–120 real-time-minute timer, after successful game saves, or on normal exit. These host-side triggers are off initially and use the shared CSV options.
- Optional timing logs for investigating Rules-tab performance.

Click **Save** in UMM to retain settings. Automatic exports do not save the game or create an export history. A first export performed only on exit cannot retain a newly created export ID without a later game save.

## Help and bug reports

For a bug report, include Fleet Manager and game versions, host/client role, steps to reproduce, the expected result and Player.log. The log folder is:

```text
%USERPROFILE%\AppData\LocalLow\Giraffe Lab LLC\Railroader
```

See [SUPPORT.md](SUPPORT.md) for troubleshooting and known limits, or [report an issue](https://github.com/BMR-Modding/BMR-Fleet-Manager-Releases/issues).
