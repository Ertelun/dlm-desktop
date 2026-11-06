# DLM Desktop 1.3.19 / r230 — Browser recovery

安定版WebView2 Runtime **157.0.4341.42以降**を条件に、埋込みブラウザーとWebView2を使うブラウザーキャッシュ操作を復旧しました。MicrosoftのWindows x64安定版修正対応表はCVE-2026-121035、121126、121156、121203を含み、同版の公式WebView2配布・実エンジンを照合しています。古い版・不明な版・プレビュー版は引き続き拒否し、環境作成後も実際のRuntime版を再確認します。

The embedded browser and WebView2-backed browser-cache operations are restored behind a minimum **stable WebView2 Runtime157.0.4341.42** gate. Microsoft's Windows x64 stable fix mapping includes CVE-2026-121035, CVE-2026-121126, CVE-2026-121156 and CVE-2026-121203; the official same-version WebView2 distribution and actual engine are verified. Older, unknown and preview Runtime versions remain denied, including an unsafe selection change after environment creation.

Close DLM, extract the complete1.3.19 ZIP into a new empty folder, keep the EXE and app/ together, update the official stable WebView2 Runtime to157.0.4341.42 or later, then restart DLM. r229 stays paused even after a Runtime-only update. The external WebView2 Runtime is not bundled or installed by this ZIP.

DLMを終了→ZIP全体を新しい空フォルダーへ展開→EXEとapp/を一緒に保持→公式の安定版WebView2を157.0.4341.42以降へ更新→DLMを再起動してください。r229はRuntimeだけ更新しても停止のままです。外部RuntimeはこのZIPに同梱・自動インストールしません。

Library management, local viewing, Manual Intake, main.NET10.0.14 guarded HTTP decompression, previous download-start and cache-cleanup fixes remain. Credentials, cookies, redirects, paths, archive and native-parser boundaries are retained. No unrelated SDK/runtime/dependency upgrades. Windows x64, unsigned ZIP. Source/source ZIP/debug payloads are not published.

Fresh release qualification covers all23test projects, recovered browser admission and actual official-engine source/package/finalZIP fixtures, HTTP guard checks,7exact-package and7exact-ZIP regression runners, startup/window smoke,39native probes, and source/debug exclusion. Test fixtures are isolated synthetic data; no real accounts, libraries, purchases or exploit/RCE testing. Verification assets contain the exact results and limits; no blanket dependency-safety claim.

Sources:
- https://edgeupdates.microsoft.com/api/products?view=enterprise
- https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
- https://learn.microsoft.com/en-us/microsoft-edge/webview2/concepts/distribution
- https://developer.microsoft.com/en-us/microsoft-edge/webview2/

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.19
