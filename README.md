# Neon Midnight — GamepadViewer skin

| File | What it is |
|---|---|
| `neon-skin.css` | The skin. Pure CSS, no images, so this one file is all you host. |
| `viewer.html` | Local viewer that runs the skin without gamepadviewer.com (good for testing, or as an OBS source). |

## Option A — use it on gamepadviewer.com (needs a CSS link)

GamepadViewer only loads skins from a public URL, so the CSS has to be online.
Easiest free way, GitHub:

1. Create a public repo on github.com (e.g. `gamepad-skins`) and upload `neon-skin.css`.
2. Open the file on GitHub, click **Raw**, and copy that URL. It looks like:
   `https://raw.githubusercontent.com/YOUR-NAME/gamepad-skins/main/neon-skin.css`
3. Your overlay link is:

```
https://gamepadviewer.com/?p=1&css=https://raw.githubusercontent.com/YOUR-NAME/gamepad-skins/main/neon-skin.css
```

GamepadViewer automatically turns `raw.githubusercontent.com` links into jsDelivr
links (GitHub raw files don't load as stylesheets by themselves). A GitHub Gist
raw link also works. jsDelivr caches files, so after you edit the CSS it can take
up to ~12 hours to update. Add `?v=2` to the end of the link to see changes sooner.

Useful extra URL options: `&p=2` (player 2), `&sc=0.5` (scale), `&dz=0.15` (stick dead zone).
You don't need `&s=`. When `css=` is set the site ignores the base skin and uses this file.

## Option B — no hosting: use `viewer.html` in OBS

1. OBS → Sources → **+** → **Browser**.
2. Tick **Local file** and pick `viewer.html` (keep `neon-skin.css` in the same folder).
3. Width 1280, height 720. The background is transparent inside OBS automatically.
4. Press a button on your controller to wake it up.

Opening `viewer.html` in Chrome or Edge works too. If no controller is plugged in,
you can try the skin with the keyboard (the controls are listed on the page).

## Recolouring

Change the variables at the top of `neon-skin.css` (`--accent`, `--accent-2`,
`--body`, `--btn-a` … `--btn-y`), then re-upload.
