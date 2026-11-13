# Provider Capabilities — DLM Desktop 1.3.21

**埋込みブラウザーとWebView2を使うキャッシュ操作には、公式の安定版 WebView2 Runtime 157.0.4341.57 以降が必要です。DLMと公式Runtimeを更新し、DLMを再起動してください。**

**The embedded browser and WebView2-backed cache controls require official stable WebView2 Runtime 157.0.4341.57 or later. Update DLM and the official Runtime, then restart DLM.**


ログイン、購入、ダウンロード開始は、ユーザー自身が各サービスの公式画面で操作します。取得できる配信形式を限定し、保存したファイルを検証してローカルライブラリへ登録します。

Sign-in, purchases and download initiation are user actions on official pages. Acquisition assistance is limited to supported delivery modes; files are validated before local registration.

| 配信元 / Provider | 対応する経路 / Supported route |
|---|---|
| DLsite | 通常の対応アーカイブと分割ファイル。part1.exe・後続partを原本のまま同じ作品へ保存。 / Supported ordinary archives and multipart originals grouped under one work. |
| DMM/FANZA | 対応する通常ダウンロードの保存・検証・登録。 / Supported ordinary-download validation and registration. |
| itch.io / BOOTH | 対応アーカイブと確認済みの単体ファイル形式。 / Supported archives and reviewed direct-file formats. |
| Gumroad | 公式ライブラリやコンテンツ画面から明示的に開始した対応ファイル。 / Supported files explicitly downloaded from official library/content pages. |
| GOG | Offline Backup Game Installerの.exe/.bin等を保存し、ユーザーが受付を確定して1作品へ登録。 / Save the required offline installer files, then explicitly finalize intake as one work. |
| pixiv | 投稿詳細で明示的に保存した画像を作者ID・投稿ID別に登録し、作者アイコンをサムネイルに使用。 / Explicitly saved artwork images grouped by creator/artwork ID, with creator profile icons. |
| X（Twitter） | 右操作欄で作品名・作者名を入力して画像を保存。同じ名前へ追加し、最初の画像をサムネイルに保持。 / Save images using the title/creator fields; matching names append, retaining the first image thumbnail. |
| Fantia / pixivFANBOX / Patreon / Ci-en | 選択した投稿で明示的に保存した画像・添付ファイルをまとめて登録。 / Group supported images and attachments explicitly saved from the selected post. |

Ci-enの対応するDLsite作品・予告作品リンクは、DLsite画面へ引き継ぎます。DLsiteの分割ファイルの結合、インストーラーの自動実行は行いません。

Supported Ci-en links to DLsite work/announcement pages open in the DLsite screen. Multipart merging and automatic installer execution are not provided.

保護された配信、公式プレイヤー専用、DRM管理などの対象外の方式は、各サービスの公式手段をご利用ください。任意のローカルフォルダを新規作品として登録する独立した手動取り込みは提供していません。既存取得フローのフォルダ選択・検証補助とは別です。

Protected, official-player-only, DRM-controlled and unsupported delivery modes remain on official provider routes. Standalone registration of arbitrary local folders is not shipped; local folder selection in existing handoff flows is a validation helper.

DLMは各サービスの公式アプリ・提携製品ではありません。全作品・全配信形式への対応やアカウント自動操作を保証するものではありません。

DLM is not an official or affiliated provider application. Support is not universal across works or delivery modes and does not include provider-account automation.

## Explicit work update checks / 作品のアップデート確認

DMM/FANZA、DLsite、BOOTH、Gumroad、GOGでは、選択した登録済み1作品の公開商品ページに対する明示的な更新確認を許可します。更新日やローカルの比較日時が不明な場合、自動で再ダウンロードを決めません。これはバックグラウンド同期や作品一覧の自動取得を許可するものではありません。

DMM/FANZA, DLsite, BOOTH, Gumroad and GOG permit an explicit public-page update check for one selected registered work. Missing official or local dates do not trigger an automatic redownload decision. This does not enable background synchronization or catalog enumeration.

## pixiv・X（Twitter）の画像保存 / pixiv and X image saving

会員・支援サイトにpixivとX（Twitter）を追加しました。並び順はpixiv → pixivFANBOX → Fantia → Patreon → Ci-en → Xです。保存したい画像の操作は、ユーザー自身が公式ページ上で開始します。一覧の巡回や一括取得は行いません。

**pixiv:** 投稿詳細を開いて画像を保存します。現在の投稿情報から作者名・作者ID・タイトル・投稿ID・投稿URLを取得し、ライブラリ内のpixiv／作者ID／投稿IDへ分類します。同じ投稿の追加画像は同じ作品にまとめます。サムネイルには作者のプロフィールアイコンを使います。旧形式・新形式の初期ページ情報と、表示中のページ自身が受信した作品・作者情報を照合します。作者を特定できない場合は受付を止め、アイコンだけ取得できない場合は画像を保存して「作者アイコン未取得」と表示します。

**X（Twitter）:** 右側の操作欄で「保存作品名」「作者名」を確認・編集してから画像を保存します。初期作者名は「X（twitter）」、初期作品名はXを初めて選んだ現在日時（日本時間）です。画像保存ごとのフォルダー選択画面は出ません。入力した名前からライブラリ内の保存先を自動作成し、同じ作品名・作者名なら同じ作品へ追加します。「新しい作品」で作品名を現在日時に戻せます。最初に保存した画像をサムネイルに保持し、投稿者のアカウントは推測しません。

サイトのページ構造・配信方式によって取得できない場合があります。検証は隔離した合成データを使用し、実アカウントでの全作品・全保存方式への対応を保証するものではありません。ブラウザーは正式復旧版から引き継ぐ安定版WebView2 Runtime **157.0.4341.57以降**が必要です。

## Saving images from pixiv and X (Twitter)

Membership / Fan sites now includes pixiv and X, ordered pixiv → pixivFANBOX → Fantia → Patreon → Ci-en → X. You initiate each image save on the official page. No catalog crawling or bulk downloading is provided.

**pixiv:** Open an artwork detail page and save an image. DLM reads the current artwork's creator name/ID, title, artwork ID and canonical URL, then groups saved images by creator ID and artwork ID. The creator's profile icon is used as the thumbnail. Legacy and Next page data and responses already requested by the displayed page are matched to the current artwork. An unidentified creator stops admission; an unavailable icon leaves the images saved with an explicit icon-unavailable status.

**X:** Edit Work title and Creator in the controls on the right before saving an image. Creator defaults to “X（twitter）”; the title defaults to the current Japan date/time when X is first selected. A folder picker no longer opens for each image. DLM creates the destination within the configured library from the entered names. Identical title/creator values append to the same work; New work resets the title to the current time. The first saved image remains its thumbnail. Account ownership is not inferred from timeline images.

Page structures and delivery modes can change. Qualification uses isolated synthetic data, not every real account, artwork or save route. The reviewed stable WebView2 Runtime floor remains **157.0.4341.57**. Authentication, browser-owned downloads and local validation boundaries remain in place.
