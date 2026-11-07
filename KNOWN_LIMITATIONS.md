# Known Limitations — DLM Desktop1.3.20

**1.3.20/r231：安定版WebView2 Runtime 157.0.4341.42以降を条件に、埋込みブラウザーとブラウザーキャッシュ操作を復旧しました。DLMと公式Runtimeの両方を更新し、DLMを再起動してください。**

**1.3.20/r231 restores the embedded browser and browser-cache operations with stable WebView2 Runtime157.0.4341.42 or later. Update DLM and the official Runtime, then restart DLM. Older/unknown/preview runtimes remain blocked.**


- Windows x64、ZIP、コード署名なし。ARM64はこの版の検証対象外です。 / Windows x64 ZIP, unsigned; ARM64 is outside this release's qualification.
- appフォルダを本体EXEの隣に置いてください。.NET同梱、ブラウザーは安定版WebView2 Runtime157.0.4341.42以降が必要です。 / Keep app beside the EXE. .NET is bundled; browser workflows require stable WebView2 Runtime157.0.4341.42 or later.
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

## pixiv / X

- 保存対象は対応する画像形式です。表示中の画像やページ構造によって情報を取得できない場合があります。 / Supported image formats only; metadata may be unavailable for some page structures or displayed images.
- pixivで作者を確認できない場合は保存受付を止めます。投稿ページを読み直して再試行してください。 / An unidentified pixiv creator stops admission; reload the artwork detail and retry.
- Xの作者名はユーザー入力です。実際の投稿アカウントを確認・推測しません。 / X creator names are entered by you; the actual posting account is not verified or inferred.
- Xの保存先フォルダー名は安全に変換され識別情報が付きます。表示上の作品名・作者名には入力を使用します。 / X folder names are sanitized and carry a disambiguator; displayed title/creator values retain your input.
- 同じ作品名・作者名への保存は同じ作品へ追加されます。別作品にする場合は入力を変更してください。 / Matching title/creator values append to one work; change them to start a separate work.
