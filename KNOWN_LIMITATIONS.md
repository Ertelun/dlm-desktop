# Known Limitations — DLM Desktop1.3.15

**1.3.15/r226：「ダウンロードキャッシュを削除」で、通常キャッシュに加えて管理領域に残ったダウンロードファイルも削除できるよう修正しました。失敗・再試行用ファイルを含む件数と容量を確認してから削除します。転送・取り込み中は削除せず、使用中・変更済み・削除失敗も結果に表示します。作品本体、保存サムネイル、Cookie・ログイン状態は保持します。**

**1.3.15/r226 fixes download-cache cleanup so it can also discard retained files in the managed download landing area after confirmation. The prompt includes the file count and byte total and warns about failed imports and retry files. Active transfers/imports block cleanup; locked, changed and failed files are reported. Library works, stored thumbnails, cookies and login state are preserved.**


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
