# CineVault Public Release

Public Android release package and version-control manifest for **CineVault — All in One Movie Server**.

## Files

- `CineVault.apk` — Signed standalone Android release APK (`applicationId: com.cinevault.app`).
- `version.json` — Version-control update manifest (`appVersion`, `appDisplayVersion`, `appVersionCode`, `apkPackage`, `sha256`, `changelog`, `accessControl`).
- `SHA256SUMS.txt` — SHA-256 checksum for verifying `CineVault.apk`.

## Auto-Update Behavior

- CineVault automatically checks `version.json` in the background every **60 minutes** (as well as on startup when 60 minutes have elapsed).
- When a new version is published, CineVault shows a **3-second new update popup** and makes the update available in **Servers -> App Updates**.
- Users can also tap **Check for Updates** manually anytime inside the **Servers** tab.
- If `accessControl.forceUpdateEnabled` / `forceAppUpdate` is `true` or the installed version is below `minAppVersion`, CineVault displays a mandatory update dialog with `lockTitle` and `lockMessage`.
