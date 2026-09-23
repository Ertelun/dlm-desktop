# DLM Desktop Public Beta 2 — r98 JA/EN Update (Windows x64)

Date: 2026-09-23 JST

This is an **in-place update of the existing `v0.1.0-beta.2` release**, not a new release tag.

Current replacement package:

`DLD-160-Desktop-win-x64-HOTFIX-r2-localbuild-r98.zip`

SHA-256:

`66dd0661298a7f8bc906a29fc4e8f99a5406ea346989a936ab11737c76165272`

The previously published Beta 2 package with the same filename had SHA-256 `b3174d3206f53005192cac50423950625b3b8de9d4fec619a18255b93ed7b7cf`. The old digest is retained in `PROVENANCE.json` as replaced history so the two same-name binaries are not confused.

## 日本語

### 日英UI対応

DLM Desktopのユーザー向けUIを **System / 日本語 / English** から選択できるようにしました。言語変更はDLM Desktopの再起動後に反映されます。

今回の最終ローカライズ修正では、固定XAML文字列を起動後に置換する方式を廃止し、アプリ起動時にJA/ENリソースを読み込む方式へ変更しました。

対象には次の画面が含まれます。

- Main Window
- Viewer
- Organization / Collection management
- Creator correction
- Saved Views
- Download Center

固定UI向けに **221組のJA/ENリソース** と **262箇所のDynamicResource参照** を使用しています。作品名、作者名、Provider由来のメタデータ自体は翻訳しません。

### Beta 2 r98で維持される主な不具合修正

今回の差し替えは既存r98の修正を維持したまま日英UI対応を加えたものです。以下はBeta 2に既に含まれ、今回の更新でも維持される主な修正です。

- PDF Viewerを閉じる／作品を素早く切り替える際のAppHangを抑止する非ブロッキング終了処理
- Provider ZIPのWindows属性をsymlinkとして誤認する互換性問題の修正
- archive内に安全に収まるdirectory symlink互換表現の取り込み改善
- Unicode等価表現および不要なdangling linkを含むProvider ZIPの互換性改善
- Windows Command PromptでのUTF-8 BOM解釈問題とC# compile regressionの修正
- 大容量ZIP後処理のI/O削減とwhole-tree検証の最適化
- 登録後cleanupを非ブロッキング化し、対象作品を優先してLibraryへ反映する改善
- DLsiteの販売floor差により公式商品ページを開けないケースの修正
- r98のbrowser transient-source promotion検証最適化

ZIP traversal、absolute/drive escape、Windows namespace/case collision、reparse point/junction/filesystem symlink生成禁止、最終Library内容のSHA-256検証などの安全境界は維持しています。

### 配布条件

- Windows x64
- ZIP
- unsigned
- .NET 10 self-contained
- ARM64は今回のBeta対象外
- Standalone Manual Local Intakeは未提供

DLsite / DMM・FANZAの対応する通常ダウンロードでは、ログインと公式Download操作はユーザー自身が公式ページ上で行います。DLMはその後の対応アーカイブ検証とローカルLibrary登録を支援します。

**DLM DesktopはErtelunによる独立したアプリケーションであり、DLsite、DMM、FANZAの公式アプリ・提携製品ではありません。**

## English

### Japanese / English UI support

DLM Desktop now supports **System / Japanese / English** UI selection. Restart DLM Desktop after changing the language setting.

The final localization repair replaces unreliable post-load translation of fixed XAML strings with JA/EN resources loaded before application windows are created.

Coverage includes:

- Main Window
- Viewer
- Organization / Collection management
- Creator correction
- Saved Views
- Download Center

The fixed UI layer uses **221 JA/EN resource pairs** and **262 DynamicResource references**. Work titles, creator names, and provider-supplied metadata are not machine-translated.

### Existing r98 fixes retained in this update

This replacement keeps the qualified r98 behavior and adds the JA/EN UI layer. Major Beta 2 fixes retained include:

- non-blocking PDF Viewer disposal to reduce hangs when closing or switching works quickly;
- compatibility fixes for provider ZIP Windows attributes that could be misclassified as symbolic links;
- safe handling of contained directory-symlink compatibility representations;
- compatibility improvements for Unicode-equivalent targets and unnecessary dangling provider links;
- fixes for Windows Command Prompt UTF-8 BOM handling and a C# compile regression;
- reduced I/O and optimized whole-tree verification during large ZIP post-processing;
- non-blocking post-registration cleanup and targeted library registration;
- corrected DLsite official product-page routing across reviewed sales floors; and
- r98 browser transient-source promotion verification optimization.

Security boundaries such as ZIP traversal rejection, absolute/drive escape rejection, Windows namespace/case-collision rejection, no filesystem symlink/junction/reparse creation, and final SHA-256 verification of promoted Library content remain in place.

### Distribution scope

- Windows x64
- ZIP distribution
- unsigned
- .NET 10 self-contained
- ARM64 not qualified for this Beta
- standalone Manual Local Intake not shipped

For supported ordinary downloads from DLsite / DMM・FANZA, the user performs the official-site login and Download action. DLM then assists with supported archive validation and local-library registration.

**DLM Desktop is an independent application by Ertelun and is not an official, affiliated, or endorsed application or product of DLsite, DMM, or FANZA.**

## Integrity

The replacement package SHA-256 is:

`66dd0661298a7f8bc906a29fc4e8f99a5406ea346989a936ab11737c76165272`

A matching SHA-256 verifies byte identity with the published package; it does not by itself guarantee software safety.
