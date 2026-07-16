# sarcasticsoftwarestudio.github.io

Sarcastic Software Studio's GitHub Pages site.

## `fylefunnl/` — FyleFunnl release channel

**Do not delete or rename this folder.** Every installed copy of FyleFunnl polls
`https://sarcasticsoftwarestudio.github.io/fylefunnl/version.json` once a day to learn whether a
newer release exists (see `Services/UpdateChecker.cs` in the FyleFunnl repo). The URL is baked
into shipped binaries, so it must keep serving for as long as any installed copy is out there.

To publish a release:

1. Run `build-installer.ps1` in the FyleFunnl repo — it produces `dist/version.json` alongside
   the installer.
2. Copy `dist/version.json` over `fylefunnl/version.json` here.
3. Host the installer at the manifest's `downloadUrl` (by default,
   `fylefunnl/FyleFunnl-Setup-<version>.exe` in this repo).
4. Commit and push. Pages redeploys automatically.

The manifest is a static file; the app's fetch of it carries no user data. Keep it that way —
the FyleFunnl README promises users the update check sends nothing.
