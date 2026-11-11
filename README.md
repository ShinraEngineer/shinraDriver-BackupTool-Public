# Shinra Driver Tool

A portable Windows utility that **backs up and restores your device drivers** — export every
third-party (OEM) driver on a PC into a timestamped snapshot, then reinstall them on the same
or a freshly imaged machine.

## Download

**[⬇ Download the latest release](https://github.com/ShinraEngineer/shinraDriver-BackupTool-Public/releases/latest)**

- Windows 10 / 11, 64-bit
- **Portable** — nothing is installed; run the EXE from anywhere (USB stick, network share, a folder)
- Signed by **Shinra CC** (Authenticode, SHA-256, timestamped)
- Self-elevates — administrator rights are required

## What it does

- **Back up** all third-party drivers into `Driver-Backups\<HOST>-<timestamp>\` beside the EXE,
  each snapshot carrying a `manifest.json` (host, date, OS, package/INF counts). Backups are
  never overwritten — every run keeps its own snapshot.
- **Restore** drivers from any saved snapshot via `pnputil /add-driver /install`
  (with the 32→64-bit SysNative fix applied automatically).
- Optionally **remove ghost** (disconnected) devices after a restore.
- Full per-run transcript logs under `Driver-Backups\_logs\`.

If the EXE's own folder is read-only, backups fall back to
`%USERPROFILE%\Documents\ShinraDriverTool\Driver-Backups\`.

## Updates

This is the public download + release feed. The launcher reads this repo's release feed
(`releases/latest/download/update.json`) and installs the newer signed build. The source is private.
