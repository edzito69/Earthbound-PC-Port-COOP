# Version 3.7 — Desktop Fixes & Improvements

October 27, 2026 — Windows, Linux and macOS

## Experimental co-op

- Revised nearby enemy synchronization across separate player contexts and ongoing encounters.
- Added shared defeated-enemy tracking to prevent counterparts from continuing to chase players after victory.
- Restricted scripted boss initiation to P1; P2 can approach and join.
- Fixed missing command panels in boss graphics modes.
- Revised teleport requests so a free player can teleport to the battling player and join through the shared battle system.
- Improved recognition of players returning to the same area after independent exploration.
- Removed double-right-click assignment of the mouse to P2.

## Movement and presentation

- Fixed automatic movement playback in co-op, addressing stair sequences that could leave characters walking indefinitely.
- Tested both players ascending and descending the Summers stairs.
- Revised native photo-pose rendering for saving, joining co-op and the pose shortcut.
- Applied P2's selected pajama colors to Ness while the matching pajama appearance is active.
- Revised music-state handling when switching player contexts.

## Saves, settings and packaging

- Added three rotating autosaves per drawer, with location checks and throttling to reduce repeated doorway saves.
- Made the autosave row accessible by navigating downward in F1/F2.
- Moved co-op to the top of Gameplay, with independent exploration directly below it.
- Added optional Double XP, disabled by default, for battle rewards and instant victories.
- Updated desktop in-game labels, Windows properties and macOS bundle metadata to version 3.7.
- Renamed the ROM directory to `Put your rom here - Coloque sua rom aqui`, retaining support for earlier names.
- Expanded English/Portuguese attribution and retained original third-party notices.

## Testing and known issues

- Windows cooperative regression tests and five cold-launch state cases passed.
- A scripted boss encounter passed with P2 joining by teleport, both command panels present and shared turn selection working.
- Linux/macOS builds were compiled and inspected; these latest changes were not executed locally on those operating systems.
- The full campaign and every staircase have not been exhaustively validated.
- Deep Darkness edge/canopy rendering and broader dungeon-music continuity remain under investigation.
- The reported Linux audio differences and macOS startup problem are **not confirmed resolved**.
- Co-op remains experimental. Keep backup copies of important saves.

Android has its own version and distribution; this is the desktop 3.7 release.
