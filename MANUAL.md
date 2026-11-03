# DLM Desktop マニュアル / User manual

**1.3.15/r226：「ダウンロードキャッシュを削除」で、通常キャッシュに加えて管理領域に残ったダウンロードファイルも削除できるよう修正しました。失敗・再試行用ファイルを含む件数と容量を確認してから削除します。転送・取り込み中は削除せず、使用中・変更済み・削除失敗も結果に表示します。作品本体、保存サムネイル、Cookie・ログイン状態は保持します。**

**1.3.15/r226 fixes download-cache cleanup so it can also discard retained files in the managed download landing area after confirmation. The prompt includes the file count and byte total and warns about failed imports and retry files. Active transfers/imports block cleanup; locked, changed and failed files are reported. Library works, stored thumbnails, cookies and login state are preserved.**


**DLM Desktop 1.3.15（r226） / Windows x64**

- [日本語マニュアル](manual/ja.md) — ライブラリの指定からダウンロード・閲覧までの基本操作と、目的別の詳しい操作。
- [English manual](manual/en.md) — Essential steps from choosing a library through downloading and viewing, followed by detailed task-based instructions.

| やりたいこと / Your task | 日本語 | English |
|---|---|---|
| 最初の作品をダウンロードして閲覧する / Download and view your first work | [基本操作](manual/ja.md#basic) | [Basic workflow](manual/en.md#basic) |
| サービスごとの保存方法を確認する / Check provider-specific steps | [配信元ごとの操作](manual/ja.md#providers) | [Provider-specific downloads](manual/en.md#providers) |
| 作品を検索・整理する / Find and organize works | [検索](manual/ja.md#search)・[整理](manual/ja.md#collections) | [Search](manual/en.md#search) · [Organization](manual/en.md#collections) |
| 読書・動画・音声・3Dの操作を確認する / Use the viewer | [画像・PDF](manual/ja.md#reader)・[動画・音声](manual/ja.md#media)・[3D](manual/ja.md#model3d) | [Images/PDF](manual/en.md#reader) · [Video/audio](manual/en.md#media) · [3D](manual/en.md#model3d) |
| 保存先を増やす・移す / Add or relocate storage | [ライブラリフォルダ](manual/ja.md#roots) | [Library folders](manual/en.md#roots) |
| 設定をバックアップする / Back up user state | [バックアップ・復元](manual/ja.md#backup) | [Backup and restore](manual/en.md#backup) |
| うまくいかない操作を調べる / Troubleshoot | [困ったとき](manual/ja.md#troubleshooting) | [Troubleshooting](manual/en.md#troubleshooting) |

画面ラベルは対応ソースのXAML・表示用プロパティ・日英ローカライズ処理と照合しています。アプリ内ではDLD、DLM、Libraryなどの表記が混在します。マニュアル中のコード表記は、その言語設定で実際に表示されるラベルです。サービスのWebページとWindowsの標準ダイアログは、独自の文言・言語設定に従います。

Screen labels were checked against the matching XAML, presentation properties and Japanese/English localization functions. The application uses DLD, DLM and Library in different places. Code-formatted labels in each manual match that interface language. Provider web pages and standard Windows dialogs have their own labels and language settings.

対象版 / Version: [1.3.15（r226）](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.15). 確認日 / Checked: 2026-10-31 (JST). 対応ソース / Matching source commit: `644e9139e08cb33592f35c518d683cfef8728763` ([配布記録 / Provenance](PROVENANCE.json)).

[READMEへ / Back to README](README.md)

## Program-wide cache audit / キャッシュ保存先の精査

設定 → ストレージ保守 →「キャッシュの保存状況と整理…」で、通常キャッシュ、ブラウザーキャッシュ、旧版の開発用.NET SDK、24時間以上前の処理用一時ファイル、30日以上前のクラッシュ診断の件数と容量を確認し、選択した項目を次回の通常起動時に削除できます。取り込み一時ファイルと古い診断は初期状態では選択されません。予約の取消と前回結果の確認もできます。

Settings → Storage maintenance → Cache storage and cleanup shows file/byte totals for ordinary caches (including search indexes and converted video), browser caches (HTTP/code/shaders/offline CacheStorage/component download archives, including known legacy profiles), the obsolete development SDK, processing/3D temporary files older than 24 hours, and crash diagnostics older than 30 days. Choose categories for cleanup at the next normal startup; old processing and diagnostic data are not selected by default. Requests can be cancelled, and the durable result reports deleted files/bytes, failures and changes.

Deletion runs before viewers and browser profiles open, is deferred while another DLM or Downloader Host is running, uses no-follow pinned Windows handles, preserves files written after the request, and never follows reparse points. Only exact app-owned cache roots are permitted; the saved request cannot supply arbitrary paths. Unexpected or locked files are reported and preserved.

Library works, retained download originals, cookies/sign-ins, LocalStorage, IndexedDB, installed browser components (including Widevine), stored official thumbnails, organization/reading state, import receipts and user backups are excluded. Retained downloads and stored thumbnails have separate explicit-confirmation actions. Browser disk-cache clearing remains available immediately as a separate action; the new startup cleanup also handles code/shader/offline caches and obsolete SDK files without resetting sign-ins. Deleted caches can be downloaded or rebuilt again when needed.

作品・ログイン状態・ブラウザー実行部品・整理情報・閲覧位置・バックアップ・取り込み記録は対象外です。残存ダウンロードと保存サムネイルは個別操作で確認して削除します。削除したキャッシュは次回利用時に再生成・再取得される場合があります。
