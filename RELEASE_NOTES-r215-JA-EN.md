# DLM Desktop 1.3.4（r215）

ライブラリから「設定」「続きから」「ダウンロード」などへ移動するとクラッシュする不具合を修正しました。

文字部分をクリックしたとき、WPF の Run を通常の Visual として親探索する共通マウス処理が例外を起こしていました。Run、Span、Hyperlink のコンテンツ親と、通常の画面要素の親を安全にたどる処理へ変更しました。カード選択、関連作品・管理ポップアップ、仮想化リストで同じ親探索を使う箇所も修正しています。

公開版 1.3.3 の ZIP に含まれる DLL で同じ例外を再現し、修正版の実 WPF テストでクリック入力が共通処理を経由して正常に画面へ届くことを確認しました。日本語→英語→日本語で全4遷移先、文字・アイコン・ボタン、入れ子の文字要素、切り離された要素を検証しています。既存の翻訳、ライブラリ、ダウンロード、保存状態、セキュリティのテストも実行します。実行結果は BUILD-VERIFICATION.json と Release 添付の VERIFICATION.json に記録します。

以前の DLM Desktop を終了し、ZIP を新しい空のフォルダへすべて展開して、DoujinLibraryManagerDesktop.exe を起動してください。既存ライブラリとユーザー設定を利用できます。

# DLM Desktop 1.3.4 (r215)

Fixes the crash when clicking text to navigate from Library to Settings, Continue reading, Download and other controls.

The shared preview mouse handler passed WPF Run content to VisualTreeHelper.GetParent, which only accepts Visual or Visual3D objects. The parent traversal now handles Run, Span and Hyperlink content as well as visual elements. Card selection, relation and management popups, and the virtualized list use the same safe traversal.

The regression reproduces the exact exception against the DLL from the public 1.3.3 ZIP. Real WPF tests then exercise the preview pointer route, all four destinations and repeated Japanese/English/Japanese switches. Existing localization, library, download, user-state and security tests are also run. BUILD-VERIFICATION.json and the release verification asset record the actual results.

Close the previous DLM Desktop, extract the complete ZIP into a new empty folder, and run DoujinLibraryManagerDesktop.exe. Existing libraries and user settings remain usable.

検証 / Verification: **19/19 test projects**, **201 real-WPF pointer/navigation checks**, **8,355 localization assertions**, **161 screen checks across 15 screens**, **150 security-boundary assertions**, **172 provider-policy assertions**, **39 native-parser probes**. Release build: **0 warnings / 0 errors**. The final ZIP passes startup from a Japanese/space path and coordinate clicks during normal startup with an existing library.

**[Windows x64 ZIP / ダウンロード](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.4/DLM-Desktop-v1.3.4-r215-win-x64.zip)**

SHA-256:

```text
172105ef553c2df17d3c8ca2deff6a79b21c198374cf3dde24c0d0cbfc98bd67  DLM-Desktop-v1.3.4-r215-win-x64.zip
```

.NET同梱、埋め込みブラウザにはWebView2 Runtimeが必要です。コード署名なし。appフォルダをEXEと同じ場所に置いてください。

.NET is bundled; the embedded browser requires WebView2 Runtime. This is an unsigned distribution. Keep app beside the EXE.