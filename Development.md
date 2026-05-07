## Workflow

- `npm install`.
- `npm run build`.
- Copy `main.js` and `manifest.json` (if changed) to your obsidian vault's plugin folder (e.g. `[VAULT]/.obsidian/plugins/obsidian-wallabag`).
- Disable and re-enable the plugin in Obsidian's settings to reload it.
  

## State

Relative to `[VAULT]/.obsidian/plugins/obsidian-wallabag`:

- `data.json`: List of all id's that have already been downloaded plus other configuration items. Syncs via [[Obsidian Sync]] if sync is enabled.
- `.__wallabag_token__`: Authentication credentials for Wallabag.