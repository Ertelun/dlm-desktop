# DLM Desktop 1.3.9 / r220 — セキュリティ緩和策 / Security mitigation

2026-10-21 · Windows x64 · ZIP · Japanese/English · unsigned

## 日本語

WebView2が使用するChromiumのCSS処理に新しいCriticalの問題（CVE-2026-113072）が公開されました。DLM 1.3.8/r219とWebView2 155.0.4283.62の隔離検証で、修正前の条件が残っていることを無害な参照試験で確認しました。任意コード実行の試験は行っていません。

Microsoftはセキュリティ修正を準備中と案内しています。1.3.9/r220は、埋込みブラウザーを起動前に一時停止する暫定対策です。WebView2エンジン自体の修正を含むものではありません。

- ライブラリの整理、検索、ローカル閲覧、手動取り込みを維持します。
- 埋込みブラウザーを使うプロバイダー連携とブラウザーのキャッシュ管理は一時停止します。
- WebView2の更新だけでは解除されません。再開には、Microsoftの修正を確認して検証した今後のDLM正式版が必要です。
- 旧DLMを終了し、ZIP全体を新しい空フォルダーに展開して、最上位のDoujinLibraryManagerDesktop.exeを起動してください。app/フォルダーも必要です。既存のライブラリやユーザー設定は引き続き使用できます。
- 1.3.8/r219以前は今回の緩和策を持たないため、推奨するセキュリティのロールバック先にはしません。

無関係な機能・UI・依存パッケージ・SDKの更新は含めません。.NET 10.0.12と検証済みDownloader Hostを維持します。ソースとデバッグ情報は公開配布に含めません。

## English

Chromium published a new Critical CSS issue, CVE-2026-113072. A benign, isolated observation through DLM1.3.8/r219's packaged browser admission code confirmed the unfixed prerequisite in WebView2 155.0.4283.62. No arbitrary-code-execution test was attempted.

Microsoft says it is preparing a security fix. DLM1.3.9/r220 temporarily blocks the embedded browser before Runtime discovery, browser profile creation, or controller creation. This is a product mitigation; it does not patch the WebView2 engine.

- Library organization, search, local viewing, and Manual Intake remain available.
- Provider workflows requiring the embedded browser and browser cache management are temporarily unavailable.
- Updating WebView2 alone does not lift the hold. Recovery requires a future DLM release after Microsoft's fix has been reviewed and validated.
- Close the old DLM. Extract the entire ZIP into a new, empty folder, then run the top-level DoujinLibraryManagerDesktop.exe with app/ beside it. Existing libraries and user settings remain usable.
- Releases1.3.8/r219 and earlier lack this mitigation and are not the recommended security rollback.

Unrelated features, UI, dependency packages, and SDKs are unchanged. .NET10.0.12 and the verified Downloader Host are retained. Product source and debug information remain local.

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.9
Microsoft status: https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
Official CVE record: https://www.cve.org/CVERecord?id=CVE-2026-113072
