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
