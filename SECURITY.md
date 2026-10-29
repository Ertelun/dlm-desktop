# Security Policy

Current supported distribution: **DLM Desktop 1.3.13/r224, Windows x64**.
Canonical Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.13

**1.3.13/r224：Chromiumの新しいCritical問題への緩和策として、埋込みブラウザーを一時停止しています。ライブラリ整理・検索・ローカル閲覧・手動取り込みは利用できます。ブラウザーを必要とする操作とブラウザーキャッシュ管理は停止中です。DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。再開には検証済みの修正版DLMが必要で、WebView2の更新だけでは解除されません。メインアプリの同梱.NET 10.0.14と実Runtimeガードにより、公開メタデータ・サムネイル通信のBrotli対応を安全に復旧しました。ブラウザー停止は継続します。**

**1.3.13/r224 temporarily disables the embedded browser to mitigate new Critical Chromium issues. Library organization, search, local viewing and Manual Intake remain available. Browser-dependent provider workflows and browser cache management are paused. Close DLM and extract the full official ZIP into a new empty folder. Recovery requires a reviewed DLM release; updating WebView2 alone does not lift the hold. HTTP Brotli support for public metadata/thumbnails is restored with patched .NET10.0.14 bundled with the main application and an actual-runtime guard; the browser hold remains.**

The browser hold mitigates CVE-2026-118306/118331/118348/118344 through the existing central gate, before Runtime discovery/profile/environment/controller creation. All Runtime versions are denied during this hold. The existing strict stable-version checks remain for a future reviewed recovery. This does not patch the external WebView2 engine. Microsoft is preparing a security fix. Do not treat an unreviewed preview or a Runtime-only update as recovery.

CVE-2026-111497 is addressed by bundling patched .NET10.0.14 for the main application. The three existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports restore Brotli negotiation/decoding only when the actual Runtime is the reviewed .NET10 line at10.0.14 or later. Older or unreviewed major Runtime lines retain gzip/deflate/identity without Brotli. Authorization, cookies, credentials and redirect boundaries remain unchanged; SDK10.0.402, ILLink10.0.12 and unrelated dependencies are retained. Known non-Critical or unconfirmed product-impacting candidates remain recorded locally; this release is not a claim that all dependencies are free of vulnerabilities.

Validation uses isolated synthetic data, not real libraries, credentials, purchases or provider downloads. No exploit/RCE testing is attempted. Vendor Critical severity plus the shared-engine path and actual benign product-route witness support the bounded mitigation decision. Individual FileSystem conditions are not claimed reproduced.

The ZIP is unsigned. Verify the official source and SHA-256; checksums confirm identity, not safety. Source/source archives/debug information remain local. Withdrawn1.3.6/r217 is excluded. Previous distributions are retained for history and rollback analysis; using a prior browser-enabled release reopens the removed exposure.

Report security vulnerabilities privately using this repository's Security reporting route. Do not put credentials, private data or unpatched exploit procedures in public Issues. There is no individual-support guarantee.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Brotli recovery sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 and https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json
