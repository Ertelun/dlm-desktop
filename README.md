# DLM Desktop

**増えた同人・デジタル作品を、PC上でまとめて整理・閲覧するローカル中心のライブラリ。**

DLM Desktop (Doujin Library Manager Desktop) is a local-first Windows library by Ertelun for organizing, finding, and viewing digital works you keep on your PC.

**Public Beta · Windows x64 · unsigned · by Ertelun**

> 初回Public Betaの正規配布元は、この `Ertelun/dlm-desktop` GitHub Releasesのみです。

## 主な機能

- ローカルライブラリで作品を整理・検索
- 対応形式をローカルで閲覧
- 既に手元にある作品を手動取り込み
- DLMのユーザー状態をBackup / Restore
- DLsite / DMM・FANZAの対応する通常ダウンロードでは、公式ページ上のユーザー操作後にアーカイブ検証とローカルライブラリ登録を支援

## Public Beta

初回Public Betaは **Windows x64 / ZIP配布 / unsigned** です。ARM64は初回Betaの対象外です。

このPublic Betaはコード署名されていないため、WindowsでUnknown PublisherまたはMicrosoft Defender SmartScreenの警告が表示される場合があります。公式Ertelun GitHub Releaseから取得したこととSHA-256を確認したうえで、実行するかをご判断ください。

**配布ZIP SHA-256**

`207a69e9af681b6d75d968886669e33ec7f722a864dc56c797bd364822884f4e`

SHA-256の一致は公開した配布物とのbyte同一性確認であり、単独でソフトウェアの安全性を保証するものではありません。

## Provider-assisted acquisition

DLsite / DMM・FANZAの対応する通常ダウンロードでは、DLM内の公式ページでユーザー自身がログイン・Download操作を行い、その後のアーカイブ検証とローカルライブラリ登録をDLMが支援します。

閲覧専用・公式プレイヤー専用・DRM管理・その他DLMが対応していない配信方式は、各サービスの公式手段をご利用ください。

**DLM DesktopはErtelunによる独立したアプリケーションであり、DLsiteおよびDMM/FANZAの公式アプリ・提携製品ではありません。**

詳しくは [Provider Capabilities](PROVIDER_CAPABILITIES.md) と [Known Limitations](KNOWN_LIMITATIONS.md) を確認してください。

## Free Public Beta

**DLM Desktop Public Beta（Windows x64）は無料です。**

DLM Coreのローカル利用に、支払い・DLMアカウント・サブスクリプションは必要ありません。Provider-assisted acquisitionでは、各サービスの正規ログインが必要になる場合があります。

初回Betaでは、支払い、PWYW、サブスクリプション、アプリ内広告、有料プロモーション、分析SDK/テレメトリSDKを有効化しません。

## Feedback / Security

- 通常の不具合・互換性・機能要望: `{BUG_REPORT_URL}`
- Provider互換性: `{PROVIDER_COMPATIBILITY_REPORT_URL}`
- Security vulnerability: `{PRIVATE_SECURITY_REPORT_URL}`

公開前に上記トークンを実URLへ置換してください。

## Privacy / Security

- [Privacy](PRIVACY.md)
- [Security](SECURITY.md)
- [Known Limitations](KNOWN_LIMITATIONS.md)
- [Release provenance](PROVENANCE.json)
