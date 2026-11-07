# DLM Desktop 1.3.20 / r231 — pixiv and X image saving

## 日本語

会員・支援サイトにpixivとX（Twitter）を追加しました。

- pixivの投稿画像を、作者IDと投稿IDで分類して保存。作者名・投稿タイトル・投稿URLを記録し、作者のプロフィールアイコンをサムネイルに使用します。
- 現行pixivのページ構造に対応。初期ページ情報がない場合も、表示中のページ自身が受信した作品情報を照合します。取得失敗の理由を記録し、作品情報エラーへ認証拒否の一般案内を付ける問題も修正しました。
- Xの右操作欄に保存作品名・作者名を追加。初期値は現在日時と「X（twitter）」です。画像保存ごとのフォルダー選択を廃止し、同じ名前なら同じ作品に画像を追加。最初の保存画像をサムネイルに保持します。
- サイト順をpixiv → pixivFANBOX → Fantia → Patreon → Ci-en → Xへ変更しました。

画像の保存開始はユーザー操作です。一覧の巡回、一括保存、投稿アカウントの推測は行いません。作者情報不明時は誤分類せず受付を停止し、作者アイコンのみ不明なら画像は保存してアイコン未取得を表示します。サイト構造や保存方式によって取得できない場合があります。

DLMを終了し、ZIP全体を新しい空フォルダーへ展開してください。EXEとapp/を一緒に保持します。既存ライブラリと設定を利用できます。Windows x64、コード署名なし。.NET同梱。ブラウザーには公式安定版WebView2 Runtime **157.0.4341.42以降**が必要です。1.3.19の正式な復旧条件とHTTP・認証・保存先の検査を引き継ぎ、ローカル検証用の解除設定は含みません。

## English

Adds pixiv and X (Twitter) to Membership / Fan sites.

- pixiv saves artwork images by creator ID and artwork ID, records creator/title/canonical URL, and uses the creator's profile icon as the thumbnail.
- Supports current pixiv page structures, including matching metadata already received by the displayed page. Adds bounded failure diagnostics and removes misleading authentication guidance from metadata failures.
- X uses Work title and Creator fields on the right. Defaults are the current Japan date/time and “X（twitter）”. No per-image folder picker: matching names append to one work, retaining its first image as thumbnail.
- Site order is pixiv, pixivFANBOX, Fantia, Patreon, Ci-en, X.

Saves remain user initiated. No crawling, bulk downloading or account inference. Unknown pixiv creators stop admission; missing profile icons leave images saved with an explicit status. Some page structures/save routes may remain unsupported.

Close DLM and extract the complete ZIP into a new empty folder, keeping EXE and app/ together. Existing libraries/settings remain usable. Windows x64, unsigned, .NET bundled. Browser workflows retain the reviewed stable WebView2 **157.0.4341.42+** requirement from 1.3.19, along with HTTP/authentication/path checks. No local verification override is shipped.

Qualification uses isolated synthetic data and actual WebView2. Real account logins, every artwork/save route and purchases were not tested. No dependency/SDK/runtime upgrade is included in this feature release.

Release: https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.20
