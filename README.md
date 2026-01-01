# Personal Mani Manifest (Nick)

This repo defines my personal Mani manifest. I clone it directly to `~/dev/atlas` so Anvil can sync these repos alongside the shared Beta-Techno workspaces.

## Layout

```
~/dev/
  atlas/        # this repo (mani.yaml + README)
  persona-site/
  damico/
```

## Usage

1. Add the personal repos you care about to `mani.yaml` (see sample entries below).
2. Push this repo to `git@github.com:nickbendasg/persona.git`.
3. In the bootstrap bundle, add:
   ```yaml
   mani_manifests:
     - repo_url: git@github.com:Beta-Techno/atlas.git
       repo_path: ~/org/Beta-Techno/infra/atlas
       sync_tags: [infra]
     - repo_url: git@github.com:nickbendasg/atlas.git
       repo_path: ~/dev/atlas
       sync_tags: [personal]
   ```
4. Re-run `anvil up`—both manifests will sync automatically.
