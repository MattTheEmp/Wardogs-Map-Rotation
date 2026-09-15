# Wardog Rotation Builder

A single-file HTML tool for building `.RotationEntries=` config lines for the game **Wardog** — no install, no server, just open it in a browser.

## Usage

Open [`wardog_map_rotation.html`](wardog_map_rotation.html) in any browser (double-click the file, or open it from GitHub via [raw.githack.com](https://raw.githack.com/MattTheEmp/Wardogs-Map-Rotation/main/wardog_map_rotation.html)).

### Builder tab

1. Pick a **Map**, toggle **Infantry Only** / **Hardcore**, set **Time of Day** and **Control Zone**.
2. Click **Add to Rotation** — the entry appears in the manifest on the right.
3. Click **Copy Config Block** to copy the generated lines.

### Bulk Generate tab

Check off multiple maps, times of day, zones (per map), and modifier combinations, then click **Generate All Combinations** to add every resulting entry to the manifest at once.

### Options tab

Edit the Map / Time of Day / Control Zone lists directly — add, rename, or remove entries. Changes are saved to that browser's local storage.

## Output format

Entries are grouped by map, then by game mode, with a blank line between map groups:

```
// Bakurani
// KOTH
.RotationEntries=(Map="Kavkazi",Experience="Bakurani_KOTH_01",Lighting="DayClear",ZoneAlternator="ZoneAlternator.Bakurani.Default.Circle")
// KOTH Infantry Only
.RotationEntries=(Map="Kavkazi",Experiences="Bakurani_KOTH_01+KOTH_InfantryOnly",Lighting="DayClear",ZoneAlternator="ZoneAlternator.Bakurani.Farmland.Circle")

// Ozeti
// KOTH
.RotationEntries=(Map="Europe",Experience="Ozeti_KOTH_01",Lighting="DayEarlyFog",ZoneAlternator="ZoneAlternator.Ozeti.Church.Circle")
```

The `Experience` field is singular with no modifiers, and `Experiences` (modifiers joined with `+`) when one or more are added.

See [CHANGELOG.md](CHANGELOG.md) for version history.
