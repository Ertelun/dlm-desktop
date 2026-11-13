# DLM Desktop マニュアル / User manual

## pixiv・X（Twitter）の画像保存 / pixiv and X image saving

会員・支援サイトにpixivとX（Twitter）を追加しました。並び順はpixiv → pixivFANBOX → Fantia → Patreon → Ci-en → Xです。保存したい画像の操作は、ユーザー自身が公式ページ上で開始します。一覧の巡回や一括取得は行いません。

**pixiv:** 投稿詳細を開いて画像を保存します。現在の投稿情報から作者名・作者ID・タイトル・投稿ID・投稿URLを取得し、ライブラリ内のpixiv／作者ID／投稿IDへ分類します。同じ投稿の追加画像は同じ作品にまとめます。サムネイルには作者のプロフィールアイコンを使います。旧形式・新形式の初期ページ情報と、表示中のページ自身が受信した作品・作者情報を照合します。作者を特定できない場合は受付を止め、アイコンだけ取得できない場合は画像を保存して「作者アイコン未取得」と表示します。

**X（Twitter）:** 右側の操作欄で「保存作品名」「作者名」を確認・編集してから画像を保存します。初期作者名は「X（twitter）」、初期作品名はXを初めて選んだ現在日時（日本時間）です。画像保存ごとのフォルダー選択画面は出ません。入力した名前からライブラリ内の保存先を自動作成し、同じ作品名・作者名なら同じ作品へ追加します。「新しい作品」で作品名を現在日時に戻せます。最初に保存した画像をサムネイルに保持し、投稿者のアカウントは推測しません。

サイトのページ構造・配信方式によって取得できない場合があります。検証は隔離した合成データを使用し、実アカウントでの全作品・全保存方式への対応を保証するものではありません。ブラウザーは正式復旧版から引き継ぐ安定版WebView2 Runtime **157.0.4341.57以降**が必要です。

## Saving images from pixiv and X (Twitter)

Membership / Fan sites now includes pixiv and X, ordered pixiv → pixivFANBOX → Fantia → Patreon → Ci-en → X. You initiate each image save on the official page. No catalog crawling or bulk downloading is provided.

**pixiv:** Open an artwork detail page and save an image. DLM reads the current artwork's creator name/ID, title, artwork ID and canonical URL, then groups saved images by creator ID and artwork ID. The creator's profile icon is used as the thumbnail. Legacy and Next page data and responses already requested by the displayed page are matched to the current artwork. An unidentified creator stops admission; an unavailable icon leaves the images saved with an explicit icon-unavailable status.

**X:** Edit Work title and Creator in the controls on the right before saving an image. Creator defaults to “X（twitter）”; the title defaults to the current Japan date/time when X is first selected. A folder picker no longer opens for each image. DLM creates the destination within the configured library from the entered names. Identical title/creator values append to the same work; New work resets the title to the current time. The first saved image remains its thumbnail. Account ownership is not inferred from timeline images.

Page structures and delivery modes can change. Qualification uses isolated synthetic data, not every real account, artwork or save route. The reviewed stable WebView2 Runtime floor remains **157.0.4341.57**. Authentication, browser-owned downloads and local validation boundaries remain in place.


**埋込みブラウザーとWebView2を使うキャッシュ操作には、公式の安定版 WebView2 Runtime 157.0.4341.57 以降が必要です。DLMと公式Runtimeを更新し、DLMを再起動してください。**

**The embedded browser and WebView2-backed cache controls require official stable WebView2 Runtime 157.0.4341.57 or later. Update DLM and the official Runtime, then restart DLM.**


**DLM Desktop 1.3.21（r232） / Windows x64**

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

対象版 / Version: [1.3.21（r232）](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.21). 確認日 / Checked: 2026-11-03 (JST). 対応ソース / Matching source commit: `bd3f4b6623a38f8f60bada2a17c96e5bfbc85dd2` ([配布記録 / Provenance](PROVENANCE.json)).

[READMEへ / Back to README](README.md)

## Program-wide cache audit / キャッシュ保存先の精査

設定 → ストレージ保守 →「キャッシュの保存状況と整理…」で、通常キャッシュ、ブラウザーキャッシュ、旧版の開発用.NET SDK、24時間以上前の処理用一時ファイル、30日以上前のクラッシュ診断の件数と容量を確認し、選択した項目を次回の通常起動時に削除できます。取り込み一時ファイルと古い診断は初期状態では選択されません。予約の取消と前回結果の確認もできます。

Settings → Storage maintenance → Cache storage and cleanup shows file/byte totals for ordinary caches (including search indexes and converted video), browser caches (HTTP/code/shaders/offline CacheStorage/component download archives, including known legacy profiles), the obsolete development SDK, processing/3D temporary files older than 24 hours, and crash diagnostics older than 30 days. Choose categories for cleanup at the next normal startup; old processing and diagnostic data are not selected by default. Requests can be cancelled, and the durable result reports deleted files/bytes, failures and changes.

Deletion runs before viewers and browser profiles open, is deferred while another DLM or Downloader Host is running, uses no-follow pinned Windows handles, preserves files written after the request, and never follows reparse points. Only exact app-owned cache roots are permitted; the saved request cannot supply arbitrary paths. Unexpected or locked files are reported and preserved.

Library works, retained download originals, cookies/sign-ins, LocalStorage, IndexedDB, installed browser components (including Widevine), stored official thumbnails, organization/reading state, import receipts and user backups are excluded. Retained downloads and stored thumbnails have separate explicit-confirmation actions. WebView2-backed disk-cache clearing requires the same stable Runtime157.0.4341.57 admission; the new startup cleanup also handles code/shader/offline caches and obsolete SDK files without resetting sign-ins. Deleted caches can be downloaded or rebuilt again when needed.

作品・ログイン状態・ブラウザー実行部品・整理情報・閲覧位置・バックアップ・取り込み記録は対象外です。残存ダウンロードと保存サムネイルは個別操作で確認して削除します。削除したキャッシュは次回利用時に再生成・再取得される場合があります。
