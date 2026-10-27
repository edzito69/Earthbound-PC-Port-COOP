# EarthBound PC Port COOP - Version 3.6

**Platforms:** Windows • Linux • MACOS VERSION NOT WORKING  
**Latest Update:** October 26, 2026  


⚠️ ATENTION ⚠️ I'm sorry if you had a issue trying to open the new executable! The problem was I misspelled "Rom" as "Room". I've corrected the folder's name and the whole process of using the rom mas broken. So... just add one "o" on the folder's name "Coloque sua Rom aqui", so it goes "Coloque sua Room aqui". Yeah, that's stupid.
But you can normally download the complete repository now and it works because I left the mispronounce as a feature. ;)
(soon I'll fix this, I'm very tired right now. and ashamed.)

well

HAVE FUN!

## What's New — Version 3.6

### Added Features

- **Automatic Saves:** A dedicated autosave slot is available in each drawer under `F1/F2 → Saves`. Autosaves trigger when changing towns, passing through doors, and winning battles, after transitions finish.

- **Simultaneous Battle Commands:** P1 and Mess can select their actions simultaneously in adjacent native battle menus. Actions execute once both players finish selecting, preserving the original targeting, item, and turn rules. Save states also retain selections in progress.

- **Mouse-Controlled P2:** With co-op enabled, double-click the right mouse button to request control of Player 2. The keyboard and unassigned controllers remain assigned to Player 1.

- **Independent Exploration:** Optional support for players exploring separate rooms independently.

- **Photo Pose Shortcut:** Press the bottom face button + `R1/RB` to perform a photo pose in the overworld.

- **Support Monkey:** An optional cosmetic companion for P1, available under `F1 → Gameplay`. Disabled by default and independent of the story companion.

- **God Menu Teleportation:** Teleport destinations now include towns, pizzerias, pharmacies, weapon shops, and other establishments. Teleportation preserves inventory and story progress.

---

##  Changes & Improvements

### Multiplayer & Gameplay

- Experimental co-op is now available in **all desktop editions**. Enable it under `F1 → Gameplay`. It is disabled by default.
- English is now the default language for both the game and F1/F2 menus. Portuguese remains available.
- The P2 join prompt appears directly over gameplay without opening F1.
- Both players perform the photo pose when P2 joins, accompanied by a cheerful sound effect without interrupting the music.
- Balanced and Exploration kits now provide weaker equipment and leave more inventory space.
- Mess receives equipment equivalent to P1's and a copy of half the eligible food/healing items in P1's active leader inventory, rounded down and limited by available space. P1 keeps the original items.
- Ordinary item pickups are shared between players. Quest items are not duplicated, and internal transfers do not create extra copies.
- Overflow item copies are sent to Escargo.
- Battle reward deposits credit both players with the same amount.
- Story progress is shared, allowing either player to continue without repeating completed quest dialogue.
- In co-op, a defeated player returns to the overworld with **15% HP**, while the other player can continue fighting. Single-player follows the Gameplay preference.
- Gameplay and co-op settings now apply immediately without requiring the Apply button.

---

##  Controls & Shortcuts

| Player | Input | Action |
|---|---|---|
| P1 | `T` (Keyboard) | Teleport to Player 2 |
| P1 | `L3` | Teleport to Player 2 |
| P2 | `L3` | Teleport to Player 1 |
| P2 | `R3` | Cycle through six clothing palettes |
| P2 | `Select` | Leave the co-op session |
| Both | `Triangle` | Display party HP/PP alongside money |
| Both | Bottom Face Button + `R1/RB` | Perform a photo pose |

### Additional Control Notes

- Teleportation waits for a safe moment outside battles and dialogue.
- `L3 + Triggers` remains reserved for zoom.
- P2's pajamas follow Ness's current appearance.
- Pressing P2's Select button leaves the session without opening F2 on release.

---

##  Saves & Distribution

- Distribution ZIP files **do not include ROMs, personal saves, or preferences**.
- Updating the game does not overwrite existing saves.
- Use `F1/F2 → Save States` to preserve both players' progress.
- Original telephone saves continue to store P1's campaign.
- Automatic saves are available, but this feature is still experimental.

---

##  Testing & Known Limitations

### Platform Testing

| Platform | Status |
|---|---|
| Windows | ✅ Built, executed, and tested |
| Linux | ⚠️ It works, but audio and effects are a little weird |
| macOS | ⚠️ Doesn't worked yet :/ |

**Important:**

- Co-op remains experimental.
- The entire campaign has not yet been fully validated.
- Some features may behave unexpectedly during extended gameplay.

---

## ⚠️ Known Bugs & Important Recommendations

**PLEASE READ BEFORE PLAYING CO-OP!**

This is an experimental project, and some bugs are still being investigated and fixed.

###  1. Save Frequently!

**Use save states, rewind, and quick saves regularly!**

A new autosave feature has been introduced, but the Windows implementation is currently somewhat buggy. It appears to work, although reliability is not yet guaranteed. ;)

For now, manual save states are strongly recommended!

###  2. Boss Battles in Co-op

When fighting a boss with two players:

- **Let Player 1 initiate the battle.**
- **Make sure BOTH players are in the SAME ROOM before starting the fight.**

This is a precaution to avoid unexpected behavior during boss encounters.

###  3. Independent Exploration & Rendering Issues

Version 3.6 introduces an experimental feature allowing both players to explore different rooms independently.

However, when players are far apart, the game must handle **two separate overworld environments**.

This can occasionally cause issues with rendering:

- Enemies
- NPCs
- Interactive objects
- Other overworld elements

These issues are related to the new independent exploration system and are still being worked on.

**If you experience rendering problems, you can disable COOP/Independent Exploration in the Gameplay Menu**

Doing!
