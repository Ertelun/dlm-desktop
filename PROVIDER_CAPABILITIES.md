# Provider Capabilities — DLM Desktop 1.3.5

**1.3.11/r222：HTTP応答のBrotli自動展開を停止し、CVE-2026-111497への緩和策を適用しました。gzip・deflateの処理と既存機能を保持します。古いDLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。埋込みブラウザーには安定版WebView2 Runtime156.0.4314.42以降が必要です。**

**1.3.11/r222 mitigates CVE-2026-111497 by disabling automatic HTTP Brotli decoding while retaining gzip, deflate and existing features. Close the old DLM and extract the full official ZIP into a new empty folder. Embedded browsing still requires stable WebView2 Runtime156.0.4314.42 or later.**


ログイン、購入、ダウンロード開始は、ユーザー自身が各サービスの公式画面で操作します。取得できる配信形式を限定し、保存したファイルを検証してローカルライブラリへ登録します。

Sign-in, purchases and download initiation are user actions on official pages. Acquisition assistance is limited to supported delivery modes; files are validated before local registration.

| 配信元 / Provider | 対応する経路 / Supported route |
|---|---|
| DLsite | 通常の対応アーカイブと分割ファイル。part1.exe・後続partを原本のまま同じ作品へ保存。 / Supported ordinary archives and multipart originals grouped under one work. |
| DMM/FANZA | 対応する通常ダウンロードの保存・検証・登録。 / Supported ordinary-download validation and registration. |
| itch.io / BOOTH | 対応アーカイブと確認済みの単体ファイル形式。 / Supported archives and reviewed direct-file formats. |
| Gumroad | 公式ライブラリやコンテンツ画面から明示的に開始した対応ファイル。 / Supported files explicitly downloaded from official library/content pages. |
| GOG | Offline Backup Game Installerの.exe/.bin等を保存し、ユーザーが受付を確定して1作品へ登録。 / Save the required offline installer files, then explicitly finalize intake as one work. |
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
