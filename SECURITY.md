# Security Policy

Current supported distribution: **DLM Desktop 1.3.21/r232, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.21

埋込みブラウザーとWebView2を使うキャッシュ操作には、公式の安定版 WebView2 Runtime 157.0.4341.57 以降が必要です。DLMと公式Runtimeを更新し、DLMを再起動してください。

The embedded browser and WebView2-backed cache controls require official stable WebView2 Runtime 157.0.4341.57 or later. Update DLM and the official Runtime, then restart DLM.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation covers the admission gate, the actual signed Microsoft WebView2 engine, and browser workflows with isolated synthetic data.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis. r229 is the rollback option with its browser hold; browser-enabled older releases do not enforce the new floor.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/

# DLM Desktop 1.3.21 / r232

## 日本語

埋込みブラウザーとWebView2を使うキャッシュ操作には、公式の安定版 WebView2 Runtime 157.0.4341.57 以降が必要です。DLMと公式Runtimeを更新し、DLMを再起動してください。

Microsoft の Windows x64 Edge Stable の修正一覧では 157.0.4341.57 に CVE-2026-126879、CVE-2026-126885、CVE-2026-126895、CVE-2026-126911 が含まれます。CVE-2026-125350 の修正は .46 で配信済みです。Microsoft は .57 の WebView2 Evergreen と固定版を配信しています。

ライブラリ閲覧と手動取り込みは引き続き利用できます。DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。

## English

The embedded browser and WebView2-backed cache controls require official stable WebView2 Runtime 157.0.4341.57 or later. Update DLM and the official Runtime, then restart DLM.

Microsoft lists CVE-2026-126879, CVE-2026-126885, CVE-2026-126895 and CVE-2026-126911 in the Windows x64 Edge Stable .57 update. The CVE-2026-125350 fix shipped in .46. Microsoft distributes WebView2 .57 through Evergreen and Fixed Version channels.

Library browsing and manual import remain available. Close DLM and extract the complete ZIP into a new empty folder.

- [Official stable WebView2 download](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)
- [Microsoft Windows x64 Stable version and CVE feed](https://edgeupdates.microsoft.com/api/products?view=enterprise)
- [Microsoft Update Catalog WebView2 x64](https://www.catalog.update.microsoft.com/ScopedViewInline.aspx?updateid=6a525376-8d7d-4462-8dfc-fd67e1b9b33d)
