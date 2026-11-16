# Nex Machina Hidden Weapons

Two special weapons, the **Shotgun** and the **Tag Weapon**, are still inside Nex Machina (Housemarque, 2017, Steam v1.05) but never drop in normal play.

Found by CubicCanvas. Notes only: no game files, no patched exe, no assets are in this repo.

## What is there

- Both are defined in the weapon config next to the Rocket Launcher, with full stats and effects.
- The game code has pickup types for both (token ids: Shotgun 0x10, Tag Weapon 0x12; for comparison Powershot 0x0e, Rocket Launcher 0x0f, Smartbomb 0x11, Sword 0x0d, Bomberman 0x13, Beam 0x14).
- The random special-weapon drop list has six slots, all other weapons. The Shotgun and Tag Weapon are in none of them.
- No achievement, guide, forum or trophy list that I could find mentions either weapon, so they look like content cut before release.

## Making them drop (offline test copy only)

The drop list is a table of six bytes in the exe. In v1.05 it sits at file offset `0x8b72e0` and reads:

    13 14 0e 0f 11 0d      (Bomberman, Beam, Powershot, Rocket, Smartbomb, Sword)

Changing the last two entries to the new ids makes the cut weapons drop:

    13 14 0e 0f 10 12      (Smartbomb -> Shotgun, Sword -> Tag Weapon)

Same length, one table, nothing else touched. Both weapons pick up, fire and play normally; the author beat the game with them and found both great.

## Rules I followed

- Do this on a copy of the game folder, never the Steam install.
- Offline play only. Not for Online Arena or leaderboards.
- Back up your save first.
- Please do not share patched exes or game files.

## Questions

Has anyone seen either weapon in a real match, or heard anything from the developers? Open an issue.

Steam forum thread: https://steamcommunity.com/app/404540/discussions/0/738188080312401277/
