# Changelog

All notable changes to the Wardog Rotation Builder.

## 2026-09-15

- Fixed map/experience-prefix mismatch: the `Experience`/`Experiences` value now uses each map's own game-mode prefix (e.g. Europe's is `Madrid`, NorthAmerica's is `Detroit`) instead of assuming it always matches the app-side map name. Each map now has three editable fields in the Options tab: app name, config value, and experience prefix.

## 2026-09-14

- Config output now groups entries: a `// <Map>` comment per map, a `// <Game Mode>` comment per modifier variant within it, and a blank line between map groups.
- Modifiers are now joined into one string with `+` (e.g. `Experiences="Bakurani_KOTH_01+KOTH_InfantryOnly"`); the field is `Experience` (singular) with no modifiers and `Experiences` (plural) with one or more.
- Each line is prefixed `.RotationEntries=` and fields are written with no space after commas, matching the game's own config style.
- Added a **Bulk Generate** tab: check maps, times of day, zone options (per map), and modifier combinations (including Infantry Only + Hardcore together), then generate every combination as separate entries in one click.

## Earlier

- Added an **Options** tab to edit the Map / Time of Day / Control Zone option lists directly in the browser, saved to local storage.
- Removed the redundant "None" zone choice (Default already covers it).
- Rebuilt as a single-file HTML/JS tool (no install required) after the original Python/Tkinter version couldn't run in the user's local Python environment.
