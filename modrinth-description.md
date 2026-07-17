# Alpha & Beta Volumes

Ever miss the days when Minecraft only had *Sweden*, *Wet Hands*, and *Living Mice*?
This mod strips out every music track added since the original Alpha/Beta era and
brings back C418's **Minecraft - Volume Alpha** and **Minecraft - Volume Beta** as
the only background music in the game.

## What it does

Minecraft's background music is controlled by a set of "music events" — one for the
overworld, one for each individual biome and cave type, one for each Nether biome,
one for underwater, one for the main menu, and so on. Since the early days, Mojang
has kept adding new tracks into these pools (Nether Update, Caves & Cliffs, the Wild
Update, Trails & Tales, Tricky Trials, and beyond), so the classic C418 tracks now
only play occasionally, mixed in with dozens of newer ones.

This mod overrides every one of those pools so they *only* draw from the original
soundtrack:

- **Overworld, every biome, every cave type:** Key, Subwoofer Lullaby, Living Mice,
  Haggstrom, Minecraft, Oxygène, Mice on Venus, Dry Hands, Wet Hands, Clark, Sweden,
  Danny
- **The Nether (all sub-biomes):** Ballad of the Cats, Concrete Halls, Dead Voxel,
  Warmth
- **Main menu:** Beginning 2, Floating Trees, Moog City 2, Mutation
- **Underwater:** the same classic overworld pool (the original game had no separate
  underwater music — that was only added in Update Aquatic)

The credits theme, the End theme, the Ender Dragon fight theme, and the Creative-mode
music were already 100% classic C418 tracks in vanilla, so those are untouched.

**Jukebox discs are not affected** — Cat, 13, Otherside, Pigstep, and the rest still
work exactly as normal, since those are player-placed items rather than automatic
background music.

## Compatibility

- Requires **Fabric Loader** only — no Fabric API dependency.
- Client-side only. Safe to use on servers (it simply won't do anything server-side),
  and doesn't need to be installed on a server for singleplayer/LAN use.
- Pure data/resource override — no mixins, no compiled game code — so it's very
  unlikely to conflict with other mods.
- Works alongside resource packs and other music/sound mods, though the *last*
  loaded resource-pack-style override for a given sound event wins if something else
  also touches `music.*` events.

## A note on assets

This mod doesn't bundle or redistribute any copyrighted audio. It only edits
`sounds.json` to reference the classic tracks that already ship inside every
official Minecraft client install — the same files Mojang has kept bundled since
those songs were composed. No new audio is added, and no vanilla files are removed
or replaced on disk.

## Credits

All music by **C418**, originally released as *Minecraft - Volume Alpha* (2011) and
*Minecraft - Volume Beta* (2013). This mod does not claim any ownership of the
music — it just changes which of Mojang's own bundled tracks get selected during
gameplay.
