# DLM Desktop 1.3.15 / r226 — Download cache cleanup / ダウンロードキャッシュ削除の修正

「ダウンロードキャッシュを削除」を押しても、ブラウザーの管理領域（Landing）に残ったファイルが対象外となり、ディスク容量が戻らない問題を修正しました。

The download-cache action previously cleared only the ordinary cache, leaving retained browser downloads in the managed Landing area. It now offers explicit deletion of those files too.

- 残存ファイルの件数・容量と、失敗・再試行用ファイルも対象となることを確認してから削除します。初期選択は「いいえ」です。
- 転送・取り込み中は削除しません。確認後に増えたファイル、変更済み・使用中のファイルは保持します。
- 削除件数・バイト数・失敗・変更/消失を表示し、パスやファイル名を含めずログへ記録します。
- ライブラリの作品、保存サムネイル、整理情報、Cookie・ログイン状態は保持します。ブラウザーのディスクキャッシュ削除は別操作です。

Confirm the file count and byte total before discarding retained downloads, including failed imports and files kept for retry. No is selected by default. Downloads/imports block cleanup; files added after the preview, changed files and locked files are preserved. The result reports deleted files/bytes and failures or changes. Cleanup is limited to regular files in managed provider/session folders, with no-follow Windows handles; it never recursively deletes unexpected subfolders or touches library works, stored thumbnails, organization, cookies or login state. Browser disk-cache clearing remains a separate action.

Close DLM, extract the complete ZIP into a new empty folder, and keep the top-level EXE and app/ together. Existing libraries/settings remain usable. For browser workflows, the stable WebView2 Runtime requirement remains 156.0.4314.58 or later; no SDK/runtime/dependency upgrade is included. Windows x64, unsigned ZIP. Product source and source ZIP remain local.

DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。EXEとapp/を一緒に保持します。既存のライブラリ・設定を利用できます。ブラウザー利用時の安定版WebView2 Runtime 156.0.4314.58以降という条件は維持しています。

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.15

## Program-wide cache audit / キャッシュ保存先の精査

設定 → ストレージ保守 →「キャッシュの保存状況と整理…」で、通常キャッシュ、ブラウザーキャッシュ、旧版の開発用.NET SDK、24時間以上前の処理用一時ファイル、30日以上前のクラッシュ診断の件数と容量を確認し、選択した項目を次回の通常起動時に削除できます。取り込み一時ファイルと古い診断は初期状態では選択されません。予約の取消と前回結果の確認もできます。

Settings → Storage maintenance → Cache storage and cleanup shows file/byte totals for ordinary caches (including search indexes and converted video), browser caches (HTTP/code/shaders/offline CacheStorage/component download archives, including known legacy profiles), the obsolete development SDK, processing/3D temporary files older than 24 hours, and crash diagnostics older than 30 days. Choose categories for cleanup at the next normal startup; old processing and diagnostic data are not selected by default. Requests can be cancelled, and the durable result reports deleted files/bytes, failures and changes.

Deletion runs before viewers and browser profiles open, is deferred while another DLM or Downloader Host is running, uses no-follow pinned Windows handles, preserves files written after the request, and never follows reparse points. Only exact app-owned cache roots are permitted; the saved request cannot supply arbitrary paths. Unexpected or locked files are reported and preserved.

Library works, retained download originals, cookies/sign-ins, LocalStorage, IndexedDB, installed browser components (including Widevine), stored official thumbnails, organization/reading state, import receipts and user backups are excluded. Retained downloads and stored thumbnails have separate explicit-confirmation actions. Browser disk-cache clearing remains available immediately as a separate action; the new startup cleanup also handles code/shader/offline caches and obsolete SDK files without resetting sign-ins. Deleted caches can be downloaded or rebuilt again when needed.

作品・ログイン状態・ブラウザー実行部品・整理情報・閲覧位置・バックアップ・取り込み記録は対象外です。残存ダウンロードと保存サムネイルは個別操作で確認して削除します。削除したキャッシュは次回利用時に再生成・再取得される場合があります。
