# V23 — General settings and staff access prototype

Builds on V22 and the owner-approved Take App parity principle. Activates the existing Settings navigation; one page, no new account system.

- Owner demo role can change the internal shop display name (validated 1–60 characters); updates sidebar profile, records session-only name change history. Currency MAD and Casablanca date boundary remain fixed. No storefront publication or payment configuration changes.
- Reuse SettingsDemo as the single existing role preview authority (Owner, Operator, Reviewer). Settings and WhatsApp role selectors share the same state; sidebar displays active demo role. Finance and Reports navigation hidden for non-owner roles, with existing page-level checks retained.
- Display current existing capabilities and explicitly distinguish demo permissions from real authentication. All roles can switch the fictional preview; not a production role assignment or real employee account. Existing authorization gaps in other modules remain open.
- Integration status and shortcuts reuse WhatsApp settings, Label Studio, and Online Store. No real provider, hardware, storefront connection, credential management or invitations.

## Verification
HTML fixprio-v23-settings.html SHA-256 f61b060450b30c58c06c96f106d49907c721b3001ca5372cc538b8587a96f83c.
Test fixprio-v23-settings-tests.py SHA-256 8a57e3aad4f20c39fd02823c5550d4590136d11583288b64a001ceb6a11fbcb3.
Three Chromium suites at 1440/390/320 (9 passing suite-width combinations): focused settings, V22 reports, V21 finance. Focused: navigation, valid/invalid shop names, shared role switch, denied non-owner settings mutation, owner finance navigation, integration shortcuts, no horizontal overflow. Fixed WhatsApp shortcut resetting to inbox; corrected test of hidden mobile sidebar to inspect textContent. Focused suite rerun after scoped mobile spacing improvement; finance/reports suites ran before this CSS-only change. Synthetic storage and records only. No full ecosystem regression, physical hardware or production authentication tests.

## Boundaries
Real staff creation, invitations, role assignment, permission changes, read restrictions, sessions, revocation and durable configuration require server-side implementation. Do not treat hiding menu links as authorization. Proposed fixed roles remain subject to actual staff duties. No production systems changed. Documentation only published; full historical archive upload remains unverified.

Next: V24 multilingual and RTL (English, French, Arabic), preserving the approved visual baseline and testing real staff-facing workflows.
