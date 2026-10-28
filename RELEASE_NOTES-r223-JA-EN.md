# DLM Desktop 1.3.12 / r223 — browser security hold

2026-10-28 · Windows x64 · Japanese / English · free · unsigned ZIP

## 日本語

Chromiumに新たに公開されたCriticalの問題（CVE-2026-118306、CVE-2026-118331、CVE-2026-118348、CVE-2026-118344）への緩和策として、埋込みブラウザーを一時停止します。対象はFileSystem、FileAPI、Skia、Layoutです。Microsoftは修正を準備中で、現時点で確認できた公式情報に、この4件を修正した安定版WebView2の個別マッピングはありません。

DLMはRuntime検出・プロフィール・Environment・controllerの作成前に中央ゲートで停止します。ライブラリ整理・検索・ローカル閲覧・手動取り込みは利用できます。ブラウザーを使う配信サービス操作とブラウザーキャッシュ管理は停止中です。再開には、公式修正の照合と製品検証を行った今後の修正版DLMが必要です。WebView2の更新だけでは解除されません。

更新：DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開してください。最上位EXEとapp/を一緒に使用します。既存のライブラリと設定は継続利用できます。前版のHTTP Brotli対策、同梱.NET10.0.12、SDK10.0.402、依存関係、ライセンス、検証済みDownloader Hostは維持しています。

この対応は製品のブラウザー到達経路を遮断する緩和策です。外部エンジンの修正や、全依存関係の無脆弱性を保証するものではありません。正規のHTMLだけを使った隔離確認で、実r222の中央ゲートからLayout/Canvas/File APIが利用されることを確認しました。悪用・任意コード実行テストは行っていません。FileSystem固有条件は一括して再現したとは扱いません。

## English

This security release temporarily disables the embedded browser to mitigate four newly disclosed Chromium Critical issues in FileSystem, FileAPI, Skia and Layout: CVE-2026-118306, CVE-2026-118331, CVE-2026-118348 and CVE-2026-118344. Microsoft says it is preparing a fix. No reviewed fixed stable WebView2 mapping for these four issues is available in the retrieved official information.

The existing central gate blocks before Runtime discovery, profile, environment or controller creation. Library organization, search, local viewing and Manual Intake remain available. Provider workflows requiring the embedded browser and browser cache management are paused. Recovery requires a future reviewed DLM release; updating WebView2 alone does not lift this hold.

To update, close DLM and extract the complete official ZIP into a new empty folder. Keep the top-level EXE with app/ beside it. Existing libraries/settings remain usable. The HTTP Brotli mitigation from r222, bundled .NET10.0.12, SDK10.0.402, dependency versions, licenses and the verified Downloader Host are retained.

This is a product-path mitigation, not an engine patch or blanket dependency-safety claim. A trusted synthetic HTML witness through the exact r222 packaged gate confirmed ordinary Layout, Canvas and File API access on the actual signed Runtime. No exploit or arbitrary-code-execution test was performed, and the FileSystem-specific conditions were not individually reproduced.

Validation details and public artifact hashes are provided with the formal Release. Source and source archives remain local and are not uploaded.

Sources: https://chromereleases.googleblog.com/2026/10/stable-channel-update-for-desktop_0562499947.html and https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
