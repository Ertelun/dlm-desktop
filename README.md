# DLM Desktop — Doujin Library Manager Desktop

**増えた同人・デジタル作品を、PC上でまとめて整理・閲覧するローカル中心のライブラリ。**

DLM Desktop is a local-first Windows library by Ertelun for organizing, finding, and viewing digital works you keep on your PC.

**Public Beta 2 · Windows x64 · ZIP · unsigned · by Ertelun**

[Public Beta 2をダウンロード](https://github.com/Ertelun/dlm-desktop/releases/tag/v0.1.0-beta.2)

配布元はこの公式Ertelun GitHub Releaseです。SHA-256はReleaseページとsidecarで確認できます。

## 主な機能

- 登録済みローカルライブラリの整理・検索
- 画像/PDF等の対応形式をローカル閲覧
- 閲覧位置の保存・再開
- DLMユーザー状態のBackup / Restore
- DLsite / DMM・FANZAの対応する通常ダウンロードでは、公式ページ上のユーザー操作後にアーカイブ検証とローカルライブラリ登録を支援

> **Public Beta 2では、任意の手元フォルダを新規作品として登録する standalone Manual Local Intake は提供しません。**
> 一部の既存Provider-handoff画面にはローカルフォルダ選択・検証の補助がありますが、それ自体は新規ローカル作品のLibrary登録を完了する機能ではありません。

## Screenshots

以下は公開用のsynthetic demo libraryです。顧客データ、購入履歴、実アカウント情報、著作権保護された作品画像は使用していません。

### Library overview

![DLM Desktop library overview showing a synthetic local library](screenshot-library-overview.png)

<table>
<tr>
<td width="50%">

**作者別グルーピング**

<img src="screenshot-library-grouping.png" alt="DLM Desktop library grouped by synthetic creator names">

</td>
<td width="50%">

**作品詳細**

<img src="screenshot-work-detail.png" alt="DLM Desktop work detail panel for a synthetic demo work">

</td>
</tr>
<tr>
<td width="50%">

**Viewer**

<img src="screenshot-viewer.png" alt="DLM Viewer displaying a synthetic demo page">

</td>
<td width="50%">

**Settings / Backup & Restore**

<img src="screenshot-settings-backup.png" alt="DLM Desktop settings showing library root and backup restore controls">

</td>
</tr>
</table>

## Public Beta

Public Beta 2は **Windows x64 / ZIP / unsigned** で公開します。ARM64はPublic Beta 2の対象外です。

このPublic Betaはコード署名されていないため、WindowsでUnknown PublisherまたはMicrosoft Defender SmartScreenの警告が表示される場合があります。この公式Ertelun GitHub Releaseから取得したこととSHA-256を確認したうえで、実行するかをご判断ください。

Public Beta 2 package SHA-256:

`b3174d3206f53005192cac50423950625b3b8de9d4fec619a18255b93ed7b7cf`

SHA-256の一致は公開した配布物とのbyte同一性確認であり、単独でソフトウェアの安全性を保証するものではありません。

大容量作品では、整合性検証・展開・物理コピー・最終SHA-256検証のため、Download完了後からLibrary登録まで数分以上かかる場合があります。Public Beta 2では最終整合性検証を省略していません。

## Provider-assisted acquisition

DLsite / DMM・FANZAの対応する通常ダウンロードでは、DLM内の公式ページでユーザー自身がログイン・Download操作を行い、その後のアーカイブ検証とローカルライブラリ登録をDLMが支援します。

閲覧専用・公式プレイヤー専用・DRM管理・その他DLMが対応していない配信方式は、各サービスの公式手段をご利用ください。

**DLM DesktopはErtelunによる独立したアプリケーションであり、DLsiteおよびDMM/FANZAの公式アプリ・提携製品ではありません。**

詳しくは [Provider Capabilities](PROVIDER_CAPABILITIES.md) と [Known Limitations](KNOWN_LIMITATIONS.md) を確認してください。

## Free Public Beta

Public Beta 2は無料です。DLM Coreのローカル利用に、支払い・DLMアカウント・サブスクリプションは必要ありません。

Public Beta 2では、支払い、PWYW、サブスクリプション、アプリ内広告、有料プロモーション、分析SDK/テレメトリSDKを有効化していません。

## Feedback / Security

公開Issueで受け付ける主なカテゴリは次の2つです。

- 既存機能の再現可能な不具合
- 既に対応しているDLsite / DMM・FANZAフローの互換性問題

新機能要望・個別UX改善要望は、Public Betaでは原則として受付対象としていません。

- [Normal feedback / bug reports](https://github.com/Ertelun/dlm-desktop/issues)
- [Feedback guidance](FEEDBACK.md)
- [Security policy](SECURITY.md)
- [Privacy](PRIVACY.md)
- [Known Limitations](KNOWN_LIMITATIONS.md)
- [Release provenance](PROVENANCE.json)

セキュリティ脆弱性は公開Issueへ投稿せず、GitHubの **Security → Report a vulnerability** からPrivate Vulnerability Reportingを使用してください。
