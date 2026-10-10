# Provider Capabilities — DLM Desktop 1.3.2（r213）

DLM Desktopはローカルライブラリの整理・閲覧を中心とするアプリです。サイト上のログイン・購入・ダウンロード開始はユーザー自身が公式画面で行います。以下は対応する形式についての保存・検証・登録の補助範囲です。

DLM Desktop focuses on local-library organization and viewing. Users sign in, purchase, and start downloads on official pages. These are the supported assisted flows, subject to delivery-mode limits.

| サイト / Provider | 対応する操作 / Assisted flow | 制約 / Limits |
|---|---|---|
| DLsite | 公式画面から開始した通常ダウンロードの検証・登録。partファイルは同一作品のフォルダへ保存。 / Validate/register supported downloads; group multipart files under one work. | 分割ファイルの結合・EXEの自動実行は行わない。 / No automatic joining or executable launch. |
| DMM / FANZA | 対応する通常ダウンロードの検証・登録。 / Validate/register supported ordinary downloads. | 公式プレイヤー専用・DRM管理形式は公式手段を利用。 / Official-player/DRM modes stay on provider routes. |
| itch.io / BOOTH / Gumroad | ユーザーが開始した対応ファイルの保存・検証・登録。 / Save, validate, and register supported user-initiated downloads. | 全配信形式・全作品の対応は保証しない。 / Delivery-mode limits apply. |
| GOG | Offline Backup Game Installer / bonus file等を受付し、手動確定後に同一作品へ登録。 / Stage supported offline installers/bonus files, then group them after manual finalization. | 対象形式はEXE/BIN/ZIP。必要な一式を保存後「GOG受付を確定して登録」を押す。インストーラーの実行・展開は行わない。 / EXE/BIN/ZIP; explicitly finalize the complete set; no installer execution/unpacking. |
| Fantia / pixivFANBOX / Patreon / Ci-en | 1投稿を確認し保存受付を開始した後、ユーザーが明示的に保存した画像・添付ファイルを投稿ごとに登録。 / Confirm one post, start intake, and register files explicitly saved from it. | 投稿内全画像の列挙・作者の投稿巡回・バックグラウンド同期は提供しない。 / No post-asset enumeration, creator crawling, or background sync. |
| Ci-en内のDLsiteリンク / DLsite links in Ci-en | 対応するDLsite作品・予告作品リンクをDLsite画面へ引き継ぐ。 / Hand supported work/announcement links to the DLsite browser view. | 任意の外部ドメインへの横断ダウンロードは提供しない。 / No arbitrary cross-domain acquisition. |

**GOGは必要なファイルをすべて保存してから「GOG受付を確定して登録」を押してください。** 保存・検証中のファイルがある場合は確定できません。

**For GOG, save all required files, then click “Finalize GOG intake and register” (`GOG受付を確定して登録`).** Finalization waits for downloads and validation.

作品情報・サムネイルは対応する表示情報や公開情報から補助的に取得します。サイトの変更、ページの状態、配信形式などにより取得できない場合があります。

Metadata and thumbnails are assisted reads of supported visible/public information; availability depends on page state, site behavior, and delivery mode.

任意の手元フォルダを新規作品として登録する独立したManual Local Intakeは提供していません。一部の作品詳細にあるフォルダ選択・検証は既存の取得フローの補助です。

Standalone registration of arbitrary local folders is not provided. Folder selection/validation in some work-detail screens assists existing acquisition flows.

閲覧専用・公式プレイヤー専用・DRM管理・その他非対応形式は各サービスの公式手段をご利用ください。

Viewer-only, official-player-only, DRM-controlled, and unsupported modes remain on official provider routes.

**DLM DesktopはErtelunによる独立したアプリケーションであり、上記サイトの公式アプリ・提携製品ではありません。**

**DLM Desktop is an independent application by Ertelun, unaffiliated with and not endorsed by the listed providers.**
