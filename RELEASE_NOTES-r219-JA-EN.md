# DLM Desktop 1.3.8（r219）— 全画面削除と連続閲覧の改善

## 日本語

全画面で作品を削除しながら続けて閲覧すると、画像が消えたまま次の作品が出ないことがある問題に対処しました。

- **全画面で Shift+Delete**：表示中の作品のフォルダーを完全削除する確認を表示します。確認の初期選択はキャンセルです。削除後は同じ全画面で次の作品へ進みます。現在の絞り込みと表示順・ランダム設定に従い、表示順の末尾や対象なしの場合はライブラリに戻ります。
- **削除中の進捗表示**：処理段階、削除済みファイル数、経過時間を表示します。Esc または「ライブラリに戻る」で閲覧を終了できます。確認済みの削除は戻った後も続行します。作品フォルダーの完全削除は元に戻せません。
- **連続閲覧の安定性**：削除のたびにライブラリ全体を読み直す処理を差分更新に変更しました。閲覧中に届く更新をまとめ、前の画像・PDF・目次処理をキャンセルし、終了後に残った古い更新予約が新しい表示を上書きする競合に対処しました。
- **調査ログの改善**：削除段階・所要時間・UIの応答記録を追加しました。ファイル数やストレージの状態によって、物理削除自体には時間がかかる場合があります。

1.3.7（r218）のWebView2対策と、同梱 .NET 10.0.12 を維持しています。外部ページには WebView2 Runtime 155.0.4283.60 以降が必要です。Downloader Host は検証済みのr218版をそのまま同梱しています。

更新は旧DLMを終了し、ZIP全体を新しい空フォルダーに展開して、ルートの `DoujinLibraryManagerDesktop.exe` を起動してください。`app` フォルダーも一緒に使用します。既存のライブラリと設定を利用できます。Windows x64、無料、日本語・英語UI、コード署名なし。

合成データを使った23テストプロジェクトを実行し、削除・連続閲覧1,255項目、WebView2対策49項目、画面操作201項目を最終配布アセンブリでも検証しています。全サービス・全作品での動作を保証する試験ではありません。

## English

This update addresses a case where the image disappears after deleting a work during continuous fullscreen viewing and the next work does not appear.

- **Shift+Delete in fullscreen** opens a confirmation to permanently delete the folder of the work currently being viewed. Cancel is selected by default. After success, viewing continues in the same window using the current filter and ordered/random mode. Ordered viewing returns to the library at the end; an empty candidate list also returns to the library.
- **Deletion progress** shows the current phase, deleted file count and elapsed time. Press Esc or select Return to Library to leave viewing. A confirmed deletion continues in the background. Permanent folder deletion cannot be undone.
- **More reliable continuous viewing** uses targeted library updates instead of reloading the entire library for each deletion, coalesces updates received during viewing, cancels obsolete image/PDF/table-of-contents work, and discards stale queued refreshes after viewing ends.
- **Better diagnostics** record deletion stages, elapsed time and UI responsiveness. Physical deletion can still take time depending on file count and storage.

The WebView2 mitigation from 1.3.7/r218 and bundled .NET 10.0.12 are retained. External pages require WebView2 Runtime 155.0.4283.60 or later. The verified r218 Downloader Host is retained unchanged.

Close the old DLM, extract the complete ZIP into a new empty folder, then start `DoujinLibraryManagerDesktop.exe` at the root. Keep the `app` folder alongside it. Existing libraries and settings remain usable. Windows x64; free; Japanese/English UI; unsigned.

All 23 synthetic-data test projects passed. Deletion/continuous viewing (1,255 checks), browser admission (49) and pointer navigation (201) were also tested against the final packaged assemblies. These checks do not certify every service or work.

Release and checksums: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.8

Manual: https://github.com/Ertelun/dlm-desktop/blob/main/MANUAL.md
