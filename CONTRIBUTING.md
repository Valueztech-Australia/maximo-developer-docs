# Contributing to Valueztech Maximo Developer

Thanks for helping improve Valueztech Maximo Developer. Issues and pull requests are welcome.

## Reporting a bug

Open a [GitHub issue](https://github.com/Valueztech-Australia/maximo-developer-docs/issues/new) with:

- Extension version and VS Code version
- Maximo / MAS version
- The relevant part of `.maximo-sync.json` (**remove server URLs and never include API keys**)
- The **Maximo Developer** output log (Maximo Developer view, `...` menu, **Show Log**), with host names removed if needed

## Development setup

Requirements: Node.js 18+ and VS Code 1.80+. There are no runtime dependencies to install.

```bash
git clone https://github.com/Valueztech-Australia/maximo-developer.git
cd maximo-developer
npm test
```

- `npm test` runs the sync engine tests and an extension smoke test against a mock Maximo server (`test/mock-maximo.js`).
- `npm run mock` starts the mock on `http://127.0.0.1:8765/maximo` with API key `test-key`.
- Press **F5** in VS Code to start an Extension Development Host with `examples/workspace` open.

## Code layout

| Path | Purpose |
|---|---|
| `extension.js` | VS Code UI: view, commands, diffs, SecretStorage |
| `lib/engine.js` | Staging, three-way comparison, apply, backups (no `vscode` import) |
| `lib/maximo-api.js` | `automationScripts` and `mafApp` sources |
| `lib/sources.js` | `objectStructure` and `zip` sources |
| `lib/http.js`, `lib/zip.js`, `lib/glob.js` | Dependency-free HTTP client, zip reader and glob matcher |
| `cli.js` | Command line using the same engine |
| `schemas/` | JSON schema for `.maximo-sync.json` |

## Pull requests

1. Keep the engine free of `vscode` imports so it stays testable and usable from the CLI.
2. Add or update tests in `test/` for behaviour changes; `npm test` must pass.
3. Do not add runtime dependencies without discussing it in an issue first.
4. Update `CHANGELOG.md` under an *Unreleased* heading.
5. User-facing text uses Australian English.

By contributing you agree that your contributions are licensed under the MIT Licence of this project.
