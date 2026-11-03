# Security Policy

Current supported distribution: **DLM Desktop 1.3.16/r227, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.16

**1.3.16/r227：DMM/FANZA・DLsite・BOOTHで登録済み作品をダウンロード開始時に確認し、同じ配信元・作品IDがライブラリにあればスキップします。照合中は転送を一時停止。更新や取り直しには作品詳細の「再ダウンロード」を使用してください。作品IDが不明な場合や内容ハッシュで識別するサービスは、完了後の検証を継続します。**

**1.3.16/r227 checks supported DMM/FANZA, DLsite and BOOTH product IDs when a download starts and skips works already registered in any configured library. Transfers pause during the local check. Use Redownload in the work details for intentional updates or replacements. Unknown and content-hash identities retain completed-file verification.**

The reviewed stable WebView2 floor156.0.4314.58 restores the embedded browser and disk-cache management after official Microsoft fixed-version mapping and actual-runtime validation. Stable-only selection, strict version parsing, pre-profile available-version admission and post-environment recheck remain. This release does not bundle/install WebView2 or claim every dependency is vulnerability-free.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation uses isolated synthetic data, not real libraries, credentials, purchases or provider downloads. No exploit/RCE testing is attempted. Vendor Critical severity plus the shared-engine path and actual benign product-route witness support the bounded mitigation decision. Individual FileSystem conditions are not claimed reproduced.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis; using a prior browser-enabled release reopens the removed exposure.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/
