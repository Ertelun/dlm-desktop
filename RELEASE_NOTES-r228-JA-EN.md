# DLM Desktop 1.3.17 / r228 — Download start recovery

1.3.16で追加した重複確認の一時停止を、転送失敗と誤認する不具合を修正しました。DMM/FANZAで開始直後に「Interrupted or canceled browser download was not promoted」と表示される問題を確認しました。同じ開始処理を使う配信元にも修正を適用しています。

Version 1.3.16 could mistake its own temporary duplicate-check pause for a failed download and detach completion tracking before resuming. This was observed with DMM/FANZA. The correction applies to the shared browser-download admission path.

- アプリ自身の一時停止を、再開後の実際の転送進行まで追跡し、開始画面の更新順序による誤判定を防ぎます。
- 登録済み作品のスキップ、作品詳細の「再ダウンロード」、完了後のファイル検証は継続します。
- ユーザーが取り消した転送を再開しません。実際の失敗は失敗として扱います。再開待ちには上限があります。

The app now distinguishes its own preflight pause until resumed byte progress is observed. It keeps duplicate skips, explicit Redownload and completed-file validation. A customer cancellation remains terminal. Resume waiting is bounded; this does not bypass browser reputation checks or provider authentication.

The regression was reproduced with the unmodified r227 host and corrected using real WebView2 with isolated synthetic responses and loopback downloads. Tests cover synchronous/asynchronous started notifications, asynchronous preflight, duplicate skipping, user cancellation and a failing started UI callback. This is not a claim that all real-provider delivery methods were tested.

Windows x64, unsigned ZIP. Close DLM, extract the whole ZIP into a new empty folder, and keep the top-level EXE and app/ together. Existing libraries and settings remain usable. Stable WebView2 Runtime 156.0.4314.58 or later remains required. No SDK/runtime/dependency upgrade is included. Product source and source ZIP remain local.

DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。EXEとapp/を一緒に保持します。

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.17
