# Changelog

All notable changes to Valueztech Maximo Developer are listed here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and the project uses [Semantic Versioning](https://semver.org/).

## [1.3.1] - 2026-10-29

### Added
- Step-by-step [setup guide with screenshots](docs/SETUP.md), linked from the README and the Marketplace page.

### Fixed
- Broken logo and badges on the Marketplace page. Images and links now resolve to the public docs repository `Valueztech-Australia/maximo-developer-docs`; the source repository is private.

## [1.3.0] - 2026-10-29

### Changed
- Renamed from Maximo Code Sync to **Valueztech Maximo Developer**. Extension ID is now `valueztech.maximo-developer` and the repository is `valueztech/maximo-developer`.
- The view, command category, messages and log are now titled **Maximo Developer**.
- Unchanged so existing projects keep working: the `.maximo-sync.json` config file, the `.maximo-sync/` state folder, `maximoSync.*` settings and command IDs.
- Upgrading from a Maximo Code Sync `.vsix`: uninstall it first, then run **Maximo Developer: Set API Key** again (VS Code keeps stored keys per extension).

## [1.2.0] - 2026-10-28

### Added
- `automationScripts`: integration framework scripts are recognised by IBM's naming convention and written to `Integration/<Type>/<Component>/` instead of `Standalone/`:
  `ObjectStructure` (`OSIN.`, `OSOUT.`, `OSACTION.`), `PublishChannel` (`PUBLISH.<channel>.EXTEXIT|USEREXIT...`, `...EVENTFILTER`), `InvocationChannel` (`INVOKE.`), `EnterpriseService` (`SYNC.`, `CREATE.`, `UPDATE.`, `DELETE.`, `QUERY.` exits).
- `_manifest.json` records the integration type, component and role for these scripts.
- Options `detectIntegration`, `integrationFolder` and `integrationGroupBy`.

## [1.1.1] - 2026-10-28

### Fixed
- `mafApp`: when the attachment is a zip that wraps `app-source.zip`, the inner archive is now extracted so the app files (`src/`, `config/`, `package.json` and so on) land directly in the app folder instead of a single `app-source.zip` file. Controlled by `extractNestedZip` (default `true`).

## [1.1.0] - 2026-10-28

### Added
- `automationScripts` source: every automation script from `MXAPIAUTOSCRIPT` with its launch points, written into `<Type>/<OBJECT>/` folders (`Object`, `Attribute`, `Action`, `CustomCondition`) or `Standalone/`, plus `_manifest.json`.
- `mafApp` source: `app-source.zip` of a Maximo Application Framework app from `OSLCMAFAPPDATA`, read through the standard attachments API and extracted per app.
- **Inspect Source** command (and `cli.js inspect`) to see what the API returns without writing anything.
- SQL style `like` in `where` is converted to OSLC syntax automatically.
- Clearer Maximo error messages with hints for common BMXAA codes.

### Changed
- No custom automation script is needed on the server; everything uses the standard REST API.
- Background checks never prompt for an API key.

## [1.0.0] - 2026-10-28

### Added
- Initial release: object structure and zip sources, Incoming Changes view with Local ↔ Server diffs, three-way conflict detection, backups, API keys in SecretStorage, status bar, background checks and a command line.
