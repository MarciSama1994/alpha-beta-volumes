# Alpha & Beta Volumes

A Fabric mod for Minecraft that removes every music track added since the original
Alpha/Beta days and restores C418's **Minecraft - Volume Alpha** and
**Minecraft - Volume Beta** as the game's only background music.

## What it does

Minecraft's background music is driven by `assets/minecraft/sounds.json`, which maps
"music events" (overworld, each cave/biome variant, nether, underwater, menu, etc.) to a
pool of tracks the game picks from at random. This mod ships a replacement
`sounds.json` that overrides every one of those pools so they only draw from the
original C418 tracks:

- **Overworld / all biomes / caves:** Key, Subwoofer Lullaby, Living Mice, Haggstrom,
  Minecraft, Oxygène, Mice on Venus, Dry Hands, Wet Hands, Clark, Sweden, Danny
- **Nether (all sub-biomes):** Ballad of the Cats, Concrete Halls, Dead Voxel, Warmth
- **Main menu:** Beginning 2, Floating Trees, Moog City 2, Mutation
- **Underwater:** same classic pool as the overworld (the original game had no
  separate underwater music, that was added later, in Update Aquatic)

The credits theme (Alpha), the End theme (The End), the dragon fight theme (Boss),
and the Creative-mode pool (Aria Math, Biome Fest, Blind Spots, Dreiton, Haunt Muskie,
Taswell) were already 100% classic C418 tracks in vanilla, so those are left alone.

**Not touched:** jukebox discs (Cat, 13, Otherside, Pigstep, etc.), those are
player-placed items, not the automatic background soundtrack, so they still work
exactly as normal.

## How it works technically

This is a **pure resource-pack mod**, it contains no compiled Java code, just a
`fabric.mod.json` (so Fabric Loader recognizes it as a mod and auto-applies its
`assets` folder as a resource pack) and the overridden `sounds.json`. Because there's
no code, it doesn't need Fabric API, Minecraft mappings, or a build toolchain to
produce, the "build" step is just zipping the folder into a `.jar`.

## Installation

1. Install [Fabric Loader](https://fabricmc.net/use/) for your Minecraft version
   (Fabric API is *not* required for this mod).
2. Drop `alpha-beta-volumes-1.0.0.jar` into your `.minecraft/mods` folder (or your
   modpack's `mods` folder).
3. Launch the game.

Tested against the current Minecraft version's asset layout (26.2 at time of
writing). Since it's plain JSON with no version-specific code, it should keep
working on new versions unless a future update renames these files or event keys,
if a new Minecraft release breaks it, the fix is just regenerating `sounds.json`
from that version's assets, no coding required.

## Rebuilding / editing

The whole mod is just this folder. To change the track selection, edit
`assets/minecraft/sounds.json` directly (each event has a `"sounds"` array of
`{"name": "music/game/<track>", "stream": true}` entries, add or remove entries,
keep `"replace": true` so it fully overrides vanilla's list instead of merging with
it), then re-zip:

```
jar cf alpha-beta-volumes-1.0.0.jar fabric.mod.json assets
```

(or just select the `fabric.mod.json` file and `assets` folder and "compress to zip",
then rename the `.zip` to `.jar`)
