EnemyEdit — Helldivers 2 Unit Replacement Mod (v0.1)

Replace every enemy that can spawn in a mission with whatever unit you want.

Supports four tabs: Terminids, Illuminate, Automatons, and Humans. Covers all combat units the spawn system can call in the current game build, including variants: Burst Terminids, Predator Terminids, Spore Terminids, Incendiary Corps, Jet Brigade, and the Cyborg line.

Requires Bingus Shared Loader v15 or newer.

Installation

1. Fully exit the game.
2. Import this zip with HD2 Mod Manager / Arsenal.
3. Deploy.
4. Launch the game.

Usage

Before each mission, it's not recommended to change or revert to default while inside a mission. I only tested that reverting to default still spawns the selected unit, plus some question marks spawning on the ground.

Press F9 to open/close the panel. It's a bit rough—an external window, hidden from the taskbar. Press it when you want to use it; if it doesn't show up, press it again. Sometimes if you forget to close it and don't know where it went, you just have to press it twice.

The top of the panel has four tabs: Terminids / Illuminate / Automatons / Humans. Click a tab to switch.

Scroll the list with the mouse wheel, click a row to select it. (Actually, the mouse cursor and the selected position are a bit offset. Too lazy to fix it—good enough if it works. You can also probably see from the highlight which row you're on.)

Click Apply. The bottom shows `[faction name] patched N/M -> unit name`, meaning it applied successfully.

To switch to another unit, select again and Apply.

To restore the original, click Default.

Click Close or press F9 again to close the window.

About this mod: I originally wanted to do a lot more. The first page would have the current version's features. The second page would have multi-enemy combination spawning with configurable weights and sub-weights. That seems to exist on Git, but I haven't used it and don't know how it performs. I planned to port it, but now I no longer plan to integrate that—it's too hard to deal with. The third page would be behavior patterns for specific units, plus plugins for part HP enhancements, with optional toggles and community share import/export. That's even more future stuff—not talking about it.

Based on what I figured out while making this mod:
Spawning should be: patrols, breaches / reinforcements, natives (or guards) split into objective guards, resource point guards, nest guards, active spawns inside nests (from bug holes, bot fabricators), enemy chain summons (e.g., commanders calling reinforcements, Terminid nests continuously spawning).

There's also a check in spawning: tags, entities, and a TaskUser that feels like some kind of unit classification within a faction—warrior, mage, etc. Component budget cap, total on-field component cap, and difficulty and what point it is: breach, patrol, guard, etc. It tries to spawn, and if it can't, it gets rejected and there are no enemies. (I actually had the idea to make a version where if it can't spawn, it just uses the original enemy, but I still didn't do it.)

For example, after applying this mod, natives will be attempted. If you switch to a Charger, resource points and small nests will have no initial enemies, lowering the difficulty. Like difficulty 1, there just won't be enemies, or you'll basically see no patrols.

Cases where it doesn't work or gives counterintuitive results (from my experience testing several missions with consecutive changes):

Using the Human tab to replace enemy unit spawning doesn't work. But the related human units, once spawned, are indeed the units I selected. (This probably specifically means SEAF units. I haven't tested what happens with the people coming out of the extraction door, by the way.)

In missions with special buffs, the replacement "follows the buff." For example, if the mission has the Incendiary Corps buff and you replace enemies with "Hulk," what actually spawns is "Incendiary Hulk" (the Incendiary version of Hulk), not a regular Hulk. This is the engine's own replacement logic.

Applying certain replacements on maps without the corresponding spawn environment may spawn no units at all, and may even cause lag or crashes. Two confirmed examples: applying Human replacements in an extermination mission without city / SEAF spawn conditions causes weird unit spawning; replacing a unit with an extremely high component cost like Hivelord causes an immediate freeze and crash.

Small resource point guards: in vanilla, these points only place the cheapest small enemies (Scavengers, etc.). When you replace them with a high-cost unit like a Charger, because the single-unit component cost exceeds the engine's total allowed budget for that spawn, the engine simply rejects the whole batch, resulting in zero spawns. Large nests natively place medium-weight units, so the budget is enough and the replacement succeeds. There's currently no good way to make the engine spawn high-cost units at small resource points.

Multiplayer notice

This mod was developed entirely in single-player. Host/client behavior in multiplayer is unknown.
I also urge all players: when using this mod, play as host. Don't be a client and affect others—that's a matter of character.
When hosting a public game, notify every player who joins. It's the host's duty when using a mod that affects the client's gameplay experience.
Premade squads are fine—nobody cares.

My previous mod was made exactly for this phenomenon, to make it easier to blacklist people on various levels.

Troubleshooting

Mod conflicts: Unknown. This mod has always been tested in a single-mod state, and I haven't used it together with multi-enemy mods.

Press F9 does nothing: Confirm Bingus Shared Loader is running (BingusSharedLoader.log has loader-v15 or newer, and API 1), and confirm this mod is `loaded` rather than `load failed` in the loader's Discovery list.

Panel opens but nothing changes in-mission after Apply: Try a lower-component-cost unit (Hunter, Warrior MK2, Scavenger MK2) and try again.

Crash during a mission: Force-quit the game and restart. Before entering the game, switch to a cheaper unit on the ship, or click Default to restore vanilla.

Log location: `%LOCALAPPDATA%\CowboyBingus\Helldivers2\Logs\`, where `enemyedit_log.txt` records the result of each Apply / Default.

Uninstall

Exit the game, disable / remove this mod in the manager, Deploy again, and restart the game. All replacements exist only in process memory. After disabling + restarting, everything returns to normal.

Version v0.1 — First release. Basic three-faction replacement + Human tab + Default restore. Variant units are already included in the four tabs.

The mods above that can be published are just ones I made because I got interested in this direction during this whole incident. I also have some personal-use mods that would basically get removed even from Git.

Due to life and work commitments, for mods whose features already do what I need, I probably won't provide any updates or maintenance fixes. So feel free to unpack and study them, so people after me can make even better mods.

For the development of this mod, thanks to Ayakamods @taffy- and the authors of the multi-enemy project on Git: NatsunXD, KurobaAyari, InnocentVillager. Although I didn't port the actual features, I copied the UI.

Lastly, thanks to all the open-source work out there for the learning experience, inspiration, and ideas. Thanks to DS.

Timestamp: Beijing Time, October 3, 2026, 15:05
