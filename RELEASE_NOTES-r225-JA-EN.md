# DLM Desktop1.3.14/r225 — Browser recovery / ブラウザー復旧

安定版Microsoft Edge WebView2 Runtime156.0.4314.58以降で、埋込みブラウザーを使う既存のプロバイダー操作とブラウザーのディスクキャッシュ管理を復旧しました。Microsoftの156.0.4314.56で旧4Critical（CVE-2026-118306/118331/118348/118344）、156.0.4314.58でCVE-2026-76024の修正収録を確認しています。

Restores existing provider browser workflows and browser disk-cache management with reviewed stable WebView2 Runtime156.0.4314.58 or later. Strict old/unknown/preview rejection, stable-only discovery and actual-environment recheck remain. This ZIP does not bundle or install WebView2.

DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開してください。公式WebView2 Runtimeを156.0.4314.58以降へ更新し、DLMを再起動してください。EXEとapp/は一緒に保持します。既存のライブラリ・設定は継続利用できます。

Close DLM and extract the complete official ZIP into a new empty folder. Also update the official stable WebView2 Runtime to156.0.4314.58 or later, then restart DLM. Keep the top-level EXE and app/ together. Existing libraries/settings remain usable. Unsupported Runtime keeps browser workflows unavailable; local organization/viewing/Manual Intake remain available.

Main .NET10.0.14, the guarded HTTP Brotli recovery fromr224, SDK10.0.402, unrelated dependencies and retained r218 Downloader Host/runtime10.0.12 are unchanged. No real account/library data was used. Source and source ZIP remain local. The product ZIP remains unsigned.

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.14
Official mapping: https://edgeupdates.microsoft.com/api/products?view=enterprise
Security notes: https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
WebView2 updates: https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution
Official runtime download: https://developer.microsoft.com/en-us/microsoft-edge/webview2/

Fresh final source/ZIP regression, live local WebView2 engine and cache-cookie-preservation checks, startup/major-operation and distribution validation are required before publication; final records accompany the Release.
