# Security Policy

Current supported distribution: **DLM Desktop 1.3.14/r225, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.14

**1.3.14/r225：修正収録を確認した安定版Microsoft Edge WebView2 Runtime 156.0.4314.58以降で、埋込みブラウザーとブラウザーキャッシュ管理を復旧しました。古い版・不明な版・プレビュー版は引き続き拒否します。DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開してください。ブラウザー利用時は公式WebView2 Runtimeも更新してDLMを再起動してください。.NET 10.0.14によるHTTP Brotli対応と認証情報・Cookie・リダイレクトの境界は維持しています。**

**1.3.14/r225 restores the embedded browser and browser cache management with reviewed stable Microsoft Edge WebView2 Runtime 156.0.4314.58 or later. Older, unknown and preview versions remain denied. Close DLM and extract the complete official ZIP into a new empty folder. For browser workflows, also update the official WebView2 Runtime and restart DLM. Patched .NET10.0.14 HTTP Brotli support and credential, cookie and redirect boundaries are retained.**

The reviewed stable WebView2 floor156.0.4314.58 restores the embedded browser and disk-cache management after official Microsoft fixed-version mapping and actual-runtime validation. Stable-only selection, strict version parsing, pre-profile available-version admission and post-environment recheck remain. This release does not bundle/install WebView2 or claim every dependency is vulnerability-free.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation uses isolated synthetic data, not real libraries, credentials, purchases or provider downloads. No exploit/RCE testing is attempted. Vendor Critical severity plus the shared-engine path and actual benign product-route witness support the bounded mitigation decision. Individual FileSystem conditions are not claimed reproduced.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis; using a prior browser-enabled release reopens the removed exposure.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/
