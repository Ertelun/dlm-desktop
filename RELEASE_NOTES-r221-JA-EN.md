# DLM Desktop 1.3.10 / r221 — ブラウザー再開・作品の更新確認修正

2026-10-24 · Windows x64 · ZIP · 日本語 / English · 無料 / Free · コード署名なし / Unsigned

## 日本語

Microsoftの公式修正情報と、修正済みWebView2 Runtimeの隔離検証を確認し、埋込みブラウザーを再開しました。**Microsoft Edge WebView2 Runtime 156.0.4314.42以降の安定版**が必要です。旧版、不明な版、プレビュー版では外部ページを開きません。検出時と実際のブラウザー環境を生成した後に、版を再確認します。

作品の「アップデート確認」で、選択した作品の公式商品ページへ通信する前に処理が拒否され、「公式商品ページを確認できませんでした」と表示される問題も修正しました。更新確認中だけ同一作品の公開ページを読み取り、終了・失敗・キャンセル後に通信の許可を残しません。バックグラウンド同期や別作品の取得には広げません。

更新方法:

1. 古いDLM Desktopを終了し、この版のZIP全体を新しい空フォルダーへ展開します。最上位のEXEと`app/`を一緒に使用してください。
2. 必要に応じて[Microsoft公式WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)を156.0.4314.42以降の安定版へ更新します。DLMのZIPはWebView2 Runtimeを同梱・自動インストールしません。
3. DLMを起動し直します。既存のライブラリとユーザー設定を引き続き使用できます。今後のEvergreen Runtime更新後もDLMを再起動してください。

公式CVRFはCVE-2026-113072 / 113271 / 113279 / 113280 / 113303の修正ビルドを156.0.4314.42としています。Microsoft署名付きの同版Runtimeで、通常DOMの対照試験と、CSS疑似要素がLCP APIからDOM要素として露出しない修正後の挙動を無害な隔離ページで確認しました。任意コード実行や危険なDOM操作の試験ではありません。

23プロジェクト、最終配布アセンブリに対する6つの回帰ランナー、起動・ZIP整合性・ソース/デバッグ情報の除外を検証しました。検証結果の詳細はReleaseのVERIFICATIONをご覧ください。実アカウントでのログイン、購入、実作品のダウンロードは検証に使用していません。すべてのサイト・作品・依存部品の安全性を一括して保証するものではありません。

既存の閲覧・削除修正、.NET 10.0.12、依存部品と検証済みDownloader Hostを保持しています。製品ソースとデバッグ情報は公開配布に含めません。

## English

Embedded browsing is available again after review of Microsoft's fixes and isolated validation of the corrected WebView2 Runtime. **Microsoft Edge WebView2 Runtime 156.0.4314.42 or later from the stable channel is required.** Old, unknown and preview Runtime versions are rejected before external content is opened. DLM checks the discovered version and checks the actual environment again before creating a controller.

This release also fixes a work's **Check for updates** action being rejected before contacting its official product page, producing a misleading page-unavailable warning. An explicit update check now grants a temporary, read-only scope for that selected product. The scope ends on completion, failure or cancellation; it does not enable background synchronization or unrelated product requests.

To update:

1. Close the old DLM, extract the complete ZIP into a new empty folder, and keep the top-level EXE with `app/` beside it.
2. If necessary, update the stable Runtime from [Microsoft's official WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/). The DLM ZIP does not bundle or install WebView2.
3. Restart DLM. Existing libraries and user settings remain usable. Restart DLM after future Evergreen Runtime updates as well.

Microsoft's CVRF identifies 156.0.4314.42 as the fixed build for CVE-2026-113072,113271,113279,113280 and113303. A benign isolated observation on the Microsoft-signed Runtime confirmed the corrected CSS pseudo-element/LCP behavior with an ordinary-DOM control. No arbitrary-code-execution or unsafe DOM-mutation test was attempted.

All 23 projects, 6 exact-package regression runners, startup/ZIP integrity and product source/debug exclusion were validated. See the release's VERIFICATION asset for the precise scope. Tests did not use real accounts, purchases or real work downloads. These checks do not certify every provider, work or dependency.

Existing viewing/deletion fixes, .NET 10.0.12, dependencies and the verified Downloader Host are retained. Product source and debug information remain local.

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.10

Manual: https://github.com/Ertelun/dlm-desktop/blob/main/MANUAL.md

Official security information: https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security

Vendor fixed-build data: https://api.msrc.microsoft.com/cvrf/v3.0/cvrf/2026-Oct
