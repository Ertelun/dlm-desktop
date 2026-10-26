# DLM Desktop 1.3.11 / r222 — security update

2026-10-26 · Windows x64 · Japanese / English · unsigned ZIP

## 日本語

公開商品情報・公式サムネイル取得のHTTP処理でBrotli応答の自動展開を停止し、CVE-2026-111497へのアプリケーション側の緩和策を適用しました。CNAのCVSS 4.0評価はCritical 9.2、Microsoftの.NET向けCVSS 3.1評価はHigh 8.1です。同梱.NET 10.0.12と、Brotliの自動展開を有効にしていた実際の3つのHTTP処理を照合して対応しています。gzip・deflate・非圧縮応答の処理は保持します。

古いDLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。最上位EXEとapp/を一緒に使用します。既存のライブラリ・ユーザー設定を引き続き利用できます。展開済みの古い実行ファイルだけを置き換えないでください。

WebView2の安定版156.0.4314.42以降の2段階チェック、作品の明示的なアップデート確認、閲覧・削除・バックアップ保護は保持します。WebView2は同梱・自動インストールしません。外部Runtimeの更新後はDLMを再起動してください。

.NET 10.0.12と他の依存関係は変更していません。この対策はDLMの確認済みHTTP経路で脆弱なBrotliデコーダーへ応答を渡さないためのもので、同梱・外部コンポーネント全体の脆弱性を全て解消したとの主張ではありません。今後Brotli利用を追加する場合は、修正済み依存関係と再検証が必要です。

## English

This release mitigates CVE-2026-111497 in the three confirmed DLM HTTP transports used for public product metadata and official thumbnails. It stops advertising and automatically decoding Brotli responses while retaining gzip, deflate and identity responses. The CNA rates the Brotli issue Critical (CVSS 4.0 9.2); Microsoft's .NET advisory rates it High (CVSS 3.1 8.1). Applicability was checked against the bundled .NET 10.0.12 and the actual production HTTP handlers.

Close the old DLM, extract the complete official ZIP into a new empty folder, and start the top-level EXE with app/ beside it. Existing libraries and user settings remain usable. Do not replace only the old EXE.

The stable WebView2 minimum156.0.4314.42 and two-stage admission checks, explicit work update checks, viewing/deletion and backup protections are retained. WebView2 is external and is not installed by this ZIP. Restart DLM after an external Runtime update.

Bundled .NET10.0.12 and other dependencies are unchanged. This is an application-level mitigation of the confirmed HTTP paths, not a claim that every bundled or external component is free of vulnerabilities. Future Brotli use requires patched dependencies and renewed validation.

## Validation / 検証

The exact published1.3.10/r221 assemblies and runtime were observed with a harmless loopback compression fixture: all three constructor-created transports admitted Brotli. The patched production transports pass85 checks covering request negotiation, unsolicited Brotli, stacked encoding, gzip/deflate/identity compatibility and credential-free requests. No exploit or arbitrary-code-execution test was attempted.

Formal publication requires fresh23-project validation, exact-final-package regressions including the85HTTP checks,53browser checks and36work update-check assertions, isolated startup/major operations,39native parser probes and finalZIP/source/debug-exclusion gates. The VERIFICATION asset records the completed results and exact ZIP hash; earlier logs are not reused as fresh validation.

## Sources

- https://cveawg.mitre.org/api/cve/CVE-2026-111497
- https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9
- https://api.msrc.microsoft.com/cvrf/v3.0/cvrf/2026-Oct

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.11


2026-10-26 metadata correction: the runtime ZIP is unchanged. The original verification asset mistyped FileVersion as 1.3.11.221; the actual validated EXE is 1.3.11.222. Use VERIFICATION-v2, PUBLIC-PROVENANCE-v2 and SHA256SUMS-v2 below. The original metadata assets are retained as historical records and are superseded. The README ZIP hash has also been corrected to the published SHA256SUMS value.
資料訂正：配布ZIPは変更していません。検証資料のFileVersion転記ミスとREADMEのハッシュ表記を訂正しました。最新版の資料は末尾v2の3ファイルです。旧資料は履歴として保持しています。
