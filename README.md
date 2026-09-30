# Moor Mushroom Launch v1.0.0

By **Miker and ChatGPT/Codex**. Requires Bingus Shared Loader v15 or newer / API 1.

Brings back a stronger mushroom launch with **55 stagger and 55 push** by default,
up from the captured **25 stagger / 15 push**. These defaults were verified in-game
by Miker. Damage remains 5/5; penetration, demolition, status effects and explosion
radii are unchanged. This recreates a stronger launch, not a guaranteed exact
historical physics behavior or fixed travel distance.

## Shared explosion profile

The mushroom burst shares damage record 485 with explosion 312, consistent with
the older Illuminate power-node entry. **That explosion receives the same stagger
and push changes.** This mod is not mushroom-exclusive. The smoke and separate
damage profile 486 are not modified.

## Installation and upgrading

1. Close the game and replace the test package with this ZIP.
2. Disable the mushroom probe and other mods editing the same damage record.
3. Enable this mod alongside Bingus Shared Loader, then **Purge / Deploy**.
4. Launch and wait for APPLIED or DONE in the status file below.

The release retains the test version's mod identity. The scan runs once and stops
when finished. It does not continually enforce values during gameplay.

## Configuration

First launch creates:

```text
%LOCALAPPDATA%\CowboyBingus\Helldivers2\MoorMushroomLaunch\settings.ini
```

```ini
enabled=1
stagger=55
push=55
```

- `enabled`: 1 enables the patch; 0 disables it on the next fresh game launch.
- `stagger`: hit-reaction strength. Captured stock 25; tested default 55.
- `push`: launch impulse. Captured stock 15; tested default 55. Higher values may
  launch targets farther, but distance depends on the game's physics and position.

Stagger and push accept whole numbers from 0 to 1000. These are validation limits,
not gameplay-tested ranges. Only the 55/55 preset has been verified in-game.
Use 25/15 to retain the captured stock values. Close the game before editing,
save, then restart. **No rebuild or redeploy is needed for INI edits.** Existing
settings are preserved. Invalid values or duplicate keys stop the patch and
report a configuration error. Do not add duplicate lines.

## Status and troubleshooting

```text
%LOCALAPPDATA%\CowboyBingus\Helldivers2\MoorMushroomLaunch\STATUS.txt
```

APPLIED/DONE reports the chosen settings. NO MATCH means the matching record was
not found or did not match its expected fingerprint. Send STATUS.txt if needed.
Game updates or mods altering this same record can cause refusal. Writes are
verified; failures trigger an attempt to restore the original record. The scan
does not automatically reapply changes if the game reloads its tables later.

To uninstall, disable the mod, Purge / Deploy and restart. The Lua changes exist
only in process memory; it does not edit saves. Optional settings files remain.

## Source and rebuilding

Editable Lua and a rebuild script are in Source. With Python 3 and a
BingusSharedLoader source checkout:

```text
python Source/build.py "path/to/BingusSharedLoader"
```

The builder writes the ZIP beside Source. No captures or tests are in the release.

## Credits

- **Miker** — concept, captures and in-game testing.
- **ChatGPT/Codex** — implementation, configuration and offline checks.
- CowboyBingus — Bingus Shared Loader and addon packaging tools.
- shalzuth/HelldiversData and Darctor's Helldivers2 RawData — reference data.
- Helldivers Wiki — the provided statistics.
- Original supplied M6C addon — memory-reader reference used in earlier experiments.

## Version 1.0.0

Publishable release retaining the tested 55/55 defaults, with independent INI
controls for stagger and push. Configurable values and failure rollback passed
offline checks against the live capture; custom presets need gameplay testing.

If you enjoy my mods and would like to support my work, consider buying me a coffee on Ko-fi! Any support is greatly appreciated, but all my mods will remain completely free. [❤️](https://cdn.jsdelivr.net/joypixels/assets/8.0/png/unicode/64/2764.png)
[https://ko-fi.com/mikerbiker](https://ko-fi.com/mikerbiker)
