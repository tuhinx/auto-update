This repository runs a GitHub Actions workflow that builds JSON from an M3U playlist and pushes the results into a target repo (recommended: `owner/ayna-tv-fetch`). For end‑to‑end CLI usage, see the main `README.md` in the `ayna-tv-fetch` folder.

Setup (repo secrets):
- `PLAYLIST_URL`: required
- `PLAYLIST_REFERER`: optional (use `null` to disable auto)
- `PLAYLIST_ORIGIN`: optional (use `null` to disable auto)
- `CODE_REPO`: `owner/ayna-tv-fetch`
- `CODE_REF`: `main`
- `CODE_TOKEN`: leave empty if `ayna-tv-fetch` is public; else PAT with Contents: Read
- `TARGET_REPO`: `owner/ayna-tv-fetch`
- `TARGET_TOKEN`: PAT with Contents: Read/Write on `ayna-tv-fetch`
- `TARGET_BRANCH`: `main`
- `TARGET_DIR`: `output` (or desired folder)

Behavior:
- Generates `output/api.json` and `output/filtered.json` in the workflow workspace
- Does not commit to this `auto-update` repo
- Copies and pushes outputs into `TARGET_REPO` at `TARGET_DIR`
