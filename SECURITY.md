# Security Policy

Current supported distribution: **DLM Desktop 1.3.6 (r217), Windows x64**.

Canonical download: [Ertelun GitHub Release v1.3.6](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.6).

Package SHA-256: `be8820a0a0c95528ebb82b540d11ce52bad640ac80a526b384a8c1047f939d72`.

The embedded browser requires **Microsoft Edge WebView2 Runtime 155.0.4283.60 or later**. DLM 1.3.6 refuses older or unrecognized Runtime versions before opening external content and checks the selected environment again. This mitigates the Chromium SVG/media issues Microsoft rates Critical, CVE-2026-110148 and CVE-2026-110151. WebView2 remains an external, automatically updated shared Runtime. Obtain updates from the [official Microsoft WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and restart DLM. Library organization, local viewing and Manual Intake remain available while the browser is paused.

Meeting this minimum does not certify the absence of other vulnerabilities. Keep Evergreen security updates enabled. The .NET Runtime and other dependency versions are retained; the release verification asset describes the actual validation scope.

The ZIP is unsigned. Verify the official source and SHA-256. A checksum verifies package identity and does not by itself guarantee safety. Historical releases are retained for traceability; older browser admission behavior is not the recommended rollback for this security mitigation.

Please report sensitive vulnerabilities privately through GitHub **Security → Report a vulnerability**. Do not post credentials, tokens, private account information, purchased files or sensitive local paths in public issues. Private vulnerability reporting is enabled for this repository.

現在のサポート対象はDLM Desktop 1.3.6（r217）、Windows x64です。埋込みブラウザはWebView2 Runtime 155.0.4283.60以降で利用できます。古い版や確認できない版では外部ページを開きません。Microsoft公式のEvergreen Runtimeを更新してDLMを再起動してください。ライブラリと手動取り込みは引き続き利用できます。配布物のSHA-256と正式な配布元を確認してください。

機密性のある脆弱性はGitHubのSecurity → Report a vulnerabilityから非公開で報告してください。認証情報、トークン、購入ファイル、機密のローカルパスなどを公開Issueへ投稿しないでください。