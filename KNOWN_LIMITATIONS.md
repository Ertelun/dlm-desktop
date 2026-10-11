# Known Limitations — DLM Desktop 1.3.4

- Windows x64、ZIP、コード署名なし。ARM64はこの版の検証対象外です。 / Windows x64 ZIP, unsigned; ARM64 is outside this release's qualification.
- appフォルダを本体EXEの隣に置いてください。.NET同梱、ブラウザにはWebView2 Runtimeが必要です。 / Keep app beside the EXE. .NET is bundled; the browser requires WebView2 Runtime.
- 日英の言語変更はアプリ画面へ即時反映します。作品情報は機械翻訳しません。WebページとWindows標準ファイル選択画面はそれぞれの言語設定に従います。 / Application language changes apply immediately. Work metadata is not machine-translated. Web pages and Windows file dialogs use their own language settings.
- 各サービスの仕様は独立して変わるため、対応する通常配信に範囲を限定しています。 / Provider behavior can change independently; assistance is limited to supported delivery modes.
- ログイン・購入・ダウンロード開始はユーザー操作です。保護された配信などは公式手段を利用してください。 / Login, purchases and downloads remain user actions. Protected delivery stays on official routes.
- GOGは必要なファイル一式の保存・検証完了後、受付確定が必要です。 / GOG requires explicit finalization after the complete file set finishes saving and validation.
- DLsite分割ファイルの結合・インストーラー自動実行は行いません。 / Multipart merging and automatic installer execution are not provided.
- 任意の手元フォルダを新規作品登録する独立した手動取り込みは提供していません。 / Standalone registration of arbitrary local folders is not provided.
- 大きなアーカイブは整合性検証・展開・コピー・最終照合に時間がかかります。 / Large archives take time to validate, extract, copy and verify.
- ユーザー設定バックアップは作品ファイルのバックアップを含みません。 / User-state backups do not include original work files.
