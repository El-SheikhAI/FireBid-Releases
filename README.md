# FireBid Releases

Public release artifacts for the **FireBid** Windows desktop application.

This repository contains **no source code** — only the built installer and the
auto-update manifest consumed by the installed app.

## Assets per release

| File | Purpose |
| --- | --- |
| `FireBid_<version>_x64-setup.exe` | Windows per-user installer (NSIS) |
| `FireBid_<version>_x64-setup.exe.sig` | Minisign signature of the installer |
| `latest.json` | Tauri updater manifest (version, notes, download URL, signature) |

## Auto-update

The installed app checks `releases/latest/download/latest.json` on every launch.
When a newer version is present it is downloaded, verified against the embedded
public key, installed and the app restarts — no user action required.

## Requirements

- Windows 10/11 x64
- Microsoft Edge WebView2 Runtime (preinstalled on modern Windows)
