# Security — Public Beta

## Distribution authenticity

Canonical first-Beta distribution is the official `Ertelun/dlm-desktop` GitHub Release.

Expected Windows package SHA-256:

`207a69e9af681b6d75d968886669e33ec7f722a864dc56c797bd364822884f4e`

SHA-256 verifies byte identity with the published package. It is not, by itself, a guarantee that software is safe.

## Unsigned Beta

This first Public Beta is unsigned. Windows may display Unknown Publisher or Microsoft Defender SmartScreen warnings.

Do not describe SmartScreen as a false positive and do not instruct users to ignore a warning. Users should verify the canonical source and published hash and decide whether they are comfortable proceeding.

## Provider security boundary

- Login occurs on the provider/browser page and is user-operated.
- DLM does not use provider passwords, browser cookies, Authorization headers, session tokens, or private signed download URLs as a separate downloader credential path.
- The official Download action is user-operated.
- Completed browser archives are treated as untrusted input before validation/promotion.
- Library registration occurs only after validation/promotion.
- DLD-managed Landing source cleanup occurs only after confirmed successful promotion.
- Failed/cancelled/rejected transfers do not promote content.

## Vulnerability reports

Private Security report route:

`{PRIVATE_SECURITY_REPORT_URL}`

Do not post passwords, cookies, tokens, provider account details, purchased payloads, private local paths, or sensitive logs in public Issues.
