# Changelog

## 1.0.0 — 2026-11-11

- First public, signed release of the Shinra Driver Tool.
- Back up every third-party driver into a timestamped snapshot with a `manifest.json`.
- Restore drivers from any saved snapshot (`pnputil`, with the 32→64-bit SysNative fix).
- Optional ghost-device (disconnected) cleanup after a restore.
- Portable, self-contained, self-elevating; signed by Shinra CC and timestamped.
- Published to the launcher release feed (`update.json`) for managed updates.
