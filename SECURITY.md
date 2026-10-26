# Security Policy

Current supported security distribution: **DLM Desktop1.3.11 (r222), Windows x64**.

Canonical download: [GitHub Release v1.3.11](https://github.com/Ertelun/dlm-desktop/releases/tag/v1.3.11).

## HTTP Brotli mitigation / HTTP応答の緩和策

CVE-2026-111497 affects the native Brotli decoder used by the bundled .NET10.0.12. The confirmed DLM product paths were three HTTP transports for public metadata and official thumbnails. This release follows Microsoft's application mitigation: stop Brotli negotiation/automatic decoding, retaining the existing gzip/deflate behavior. A harmless exact-published-baseline witness and85patched transport checks verify the change, including unsolicited Brotli and stacked response encoding. No exploit was executed.

CNA: Critical/CVSS4.0 9.2; Microsoft .NET: High/CVSS3.1 8.1. The decision also relies on the actual affected runtime and reachable production settings, not solely a severity label. Bundled dependencies remain unchanged. Future Brotli use must use a patched decoder and be revalidated. External WebView2 security remains governed by the vendor channel and the separate browser admission policy; this mitigation does not claim to patch its native libraries.

- [Microsoft advisory and application mitigation](https://github.com/dotnet/runtime/security/advisories/GHSA-p3jp-9v83-76w9)
- [CNA record](https://cveawg.mitre.org/api/cve/CVE-2026-111497)

DLMを終了し、正式ZIP全体を新しい空フォルダーへ展開して起動してください。確認済みHTTP経路のBrotli自動展開を停止し、gzip・deflateを維持します。同梱.NET全体を修正済み版へ更新したものではありません。

## Retained embedded-browser policy

Embedded browsing continues to require **Microsoft Edge WebView2 Runtime156.0.4314.42 or later from the stable channel**. DLM rejects old, unknown and preview Runtime versions before opening external content, and rechecks the actual environment before creating a controller. Provider windows, popups and temporary controllers use the central checked environment path.

Microsoft's October CVRF identifies156.0.4314.42 as the fixed build for CVE-2026-113072,113271,113279,113280 and113303. A benign isolated observation on the Microsoft-signed Runtime confirmed the corrected CSS pseudo-element/LCP behavior with an ordinary-DOM control. This is limited validation, not an arbitrary-code-execution test or a guarantee that every vulnerability is resolved.

- [Microsoft fixed-build data](https://api.msrc.microsoft.com/cvrf/v3.0/cvrf/2026-Oct)
- [Microsoft security release notes](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-relnotes-security)
- [Official WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)

Update DLM and the official Evergreen Runtime, then restart DLM. The DLM ZIP does not bundle or install WebView2. Keep Evergreen updates enabled and restart DLM after Runtime updates. Existing provider navigation/authentication/download boundaries, disabled host objects/web messages and isolated provider profiles are retained.

The work update-check fix grants a temporary read-only scope for one selected product. It does not enable unattended synchronization, credential/cookie import or download-URL replay. Actual account sign-in, purchases and real work downloads are outside the regression-test scope.

Release validation uses fresh23-project tests, exact-package regressions, native parser probes and isolated actual-Runtime checks. See the VERIFICATION asset for the precise evidence. Bundled .NET10.0.12 and other dependencies are unchanged; this release does not certify all dependencies. CVE-2026-110922 lacks an individual row in the retrieved October CVRF; its assessment relies on later cumulative Chromium/Edge/WebView2 updates without claiming an exact individual Microsoft mapping.

The ZIP is unsigned. Verify its official source and SHA-256; a checksum confirms file identity, not safety. Product source, source archives and debug information remain local. Historical1.3.9/r220 retains its temporary all-browser hold;1.3.6/r217 remains withdrawn. Use the current supported release.

Report sensitive vulnerabilities privately through GitHub **Security → Report a vulnerability**. Do not post credentials, tokens, purchased works, exploit details or sensitive local paths in public issues.

## 日本語

現在のサポート対象は **DLM Desktop1.3.11（r222）**。Microsoftの修正情報と隔離した実Runtimeの確認に基づき、埋込みブラウザーを再開します。安定版WebView2 Runtime156.0.4314.42以降が必要です。旧版・不明な版・プレビュー版は拒否し、検出時と実Environment生成後に再確認します。

DLMと公式Runtimeを更新してDLMを再起動してください。WebView2はDLMのZIPに含まれません。作品のアップデート確認修正を含み、既存のライブラリ保護と閲覧・削除修正を保持します。検証の範囲と未確認事項はVERIFICATIONを参照してください。ソースとデバッグ情報は公開配布しません。
