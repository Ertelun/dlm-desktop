# DLM Desktop1.3.13 / r224 — safe partial HTTP recovery

2026-10-29 · Windows x64 · Japanese / English · unsigned ZIP

## 日本語

CVE-2026-111497への対応として制限していた、Gumroad公開メタデータ・GOG公開カタログ・公式サムネイル通信のBrotli対応を復旧します。メインアプリの同梱.NETをMicrosoftが修正済みと明記する10.0.14へ更新しました。実際のRuntimeが修正済み.NET10系列の場合だけBrotliを許可し、旧版や未確認の別メジャー系列ではgzip/deflate/identityに限定します。既存の認可・Cookie・認証情報・リダイレクト境界は維持しています。

これはHTTP通信経路だけの部分復旧です。Chromium Critical4件（CVE-2026-118306/118331/118348/118344）に対する埋込みブラウザーとキャッシュ管理の停止は継続します。Microsoftの該当修正を収録した安定版WebView2の対応がまだ確認できないためです。ライブラリ整理・検索・ローカル閲覧・手動取り込みは引き続き利用できます。

DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。実行中アプリやシステムのRuntimeを更新するだけでは、自己完結型の配布物は置き換わりません。既存ライブラリと設定は継続利用できます。

## English

This release restores Brotli responses for the existing credential-free Gumroad metadata, GOG catalog and official thumbnail HTTP transports by bundling patched .NET10.0.14 for the main application for CVE-2026-111497. An actual-runtime guard admits Brotli only on the reviewed .NET10 line at10.0.14 or later. Older and unreviewed major lines retain gzip/deflate/identity. Existing authorization, cookie, credential and redirect boundaries remain in place.

This is partial HTTP recovery. The embedded-browser and browser-cache security hold remains for CVE-2026-118306/118331/118348/118344 because a reviewed fixed stable WebView2 mapping is not yet established. Library organization, search, local viewing and Manual Intake remain available.

To update, close DLM and extract the entire official ZIP into a new empty folder. A system Runtime update alone does not replace this self-contained distribution. Existing libraries/settings remain usable. SDK10.0.402, ILLink10.0.12, other package versions and the verified Downloader Host are retained. Source/source archives/debug payloads are not published.

Fresh final-source and final-ZIP verification details accompany this formal Release. Synthetic isolated data only; no exploit/RCE or real account/library tests. This release does not claim every dependency is vulnerability-free.

Sources: https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9 ; https://builds.dotnet.microsoft.com/dotnet/release-metadata/10.0/releases.json ; https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security
