# V24 — Multilingual and RTL preview

Builds on V23. Owner-approved Take App parity and simplicity remain the product constraints.

- One EN/FR/Arabic selector in the existing top bar; no new pages. Interface language is independent of WhatsApp notification preference. Default English; chosen locale saved locally when browser storage works.
- Scoped exact-text UI dictionary for navigation, primary page headings, common actions, states, and selected instructions. Locale changes update DOM presentation, not business records. Option values remain stable; codes, label renderer, product-cell names and contact fields intentionally excluded. Arabic sets lang=ar and dir=rtl, mirrors sidebar and mobile drawer, and retains LTR QR payload entry and printed label cards. Arabic uses installed Noto Sans Arabic or system fallback; no font bundled. French and Arabic mobile headings wrap for longer text.
- This is an incremental prototype translation layer using a MutationObserver and exact strings, not production i18n. Dynamic messages, dialogs, detail screens, date/number formatting, accessibility labels and arbitrary user-generated text collisions are not comprehensively addressed. Some English remains; actual Moroccan staff terminology review and keyed translation catalogs are required before release. No translations of customer messages or product content are inferred.

## Evidence
HTML fixprio-v24-localization.html SHA-256 2bd7aaa76b5b6ff687467b360e10d2e37657047944a822c0c95021497cbf5c87.
Test fixprio-v24-localization-tests.py SHA-256 85e3a3cccc4565c84e92a5fe6b5aeeb7bda59613476c87d4faf3ec1c921d5795.
Four suites passed at 1440/390/320 (12 suite-width executions): focused localization, V23 settings, V22 reporting, V21 finance. Focused coverage: EN/FR/AR switching, 14 page headings in Arabic, right-edge desktop sidebar/mobile drawer, root width check on those pages, unchanged staff role values, product example and QR payload, LTR label card and scan field, locale write to simulated storage, French scanner sale draft retained through Arabic switch and undo with unchanged stock. Settings and POS previews inspected; adjusted localized mobile page headings and translated selected warnings. Finance regression initially interrupted by test runner timeout; standalone rerun passed all widths. No physical device testing, actual browser persistence, complete translation review, full QR regression, staff parity or production authorization acceptance.

## Remaining
Complete keyed translations and localized dynamic messages, dates/currency/accessibility, mixed-direction content and dialog coverage during implementation. Confirm vocabulary with Moroccan staff. Preserve QR identity and audit values across locales. No production code/deployment changed. Checkpoint documentation only published; full source archive upload remains unverified.

Next: V25 final visual refinement, preserving familiar layout and prioritizing defects rather than novelty.
