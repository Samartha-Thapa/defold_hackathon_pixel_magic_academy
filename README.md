# Pixel Academy: The Stolen Spellbooks

A 2D pixel magic adventure built in **Defold** for a hackathon. Theme: **Magic**.

Talk to the Headmaster, learn to cast fireball, fight slimes blocking the roads, recover 3 stolen spellbooks, and save Pixel Academy.

[Gameplay](screenshot.png)

> Screenshot: Starting courtyard. Mana bar top-left, Books counter top-right, Headmaster in front of the academy, slimes guarding the left path.

## Play

**Goal:** Collect all 3 spellbooks and return to the Headmaster.

1. Walk to the Headmaster and press **E** to take the quest
2. Slimes block the roads to the books. Kill them with fireball
3. Pick up a book to get `Books 1/3`, then `2/3`, then `3/3`
4. Go back to the Headmaster and press **E** again to win
5. On the win screen, press **RESTART** to play again, or **X** to close it and keep exploring

## Controls

| Action | Key |
| --- | --- |
| Move Up / Down / Left / Right | W A S D or Arrow Keys |
| Talk / Interact | E |
| Cast Fireball | SPACE |
| Click Buttons | Mouse Left Click / Touch |

## Features

- **Quest system:** Talk to Headmaster to start, dialogue changes with progress, win dialogue at 3/3 books
- **Magic combat:** Fireball with directional casting, 100 mana, 20 mana per cast, 10 mana per second regen, 0.4s cooldown
- **Enemies:** Slimes guard the roads, chase you when you get close, block your path, take 3 fireball hits to die
- **HUD:** Live mana bar that drains and refills, live Books counter `0/3` to `3/3`
- **Win screen:** Trophy image, gold border, bounce animation, RESTART and Close buttons
- **Expanded map:** Courtyard, fountain, magic circle, forest, pond, houses, with tile collision for walls, trees, and buildings
- **Dialogue system:** Bottom dialogue box with wrapping text and different lines for quest start, progress, and win

## How to Run

### Option 1: Play in Defold Editor
1. Open Defold 1.14.0
2. Open this project
3. Press **Project > Build** or **F5** to run

### Option 2: Play HTML5 Build
1. In Defold, go to **Project > Build HTML5**
2. Open the generated `index.html` in Chrome
3. Or play the build from GitHub Releases if provided

## Tech

- **Engine:** Defold 1.14.0
- **Language:** Lua
- **Art:** Pixel art tiles, sprites, and atlases
- **Physics:** Defold Box2D, Kinematic player and slimes, Trigger fireballs, books, and NPC sensor
- **GUI:** Defold GUI for dialogue, HUD, and win screen

## Project Structure

```text
main/
  main.collection       Main level, player, headmaster, books, slimes, UI
  player/
    player.go           Player, camera, fireball factory, body + interaction colliders
    character.script    Movement, mana, facing, quest, books, dialogue, casting
  fireball/
    fireball.go         Fireball sprite + Trigger colliders
    fireball.script     Movement, life, hit slime and world
  slime/
    slime.go            Slime sprite + Kinematic collider
    slime.script        HP 3, chase player, take hit, die
  book/
    book.go             Spellbook sprite + Trigger collider
  headmaster/
    headmaster.go       NPC Trigger
  win/
    win.gui             Win screen layout
    win.gui_script      Show win, RESTART with sys.reboot, Close to hide
  HUD_GUI/
    hud.gui             Mana bar + Books counter
    hud.gui_script      Update bar and counter from player
  headmaster_dialogue.gui   Dialogue box
game.project
game.input_binding    W A S D, E interact, SPACE cast, Touch for clicks
```

## Balancing

- Player speed: 180
- Fireball speed: 400, life 1.5s, damage 1
- Slime HP: 3, speed 60, chase range 220
- Mana: 100 max, 20 per fireball, 10 per second regen

## Credits

- Game design, code, and level design: Samartha Magar
- Engine: Defold
- Art: Pixel Academy tileset and sprite sheets in `assets/`

## License

For hackathon demo and learning. Art assets are used as in the project.
