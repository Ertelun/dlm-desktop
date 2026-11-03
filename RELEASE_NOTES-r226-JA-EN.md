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
