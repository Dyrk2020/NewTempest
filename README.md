# Create: New Tempest (Ironmaw)

**Create: New Tempest** is a Minecraft 1.19.2 (Forge) mod that bridges [Create](https://www.curseforge.com/minecraft/mc-mods/create) and [Tensura: Reincarnated](https://www.curseforge.com/minecraft/mc-mods/tensura-reincarnated). It introduces the **Mechanical Construct** race — a machine-bodied lineage built on Create-style engineering — with a three-tier, nine-race evolution tree, five intrinsic skills, two transformation effects, and Create-flavoured recipes that turn Tensura materials into machine parts.

The mod id is `create_new_tempest`; the artifact ships as `create_new_tempest-0.0.1-1.19.2.jar` under the `net.dyrk2020.create_new_tempest` group.

## Features

### Race line — Mechanical Construct

Players can awaken as a **Mechanical Construct** (or roll it on reincarnation). The race is majin-class, with 26 base health, ×2 spiritual health multiplier, 1500–3000 base magicules, and high knockback resistance — but **water corrodes the frame** (Corrosion while submerged, Paralysis while caught in the rain). Evolution follows one of three branches, gated by EP thresholds that are configurable per race:

| Branch | Tier 1 | Tier 2 (10,000 EP) | Tier 3 (20,000 EP) | Apex (50,000 EP) |
| --- | --- | --- | --- | --- |
| Titan | Mechanical Construct | Mechanical Giant | Mechanical Colossus | Mechanical Titan |
| Warrior | Mechanical Construct | Mechanical Combatant | Mechanical Soldier | Mechanical Warrior |
| Scholar | Mechanical Construct | Mechanical Novice | Mechanical Expert | Mechanical Scholar |

Each evolution grants the next tier's intrinsic skills and stat scaling (magicule pools grow from 1,500 up to 4,500 at the apex).

### Intrinsic skills

| Skill | Unlocked at | Effect |
| --- | --- | --- |
| **Mechanical Eye** | Mechanical Construct | Toggleable. Registers you as wearing [Create goggles](https://github.com/Creators-of-Create/Create), revealing machine goggle overlays without the item. Costs 10 magicules to toggle. |
| **Mechanical Hands** | Mechanical Construct | Two-mode skill (**Rotate** / **Remove**) that lets you operate Create `IWrenchable` blocks with wrench-like interactions, no wrench required. |
| **Mechanical Body** | Mechanical Novice | Passively tracks nearby entities within 30 blocks that share your name; enables a second mechanical body so the harshest blows can't end your existence. |
| **Overclock** | Mechanical Combatant | Transformation. Grants +20 max health, +15 attack damage, +5% movement speed and ×1.5 magicule/aura caps, wreathed in red lightning sparks. Lasts 3 min (6 min mastered), 60 s cooldown. |
| **Augment Frame** | Mechanical Giant | Transformation. Grants +15 armor, +15 attack damage, +2 attack knockback, +1 step height, +1 attack range/reach and ×1.5 size — trading agility (-5% speed, reduced jump) for raw frame power. Also slowly restores hunger/health. |

### Mob effects

- **Overclock** (`create_new_tempest:overclock`) — applied by the Overclock skill.
- **Augmented Frame** (`create_new_tempest:augmented_frame`) — applied by the Augment Frame skill.

### Create × Tensura recipes

- **Demon Essence Crushing** — crush Netherrack in a Create crushing wheel for a 2% chance of Tensura Demon Essence.
- **Slime Chunk Mixing** — mix a Tensura Slime Chunk in a Create basin to roll one of six **Slime Poop** items (blue/teal/green/red/yellow/pink), each at 14%.

## Dependencies

| Dependency | Version |
| --- | --- |
| Minecraft | 1.19.2 |
| Forge | 43.4.0 |
| [Create](https://www.curseforge.com/minecraft/mc-mods/create) | 0.5.1.i |
| [Tensura: Reincarnated](https://www.curseforge.com/minecraft/mc-mods/tensura-reincarnated) | 1.0.0.7 |
| [ManasCore](https://www.curseforge.com/minecraft/mc-mods/manascore) | 2.1.4.3 |
| GeckoLib (transitive, Create) | 3.1.40 |
| TerraBlender (transitive, Tensura) | 1.19.2-2.0.1.162 |

Java 17 is required to run the mod and to build it.

## Installation

1. Install Minecraft **1.19.2** with **Forge 43.4.0** (or newer 43.x).
2. Install **Create 0.5.1.i**, **Tensura: Reincarnated 1.0.0.7**, and **ManasCore 2.1.4.3**.
3. Drop `create_new_tempest-0.0.1-1.19.2.jar` into your `mods/` folder.

For development builds, this repository also vendors the exact dependency jars in [`lib/`](lib/) (`create-1.19.2-0.5.1.i.jar`, `tensura-1.19.2-1.0.0.7.jar`, `ManasCore-1.19.2-2.1.4.3.jar`); they are wired into the Gradle build via a `flatDir` repository, so no extra download is needed to compile.

## Building

```bash
./gradlew build
```

The compiled, reobfuscated jar lands in `build/libs/`. A data-generation run is available with `./gradlew runData`, and a client dev environment with `./gradlew runClient`.

## First-launch configuration

On the game's first launch the mod automatically injects itself into Tensura's race config:

- It appends `create_new_tempest:mechanical_construct` to both the `startingRaces` and `possibleRandomRaces` lists in `defaultconfigs/tensura-reincarnated/common.toml`.
- A marker file (`defaultconfigs/tensura-reincarnated/tempest_first_launch_marker`) records that the injection already ran, so it happens only once per instance.

If you want players to be able to awaken as a Mechanical Construct without the automatic injection, add the id manually to those lists in Tensura's `common.toml`.

Evolution EP thresholds for all nine races are exposed in the mod's own config file (`tensura-reincarnated/create-new-tempest-common.toml`) and can be tuned between 0 and 1,000,000,000 EP.

## License

This project is licensed under the [MIT License](LICENSE).