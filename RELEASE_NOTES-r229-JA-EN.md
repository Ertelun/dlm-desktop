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
