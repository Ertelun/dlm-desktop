> **1.3.18/r229：埋込みブラウザーとWebView2を起動するキャッシュ操作を安全のため一時停止しています。ライブラリ・ローカル閲覧・手動取り込みは利用できます。WebView2の更新だけでは解除されません。**
>
> **Embedded browser and WebView2-backed cache operations are temporarily paused. Library, local viewing and Manual Intake remain available. A reviewed DLM recovery release is required; updating WebView2 alone does not lift this hold.**

# Security Policy

Current supported distribution: **DLM Desktop 1.3.18/r229, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.18

**1.3.18/r229：新規Chromium Criticalへの緩和として埋込みブラウザーを一時停止しました。r228までの修正と既存のHTTP安全策は保持します。**

**1.3.18/r229 temporarily pauses the embedded browser for new Chromium Critical advisories. Earlier r228 corrections and existing HTTP safeguards are retained.**

r225以前のCriticalへの復旧判定は新しいCriticalへの解除根拠にはしません。r229はRuntime検出前に停止し、修正済み安定版WebView2への収録と製品の検証を完了した復旧版で解除します。 / Earlier recovery evidence does not establish fixes for the new Critical advisories. r229 blocks before Runtime discovery; a validated DLM recovery release is required.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation uses isolated synthetic data, not real libraries, credentials, purchases or provider downloads. No exploit/RCE testing is attempted. Vendor Critical severity plus the shared-engine path and actual benign product-route witness support the bounded mitigation decision. Individual FileSystem conditions are not claimed reproduced.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis; using a prior browser-enabled release reopens the removed exposure.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json

Browser recovery sources: https://edgeupdates.microsoft.com/api/products?view=enterprise ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security ; https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution ; https://developer.microsoft.com/en-us/microsoft-edge/webview2/

# DLM Desktop 1.3.18 / r229 — Browser security hold

埋込みブラウザーを安全のため一時停止しました。ChromiumのPrerender / Core / Dawn / Geometryの新規Critical情報（CVE-2026-121035、121126、121156、121203）に対し、DLMが利用する安定版WebView2への修正収録を確認できるまで、Runtimeの探索・プロファイル作成・環境・コントローラー作成より前で遮断します。これは外部Runtime自体の修正ではありません。

The embedded browser is temporarily paused in response to new Chromium Critical advisories affecting Prerender, Core, Dawn and Geometry (CVE-2026-121035, CVE-2026-121126, CVE-2026-121156, CVE-2026-121203). The central product gate blocks before Runtime discovery, profile, environment or controller creation while a fixed stable WebView2 mapping remains unverified. This mitigates the product browser route; it does not patch the external engine or claim that every CVE was reproduced in DLM.

- 配信元の埋込みブラウザー操作と、WebView2の起動を伴うブラウザーキャッシュ操作は一時停止します。
- ライブラリ、ローカル閲覧、手動取り込みと、既存のHTTP側.NET 10.0.14/Brotli安全策は継続します。r228のダウンロード開始修正も保持します。
- 安定版Runtimeが更新されても、このアプリ側停止は解除されません。各対象CVEの修正収録と実際の安定版Runtime、製品の回帰・最終ZIP検証を通したDLM復旧版で解除します。安全に独立復旧できる経路は毎時再評価します。

Provider browser flows and WebView2-backed browser-cache operations are paused. Library management, local viewing and Manual Intake remain available. The existing .NET 10.0.14 HTTP decompression guard and r228 download-start correction are retained. Updating WebView2 alone does not lift this hold; a reviewed DLM recovery release is required.

Windows x64, unsigned ZIP. Close DLM, extract the complete ZIP into a new empty folder, and keep the top-level EXE and app/ together. DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。EXEとapp/を一緒に保持します。SDK、Runtime、依存ライブラリの一括更新は含みません。製品ソース・ソースZIPは公開しません。

Primary sources:
- https://chromereleases.googleblog.com/2026/11/stable-channel-update-for-desktop.html
- https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
- https://edgeupdates.microsoft.com/api/products?view=enterprise

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.18
