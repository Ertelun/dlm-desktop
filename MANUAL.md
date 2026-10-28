# DLM Desktop マニュアル / User manual

**1.3.12/r223：Chromiumの新しいCritical問題への緩和策として、埋込みブラウザーを一時停止しています。ライブラリ整理・検索・ローカル閲覧・手動取り込みは利用できます。ブラウザーを必要とする操作とブラウザーキャッシュ管理は停止中です。DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。再開には検証済みの修正版DLMが必要で、WebView2の更新だけでは解除されません。前版のHTTP Brotli対策は維持しています。**

**1.3.12/r223 temporarily disables the embedded browser to mitigate new Critical Chromium issues. Library organization, search, local viewing and Manual Intake remain available. Browser-dependent provider workflows and browser cache management are paused. Close DLM and extract the full official ZIP into a new empty folder. Recovery requires a reviewed DLM release; updating WebView2 alone does not lift the hold. The previous HTTP Brotli mitigation is retained.**


**DLM Desktop 1.3.12（r223） / Windows x64**

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

対象版 / Version: [1.3.12（r223）](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.12). 確認日 / Checked: 2026-10-28 (JST). 対応ソース / Matching source commit: `f591dc6ca15e0de03544d6c418573252ce7e2a2f` ([配布記録 / Provenance](PROVENANCE.json)).

[READMEへ / Back to README](README.md)
