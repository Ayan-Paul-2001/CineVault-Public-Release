<div align="center">

<img src="logo.svg" alt="CineVault Logo" width="84" height="84" />

# CineVault — Public Release

**Official signed Android release package and version-control manifest for CineVault — All in One Movie Server.**

</div>

---

## Release Files

- `CineVault.apk` — Signed standalone Android release APK (`applicationId: com.cinevault.app`).
- `version.json` — Version-control update manifest (`appVersion`, `appDisplayVersion`, `appVersionCode`, `apkPackage`, `sha256`, `changelog`, `accessControl`).
- `SHA256SUMS.txt` — SHA-256 integrity checksum for verifying `CineVault.apk`.

## Auto-Update System

- CineVault checks `version.json` over HTTPS via global CDN in the background every **60 minutes** (scaling seamlessly to millions of concurrent users with zero API rate limits).
- When a newer version is published, CineVault displays a **3-second update popup** and keeps the update ready inside **Servers -> App Updates**.
- Users can also tap **Check for Updates** manually anytime inside the **Servers** tab.
- If `accessControl.forceUpdateEnabled` / `forceAppUpdate` is `true` or the installed version is below `minAppVersion`, CineVault shows a mandatory update lock dialog using `lockTitle` and `lockMessage`.

## Privacy & Per-Device Isolation

- Every Android device runs its own completely standalone on-device SQLite database inside Android's private app sandbox (`allowBackup="false"`, cloud backup and device transfer disabled).
- Each device generates its own unique local session identifier, preserving its own Watch History, Continue Watching progress, Watchlist, and preferences strictly on that device with zero interference across concurrent users.
