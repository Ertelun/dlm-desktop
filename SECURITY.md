# Security Policy

Current supported distribution: **DLM Desktop1.3.9 (r220), Windows x64**.

Canonical download: [Ertelun GitHub Release v1.3.9](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.9).

Package SHA-256: 58e0fe07dff8b2d8d3f08d1a1e71443e1bf0726324e680669f498ee77a0ab23e.

## Temporary embedded-browser hold

Chromium rates CVE-2026-113072 Critical (CISA CVSS3.1:9.6). A benign isolated observation through the1.3.8/r219 packaged admission code confirmed an unfixed prerequisite in WebView2 155.0.4283.62. No arbitrary-code-execution test was attempted.

[Microsoft's security notes](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security) say a security fix is being prepared. **DLM1.3.9/r220 blocks the embedded browser before Runtime discovery, browser profile creation or controller creation.** This is a product mitigation, not a patch to the WebView2 engine. No Runtime version or environment setting lifts the hold. Recovery requires a future reviewed DLM release after vendor fixes and validation.

Library organization, local viewing and Manual Intake remain available. Workflows requiring the embedded browser and browser cache management are temporarily unavailable. Close the old DLM and extract the complete ZIP into a new empty folder, then start the new EXE with app/ beside it. Existing libraries and settings remain usable.

The earlier minimum Runtime155.0.4283.60 addressed SVG/media issues; it is not sufficient assurance for this new issue. Keep Evergreen updates enabled. Bundled .NET10.0.12, other dependencies and the verified Downloader Host are unchanged. This does not certify that every other dependency vulnerability is resolved.

All23 test projects,70 browser hold checks,6 exact-package regression runners, final ZIP startup checks and39 native parser probes passed with isolated synthetic data. The verification asset states the scope. Product source, source archives and debug information remain local.

The ZIP is unsigned. Verify the official source and SHA-256. A checksum confirms identity, not safety. Historical releases remain for traceability.1.3.8/r219 and earlier lack this hold and are not the recommended security rollback.1.3.6/r217 remains withdrawn.

Report sensitive vulnerabilities privately through GitHub **Security → Report a vulnerability**. Do not publish credentials, tokens, purchased files or sensitive local paths in issues.

## 日本語

現在のサポート対象は **DLM Desktop1.3.9（r220）** です。CVE-2026-113072への暫定対策として、埋込みブラウザーを起動前に一時停止します。ライブラリ・ローカル閲覧・手動取り込みは利用できます。WebView2の更新だけでは解除されません。再開にはMicrosoftの修正を確認し検証した今後のDLM正式版が必要です。

旧DLMを終了し、ZIP全体を新しい空フォルダーに展開して起動してください。ソースとデバッグ情報は公開配布しません。機密性のある問題はGitHubの非公開の脆弱性報告を使用してください。
