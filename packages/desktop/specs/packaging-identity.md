# Desktop packaging identity

## Behavior

- The production desktop package is displayed as `Codex`.
- The preview desktop package is displayed as `Codex Preview`.
- Existing `appId`, `ZCODE_*` protocol names, and internal package namespaces remain unchanged.
- The production runtime display name changes to `Codex`, but its existing `ZCode` user-data directory remains the storage owner so existing settings and sessions are not silently abandoned.
- macOS application, DMG volume, and packaged runtime icon assets are sourced from the provided `codex.icns` artwork.
- Windows application, window, tray, installer, and uninstaller icon assets are derived from the same provided `codex.icns` artwork.
- Linux package, runtime, AppImage integration, and hicolor icon assets are derived from the same provided `codex.icns` artwork.

## Acceptance

- electron-builder resolves the production `productName` to `Codex`.
- A packaged macOS app has a `Codex.app` bundle and the existing production bundle identifier.
- The packaged app contains the replacement macOS icon and runtime PNG icon.
- Windows packaging retains the application ICO sizes `16`, `24`, `32`, `48`, `64`, `128`, and `256`, plus the dedicated `256` installer ICO and `1024` runtime PNG.
- Linux packaging retains hicolor PNG sizes `16`, `24`, `32`, `48`, `64`, `128`, `256`, `512`, and `1024`.
- Existing production data remains under the legacy `ZCode` data directory.
