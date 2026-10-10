# Known Limitations — DLM Desktop 1.3.2（r213）

- The qualified package is an **unsigned Windows x64 ZIP**. ARM64 has not been qualified. Windows may display Unknown Publisher / SmartScreen notices.
- Extract the complete ZIP. Keep `app/` beside `DoujinLibraryManagerDesktop.exe`; it contains the bundled .NET runtime and supporting files.
- The embedded browser requires **Microsoft Edge WebView2 Runtime**.
- The canonical public binary source is [Ertelun/dlm-desktop Releases](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.2).
- GitHub's automatically generated “Source code” ZIP/TAR contains public documentation, not the application build source.
- UI language is System / Japanese / English. Changing it requires an application restart. Work titles, creator names, and site metadata are not machine-translated.
- Provider-site behavior can change independently of DLM. Supported acquisition depends on the specific delivery mode; see [Provider Capabilities](PROVIDER_CAPABILITIES.md).
- Sign-in, purchases, and download initiation remain user-operated on official pages. Protected, viewer-only, official-player-only, DRM-controlled, and unsupported modes stay on provider official routes.
- DLsite multipart files are grouped with their original names. DLM does not join them or automatically run `part1.exe`.
- **GOG requires explicit “Finalize GOG intake and register” (`GOG受付を確定して登録`) after all required files have been saved.** Pending downloads/validation prevent finalization. DLM stores installers without running/unpacking them.
- Membership/fan-site intake is for one selected post and files explicitly saved by the user. Asset enumeration, creator-post crawling, and background sync are not provided.
- Metadata/thumbnail retrieval is best-effort within supported flows; not every page or work yields metadata.
- Standalone Manual Local Intake for registering arbitrary local folders is not provided. Some existing provider-handoff screens offer folder selection/validation as a helper.
- Large downloads can require additional time for integrity checks, extraction where supported, physical copy, and final SHA-256 verification.
- Backup / Restore covers **DLM user state**, not all original purchased files. Maintain separate backups of irreplaceable original files.
- Verification records describe the tested scope; they do not establish exhaustive compatibility with every site/delivery mode or external security certification.
- No future update cadence is promised.
