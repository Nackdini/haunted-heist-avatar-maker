# Haunted Heist Avatar Maker

Make a Haunted Heist profile picture in your browser: pick a heister or trickster,
an outfit, face, hat, body color, body shape and a room from the mansion, then
download a PNG.

Everything runs client-side. There is no build step and no server code.

## Hosting

This folder is a static site. To publish it with GitHub Pages: **Settings → Pages →
Build and deployment → Deploy from a branch → `main` / `(root)`**.

To try it locally (`fetch()` can't read `file://`):

```bash
python -m http.server 8765
```

## Updating

This repo is generated, so don't edit `layers/` by hand. The layers are rendered in-engine
in the game repo:

1. `BenchTools/pfp_layer_bake.tscn` renders the character layers and `layers/manifest.json`.
2. `BenchTools/pfp_room_bake.tscn` renders the room backgrounds and `layers/backgrounds/backgrounds.json`.
3. `python tools/pfp_maker/sync_site.py` copies the page and every referenced file here, and removes stale ones.

Then commit and push this repo.

Art © Haunted Heist.
