# V21 — Finances and daily closing prototype

2026-11-26. Builds on frozen V20.6 QR prototype. Follows [Take App parity](../specifications/take-app-parity.md). One finance page and existing Overview daily-closing shortcut; existing navigation retained. Proposed owner-only finance role for review.

- Read existing order payment histories and supplier payment histories; newly recorded POS and order payments now carry ISO timestamps. Do not count historical fixtures as today's receipts. Use Casablanca calendar date and integer MAD centimes for finance aggregation. POS cash includes net sale amount, not tendered cash before change.
- Separate recorded cash flow, supplier/customer outstanding balances and cash-register reconciliation. Confirmed/completed order balances include fictional historical data; unreceived purchase commitments and repair charges excluded. Net recorded flow is not profit.
- Owner can set a single opening cash amount and record externally completed expenses (reason, method and amount). Cash, card and bank transfer kept distinct. No payment initiation. Do not duplicate supplier payments as expenses.
- Daily closing saves a single session snapshot of expected vs counted cash; difference needs reason. Reject stale review and duplicate closing. Later POS or purchase payments remain possible and visibly invalidate the snapshot's completeness without rewriting it. Expense recording disabled after closing; no reopen/correction workflow. Not a full day lock or full accounting ledger.
- Existing UI and stock operations retained. No new production changes.

## Verification
HTML fixprio-v21-finances.html SHA-256 a1e6e486b8f47865a5ba05a8b40520f6ec03867384caabae9b5bdd555b44820f.
Test fixprio-v21-finance-tests.py SHA-256 448989e2224afd19ed1f302919e1f4ee2cc6fd736da2ccd38de2937184b61f3f.
Three suites passed at 1440/390/320px (9 executions): focused finance workflow, V16 integrated receiving/repair/POS/WhatsApp, inventory and POS regression. Focused checks: zero initial cash flow despite historical fixture balances, opening float, POS cash/change, partial purchase receipt and bank payment, supplier debt, cash expense, expected cash, stale/duplicate closing, discrepancy reason, late payment warning, actual order card payment and reduced customer debt, role restriction. Desktop and mobile screenshots inspected and scoped layout improved, tests rerun. Synthetic storage and browser tests only, not full QR suite or physical acceptance.

## Boundaries
Session-only; no actual accounting, tax/invoices, refunds, expense corrections, reconciliation across devices, bank statement verification, cash transfers, repair payments, or production staff security. Existing demo order-payment role enforcement is not hardened by this milestone. Closing only covers payments recorded in this session on the local business date; owner must provide opening cash. No durable ledger, idempotent payment recovery, or official daily closing. Production receipt provenance issue and QR acceptance remain open. Checkpoint documentation only published; complete source archive transfer not verified.

Next: V22 reports and profitability; distinguish reliable metrics from unavailable cost/repair/payment data. Avoid introducing redundant finance systems.
