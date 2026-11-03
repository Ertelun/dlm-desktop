# Download duplicate preflight / ダウンロード開始時の重複確認

DLM Desktop 1.3.16 / r227

## 登録済み作品の不要な再転送を避ける

DMM/FANZA・DLsite・BOOTHで作品IDを開始時に確認できる場合、登録したすべてのライブラリを照合します。同じ配信元・作品IDがあればダウンロードをスキップし、ダウンロードセンターに表示します。★以外のライブラリも対象です。タイトルや作者名の類似だけでは判定しません。

更新・取り直しには作品詳細の「再ダウンロード」を選び、公式ページでダウンロードを開始してください。元の保存先を開始前と完了時に確認します。通常ファイルの許可は一回だけ、未使用許可は2時間以内です。DLsiteの同じ作品の分割ファイルは残りのパートも受け付けます。

作品ID不明・矛盾するヒント・内容ハッシュでの識別は従来の完了後検証を使います。未接続ライブラリは確認済みとは扱いません。照合中は転送を一時停止しますが、開始直後の通信・先読み分が発生する場合があります。一時停止をRuntimeが拒否しても、開始時の照合と既知の重複キャンセルは実行します。

## Avoid transferring a registered work again

Downloads with an unambiguous DMM/FANZA, DLsite or BOOTH product ID check every configured library at start, not only the current new-download destination. An exact provider/product match is skipped and recorded in Download Center. Title or creator similarity alone never cancels a transfer.

For updates or intentional replacements, select Redownload in the work details, then start the download on the official page. The original destination is checked before transfer and at import. A single-file permission is consumed once and unused permissions expire after two hours. Reviewed DLsite multipart parts for that same work can continue within the permission window.

Unknown/conflicting IDs and content-hash providers retain completed-file validation. Unavailable libraries are not reported as verified clean. The local check pauses the transfer; initial requests, browser/TCP buffering and runtime Pause failures prevent any zero-bandwidth guarantee. Existing completed-file validation and collision checks remain in place.
