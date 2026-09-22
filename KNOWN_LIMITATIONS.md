# Known Limitations — Public Beta 2

- Public Beta 2 shipping scope is **Windows x64**.
- ARM64 is **not** qualified for Public Beta 2.
- Public Beta 2 is **unsigned** and may trigger Unknown Publisher / SmartScreen warnings.
- Distribution is a **ZIP package**, not an installer.
- The only canonical Public Beta binary source is `Ertelun/dlm-desktop` GitHub Releases.
- Provider-site behavior can change independently of DLM Desktop.
- Provider-assisted acquisition is limited to qualified ordinary-download flows.
- Protected, viewer-only, official-player-only, DRM-controlled and otherwise unsupported delivery modes remain on provider official routes.
- Login and official Download actions remain user-operated.
- **Standalone Manual Local Intake of arbitrary local works is not shipped as a completed Library-registration feature in Public Beta 2.**
- Some provider-handoff UI can select and validate a local folder, but that validation helper does not by itself complete new local-work promotion/registration.
- Very large archives may take several minutes after download because integrity validation, extraction, physical copy and final SHA-256 verification are intentionally retained.
- Backup / Restore in this Beta is for **DLM user state**; it is not a backup of all original purchased works.
- Users with important libraries should maintain independent backups of irreplaceable original files.
- Public Beta compatibility/usability are still being improved.
- No update cadence is promised by this Beta.
