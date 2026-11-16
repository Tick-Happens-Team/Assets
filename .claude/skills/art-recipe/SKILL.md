---
name: art-recipe
description: Create or change TickHappens sprites in this Assets repo with the local procedural recipe pipeline (bones, primitives, palette ramps), review them, and commit sources plus the regenerated atlas. Use for any new hero, enemy, summon or prop art.
---

Tools run from the sibling Game checkout (`D:\tickhappens\Game`); sources live here. Read Game/docs/ART_STANDARD.md and ASSET_PIPELINE.md first. Never use paid generators, neural networks or downscaled AI images.

1. Branch from `dev` (`feat/<topic>`). Copy the closest recipe in `art/recipes/` (heroes 16x24, origin [8,23], `idle` 3 frames fps 3, `walk` 4 frames fps 8; enemies 16x16+ per ART_STANDARD §2). Colors only from `art/palette/tickhappens-v1.hex`; heroes contrast with dark grass and purple/amber enemies (§5).
2. Variants: from Game `dotnet run --project tools/TickHappens.AssetTool -- gen ../Assets/art/recipes/<id>.json --seeds 1-6`; open the contact sheet in `.tmp/gen/` and critique silhouette, light (top-left), noise, distinctness; write the chosen seed into the recipe.
3. Build: `dotnet run --project tools/TickHappens.AssetTool -- build` → 0 lint errors; fix TH010 (clipping) and TH011 (silhouette jumps) for new sprites.
4. Review previews (`.tmp/preview/<id>.png`) and a lineup next to existing heroes/enemies; for bigger batches ask an independent reviewer subagent against ART_STANDARD.
5. In-game check: Game `play-capture` skill with `--character <id>` or the visual bench.
6. Commit recipes and `assets/atlas/*` together (no AI attribution), PR to `dev`. Merge before the Game PR that references the new sprite ids.
Content-driven designs (owner tables) must avoid ethnic or religious caricature and copying third-party IP.
