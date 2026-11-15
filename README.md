# TickHappens Assets

Source art and runtime media for TickHappens. The current collection contains the project palette, procedural sprite recipes, hand-authored indexed sprites, a built atlas, and synthesized sound effects and music.

- `art/palette/` contains the project palette.
- `art/recipes/` contains deterministic sprite and animation recipes.
- `art/source/` contains indexed pixel art and imported artwork with provenance.
- `assets/atlas/` contains the built atlas metadata, albedo, emission, and normal maps.
- `art/audio/` contains deterministic sound (`sfx/*.sound.json`) and music (`music/*.music.json`) recipes.
- `assets/audio/` contains the rendered 32 kHz 16-bit WAV effects (one file per variant) and seamless music loops.

With Game checked out beside Assets, run `dotnet run --project tools/TickHappens.AssetTool -- build` from Game. The tool writes the atlas and audio here and previews to Game's `.tmp/preview/`. `-- audio [NAME]` renders only the sound and music recipes. See the [asset pipeline](https://github.com/Tick-Happens-Team/Game/blob/dev/docs/ASSET_PIPELINE.md) and [art standard](https://github.com/Tick-Happens-Team/Game/blob/dev/docs/ART_STANDARD.md).

Submit changes through a pull request into `dev`. When a Game PR needs the updated atlas, link the two PRs and merge Assets first. Promote tested changes to `stable` through a separate PR. CI on `stable` publishes a versioned atlas ZIP and checksum through GitHub Releases. See [CC BY 4.0 and third-party terms](LICENSE.md).
