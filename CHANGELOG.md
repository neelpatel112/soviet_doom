# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).


## [0.12.1] - 2026-03-04

### Fixed
- Status bar flickering

## [0.12.0] - 2026-03-03

### Added
- Save/Load game
- Map geometry change interpolation
- Gun swing interpolation
- Cache map geometry for faster reload (100ms instead of seconds for large maps)
- Map progress (time, kill count, etc.) can be displayed in HUD

### Changed
- Changed default fly controls to period/comma to match DSDA Doom
- increase FOV min/max (just for fun)
- More DOOM-like light diminishing (linear fall off)
- 20-25% performance improvement through: simpler sprite state machine, animated walls/flats in shader, change line data structure
- use pixelated images as much as possible. Feels more like DOOM

### Fixed
- Sprite alignment on HUD. Elements from custom wads (HACX, PD2) are now positioned correctly
- BFG was not always hitting objects when player was close to ledge
- Initial position of decorations was not correct
- Do not loop music on wad launch screen
- Boom special lines: incorrect scrolling calculation, teleport repeat flag cleared too early
- Do not apply negative y-offsets from patches (fixes TEKWALL1 among others)
- Texture alignment in some maps
- Apply velocity when exiting pusher floors
- Fix line teleport exit angle

## [0.11.0] - 2026-01-22
This is a kind of large release. It's been brewing on and off (mostly off) for a year so this list may be incomplete.

### Added
- Home screen split into play/wads/setting.
- Home screen now has "recently played maps" section to help pickup progress (no save games support yet!)
- Play DOOM sound effects when navigating menus
- A crude wad explorer to show wad lumps and browse contents
- Keyboard shortcuts on most menus
- Several new config settings: status bar scale, monster height checks, stuck monsters,
- 2-click Freedoom installation for new users
- ENDOOM support
- Support for most BOOM lindefs (still missing some pushers, sky transfers, and friction) also MUSINFO
- Some light diminishing. We don't use COLORMAP so it's not accurate but it's still a visual improvement
- Playback ogg music in WADs
- Support for ["ghost" monsters](https://doomwiki.org/wiki/Ghost_monster)

### Changed
- Upgrade to Svelte 5 and Threlte 8.
- Voodoo dolls pick up items (they don't take damage or change view height though!)
- Mobile improvements: simpler controls, full screen menus, hud on top, nicer default settings

### Fixed
- Sound propagation bug (TNT)
- Arch-Vile no longer appears to move while resurrecting enemies
- Fix objects teleporting on top of each other
- Berserk now gives 100% health
- Prevent a crash when map didn't have par time
