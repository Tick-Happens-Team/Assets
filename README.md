# TickHappens Assets

Source art and runtime media for TickHappens. The current collection contains the project palette, procedural sprite recipes, hand-authored indexed sprites, and a built atlas. Music and sound effects belong here when added.

- `art/palette/` contains the project palette.
- `art/recipes/` contains deterministic sprite and animation recipes.
- `art/source/` contains indexed pixel art and imported artwork with provenance.
- `assets/atlas/` contains the built atlas metadata, albedo, emission, and normal maps.

With Game checked out beside Assets, run `dotnet run --project tools/TickHappens.AssetTool -- build` from Game. The tool writes the atlas here and previews to Game's `.tmp/preview/`. See the [asset pipeline](https://github.com/Tick-Happens-Team/Game/blob/dev/docs/ASSET_PIPELINE.md) and [art standard](https://github.com/Tick-Happens-Team/Game/blob/dev/docs/ART_STANDARD.md).

Submit changes through a pull request into `dev`. When a Game PR needs the updated atlas, link the two PRs and merge Assets first. Promote tested changes to `stable` through a separate PR. CI on `stable` publishes a versioned atlas ZIP and checksum through GitHub Releases. See [CC BY 4.0 and third-party terms](LICENSE.md).
