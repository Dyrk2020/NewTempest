# NewTempest (Create: New Tempest)

**Create: New Tempest** is a Minecraft 1.19.2 (Forge) mod that bridges [Create](https://www.curseforge.com/minecraft/mc-mods/create) (0.5.1.i) and [Tensura: Reincarnated](https://www.curseforge.com/minecraft/mc-mods/tensura-reincarnated) (1.0.0.7). It introduces the **Mechanical Construct** race — a machine-bodied lineage built on Create-style engineering — with a three-branch, nine-race evolution tree, intrinsic skills, transformation effects, and Create-flavoured recipes turning Tensura materials into machine parts.

Mod id: `create_new_tempest`; jar: `create_new_tempest-0.0.1-1.19.2.jar`; group `net.dyrk2020.create_new_tempest`.

## The Mechanical Construct race

Players can awaken as a **Mechanical Construct** (or roll it on reincarnation). Majin-class: 26 base health, ×2 spiritual health multiplier, 1500–3000 base magicules, high knockback resistance — but **water corrodes the frame** (Corrosion while submerged, Paralysis in rain).

Evolution: three branches, EP-gated tiers.

| Branch | Tier 1 | Tier 2 (10,000 EP) | Tier 3 (20,000 EP) | Apex (50,000 EP) |
|---|---|---|---|---|
| Warrior | Mechanical Combatant | Mechanical Soldier | Mechanical Warrior | — |
| Scholar | Mechanical Novice | Mechanical Expert | Mechanical Scholar | — |
| Titan | Mechanical Giant | Mechanical Colossus | Mechanical Titan | — |

Skill sources live under `ability/skill/intrinsic/` (e.g. Mechanical Eye, Mechanical Hands, Mechanical Body).

## Build

```bash
./gradlew build
```

Requires JDK 17. Dependency jars (Create, Tensura, ManasCore) are vendored in `lib/`, so the build is offline-friendly and reproducible.

## Source map

```
config/    CreateNewTempestConfig, CreateNewTempestRacesConfig (per-race EP thresholds)
race/      mechanical_warrior|scholar|titan — nine race classes + MechanicalConstructRace
ability/   intrinsic skills
registry/  AllRaces / AllSkills / AllEffects wiring
item/      mod items
```
