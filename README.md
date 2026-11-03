# Controller Mod for S.T.A.L.K.E.R.: Shadow of Chernobyl

Shadow of Chernobyl STALKER original game's game controller native support mod

**Version 1.0** · for the GOG version of the original game (patch 1.0006, English) · Windows and Linux

Play the original *S.T.A.L.K.E.R.: Shadow of Chernobyl* on PC with a controller: moving and fighting, a
weapon wheel, and controller navigation of the menus, the inventory, looting, trading, the PDA (including
the map) and dialogues. The game's own button hints show the controller buttons, and the buttons for
playing can be changed in a simple text file.

The mod uses XInput, so it works with Xbox controllers and any controller the system presents as one (most
controllers under Steam or Proton; on Windows a PlayStation controller needs Steam Input or a tool like
DS4Windows).

## Contents

1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Controls: playing](#controls-playing)
4. [Controls: weapon wheel](#controls-weapon-wheel)
5. [Controls: menus](#controls-menus)
6. [Controls: inventory, looting and trading](#controls-inventory-looting-and-trading)
7. [Controls: PDA and map](#controls-pda-and-map)
8. [Controls: dialogues](#controls-dialogues)
9. [Settings in the game](#settings-in-the-game)
10. [Changing the buttons](#changing-the-buttons)
11. [Extra settings](#extra-settings)
12. [Problems and tips](#problems-and-tips)
13. [Sending feedback](#sending-feedback)
14. [Credits and license](#credits-and-license)

## Requirements

- **S.T.A.L.K.E.R.: Shadow of Chernobyl from GOG** (patch 1.0006, English). The mod works with fixed places
  in the game's memory, so it only works with this exact version. The installer checks the game files and
  warns you when they are different.
- **Not for the Enhanced Edition** ("Shadow of Chornobyl – Enhanced Edition"), which has its own controller
  support. The Steam version of the original has not been tested.
- Windows 10 or 11, or Linux with Wine / Proton (for example through Heroic, Steam or Lutris).

## Installation

There are two installers. Both show the same window: the game folder (found automatically, or chosen with
*Browse*), what is installed, and the buttons *Install* and *Uninstall*. Close the game before you use them.

| File | For |
|------|-----|
| `STALKER-SoC-Controller-Mod-1.0-Setup.exe` | Windows |
| `STALKER-SoC-Controller-Mod-1.0-Setup-Linux.x86_64` | Linux |

### Windows

1. Run `STALKER-SoC-Controller-Mod-1.0-Setup.exe`. Windows may warn that the program is unknown ("Windows
   protected your PC"): click *More info*, then *Run anyway*.
2. The installer finds the game (GOG Galaxy, the GOG installer, Steam or the usual folders). If it doesn't,
   click *Browse* and choose the game folder, the one that contains the `bin` folder.
3. Click *Install*. If the game is in a protected folder such as *Program Files*, the installer offers to
   start again as administrator.
4. Start the game as usual.

### Linux

1. Make the installer executable: right-click it → *Properties* → allow it to run as a program, or in a
   terminal:
   ```
   chmod +x STALKER-SoC-Controller-Mod-1.0-Setup-Linux.x86_64
   ```
2. Run it. It finds the game in Heroic (also the Flatpak version), Steam or Lutris, together with the game's
   Wine prefix. If it doesn't, choose the game folder and the Wine prefix (the folder with `drive_c` and
   `user.reg` in it) with the *Browse* buttons.
3. Click *Install*. Besides copying the files, this tells Wine to load the mod for this game: it sets
   `dinput8 = native,builtin` for `XR_3DA.exe` only, in that Wine prefix. Wine must not be running in the
   prefix at that moment: close the game and wait a few seconds.
4. Start the game as usual.

The installer needs GTK 3, which practically every Linux desktop has. Alternatively, run the Windows
installer inside the game's Wine prefix (Heroic: game settings → Wine → *Run EXE in prefix*; Lutris: *Run
EXE inside Wine prefix*). It then switches the mod on in that prefix by itself.

### What gets installed

| File (in the game folder) | Purpose |
|------|---------|
| `bin\dinput8.dll` | The mod |
| `gamedata\scripts\gamepad.script` | Item use, weapon wheel, aim assist |
| `gamedata\scripts\ui_mm_opt_controls.script`, `gamedata\config\ui\ui_mm_opt.xml` | The new entries in *Options → Controls* |
| `gamedata\scripts\ui_save_dialog.script` | Save names (no typing needed) |
| `gamedata\config\localization.ltx`, `gamedata\config\text\eng\ui_st_gamepad.xml` | Texts of the new options |
| `controller-mod-readme.txt` | This description |
| `controller-mod-install.txt` | The installer's list of files |

If another mod already has one of these files, the installer asks first, keeps a copy in the folder
`controller-mod-backup`, and puts it back when you uninstall.

At the first start the mod writes two files into the game folder, where you can change the buttons (see
[Changing the buttons](#changing-the-buttons)): `controller-gameplay-layout.txt` and
`controller-weapon-wheel.txt`.

### Updating

Run the installer of the new version and click *Update*. Your button layouts and wheel favourites stay.

### Uninstalling

Run the installer and click *Uninstall*. Your button layouts and wheel favourites stay, unless you tick
*Uninstall also deletes my button layouts and wheel favourites*. On Linux the Wine setting is removed as well.

## Controls: playing

These are the default buttons; [Changing the buttons](#changing-the-buttons) explains how to change them.

| Button | Action |
|--------|--------|
| Left stick | Move (push it a little to walk, fully to run) |
| Right stick | Look around |
| A | Jump |
| B (tap) | Crouch. When crouching (normal or low): stand up |
| B (double tap) | Low crouch. In the low crouch: back to the normal crouch |
| B (hold) | Grab the dead body under the crosshair and drag it along. Press B again to drop it |
| X (tap) | Reload. When aimed at a person, a body, a stash or a door: talk, search or open |
| X (hold) | Use / pick up (keeps picking up while held) |
| Y | [Weapon wheel](#controls-weapon-wheel) |
| LB | Aim / zoom |
| RB | Shoot |
| LT / RT | Lean left / right |
| LS (click) | Sprint. When crouching or dragging a body: stand up (dropping the body) and sprint |
| RS (click) | Flashlight |
| RS (double click) | Night vision (when your suit has it) |
| Back (tap) | Inventory |
| Back (hold) | PDA |
| Start | Menu |
| Back + Start | Quick save (hold Back and press Start, or press both at the same time) |
| D-pad | Favourite weapons (set in the weapon wheel). Pressing the arrow of the item already in your hands puts it away |
| D-pad down (hold) | Put away whatever is in your hands. With empty hands: take the last item out again |
| LB + D-pad up / down | Binoculars: zoom in / out (while aiming) |

Favourites at the start: up = primary weapon, down = grenades, left = knife, right = pistol.

Good to know:

- Crouching down with B comes at once. Standing up waits 0.3 seconds, in case a second tap (low crouch)
  follows. B only waits for a hold when a body is within reach under the crosshair.
- The flashlight comes 0.3 seconds after the click of the right stick, because the mod waits for a possible
  double click (night vision).
- As in the game itself, sprinting only works while moving forward.
- Holding Back longer than a quarter of a second opens the PDA.
- While grenades are in your hands, the wheel's *change ammo type* shortcut switches the grenade type.

## Controls: weapon wheel

The game pauses and darkens while the wheel is open. The wheel shows six places with pictures of your items;
the middle shows your medkits, bandages, anti-radiation drugs and energy drinks with the buttons that use
them.

Default places, clockwise from the top: knife, primary weapon, pistol, grenades, binoculars, bolts.

**Opening and closing**

| Button | Action |
|--------|--------|
| Hold Y | The wheel shows while Y is held. Letting go of Y closes it and takes out the highlighted item |
| Tap Y | The wheel stays open. A, B, X or Y close it and take out the highlighted item |

**Inside the wheel**

| Button | Action |
|--------|--------|
| Left stick | Highlight an option (the right stick works too) |
| A, B, X or Y | Close the wheel and take out the highlighted item |
| D-pad | Put the highlighted option on that arrow as a favourite (the arrow shows on the wheel) |
| RT | Use a medkit (the basic one first, then army, then scientific) |
| LS (click) | Use a bandage |
| LT | Use an anti-radiation drug |
| RS (click) | Drink an energy drink |
| LB | Change the ammo type (done when the wheel closes) |
| RB | Grenade launcher on / off (done when the wheel closes) |

- A stick that is already pushed when the wheel opens (because you were running or looking around) only
  chooses after you let go of it once.
- Start and Back don't open the menu, inventory or PDA while the wheel is open.
- Opened while moving, the wheel shows at once and the game pauses as soon as you have come to a stop
  (about a tenth of a second).

## Controls: menus

| Button | Action |
|--------|--------|
| D-pad or left stick | Move the highlight |
| A | Select / press |
| B | Back / close |
| LB / RB | Previous / next page (the tabs of the Options) |
| Left / right | On a slider: change the value |
| A, then D-pad, then A | Drop-down lists: open, choose, take the entry. B closes the list without a change |
| Start | In a window during the game: close it and go to the menu |

**Load game**

| Button | Action |
|--------|--------|
| A on a save | Select it; the highlight jumps to *Load*, so a second A loads it |
| Y on a save | Delete it (the game asks first, and the question starts on *No*) |

**Save game**

| Button | Action |
|--------|--------|
| A on a save | Take its name; the highlight jumps to *Save* |
| X | Save, wherever the highlight is (under the name in the name field). The game asks before it overwrites a save |
| Y on a save | Delete it (the game asks first) |

A save name is filled in for you, because a controller can't type.

- Questions (Yes / No) are answered with the D-pad and A.
- Intro videos: any button skips the current video.
- Keyboard and mouse keep working; moving the mouse brings the mouse cursor back.

## Controls: inventory, looting and trading

| Button | Action |
|--------|--------|
| D-pad | Move the highlight from item to item (its description and properties show right away) |
| A | Inventory: use or equip the item. Looting and trading: move it to the other side |
| A (hold) | Looting and trading: move the whole stack (all boxes of that ammo, all bandages, …) |
| X | Inventory and looting: the item's menu. Trading: make the deal |
| Y | Inventory and looting: drop the item |
| B | Close the item's menu or the window. Trading: back to the conversation |
| Back | Close the inventory |
| Right stick | Scroll the list of items |
| LT / RT | Scroll the item's description down / up |
| LS (click) | Weapon comparison (guns only), see below |
| Start | Menu |

After A the highlight stays in the list the item came from, on the item nearest to where it was.

**Weapon comparison:** press LS on a gun and a panel next to it shows its picture, accuracy, handling,
damage, rate of fire, condition, price and ammo. Move the highlight to another gun and the panel shows both
side by side (green is better, red is worse). LS again or B closes it.

## Controls: PDA and map

| Button | Action |
|--------|--------|
| LB / RB | Previous / next PDA section |
| D-pad | Move the highlight (tasks, objectives, the Active / Completed / Failed filters, texts) |
| A | Open or close an entry. On an objective: make it the active one (red mark); on a task: its first unfinished objective |
| Y | Show the task or objective on the map |
| X | Show the task's description instead of the map; X again goes back to the map (on another task, X shows that task's description) |
| Right stick | Scroll the list or the text (also the task description next to the list) |
| B or Back | Close the PDA |
| Start | Menu |

**The map** (the Map section and the map next to the tasks)

| Button | Action |
|--------|--------|
| Left stick | Move the round crosshair; the map scrolls under it, and at the edges of the map the crosshair moves to the edge |
| LT / RT | Zoom in / out |

On map pages the highlight appears once you use the D-pad; before that, A or Y only make it appear.

## Controls: dialogues

| Button | Action |
|--------|--------|
| D-pad | Choose an answer |
| A | Say it |
| Right stick | Scroll the conversation |
| X | Trade |
| B | End the conversation (in the trade window: back to the conversation) |

## Settings in the game

*Options → Controls* has these new entries:

| Setting | What it does |
|---------|--------------|
| Control with | *Controller* (default) or *Keyboard and mouse*. In keyboard and mouse mode the button hints show the keys again |
| Aim assist | On by default: aiming slows down over enemies, pulls gently while aiming, and zooming in (LB) snaps to an enemy near the crosshair. Only enemies in sight count |
| Controller sensitivity | How fast the right stick turns (1.0 by default) |
| Invert controller look | Up / down reversed |

These are saved with the game's other settings (`user.ltx`).

## Changing the buttons

Two text files in the game folder hold the buttons. The mod writes them at the first start. Open them with
any text editor; each one explains itself and lists everything it accepts. Saved changes work within a
second, even while the game runs. Mistakes are named at the top of the screen and in `bin\gamepad.log`.
Delete a file to get its default back.

The menus, inventory, PDA, dialogues and trading always keep the controls described above.

### controller-gameplay-layout.txt (playing)

```
<button> = <action>              on a press (or a short tap, when the button also has a hold or double action)
<button> hold = <action>         when held for hold_time seconds (0.25)
<button> double = <action>       on a double tap (within double_tap_time, 0.3 seconds)
<button> + <button> = <action>   second button pressed while the first one is held
... = none                       nothing
move_stick = left                and look_stick = right (swap both for a left-handed layout)
```

**Buttons:** `A B X Y LB RB LT RT LS RS START BACK DPAD_UP DPAD_DOWN DPAD_LEFT DPAD_RIGHT`. PlayStation
names work too: `CROSS CIRCLE SQUARE TRIANGLE L1 R1 L2 R2 L3 R3 SELECT`.

**Actions:**

```
jump  crouch  crouch_low  crouch_hold  walk  sprint
fire  aim  lean_left  lean_right  reload  use  use_or_reload  drag_body
weapon_wheel  holster  flashlight  night_vision
inventory  pda  map  contacts  menu
knife  pistol  rifle  grenade  binoculars  bolt  next_weapon  prev_weapon
favourite_up  favourite_down  favourite_left  favourite_right
fire_mode  grenade_launcher  next_ammo  zoom_in  zoom_out
medkit  bandage  antirad  energy_drink  drop  quick_save  quick_load
```

For example, to switch the fire mode with D-pad left: `DPAD_LEFT = fire_mode`

### controller-weapon-wheel.txt (the weapon wheel)

Places 0 to 5, clockwise from the top:

```
       0
  5         1
  4         2
       3
```

```
<place> = <option>    knife  primary  secondary  grenade  binoculars  bolt  none (an empty place)
<button> = <action>   shortcuts while the wheel is open: medkit  bandage  antirad  energy_drink
                      next_ammo  grenade_launcher  none
```

An option that isn't listed is not on the wheel. The left stick, the D-pad, A, B, X, Y and the button that
opens the wheel can't take shortcuts.

## Extra settings

`bin\gamepad.ini` is created when you set favourites in the wheel. You can also add these values by hand:

```ini
[wheel]
dpad_up=2              ; favourites: 0 knife, 1 pistol, 2 primary weapon, 3 grenades, 4 binoculars, 5 bolts
dpad_down=3
dpad_left=0
dpad_right=1
icons=pictures         ; or "vector" for simple drawn icons on the wheel
[sticks]
deadzone_percent=18    ; how far a stick must move before it counts
look_speed_x_deg=200   ; turning speed (degrees per second at full tilt,
look_speed_y_deg=140   ; before the Controller sensitivity setting)
[debug]
enabled=0              ; 1 writes more details into bin\gamepad.log
```

## Problems and tips

- **The controller does nothing (Linux):** the mod isn't loaded. Run the installer again and click
  *Reinstall*, for example after the launcher made a new Wine prefix for the game. Instead, the launcher can
  also set the environment variable `WINEDLLOVERRIDES=dinput8=n,b` for the game.
- `bin\gamepad.log` is written at every start and shows what the mod found, for example whether it sees the
  controller. If the file is missing, the mod didn't load.
- **The camera keeps turning by itself:** the controller (often its Bluetooth connection) keeps reporting
  the stick as pushed. Reconnect the controller. `bin\gamepad.log` then says "controller input unchanged for
  3 s with the right stick at ...".
- Changing a key in *Options → Controls* still needs the keyboard. Actions you never bound to a key (for
  example dropping an item) still work from the controller.
- The game only knows walking and running, so the stick chooses the direction and walk or run, not an exact
  speed.
- Other mods that change the same files (see [What gets installed](#what-gets-installed)) must be merged by
  hand.
- Something else? [Sending feedback](#sending-feedback) explains which files to send to the mod's author.

## Sending feedback

Found a bug, or something that doesn't work as described here? Send these files to the mod's author; they
show what happened. The game and the mod write their logs anew at every start, so collect the files before
you start the game again.

1. **If you can, turn on the mod's detailed log first.** Open `bin\gamepad.ini` in the game folder with a
   text editor (create the file if it isn't there) and add these two lines at the end:
   ```ini
   [debug]
   enabled=1
   ```
   Then start the game and make the problem happen again. Afterwards set it back to `enabled=0`, because the
   detailed log grows large.
2. **Close the game.**
3. **Copy these files into one new folder:**

   | From the game folder | |
   |------|---|
   | `bin\gamepad.log` | The mod's log |
   | `controller-gameplay-layout.txt` | Your buttons |
   | `controller-weapon-wheel.txt` | Your weapon wheel |
   | `bin\gamepad.ini` | If it is there |

   | From the game's own folder in Documents, `Stalker-SHOC` | |
   |------|---|
   | `logs\xray_<name>.log` | The game's log |
   | `logs\*.mdmp` and `*.mdmp.log` | Only after a crash: the crash report files with the newest date and time |
   | `user.ltx` | The game's settings |
   | `savedgames\<save>.sav` | If you can: a save from just before the problem (the `.sav` file; the `.dds` file next to it is only the picture) |

   Where that folder is:
   - **Windows:** `C:\Users\<your name>\Documents\Stalker-SHOC`
   - **Linux:** inside the game's Wine prefix, `drive_c/users/<name>/Documents/Stalker-SHOC` (with Proton
     `<name>` is `steamuser`; the folder name may be written in small letters)

   If it isn't there, the first line of `fsgame.ltx` in the game folder (`$app_data_root$`) names it.
4. **Write down in a few lines:**
   - what you did, what happened, and what you expected to happen,
   - your controller and how it is connected (USB, Bluetooth, Steam Input),
   - Windows or Linux; on Linux also the launcher (Heroic, Steam, Lutris) and the Proton or Wine version.
5. **Put everything into one zip file** and send it to the mod's author where you got the mod (its page's
   comments or bug reports, or a private message).
   - Windows: select the files, right-click → *Compress to ZIP file* (Windows 10: *Send to* → *Compressed
     (zipped) folder*)
   - Linux: select the files, right-click → *Compress*

The log files show folder paths, which on Windows include your user name, and your PC's processor and
graphics card.

## Credits and license

Created with [Claude Code](https://claude.com/claude-code), using the Claude Opus 5.5 model by Anthropic:
the mod, its installers and this README were written with it, following the controls the mod's author
designed and play-tested.

This mod is free to use, share and distribute. It is provided as is, without any warranty.

This is an unofficial fan mod, not affiliated with or endorsed by GSC Game World or GOG. S.T.A.L.K.E.R. is a
trademark of GSC Game World.
