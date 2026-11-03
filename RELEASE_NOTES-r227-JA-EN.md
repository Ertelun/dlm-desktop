# DLM Desktop 1.3.16 / r227 — Skip registered works at download start

登録済み作品を全量ダウンロードしてから保留する処理を改善しました。DMM/FANZA・DLsite・BOOTHで作品IDを開始時に確認できる場合、登録済みライブラリを照合し、同じ作品の転送を早い段階でスキップします。

Supported DMM/FANZA, DLsite and BOOTH downloads now check an unambiguous provider/product ID against all configured libraries at download start. Already registered works are skipped before the full transfer and import, reducing avoidable bandwidth use.

- 照合中は転送自体を一時停止し、許可した転送だけを再開します。ダウンロードセンターにスキップを記録します。
- 更新・取り直しには作品詳細の「再ダウンロード」を使用してください。開始前と完了時に元の保存先を確認します。保存先の消失・移動・重複・未接続では置換を止めます。
- 通常ファイルの明示許可は一度だけ使用し、同時開始した別の転送へ流用しません。DLsiteの同じ作品の分割ファイルは、期限内の明示許可で引き続き受け付けます。
- タイトルや作者名だけでは止めません。作品ID不明、複数ID、ファイル名と一時URLの食い違い、内容ハッシュによる識別は、従来の完了後の検証を継続します。

Use Redownload in a work's details for an intentional update or replacement. The original location is checked both before transfer and at import; missing, moved, duplicate or disconnected destinations stop replacement. Single-file permission is consumed once. Reviewed DLsite multipart filenames retain permission for remaining parts within the two-hour window.

The check uses exact provider/product identity, not title or creator similarity. Unknown/conflicting hints and content-hash providers keep their completed-file validation. Initial requests, response bytes and browser/TCP buffering can still consume bandwidth; this does not promise zero network traffic. If the runtime rejects Pause at admission, the early check and duplicate cancellation still run. No real-provider bandwidth savings percentage is claimed.

Windows x64, unsigned ZIP. Close DLM, extract the entire ZIP into a new empty folder and keep the top-level EXE and app/ together. Existing libraries/settings remain usable. Stable WebView2 Runtime 156.0.4314.58 or later remains required for browser workflows. No SDK, runtime or dependency upgrade is included. Product source and source ZIP stay local.

DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。EXEとapp/を一緒に保持します。既存ライブラリ・設定を利用できます。

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.16
