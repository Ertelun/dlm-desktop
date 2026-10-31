# Known Limitations — DLM Desktop1.3.14

**1.3.14/r225：修正収録を確認した安定版Microsoft Edge WebView2 Runtime 156.0.4314.58以降で、埋込みブラウザーとブラウザーキャッシュ管理を復旧しました。古い版・不明な版・プレビュー版は引き続き拒否します。DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開してください。ブラウザー利用時は公式WebView2 Runtimeも更新してDLMを再起動してください。.NET 10.0.14によるHTTP Brotli対応と認証情報・Cookie・リダイレクトの境界は維持しています。**

**1.3.14/r225 restores the embedded browser and browser cache management with reviewed stable Microsoft Edge WebView2 Runtime 156.0.4314.58 or later. Older, unknown and preview versions remain denied. Close DLM and extract the complete official ZIP into a new empty folder. For browser workflows, also update the official WebView2 Runtime and restart DLM. Patched .NET10.0.14 HTTP Brotli support and credential, cookie and redirect boundaries are retained.**


- Windows x64、ZIP、コード署名なし。ARM64はこの版の検証対象外です。 / Windows x64 ZIP, unsigned; ARM64 is outside this release's qualification.
- appフォルダを本体EXEの隣に置いてください。.NET同梱、ブラウザーには安定版WebView2 Runtime156.0.4314.58以降が必要です。 / Keep app beside the EXE. .NET is bundled; browser workflows require stable WebView2 Runtime156.0.4314.58 or later.
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
