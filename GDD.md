# Slime Kingdom - Game Design Specification

## 1. High-Level Concept

**Slime Kingdom** is a small 2D incremental arena game made with Unity and C#.

The player defeats slimes, earns gold, buys automated defenses and upgrades, and eventually becomes rich enough to buy a kingdom.

**Target playtime:** approximately 15 minutes.

## 2. Core Gameplay Loop

The game takes place in a square arena populated by wandering slimes.

Core loop:

1. Move the cursor around the arena to position an attached attack area that periodically deals damage.
2. Kill slimes to earn gold.
3. Spend gold on automated defenses and upgrades.
4. Increase damage output.
5. Face a dynamically increasing slime population.
6. Accumulate enough gold to purchase **Buy Kingdom** and complete the run.

The slime population increases dynamically with the player's kill rate, keeping the arena slightly more populated than the current damage output can comfortably handle.

## 3. Slimes

There are three slime rarities:

- **Red - Common**
- **Green - Uncommon**
- **Blue - Rare**

Higher-rarity slimes have more health, provide more gold, and spawn less frequently.

Slimes can also spawn at different sizes. Size modifies health and reward without changing rarity.

Movement behavior:

- Slimes periodically stop.
- They choose a random point inside the arena.
- They move toward it.
- The cycle repeats.

## 4. Defenses

### 4.1 Archers

Two archer groups can be purchased independently:

- **Vertical Archers** - up to 5 levels.
- **Horizontal Archers** - up to 5 levels.

Each level adds one archer on each of the two opposite sides of the arena (two archers per level). Each group can have up to 10 archers, for a combined maximum of 20.

Archers fire physical projectiles across the arena. A projectile damages the first slime it collides with.

Shared archer upgrades:

- **Damage** - 5 levels.
- **Attack Speed** - 5 levels.

Archer upgrades apply to both groups and unlock after purchasing the first archer level.

### 4.2 Cannons

Up to 5 cannons can be purchased.

Each cannon is represented by a targeting marker that randomly moves around the arena and periodically deals area damage at its current position.

Cannon upgrades:

- **Damage** - 5 levels.
- **Attack Speed** - 5 levels.

Cannon upgrades become available after purchasing the first cannon.

## 5. Manual Attack

Manual attack is available from the beginning.

An attack area follows the cursor and periodically deals damage to slimes inside it. Clicking or tapping is not required to trigger damage.

Upgrades:

- **Damage** - 5 levels.
- **Attack Radius** - 5 levels.

## 6. Progression

All defenses, upgrades, and the end goal are visible from the start:

- Vertical Archers.
- Horizontal Archers.
- Cannons.
- Archer and cannon upgrades.
- Manual Attack upgrades.
- Buy Kingdom.

Prices and balance values are determined during gameplay tuning.

The game has no:

- prestige system;
- offline progression;
- save system.

## 7. UI

The gameplay arena always keeps a square aspect ratio.

The surrounding UI adapts to the available screen shape:

- **Portrait / square:** information above the arena, upgrades below.
- **Landscape:** UI panels move to the sides.

## 8. Visual Style

Simple, clean 2D graphics with simple sprites.
