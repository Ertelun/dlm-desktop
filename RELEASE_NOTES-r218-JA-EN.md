# DLM Desktop 1.3.7（r218）— WebView2セキュリティ対策

埋込みブラウザは Microsoft Edge WebView2 Runtime **155.0.4283.60 以降**を必要とします。古い版や確認できない版では外部ページを開かず、Runtime更新とDLM再起動の案内を表示します。ライブラリの整理・閲覧と手動取り込みは引き続き利用できます。

MicrosoftがCriticalと公表したChromiumのSVG・メディア処理の問題（CVE-2026-110148、CVE-2026-110151）を受けた対策です。Runtimeの確認をブラウザ作成前に行い、実際に選択された環境も再確認します。認証用ポップアップは確認済み環境を共有します。ライブラリ、既存ファイル、認証情報を変更する処理はありません。

[Microsoft公式WebView2配布ページ](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)からEvergreen Runtimeを更新し、DLMを再起動してください。WebView2は外部の共有Runtimeです。このZIPはRuntime自体を同梱・インストールしません。最低条件を満たす版でも、Microsoftの継続的なセキュリティ更新を利用してください。

以前のDLMを終了し、ZIPを新しい空のフォルダへすべて展開して起動してください。既存のライブラリとユーザー設定を利用できます。1.3.5の進捗表示・日本語ZIPファイル名の修正を含みます。

# DLM Desktop 1.3.7 (r218) — WebView2 security mitigation

The embedded browser now requires Microsoft Edge WebView2 Runtime **155.0.4283.60 or later**. Older or unrecognized versions cannot open external content; DLM explains how to update the Runtime and restart. Library organization, local viewing and Manual Intake remain available.

This responds to the Chromium SVG and media issues that Microsoft rates Critical (CVE-2026-110148 and CVE-2026-110151). DLM checks the Runtime before creating a browser and checks the actual selected environment again. Authentication popups share that checked environment. The mitigation does not modify existing library files or credentials.

Update the Evergreen Runtime from the [official Microsoft WebView2 download page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and restart DLM. WebView2 is a shared external Runtime; this ZIP does not bundle or install it. Continue receiving Microsoft's security updates after meeting this release's minimum requirement.

Close the previous DLM, extract the complete ZIP into a new empty folder and run the EXE. Existing libraries and settings remain usable. The download progress and Japanese ZIP filename fixes from 1.3.5 are retained.

The .NET Runtime, NuGet packages, native libraries, features and storage formats retain their existing versions. This is a browser admission mitigation; it does not claim that all native/browser vulnerabilities are resolved. See the release verification asset for the checks actually performed.

References: [Microsoft CVE-2026-110148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-110148), [Microsoft CVE-2026-110151](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-110151), [WebView2 Runtime updates](https://learn.microsoft.com/en-us/microsoft-edge/webview2/release-notes/runtime/).
Validation: all 22 test projects PASS;49 browser admission checks; final ZIP 575 files byte matched; startup, host,5 exact ZIP regression runners and 39 native parser probes PASS; actual WPF browser smoke on signed WebView2 155.0.4283.62 PASS. No reused owner confirmation or live account access is claimed.

1.3.6（r217）は配布構成の再確認により撤回しました。現在の正式版は1.3.7（r218）です。製品デバッグファイルはローカルに保持し、配布ZIPから除外しています。

The initial 1.3.6/r217 distribution was withdrawn during packaging review. Use 1.3.7/r218. Product debug symbol files remain local and are excluded from the public ZIP.
