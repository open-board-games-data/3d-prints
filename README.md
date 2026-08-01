<div align="center">
  <img width="400" alt="Mask(1)" src="https://github.com/user-attachments/assets/6429baa3-076b-4660-b402-2b5546a08db5">
</div>

<p><strong>An open dataset mapping board games to 3D-printable upgrades, organizers, inserts, tokens, and player aids across major 3D-print platforms.</strong></p>

> [!TIP]
> **Looking for prints for your games, rather than the raw data?** Explore Meepleprint — browse, search, and plan 3D prints for your board-game collection → [meepleprint.com](https://meepleprint.com)
>
> <img height="256" alt="Meepleprint — browse 3D prints for your board games" src="https://github.com/user-attachments/assets/db5331a3-8873-47b3-9b53-44d68c1ca52b" />

## What is this?

This repository contains an open dataset of board games and the 3D-printable accessories available for them.

Board games are sourced from BoardGameGeek and matched to print listings from Printables, MakerWorld, Thingiverse, Cults3D, and other platforms.

The dataset powers the catalog behind [MeeplePrint](https://meepleprint.com) and is designed to answer one simple question:

> **Does my board game have 3D-printable upgrades, and where can I find them?**

**This is an index, not a mirror.** We don't host or redistribute 3D-print files, descriptions, or images. Each print record contains metadata and a link back to the original listing.

## What's in the data?

The dataset uses one [NDJSON](https://github.com/ndjson/ndjson-spec) file per table, with one JSON object per line. `manifest.json` contains row counts and the generation timestamp.

| File                                                  | What it is                                                                            |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `games.jsonl`                                         | Board games: name, year, BGG ID, and a link to its Meepleprint page                   |
| `game_relationships.jsonl`                            | Expansion, reimplementation, integration, and compilation relationships between games |
| `prints.jsonl`                                        | 3D-print listings: title, source, link, author, and engagement stats                  |
| `print_variants.jsonl` / `print_variant_plates.jsonl` | Weight, print time, plate count, and filament usage                                   |
| `sources.jsonl` / `categories.jsonl`                  | Reference tables for platforms and print categories                                   |
| `print_category.jsonl`                                | Categories assigned to each print                                                     |
| `game_print.jsonl`                                    | Links between games and prints, including a `match_confidence` score                  |

`game_print.jsonl` contains matches that meet our default confidence threshold. For stricter matching, apply your own cutoff using `match_confidence`.

Higher `match_confidence` values indicate stronger matches between a board game and a print listing.

## API access

Need live data instead of downloading the dataset? You can register for a free API key through Meepleprint. Create an account or log in, then visit the API tokens settings page to generate your key.

<img width="800" alt="Screen Shot 2026-08-01 at 11 25 22" src="https://github.com/user-attachments/assets/fca038f2-d92d-4be1-b197-3419b5409f49" />

## Contributing

Have a print to add or a match to fix?

* **One-off additions or corrections:** Use the **Submit a print** button on any game page at [Meepleprint](https://meepleprint.com). Submissions go through our review and matching pipeline.
* **Larger changes:** Open a pull request for new source platforms, bulk corrections, or schema and structural changes.

The JSONL files are generated from Meepleprint's live catalog, so please describe the underlying correction rather than editing generated files directly.

## Updates & license

The dataset is regenerated from Meepleprint's live catalog. Check `manifest.json` for the latest `generated_at` timestamp.

Released under the [Open Database License v1.0](./LICENSE). Attribution and per-source licensing information is available in [`ATTRIBUTION.md`](./ATTRIBUTION.md).

If you use this data, please credit this dataset and link back to this repository. Attribution helps others discover the project and helps us grow and improve the dataset. If your product has a frontend, please show the `open-bg-data-logo` image you can find in this repo and make it redirect to this repository.

Found a bad match or have an idea for the dataset? [Open an issue](../../issues).
