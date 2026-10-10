# DLM Desktop 1.3.2（r213）— 正式リリース / Stable release

2026-10-10 · Windows x64 · ZIP · unsigned · free · 日本語 / English

DLM Desktopはローカル作品の整理・検索・閲覧を行うWindowsアプリです。今回の正式版には取得・保存処理の修正と、展開先を見やすくする配布構成を含みます。

DLM Desktop organizes, searches, and displays locally stored digital works. This stable release includes acquisition/save fixes and a compact package layout.

## ダウンロード・起動 / Download and launch

[DLM-Desktop-v1.3.2-r213-win-x64-Compact.zip](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.2/DLM-Desktop-v1.3.2-r213-win-x64-Compact.zip) を取得し、新しい空のフォルダへすべて展開して `DoujinLibraryManagerDesktop.exe` を起動してください。以前のDLM Desktopは先に終了してください。

Download [DLM-Desktop-v1.3.2-r213-win-x64-Compact.zip](https://github.com/Ertelun/dlm-desktop/releases/download/v1.3.2/DLM-Desktop-v1.3.2-r213-win-x64-Compact.zip), extract the entire ZIP into a new, empty folder, and run `DoujinLibraryManagerDesktop.exe`. Close any older running instance first.

最上位は本体EXE、`README.txt`、`app/` の3項目です。`app/` はEXEと同じ場所に置いてください。.NETランタイムを同梱しています。埋め込みブラウザにはMicrosoft Edge WebView2 Runtimeが必要です。詳細資料とライセンス表記は `app/docs/` にあります。

The root has three items: the EXE, `README.txt`, and `app/`. Keep `app/` beside the EXE. The .NET runtime is bundled; the embedded browser requires Microsoft Edge WebView2 Runtime. Documentation and dependency notices are in `app/docs/`.

## 修正内容 / Changes

| 対象 / Area | 動作 / Behavior |
|---|---|
| 配布構成 / Package | DLL・ランタイム・ダウンロード用プログラムを `app/` に集約。 / Put supporting files under `app/`. |
| Debug UI | 一時的なデバッグログボタンと表示ウィンドウを削除。 / Remove the temporary debug-log button and window. |
| DLsite | `part1.exe` と後続のpartファイルを同一作品の「分割ダウンロード」フォルダへ保存。ファイル名を維持し、結合・自動実行は行わない。 / Preserve and group multipart files; do not merge or automatically run them. |
| Gumroad / GOG | 作品情報・サムネイル取得を修正。 / Fix metadata and thumbnail retrieval. |
| FANBOX | 画像保存先のフォルダ作成を修正。 / Fix image save-directory creation. |
| Patreon / Ci-en等 | 同一投稿の同名・別内容の画像を上書きせず追加保存。 / Preserve distinct same-name images from a post without overwriting them. |
| Fantia | 画像・レイアウト表示の回復用キャッシュ処理を追加。 / Add cache recovery for image/layout display problems. |
| Ci-en → DLsite | 対応する作品・予告作品リンクをDLsite画面へ引き継ぐ。 / Hand supported work/announcement links to the DLsite browser view. |
| GOG | 受付確定ボタンをブラウザ上部にも表示。保存・確認中の件数を表示し、処理中の確定を防ぐ。 / Show finalization above the browser, display active counts, and wait for download/validation completion. |

**GOGでは必要なOffline Backup Game Installer / bonus fileをすべて保存した後、「GOG受付を確定して登録」を押してください。** DLMは一式の終わりを自動推測しません。インストーラーは保存し、実行・自動展開は行いません。

**For GOG, save all required offline installer/bonus files, then click “Finalize GOG intake and register” (`GOG受付を確定して登録`).** DLM waits for this explicit grouping boundary. Installers are stored without being run or automatically unpacked.

## 検証 / Verification

- .NET SDK 10.0.401による依存関係のロック付き復元・Releaseビルド成功。警告0、エラー0。 / Locked restore and Release build passed with zero warnings/errors.
- 全17テストプロジェクト成功。未実行・ポリシーブロックなし。 / All 17 test projects passed with none blocked or skipped.
- セキュリティ境界150/150、取得元の実行時ポリシー172/172、配布DLLによるPDF・3Dモデル用ネイティブ検査39/39成功。 / Security boundary 150/150, provider runtime policy 172/172, and native PDF/3D probes 39/39 passed.
- 配布ZIPを日本語・空白のあるパスへ展開し、本体の自己テスト・画面起動・Downloader Hostの自己テスト・同梱ランタイムの使用を確認。 / Verified extracted-package self-tests, window launch, Downloader Host self-test, and bundled-runtime loading in a path with Japanese characters and spaces.
- ZIPの整合性、ソースマニフェスト775件、ライセンス表記34ファイルを確認。 / Checked ZIP integrity, 775 source-manifest entries, and 34 bundled license/notice files.

[検証記録](RELEASE_VERIFICATION-r213.json) と [provenance](PROVENANCE.json) に検査範囲を記載しています。これらは全サイト・全配信形式の網羅検証や外部機関による認証ではありません。

[Verification](RELEASE_VERIFICATION-r213.json) and [provenance](PROVENANCE.json) describe the checked scope. These checks are not exhaustive qualification of every provider/delivery mode or external certification.

## 配布条件と制約 / Distribution and limits

この版はコード署名なしのWindows x64 ZIPです。ARM64は未検証です。ログイン・購入・ダウンロード開始はユーザーが公式画面で操作します。DRM・閲覧専用等のコンテンツは各サービスの公式手段をご利用ください。DLMは対応サイトの公式アプリ・提携製品ではありません。

This is an unsigned Windows x64 ZIP; ARM64 has not been qualified. Users sign in, purchase, and initiate downloads on official pages. DRM/viewer-only content stays on official provider routes. DLM is an independent application, unaffiliated with the listed providers.

GitHubが自動生成する “Source code” アーカイブは公開資料であり、アプリのビルドソースではありません。旧Betaのタグ・添付ファイルは保持しています。

GitHub's automatically generated “Source code” archives contain public documentation, not the application's build source. Previous Beta tags and assets are retained.

## SHA-256

```text
a145ac780de0dfe715d4bfc8540a436a815d42f21f8466131b30ad53ebc39ded  DLM-Desktop-v1.3.2-r213-win-x64-Compact.zip
```

[SHA256SUMS.txt](SHA256SUMS.txt) またはRelease添付の `DLM-Desktop-v1.3.2-r213-SHA256SUMS.txt` でも確認できます。
