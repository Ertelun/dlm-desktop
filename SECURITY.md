# Security Policy

Current supported distribution: **DLM Desktop 1.3.23/r234, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.23

# DLM Desktop 1.3.23 / r234

## 日本語

埋込みブラウザーとWebView2を使うキャッシュ操作の最低許可版を、公式安定版 WebView2 Runtime **158.0.4370.33** に更新しました。DLMと公式Runtimeを更新し、DLMを再起動してください。旧Runtimeでは対象操作を開始する前に更新を案内します。ライブラリ閲覧と手動取り込みは引き続き利用できます。

MicrosoftのWindows x64安定版の修正一覧に含まれるANGLE、WebGL、GPU、Colorの問題に対応するための最小更新です。同梱.NET、ネイティブライブラリと既存の認証・ダウンロード・ファイル境界は維持します。

DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。既存の作品やユーザーデータを削除する必要はありません。

## English

Embedded browsing and WebView2-backed cache operations now require official Stable WebView2 Runtime **158.0.4370.33 or later**. Update DLM and the official Runtime, then restart DLM. Older Runtimes are rejected before those operations begin. Library browsing and Manual Intake remain available.

This minimal update requires the Microsoft Windows x64 Stable fixes for ANGLE, WebGL, GPU and Color: CVE-2026-130971, CVE-2026-130994, CVE-2026-131031 and CVE-2026-131061. Bundled .NET, native dependencies and existing credential, download and filesystem boundaries are retained. Other unmapped Chromium findings and standalone PDFium applicability remain under review; this release does not claim to resolve them.

Close DLM and extract the complete ZIP into a new empty folder. Keep existing works and user data.

- [Official WebView2 Runtime download](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)
- [Microsoft security update notes](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security)
- [Microsoft Windows x64 Stable version and CVE feed](https://edgeupdates.microsoft.com/api/products?view=enterprise)
- [WebView2 Runtime distribution and security updates](https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution)


CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation covers the admission gate, the actual signed Microsoft WebView2 engine, and browser workflows with isolated synthetic data.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis. r229 is the rollback option with its browser hold; browser-enabled older releases do not enforce the new floor.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/
