# Security Policy

Current supported distribution: **DLM Desktop 1.3.15/r226, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.15

**1.3.15/r226：「ダウンロードキャッシュを削除」で、通常キャッシュに加えて管理領域に残ったダウンロードファイルも削除できるよう修正しました。失敗・再試行用ファイルを含む件数と容量を確認してから削除します。転送・取り込み中は削除せず、使用中・変更済み・削除失敗も結果に表示します。作品本体、保存サムネイル、Cookie・ログイン状態は保持します。**

**1.3.15/r226 fixes download-cache cleanup so it can also discard retained files in the managed download landing area after confirmation. The prompt includes the file count and byte total and warns about failed imports and retry files. Active transfers/imports block cleanup; locked, changed and failed files are reported. Library works, stored thumbnails, cookies and login state are preserved.**

The reviewed stable WebView2 floor156.0.4314.58 restores the embedded browser and disk-cache management after official Microsoft fixed-version mapping and actual-runtime validation. Stable-only selection, strict version parsing, pre-profile available-version admission and post-environment recheck remain. This release does not bundle/install WebView2 or claim every dependency is vulnerability-free.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation uses isolated synthetic data, not real libraries, credentials, purchases or provider downloads. No exploit/RCE testing is attempted. Vendor Critical severity plus the shared-engine path and actual benign product-route witness support the bounded mitigation decision. Individual FileSystem conditions are not claimed reproduced.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis; using a prior browser-enabled release reopens the removed exposure.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/
