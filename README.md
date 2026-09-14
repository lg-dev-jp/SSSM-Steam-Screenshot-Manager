# SSSM - Steam Screenshot Manager

Steam screenshots, made easier to revisit.

[日本語](README_ja.md)

### [⬇ Download SSSM Public Beta](https://github.com/lg-dev-jp/SSSM-Steam-Screenshot-Manager/releases)

Free. No ads. No tracking. Portable. No account required.

## Overview

SSSM is a local-first Windows application for browsing Steam screenshots by game and date. This repository is currently for binary distribution and documentation. Source code is not published with this Public Beta.

## Features

- Automatic Steam detection and multiple local Steam accounts
- Game library, search, favorites and sorting
- Realtime detection of new F12 screenshots
- Date-grouped gallery, sticky dates and newest/oldest order
- Memories slideshows with multiple games and years, and adjustable speed
- Image viewer, clipboard copy, open folder and Recycle Bin deletion
- Hidden Games, temporary Show hidden games and Streamer Mode
- Localized game titles and artwork with reusable caches
- Fast startup from a saved library, with folder checks in the background
- Portable settings, artwork, logs and update downloads
- Updates through GitHub Releases

Hidden games are always excluded from Memories, including when Show hidden games is enabled. Streamer Mode masks identifying text in SSSM; it does not hide image content or external Windows dialogs.

## Supported languages

English, 日本語, 简体中文, 繁體中文, Русский, Español, Português (Brasil), Deutsch and 한국어.

## Requirements

- Windows 10/11 x64
- Microsoft Edge WebView2 Runtime (x64)
- Microsoft .NET Framework 4.8 or later, with x64 support (4.8.1 also works). The modern .NET / .NET Desktop Runtime does not replace this requirement.
- No Python installation or SSSM installer is needed for the Portable version.

This is a Public Beta. Windows SmartScreen may show a first-run warning for the unsigned application. Verify the official download and checksum before deciding to run it.

## Installation

1. Download the Portable ZIP from the [official GitHub Releases](https://github.com/lg-dev-jp/SSSM-Steam-Screenshot-Manager/releases).
2. Extract the entire ZIP to a writable folder.
3. Open the `SSSM_Portable` folder and run `SSSM.exe` (`SSSM_Portable/SSSM.exe`).

Keep `SSSM.exe`, `SSSMUpdater.exe`, `SSSM.exe.config` and `_internal` together in the Portable folder. Steam recordings and videos are not supported.

## Portable data

SSSM creates `data/` beside the EXE. Settings, favorites, hidden games, metadata, artwork, logs, WebView profile and updater files remain there. Move the entire folder to keep your setup. SSSM does not intentionally store persistent app data in AppData, ProgramData, Windows Temp or the Registry. Windows and WebView2 may use their own operating-system storage.

## Privacy

No ads, tracking, SSSM account or user-supplied Steam API key. SSSM does not request Steam login credentials. Your screenshots stay on your PC and are not uploaded to an SSSM server. Steam HTTPS requests retrieve game information and artwork; cached information reduces repeated requests. Update checks and downloads use HTTPS requests to GitHub. Local screenshots remain available when network services cannot be reached. Logs can contain local paths and account names: review them before sharing.

## Updating

Settings > About > Check for updates checks GitHub Releases. Automatic checks run at most about once per 24 hours, and do not block Steam browsing. Beta/RC builds can receive prereleases; stable builds ignore them. With no published release, automatic checks stay quiet.

The Portable updater downloads under `data/updates`, verifies SHA-256, stages application files, waits for SSSM to exit, preserves `data/`, replaces app files and restarts SSSM. Failed replacements attempt rollback; backups remain under `data/updates`. Download or verification failures leave installed files unchanged. Keep a backup before any beta update. SHA-256 detects corruption; it is not an independent publisher signature.

For manual updates, close SSSM, extract the new ZIP into a separate folder, then copy your existing `data/` into that folder. Keep the old folder until you confirm the new version works.

## Troubleshooting

- If Steam is not detected, choose its folder in Settings or add a screenshot folder.
- If startup fails, check WebView2 Runtime and extract the complete ZIP to a writable local folder. Keep `SSSM.exe.config` beside the EXE; it supports the existing downloaded-file startup handling. Do not disable Windows security globally.
- If Steam temporarily limits requests, leave SSSM open: it preserves caches and resumes automatically after the displayed wait.
- If an update fails, use the existing version or download the ZIP manually. Inspect `data/logs` and `data/updates/updater.log` before sharing diagnostics.

## Feedback

Send feedback and reproducible bug reports to [Issues in the official GitHub repository](https://github.com/lg-dev-jp/SSSM-Steam-Screenshot-Manager/issues). Include the SSSM version and steps to reproduce, and remove personal information before sharing logs or screenshots.

## Distribution

SSSM is free to use. The source code is not currently published. Please download SSSM only from the [official GitHub repository](https://github.com/lg-dev-jp/SSSM-Steam-Screenshot-Manager). Redistribution is not permitted. Modified or repackaged unofficial builds are not supported. Copyright LG; all rights reserved. Full third-party license notices are included in the Portable ZIP as `THIRD_PARTY_NOTICES.md`.

## Support

SSSM is free, with no ads or tracking. Optional ways to support continued development may be added in the future.
