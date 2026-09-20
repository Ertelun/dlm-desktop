# Security Policy

## Supported release

The first Public Beta is being prepared for Windows x64.

Frozen r88 candidate package SHA-256:

`207a69e9af681b6d75d968886669e33ec7f722a864dc56c797bd364822884f4e`

## Reporting a vulnerability

Please do **not** post sensitive security vulnerabilities, credentials, tokens, private account information, purchased payloads, or sensitive local paths in a public Issue.

Private vulnerability reporting will be enabled for this repository before Public Beta publication. Once enabled, use GitHub's **Security → Report a vulnerability** flow.

Until that private route is enabled, do not publish sensitive vulnerability details in public Issues.

## Distribution authenticity

The canonical first-Beta distribution source will be this repository's GitHub Releases.

SHA-256 verifies byte identity with the published package. It does not by itself guarantee software safety.

## Unsigned Beta

The first Public Beta is unsigned. Windows may display Unknown Publisher or Microsoft Defender SmartScreen warnings.

Users should verify the canonical source and published SHA-256 and decide whether they are comfortable proceeding. Do not interpret this document as an instruction to ignore Windows security warnings.
