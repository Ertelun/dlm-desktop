# DLM Desktop — Doujin Library Manager Desktop

**増えた同人・デジタル作品を、PC上でまとめて整理・閲覧するローカルライブラリ。**

DLM Desktop is a local Windows library by Ertelun for organizing, finding and viewing digital works you keep on your PC.

**1.3.4（r215）正式リリース / Stable release · 日本語 / English · Windows x64 · ZIP · free · unsigned**

[Windows x64 ZIPをダウンロード / Download Windows x64 ZIP](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.4/DLM-Desktop-v1.3.4-r215-win-x64.zip) · [正式リリース / Stable release](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.4) · [更新内容 / Release notes](RELEASE_NOTES-r215-JA-EN.md)

**[マニュアル / User manual](MANUAL.md)** · [日本語](manual/ja.md) · [English](manual/en.md)

## 起動方法 / Getting started

1. 以前のDLM Desktopを終了します。 / Close any previously running DLM Desktop.
2. ZIPを新しい空のフォルダへすべて展開します。 / Extract the entire ZIP into a new, empty folder.
3. `DoujinLibraryManagerDesktop.exe` を起動します。 / Run `DoujinLibraryManagerDesktop.exe`.

最上位は次の3項目です。appフォルダをEXEと同じ場所に置いてください。

The root contains three items. Keep the app folder beside the EXE.

```text
DoujinLibraryManagerDesktop.exe
README.txt
app/
```

.NETランタイムを同梱しています。埋め込みブラウザにはMicrosoft Edge WebView2 Runtimeが必要です。詳細資料とライセンスはapp/docsにあります。既存のライブラリとユーザー設定を利用できます。

.NET is bundled. The embedded browser requires Microsoft Edge WebView2 Runtime. Documentation and licenses are in app/docs. Existing libraries and user settings remain usable.

## 言語 / Language

「設定」→「表示とアクセシビリティ」→「言語」で、日本語・英語・システム設定を選べます。開いている画面にも反映します。メニュー、ボタン、説明、進捗、エラー、確認ダイアログを再調査・修正しました。作品名・作者名・ファイル名や保存済みの識別情報は保持します。

Choose Settings → Appearance and accessibility → Language for Japanese, English or the system language. Open screens update immediately. This release repairs menus, buttons, descriptions, progress, errors and confirmation dialogs. Work titles, creator names, filenames and stored identities are preserved.

各サービスのWebページとWindows標準ファイル選択画面は、それぞれの言語設定に従います。

Provider web pages and Windows file dialogs follow their own language settings.

| 日本語設定 / Japanese | 英語設定 / English |
|---|---|
| ![日本語の表示設定](screenshots/settings-ja-r214.png) | ![English appearance settings](screenshots/settings-en-r214.png) |

画像は合成データによる検証画面です。実アカウント、購入履歴、作品画像は含みません。

These qualification screenshots use synthetic data and contain no real accounts, purchase history or work imagery.

## 主な機能 / Main features

- 登録済みライブラリの検索・並び替え・作者別表示・コレクション / Search, sort, group by creator and organize collections.
- 対応する画像・PDF・動画・音声・3Dモデル等のローカル閲覧 / View supported local images, PDFs, video, audio and 3D models.
- 閲覧位置の保存・再開、ユーザー設定のバックアップ・復元 / Resume reading and back up or restore user state.
- 対応する公式ダウンロードの保存・検証・登録補助 / Assist with saving, validating and registering supported downloads from official provider pages.
- 選択した投稿の画像・添付ファイルを同一投稿として整理 / Group explicitly saved images and attachments from a selected post.

対応範囲は [Provider Capabilities](PROVIDER_CAPABILITIES.md) と [Known Limitations](KNOWN_LIMITATIONS.md) を確認してください。

See [Provider Capabilities](PROVIDER_CAPABILITIES.md) and [Known Limitations](KNOWN_LIMITATIONS.md) for supported routes.

## 1.3.4の修正 / Changes in 1.3.4

ライブラリから設定・続きから・ダウンロードなどへ移動するとクラッシュする不具合を修正しました。文字部分をクリックした際の共通マウス処理が WPF の Run を通常の画面要素として親探索し、例外を起こしていました。文字要素と画面要素の両方を安全にたどる処理へ変更しました。

Fixes the crash when clicking text to navigate from Library to Settings, Continue reading and Download. The shared preview mouse handler now safely follows both WPF inline content and visual elements.

公開 ZIP の DLL で同じクラッシュを再現し、修正版 ZIP の DLL で201項目の実 WPF クリック回帰テストが通ることを確認しました。通常起動でも、文字部分のクリックで全画面を往復できています。1.3.3と以前の配布は公開を取り下げてドラフトとして保存し、検証済みの1.3.4だけを公開しています。

The exact public 1.3.3 DLL reproduces the exception. The DLL extracted from the repaired ZIP passes 201 real-WPF pointer/navigation checks, and normal startup passes coordinate clicks through all four destinations. Earlier releases are retained as withdrawn drafts; the verified 1.3.4 is the current public release.

以前の機能修正と日英表示対応を含みます。**GOGは必要なファイルをすべて保存してから「GOG受付を確定して登録」を押してください。** DLsite分割ファイルは原本のまま同じ作品にまとめます。

Includes the previous feature fixes and Japanese/English presentation support. **For GOG, save every required file, then click “Finalize GOG intake and register”.** DLsite multipart files retain their original names.

## 配布物の確認 / Verify the download

配布元は [Ertelun GitHub Releases](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.4) です。コード署名なしのWindows x64 ZIPです。SHA-256は公開した配布物との一致を確認するための値です。

The canonical source is [Ertelun GitHub Releases](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.4). The Windows x64 ZIP is unsigned. Its SHA-256 verifies identity with the published package.

```text
172105ef553c2df17d3c8ca2deff6a79b21c198374cf3dde24c0d0cbfc98bd67  DLM-Desktop-v1.3.4-r215-win-x64.zip
```

全19テスト、クリック・画面遷移201項目、翻訳8,355項目、実画面15種類の161項目、セキュリティ境界150項目、配信元ポリシー172項目、実DLL39項目を検証しました。詳細はRelease添付の検証記録と [PROVENANCE.json](PROVENANCE.json) にあります。

Verification passed all 19 test projects, 201 pointer/navigation checks, 8,355 localization assertions, 161 real-WPF checks across 15 screens, 150 security-boundary assertions, 172 provider-policy assertions and 39 native-parser probes. See the release verification asset and [PROVENANCE.json](PROVENANCE.json).

## 利用と問い合わせ / Use and feedback

DLM Desktopは無料です。ローカル利用にDLMアカウントや支払いは不要です。ログイン、購入、ダウンロード開始は各サービスの公式画面で操作してください。DLMは各サービスの公式アプリ・提携製品ではありません。

DLM Desktop is free; local use requires no DLM account or payment. Sign-in, purchases and download initiation remain user actions on official provider pages. DLM is an independent application and is not affiliated with these providers.

[不具合報告 / Issues](https://github.com/Ertelun/dlm-desktop/issues) · [Feedback](FEEDBACK.md) · [Security](SECURITY.md) · [Privacy](PRIVACY.md)

セキュリティ上の問題は公開Issueではなく、Security → Report a vulnerabilityから報告してください。

Report sensitive vulnerabilities through Security → Report a vulnerability instead of public issues.
