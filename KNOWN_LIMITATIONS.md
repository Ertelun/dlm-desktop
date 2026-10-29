# Known Limitations — DLM Desktop1.3.13

**1.3.13/r224：Chromiumの新しいCritical問題への緩和策として、埋込みブラウザーを一時停止しています。ライブラリ整理・検索・ローカル閲覧・手動取り込みは利用できます。ブラウザーを必要とする操作とブラウザーキャッシュ管理は停止中です。DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。再開には検証済みの修正版DLMが必要で、WebView2の更新だけでは解除されません。メインアプリの同梱.NET 10.0.14と実Runtimeガードにより、公開メタデータ・サムネイル通信のBrotli対応を安全に復旧しました。ブラウザー停止は継続します。**

**1.3.13/r224 temporarily disables the embedded browser to mitigate new Critical Chromium issues. Library organization, search, local viewing and Manual Intake remain available. Browser-dependent provider workflows and browser cache management are paused. Close DLM and extract the full official ZIP into a new empty folder. Recovery requires a reviewed DLM release; updating WebView2 alone does not lift the hold. HTTP Brotli support for public metadata/thumbnails is restored with patched .NET10.0.14 bundled with the main application and an actual-runtime guard; the browser hold remains.**


- Windows x64、ZIP、コード署名なし。ARM64はこの版の検証対象外です。 / Windows x64 ZIP, unsigned; ARM64 is outside this release's qualification.
- appフォルダを本体EXEの隣に置いてください。.NET同梱、埋込みブラウザは一時停止中です。 / Keep app beside the EXE. .NET is bundled; the embedded browser is temporarily paused.
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
