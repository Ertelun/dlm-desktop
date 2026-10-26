# Known Limitations — DLM Desktop1.3.11

**1.3.11/r222：HTTP応答のBrotli自動展開を停止し、CVE-2026-111497への緩和策を適用しました。gzip・deflateの処理と既存機能を保持します。古いDLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。埋込みブラウザーには安定版WebView2 Runtime156.0.4314.42以降が必要です。**

**1.3.11/r222 mitigates CVE-2026-111497 by disabling automatic HTTP Brotli decoding while retaining gzip, deflate and existing features. Close the old DLM and extract the full official ZIP into a new empty folder. Embedded browsing still requires stable WebView2 Runtime156.0.4314.42 or later.**


- Windows x64、ZIP、コード署名なし。ARM64はこの版の検証対象外です。 / Windows x64 ZIP, unsigned; ARM64 is outside this release's qualification.
- appフォルダを本体EXEの隣に置いてください。.NET同梱、ブラウザにはWebView2 Runtimeが必要です。 / Keep app beside the EXE. .NET is bundled; the browser requires WebView2 Runtime.
- 日英の言語変更はアプリ画面へ即時反映します。作品情報は機械翻訳しません。WebページとWindows標準ファイル選択画面はそれぞれの言語設定に従います。 / Application language changes apply immediately. Work metadata is not machine-translated. Web pages and Windows file dialogs use their own language settings.
- 各サービスの仕様は独立して変わるため、対応する通常配信に範囲を限定しています。 / Provider behavior can change independently; assistance is limited to supported delivery modes.
- ログイン・購入・ダウンロード開始はユーザー操作です。保護された配信などは公式手段を利用してください。 / Login, purchases and downloads remain user actions. Protected delivery stays on official routes.
- GOGは必要なファイル一式の保存・検証完了後、受付確定が必要です。 / GOG requires explicit finalization after the complete file set finishes saving and validation.
- DLsite分割ファイルの結合・インストーラー自動実行は行いません。 / Multipart merging and automatic installer execution are not provided.
- 任意の手元フォルダを新規作品登録する独立した手動取り込みは提供していません。 / Standalone registration of arbitrary local folders is not provided.
- 大きなアーカイブは整合性検証・展開・コピー・最終照合に時間がかかります。 / Large archives take time to validate, extract, copy and verify.
- 既に文字化けした展開済みファイル名は元ZIPからの再展開または再ダウンロードが必要です。 / Previously garbled extracted names require extraction from the original ZIP or a fresh download.
- 深い保存先ではWindowsのパス長制限により、一時ファイルの隔離・移動に失敗する場合があります。短い保存先を使用してください。 / Deep storage paths can hit Windows path-length limits during staging quarantine or moves; use a short storage path.
- ユーザー設定バックアップは作品ファイルのバックアップを含みません。 / User-state backups do not include original work files.
