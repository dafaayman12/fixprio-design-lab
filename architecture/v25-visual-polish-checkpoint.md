# V25 — Final visual polish checkpoint

2026-11-26. Builds on V24 and [Take App parity](../specifications/take-app-parity.md). Manual light-polish pass using Damir Sokolovsky's [unslop](https://github.com/heydamir/unslop/tree/main/skills/unslop), CC BY 4.0, including signs and RTL references. Existing design direction retained: single-shop commerce/repair; familiar, exact, restrained; electronics bench and retail counter; emphasis on operational records and scanner state; permanent identification as the signature. No hero, extra decorative visual or new navigation.

## Findings and changes
- Existing screens already use restrained neutral surfaces, established accent and dense app navigation. Preserve palette, layout, section order, features and existing product content.
- Navigation section captions: sentence case, normal tracking, 12 px, consistent spacing.
- Mobile language picker: 44 px minimum height; constrain breadcrumb to remaining width.
- RTL: mirror order back and sidebar-collapse directional controls; improve selected Arabic heading/body line-height and tracking, isolate selected numeric metadata and align LTR code/contact inputs. Existing LTR QR payloads and print layout retained. This is not comprehensive RTL or translation acceptance.
- Shared focus-visible fallback and tabular numeric presentation for selected screen elements.
- Normalize negative zero at shared MAD formatting boundary; real negative values remain negative. No changes to accounting calculations or business commands.
- Screen-only CSS overrides do not alter physical label print geometry. No new pages, dependencies or provider connections.

## Evidence
V24 SHA-256 2bd7aaa76b5b6ff687467b360e10d2e37657047944a822c0c95021497cbf5c87.
V25 fixprio-v25-polished.html SHA-256 ce117901ed6bb1e1b64d87b3a857d96e628865fc6d988bb393d078e3e0028ca6.
Focused test fixprio-v25-polish-tests.py SHA-256 9bccb4e50e0dd6ac113f2620e281f5f509c25433a295e7c68fe96fbdbdd7c495.
Chromium: 15 top-level views × 3 languages × 3 widths (1440/390/320) = 135 page/language/width visits before and 135 after; no document-level horizontal overflow in either matrix. English desktop/mobile contact sheets and selected French/Arabic screenshots reviewed. Not exhaustive modal, viewport, keyboard or element-level clipping assessment.
Five suites passed at three widths (15 executions): focused polish, V24 localization, V23 settings, V22 reports, V21 finance. Focused test confirmed normal zero and real negative currency, sentence-case nav CSS, mobile 44 px picker, directional back control in Arabic and English, RTL title spacing and detail root width. Initial assertion accepted only computed 0px letter-spacing; updated to also accept equivalent normal. Earlier screenshot harness corrected nonexistent openOrders helper to showPage('orders',false).
Synthetic Map storage, local HTML and blocked external requests; no live data, physical hardware or production deployment. Full QR and ecosystem regression not rerun in this polish pass. Complete translations, accessibility, backend and real staff parity remain release gates. Full historical archive transfer remains unverified; documentation only published.

Next: V26 architecture and acceptance audit against exact V25 baseline; consolidate blockers and avoid feature creep before V27 Codex handoff.
