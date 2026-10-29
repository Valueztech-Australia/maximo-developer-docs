# Valueztech Maximo Workspace

Open `Valueztech-Maximo.code-workspace` in VS Code with the **Valueztech Maximo Developer** extension installed.

| Folder | Purpose |
|---|---|
| `maximo-automation-scripts` | Automation scripts pulled from `MXAPIAUTOSCRIPT` into `scripts/` |
| `maximo-code-package` | Code base pulled as a zip from an export API |
| `maximo-integrations` | Local only project, not synced |

First run:

1. Set `server.url` in each `.maximo-sync.json`.
2. Command Palette: **Maximo Developer: Set API Key** (name `maximo-dev`).
3. Maximo Developer view: **Check for Updates**, review the diffs, then accept or keep each change.

See the extension README for the full configuration reference.
