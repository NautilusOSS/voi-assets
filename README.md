# voi-assets

Asset logo images keyed by asset ID, plus a machine-readable index.

## Layout

```text
assets.json          # index of all assets
assets/
  {assetId}.png
  {assetId}.svg
```

## `assets.json`

Each asset ID maps to available formats with `path`, `bytes`, and `sha256`.
If the same bytes appear under another filename, `_duplicate_of_files` lists those names.

## Optimization

- SVGs compressed with [SVGO](https://github.com/svg/svgo) (`--multipass`).
- GIF/WebP extras removed when PNG/SVG already exist for the same asset ID.
- No cross-ID content dedup (duplicate logos under different IDs are kept).
