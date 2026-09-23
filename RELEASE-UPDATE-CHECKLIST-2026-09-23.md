# Public Beta 2 JA/EN in-place update checklist

Date: 2026-09-23 JST
Release: `v0.1.0-beta.2`
Target repository: `Ertelun/dlm-desktop`

## Prepared identity

- New package filename: `DLD-160-Desktop-win-x64-HOTFIX-r2-localbuild-r98.zip`
- New package SHA-256: `66dd0661298a7f8bc906a29fc4e8f99a5406ea346989a936ab11737c76165272`
- New package build time: `2026-09-23T07:59:41.7640131+09:00`
- SDK: `.NET SDK 10.0.401`
- Localization source: `DLM-EN-r98-customer-ui-r7-2026-09-23.zip`
- Localization source SHA-256: `0ec1770b87d2a9ea766b546f70b551ed5ce1cbd3d96c1524fb1f1614224899f5`
- Replaced Beta 2 package SHA-256: `b3174d3206f53005192cac50423950625b3b8de9d4fec619a18255b93ed7b7cf`

## Before merge / publication

- [x] Exact uploaded replacement ZIP SHA-256 matches supplied sidecar.
- [x] Public repository current release/tag and old asset identity captured.
- [x] README updated for Japanese/English UI and new package SHA-256.
- [x] Known Limitations updated for localization boundaries.
- [x] PROVENANCE records new source/package identity and replaced digest.
- [x] SHA256SUMS updated to the replacement package/source identities.
- [x] JA/EN release notes prepared.
- [ ] Review changes and update `main`.
- [ ] Replace the existing same-name release asset on `v0.1.0-beta.2`.
- [ ] Upload/update the checksum sidecar using `66dd0661298a7f8bc906a29fc4e8f99a5406ea346989a936ab11737c76165272`.
- [ ] Update the GitHub Release body from `RELEASE_NOTES-r98-JA-EN.md`.
- [ ] Re-download the public asset and independently verify SHA-256 = `66dd0661298a7f8bc906a29fc4e8f99a5406ea346989a936ab11737c76165272`.
- [ ] Confirm README, Release body, asset digest, sidecar, and `PROVENANCE.json` all agree.
- [ ] Only after those checks, announce the JA/EN update publicly.

## Important

Because the old and new Public Beta 2 binaries have the same filename, do not leave the old asset and new checksum visible at the same time. Treat the release-asset replacement and checksum/body update as one publication operation.
