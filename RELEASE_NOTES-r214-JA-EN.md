# DLM Desktop 1.3.3（r214）— 2026-10-10

日英表示を修正した正式リリースです。公開中止した1.3.2（r213）を置き換えます。

- メニュー、ボタン、説明、進捗、エラー、ツールチップ、確認ダイアログの翻訳を再調査・補完。
- 日本語→英語→日本語の往復切り替え、後から開くメニューやツールチップ、画面テンプレートへの反映を修正。
- 確認ダイアログの「はい」「いいえ」「キャンセル」等をアプリの言語へ統一。
- 作品名・作者名・ファイル名・コレクション名を保持し、表示翻訳によってカテゴリの絞り込み値が変わらないよう修正。
- 英語で長くなるビューアー操作列とショートカット説明を折り返し、暗い背景でもチェックボックスの説明が読めるよう修正。
- 一時的なデバッグログボタンを削除。展開先の最上位は本体EXE、README.txt、appフォルダの3項目。
- DLsiteのpart1.exeと後続partを同一作品へ原本のまま保存する修正を収録。
- Gumroad/GOGの作品情報・サムネイル、FANBOXの保存先作成、Patreon/Ci-en等の複数画像保存を修正。
- Fantiaの表示回復、Ci-enからDLsite作品・予告作品への引き継ぎを収録。
- GOG受付確定をブラウザ上部にも表示し、保存・確認中の件数を明示。

GOGではファイル一式を保存した後に「GOG受付を確定して登録」を押します。DLsiteの分割ファイルは結合・自動実行しません。既存ライブラリとユーザー設定を利用できます。

検証記録は `app/docs/BUILD-VERIFICATION.json` に収録します。ソース照合、ロック付き依存関係復元、全18テストプロジェクト、Releaseビルド、両アプリのpublish、本体の自己テストと画面起動を確認します。

# DLM Desktop 1.3.3 (r214) — 2026-10-10

Stable release repairing Japanese/English presentation. This replaces the withdrawn 1.3.2 (r213) release.

- Audit and complete translations for menus, buttons, descriptions, progress, errors, tooltips and confirmation dialogs.
- Repair repeated Japanese/English switches and localization of menus, tooltips and visual templates opened later.
- Use the selected application language for confirmation buttons, including Yes, No and Cancel.
- Preserve work titles, creator names, filenames and collection names; keep canonical category filter values stable.
- Wrap longer English viewer controls and shortcut descriptions, and keep checkbox labels readable on dark viewer backgrounds.
- Remove the temporary debug-log button. The extracted root contains the EXE, README.txt and app folder.
- Retain DLsite part1.exe and subsequent parts together under one work without merging or automatic execution.
- Fix Gumroad/GOG metadata and thumbnails, FANBOX save-directory creation, and multiple-image saves in Patreon/Ci-en and related flows.
- Include Fantia display recovery and handoff of supported Ci-en links to DLsite work and announcement pages.
- Show GOG intake finalization above the browser with downloading and verification counts.

For GOG, save the complete file set, then click “Finalize GOG intake and register”. Existing libraries and user settings remain usable.

Build verification is recorded in `app/docs/BUILD-VERIFICATION.json`, covering source checksums, locked dependency restore, all 18 test projects, Release builds, publication of both binaries, executable self-tests and window launch.


**[Windows x64 ZIP / ダウンロード](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.3/DLM-Desktop-v1.3.3-r214-win-x64.zip)** — `DLM-Desktop-v1.3.3-r214-win-x64.zip`

以前のDLM Desktopを終了し、ZIPを新しい空のフォルダへすべて展開して、`DoujinLibraryManagerDesktop.exe` を起動してください。最上位はEXE・README.txt・appの3項目です。appをEXEと同じ場所に置いてください。.NET同梱、埋め込みブラウザにはWebView2 Runtimeが必要です。コード署名なしの配布版です。

Close the previous DLM Desktop, extract the entire ZIP into a new empty folder, and launch `DoujinLibraryManagerDesktop.exe`. Keep app beside the EXE. .NET is bundled; the embedded browser needs WebView2 Runtime. This is an unsigned distribution.

検証 / Verification: **18/18 test projects**, **8,355 localization assertions**, **161 real-WPF checks across 15 screens**, **150 security-boundary assertions**, **172 provider-policy assertions**, and **39 native-parser probes** passed. Release build: **0 warnings / 0 errors**. Source checksums, ZIP integrity, the compact layout, and executable startup from a Japanese/space path passed.

SHA-256:

```text
bdb35761f3d6244b04ea51347c6158830885ded039f2f113fa9c55e3ffd65d14  DLM-Desktop-v1.3.3-r214-win-x64.zip
```

設定 → 表示とアクセシビリティ → 言語 / Settings → Appearance and accessibility → Language。開いている画面にも言語変更を反映します。作品名・作者名・ファイル名は保持します。各サービスのWebページとWindows標準ファイル選択画面は、それぞれの言語設定に従います。

Language changes update open application screens. Work titles, creator names and filenames are preserved. Provider web pages and Windows file dialogs follow their own language settings.

DLMは各サービスの公式アプリ・提携製品ではありません。ログイン、購入、ダウンロード開始は各サービスの公式画面で操作してください。

DLM is an independent application and is not affiliated with these providers. Sign-in, purchases and download initiation remain user actions on official provider pages.
