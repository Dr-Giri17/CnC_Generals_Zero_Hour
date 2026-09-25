# First Playable Spike

## Objective

Get from source fork to a tiny custom playable prototype with the least possible work.

## Gate 0 — Baseline

Confirm locally:

- repository checkout works;
- original source tree is intact;
- license/notices are intact;
- original game installation is available where needed for runtime data.

## Gate 1 — Build path

Try the practical modern path first:

1. Inspect `TheSuperHackers/GeneralsGameCode` build documentation.
2. Decide whether to build this EA archive directly or use the modernized community fork as the executable development base.
3. Document exact compiler/toolchain.
4. Produce a runnable Zero Hour executable or confirm the precise blocker.

Do not spend days repairing the 2003 toolchain if the community fork already solves the same problem.

## Gate 2 — WorldBuilder

- launch WorldBuilder;
- open an existing map;
- create a blank test map;
- terrain + road + player starts + resources;
- save and load it in-game.

**PASS:** custom map launches and is playable.

## Gate 3 — First custom object

Add one new object definition:

- clone a simple ground unit definition;
- give it a unique internal name;
- change cost/build time/health/weapon values;
- verify production and combat.

**PASS:** object exists as an independent gameplay entity.

## Gate 4 — Custom asset

Replace that object's visible representation with an original test asset:

- own model;
- own texture;
- correct orientation;
- hardpoints/turret if needed;
- death state or simple destruction behavior.

Temporary ugly art is acceptable.

**PASS:** no dependency on the original unit's visual identity.

## Gate 5 — Micro-faction

Minimum slice:

- HQ;
- builder;
- economy building / collector;
- factory;
- infantry or light vehicle;
- combat vehicle;
- defense;
- one special ability.

**PASS:** player can complete a 10–15 minute skirmish loop.

## Gate 6 — Package

Create a documented local mod package and launch procedure.

## Stop rule

If any single gate turns into an open-ended engine rewrite, stop and record the blocker instead of expanding scope.

## Deliverable

One short status file:

```text
BUILD: PASS / BLOCKED
WORLDBUILDER: PASS / BLOCKED
CUSTOM MAP: PASS / BLOCKED
CUSTOM OBJECT: PASS / BLOCKED
CUSTOM ASSET: PASS / BLOCKED
MICRO-FACTION: PASS / BLOCKED

TOP BLOCKERS:
1.
2.
3.

NEXT SAFE STEP:
```
