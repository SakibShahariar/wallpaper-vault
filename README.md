# Wallpaper Vault

A curated desktop wallpaper collection with filenames you can actually search.

## Gallery

Browse all 417 wallpapers, grouped by category with small previews that link to the full-resolution originals: **[Wallpaper Vault gallery](https://sakibshahariar.github.io/wallpaper-vault/gallery/)** (source: [`gallery/index.html`](gallery/index.html)).

## What's inside

- **417 images** — 415 JPEG, 1 PNG, 1 WebP.
- Anime and game characters, lo-fi study scenes, fantasy landscapes, cyberpunk nights, nature, pixel art, and minimal/abstract art.
- Every filename describes what is in the image, so searching the folder works without opening files:

```text
misty-forest.jpg
piano-couple-red-sunset-sea.jpg
samurai-silhouette.jpg
voyager-golden-spire-autumn-forest-20.jpg
```

## Naming convention

- Lowercase kebab-case only: `word-word-word.jpg`.
- Describe the visible subject, setting, and mood/colour — no random IDs, source names, or timestamps.
- Recognisable character/series names keep their correct spelling (`frieren`, `gojo`, `totoro`).
- Numbered sets keep the number as a suffix: `frieren-1.jpg`, `tokyo-night-23.jpg`.

## Using the collection

- Local path: `/mnt/Storage/Wallpapers`.
- Set directly with GNOME:

```sh
gsettings set org.gnome.desktop.background picture-uri 'file:///mnt/Storage/Wallpapers/misty-forest.jpg'
gsettings set org.gnome.desktop.background picture-uri-dark 'file:///mnt/Storage/Wallpapers/misty-forest.jpg'
```

- The matugen theme pipeline in `~/dotfiles` reads `matugen/.config/matugen/wallpaper_map.json`, which maps theme names to wallpapers in this folder. `apply-theme.fish` picks a mapped wallpaper (or one at random from this folder) when a theme is applied.
- Any image viewer or wallpaper tool can use the files directly.

## Adding a wallpaper

1. Name it using the convention above.
2. Add it here and, optionally, map it to a theme in `wallpaper_map.json`.
3. Refresh the local name indexes so theme assignment stays in sync:

```sh
python3 ~/Scripts/assign-wallpapers.py --index
# optional, slower: rebuild cached palettes with matugen
python3 ~/Scripts/assign-wallpapers.py --palette-index
```

4. Commit and push.

## Notes

- Filenames were bulk-normalised on 2026-11-23. If an external script still points at an old name, update the matugen map and rebuild the caches above.
- Images come from various sources; all rights remain with their respective creators.
