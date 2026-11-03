# Cache storage and cleanup / キャッシュ保存先と削除範囲

Applies to DLM Desktop 1.3.15 / r226, Windows x64.

Settings → Storage maintenance → **Cache storage and cleanup** shows file counts, logical byte totals and unreadable entries. Select categories and confirm **Schedule cleanup at next startup**. Close every DLM and Downloader Host, then start DLM again. The request can be cancelled before startup. The same screen shows the durable previous result; the application log records counts without filenames or paths.

設定 → ストレージ保守 → **キャッシュの保存状況と整理…** で保存容量を確認し、選択した項目を次回起動時の削除として予約できます。DLMとDownloader Hostをすべて終了し、起動し直してください。実行前は予約を取り消せます。前回結果は同画面とログで確認できます。

| Stored data | Producer and lifecycle | Cleanup behavior |
|---|---|---|
| Ordinary cache: search index, library-health results, video compatibility outputs | Derived from library data. Video outputs already have age/count/size pruning: stable 14 days, partial 1 hour, up to 8 stable files / 8 GiB | Select Ordinary cache. Rebuilt or transcoded when needed; source work files remain |
| Browser HTTP, code, GPU/shader caches and offline CacheStorage | Created by provider WebView2 profiles. Known current and legacy profile layouts are inspected | Select Browser cache. Cookies, sign-ins, LocalStorage, IndexedDB and profile settings are excluded. Offline pages/assets may need to be fetched again |
| Downloaded browser component archives | WebView2 component installer download cache, separate from installed components | Browser cache includes the archive cache. Installed Widevine and other execution/security components are excluded; archives may be downloaded again |
| Legacy development .NET SDK in DLM's Tooling area | Old local tooling; current main application and retained Downloader Host are self-contained | Select Legacy SDK. Kept if PATH / DOTNET_ROOT / DOTNET_HOST_PATH or an active .NET tool references this location. Shipped runtimes are outside this cleanup scope |
| Protected browser-processing, Watch Folder-processing and owned 3D staging | Temporary copies normally cleaned in finally / Dispose. Crashes can leave remnants | Optional, unselected by default. Only files older than 24 hours; original downloads, selected Watch Folder files and library works are excluded. Retry from the originals may be needed |
| Crash diagnostics | Sanitized local crash reports. Current desktop log rotates at 4 MiB | Optional, unselected by default. Only crash-prefixed reports older than 30 days; current/rotated desktop logs and recent reports remain |
| Managed download Landing files | Original downloads retained for failed imports, retries or grouped intake | Separate **Delete download cache** confirmation, including file/byte totals. Active downloads/imports block it. New, changed or busy files are preserved |
| Stored official thumbnails | Durable official images, separate from transient caches | Separate **Delete saved thumbnails** confirmation. Cache cleanup does not delete them |
| Cookies, site databases, installed browser components | Authentication, persistent site state and browser functionality | Preserved; profile folders are never reset wholesale |
| Organization, reading/3D state, corrections, saved views, import receipts, provenance and backups/snapshots | Authoritative user state or operation/recovery evidence | Preserved; not treated as disposable caches |
| Shared Windows Temp and general .NET extraction data | Managed by Windows/.NET; may be shared with active processes | Never swept generically. Only DLM's explicitly owned 3D-staging subdirectory is included above |

Cleanup runs before normal viewers/browser profiles open. A second DLM instance or Downloader Host defers the request. No-follow pinned Windows handles prevent junction/reparse traversal at scanning and deletion; regular-file handles verify size and modification time again. Only enum categories are saved, so a modified request cannot supply an arbitrary deletion path. Files written after scheduling, locked files and unexpected reparse entries are preserved. Empty managed cache subdirectories may be removed without recursive deletion. Failed and changed items are reported separately and can be reviewed before another request.

Counts report deleted logical file bytes. Actual free-space changes can differ because of filesystem allocation, open handles and other activity. Deleting rebuildable data may temporarily slow the next use, and browser cache growth can resume through normal browsing.

この整理では作品本体・ログイン情報・保存サムネイル・整理情報・取り込み記録・バックアップを消しません。表示する削除バイト数はファイルの論理サイズであり、OSの空き容量増加量と完全に一致するとは限りません。キャッシュは次の利用時に再生成・再取得されることがあります。
