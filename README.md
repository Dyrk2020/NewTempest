# Create: New Tempest

[![Minecraft](https://img.shields.io/badge/Minecraft-1.19.2-brightgreen)](https://www.minecraft.net) [![Forge](https://img.shields.io/badge/Forge-43.4.0-orange)](https://files.minecraftforge.net) [![Version](https://img.shields.io/badge/version-0.0.1-blue)]() [![License: MIT](https://img.shields.io/badge/license-MIT-yellow)](LICENSE)

**Create: New Tempest** (formerly Ironmaw) is a Minecraft 1.19.2 (Forge) mod bridging [Create](https://www.curseforge.com/minecraft/mc-mods/create) and [Tensura: Reincarnated](https://www.curseforge.com/minecraft/mc-mods/tensura-reincarnated). It adds the **Mechanical Construct** race — a machine-bodied majin lineage with a three-branch, nine-race evolution tree, five intrinsic skills, two transformation effects, and Create-flavoured recipes that turn Tensura materials into machine parts. Mod id: `create_new_tempest`.

## Features

- **Mechanical Construct race** — majin-class: 26 base health, ×2 spiritual health, 1,500–3,000 base magicules, high knockback resistance — but water corrodes the frame (Corrosion while submerged, Paralysis in rain). Awaken manually or roll it on reincarnation.
- **Evolution tree** — 9 races total across 3 branches. Every branch starts as **Mechanical Construct**; each evolution unlocks the next tier's skills and grows the magicule pool (up to 4,500 at apex). EP thresholds are configurable per race (0–1,000,000,000):

| Branch | Tier 2 (10,000 EP) | Tier 3 (20,000 EP) | Apex (50,000 EP) |
| --- | --- | --- | --- |
| Titan | Mechanical Giant | Mechanical Colossus | Mechanical Titan |
| Warrior | Mechanical Combatant | Mechanical Soldier | Mechanical Warrior |
| Scholar | Mechanical Novice | Mechanical Expert | Mechanical Scholar |

- **Intrinsic skills (5)**
  - **Mechanical Eye** (base) — toggleable, 10 magicules: registers you as wearing Create goggles, showing machine goggle overlays without the item.
  - **Mechanical Hands** (base) — Rotate / Remove modes to operate Create `IWrenchable` blocks without a wrench.
  - **Mechanical Body** (Mechanical Novice) — tracks same-named entities within 30 blocks and enables a spare mechanical body.
  - **Overclock** (Mechanical Combatant) — transformation: +20 max health, +15 attack damage, +5% speed, ×1.5 magicule/aura caps, red lightning. Lasts 3 min (6 min mastered), 60 s cooldown.
  - **Augment Frame** (Mechanical Giant) — transformation: +15 armor, +15 attack damage, +2 knockback, +1 step height, +1 reach, ×1.5 size — at the cost of −5% speed and reduced jump; slowly restores hunger/health.
- **Mob effects** — `create_new_tempest:overclock` and `create_new_tempest:augmented_frame`, applied by the two transformation skills.
- **Create × Tensura recipes** — crush Netherrack in a Create crushing wheel for a 2% chance of Demon Essence; mix a Tensura Slime Chunk in a basin to roll one of six Slime Poop items (14% each).
- **First-launch injection** — auto-adds `create_new_tempest:mechanical_construct` to the `startingRaces` and `possibleRandomRaces` lists in Tensura's `defaultconfigs/tensura-reincarnated/common.toml` (once per instance, marker-file guarded).

## Dependencies

| Dependency | Version |
| --- | --- |
| Minecraft | 1.19.2 |
| Forge | 43.4.0 |
| [Create](https://www.curseforge.com/minecraft/mc-mods/create) | 0.5.1.i |
| [Tensura: Reincarnated](https://www.curseforge.com/minecraft/mc-mods/tensura-reincarnated) | 1.0.0.7 |
| [ManasCore](https://www.curseforge.com/minecraft/mc-mods/manascore) | 2.1.4.3 |

Java 17 is required to run and build the mod. GeckoLib (via Create) and TerraBlender (via Tensura) are pulled in transitively.

## Quick start

1. Install Minecraft **1.19.2** with **Forge 43.4.0**, plus **Create 0.5.1.i**, **Tensura: Reincarnated 1.0.0.7**, and **ManasCore 2.1.4.3**.
2. Drop `create_new_tempest-0.0.1-1.19.2.jar` into your `mods/` folder.
3. Play: awaken as a Mechanical Construct (or roll it on reincarnation), then evolve along a branch by earning EP.

### Building

```bash
./gradlew build
```

The reobfuscated jar lands in `build/libs/`. `./gradlew runData` runs data generation; `./gradlew runClient` starts a dev client. The exact dependency jars are vendored in [`lib/`](lib/) and wired into Gradle via a `flatDir` repository, so no extra downloads are needed to compile.

### Configuration

- Race EP thresholds: `tensura-reincarnated/create-new-tempest-common.toml` (tunable per race, 0–1,000,000,000 EP).
- To allow awakening without the automatic injection, add the race id manually to the `startingRaces` / `possibleRandomRaces` lists in Tensura's `common.toml`.

## License

[MIT](LICENSE)
