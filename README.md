<div align="center">

<img src="logo.svg" alt="CineVault Logo" width="84" height="84" />

# CineVault — Public Release

**Official signed Android release package and version-control manifest for CineVault — All in One Movie Server.**

</div>

---

## Release Files

- `CineVault.apk` — Signed standalone universal Android release APK for **Android Phones, Tablets, and Android TV / Google TV** (`applicationId: com.cinevault.app`).
- `version.json` — Version-control update manifest (`appVersion`, `appDisplayVersion`, `appVersionCode`, `apkPackage`, `sha256`, `changelog`, `accessControl`).
- `SHA256SUMS.txt` — SHA-256 integrity checksum for verifying `CineVault.apk`.

## Supported Devices

- **Android Phones (Android 7.0+ / API 24–35):** Edge-to-edge mobile shell, 5-tab bottom navigation, VLC-style touch sliders (left brightness, right volume + 200% sound boost), 2-finger pinch-to-zoom, and 8 video aspect/size modes.
- **Android Tablets:** Responsive widescreen top navigation bar, larger poster grids (4–6 columns), taller Cinema Hero spotlight, and centered detail & server views.
- **Android TV / Google TV:** Native TV Home Screen launcher (`LEANBACK_LAUNCHER` + official `640x360` TV banner), glowing D-Pad focus highlights and card zoom animations, top navigation bar, and full TV remote playback controls (Play/Pause, D-Pad seek, 15s timeline stepping, Aspect/Zoom cycling, Captions, Menu, and Search).

## Auto-Update System

- CineVault checks `version.json` over HTTPS via global CDN in the background every **60 minutes** (scaling seamlessly to millions of concurrent users with zero API rate limits).
- When a newer version is published, CineVault displays a **3-second update popup** and keeps the update ready inside **Servers -> App Updates**.
- Users can also tap **Check for Updates** manually anytime inside the **Servers** tab.
- If `accessControl.forceUpdateEnabled` / `forceAppUpdate` is `true` or the installed version is below `minAppVersion`, CineVault shows a mandatory update lock dialog using `lockTitle` and `lockMessage`.

## Privacy & Per-Device Isolation

- Every Android device runs its own completely standalone on-device SQLite database inside Android's private app sandbox (`allowBackup="false"`, cloud backup and device transfer disabled).
- Each device generates its own unique local session identifier, preserving its own Watch History, Continue Watching progress, Watchlist, and preferences strictly on that device with zero interference across concurrent users.
