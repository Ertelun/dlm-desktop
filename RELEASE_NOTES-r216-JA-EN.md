# DLM Desktop 1.3.5（r216）

多数の同時ダウンロードで進捗表示に負荷がかかる問題と、DLsite/DMMのZIP展開時に日本語ファイル名が文字化けする問題を修正しました。

- 進捗通知を150ミリ秒ごとの画面更新にまとめ、転送ごとの最新値を反映します。総サイズが不明な転送でも「ダウンロード中（受信済み 123.4 MiB）」のように受信容量を確認できます。
- 転送後の「待機中」「検証中」やキャンセル状態が、遅れて届いた進捗通知で上書きされる問題を修正しました。
- DLsite/DMMのZIPでUTF-8フラグがない名前を一律にCP932として読む処理を修正しました。各エントリを厳密なUTF-8として確認し、それ以外はCP932で読みます。従来のCP932、フラグ付きUTF-8、日本語を含むフォルダ階層に対応します。

ダウンロード自体が停止しているとは限らず、配信元側の準備やサイズ不明の転送では待ち時間が生じる場合があります。今回の変更は進捗表示とZIP展開の修正であり、配信元の通信速度を保証するものではありません。

**既に文字化けした名前は、元ZIPから再展開する必要があります。** 元ZIPがない場合は作品詳細の「再ダウンロード」から公式サイトで取得し直してください。起動時に既存ファイルを一括改名する処理はありません。

以前のDLM Desktopを終了し、ZIPを新しい空のフォルダへすべて展開して、`DoujinLibraryManagerDesktop.exe` を起動してください。既存ライブラリとユーザー設定を利用できます。

# DLM Desktop 1.3.5 (r216)

Fixes excessive UI work from simultaneous download updates and garbled Japanese filenames when extracting DLsite/DMM ZIPs.

- Coalesces progress notifications into one UI batch every 150 ms while preserving the latest value for each transfer. Downloads with an unknown total size now show the number of bytes received.
- Prevents late progress callbacks from overwriting waiting, validation or cancellation states.
- Replaces the forced CP932 decoding of unflagged ZIP entry names with strict UTF-8 detection per entry and CP932 fallback. Flagged UTF-8 names and Japanese directory paths remain supported.

Some providers require preparation time or transfer data without reporting a total size. This update improves progress reporting and extraction; it does not promise faster provider transfers.

**Previously garbled extracted names require extraction from the original ZIP.** If the original is unavailable, use Redownload from the work details and download again from the official provider. The application does not rename existing files in bulk on startup.

Close the previous DLM Desktop, extract the complete ZIP into a new, empty folder, and run `DoujinLibraryManagerDesktop.exe`. Existing libraries and user settings remain usable.

Verification includes all 21 test projects, 18 ZIP encoding/extraction checks, 118 real-WPF progress checks with 100 simultaneous synthetic transfers and 100,000 notifications, and the existing localization, navigation, storage, download and security regressions. The release verification asset records the final package results and scope. Owner verification of test build 20261015-1: PASS.

**[Windows x64 ZIP / ダウンロード](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.5/DLM-Desktop-v1.3.5-r216-win-x64.zip)** · [Manual / マニュアル](https://github.com/Ertelun/dlm-desktop/blob/main/MANUAL.md)

.NET is bundled; the embedded browser requires WebView2 Runtime. Unsigned distribution. Keep `app` beside the EXE. SHA-256 is available in the release's `SHA256SUMS.txt`.
