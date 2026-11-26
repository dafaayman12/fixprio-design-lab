# V22 — Reports and profitability prototype

2026-11-26. Extends V21 with one owner-only Reports page using existing source records. Follows [Take App parity](../specifications/take-app-parity.md). No separate reporting ledger or analytics platform.

## Implemented
- Today in Casablanca: completed and fulfilled POS sales created in this session, with timestamps and catalog cost snapshots on each new POS order line. Historical fixtures, online orders and repairs are excluded from this sales measure.
- Sales value, completed POS count, quantity sold, best sellers ranked by units, estimated gross margin and margin rate. Use integer centimes. Existing price/cost changes do not rewrite recorded sales or cost snapshots. Missing or nonpositive catalog cost is treated as unknown; suppress aggregate margin and rate if any sold unit lacks a cost. Display covered revenue, estimated costs and unknown units.
- Inventory snapshot: on hand, reserved, available, current positive catalog-cost estimate and uncovered units; show first eight low/out-of-stock products, with link to Inventory. Proposed low-stock threshold 1–3 available units; zero is out of stock. This is not accounting valuation or exact-unit sellability.
- Reuse FinanceDemo payment aggregation (all recorded methods; net flow is not profit). Repair costs read existing consumed allocation snapshots across the session. No repair revenue, labor cost or profitability inferred. No date-range selector, exports, forecasts or unrelated analytics.
- Owner-only simulated reporting access; existing navigation and QR workflows retained.

## Verification
HTML fixprio-v22-reports.html SHA-256 d6ff56ab82d42dee3055aac80313e7b25a0bde94b473715238fe9573bf8c194f.
Test fixprio-v22-report-tests.py SHA-256 d000ed48a56a167b388ca547b5c324019165b7fcc8d8f0c5bec0156a67d1070e.
Four Chromium suites passed at 1440/390/320 px (12 suite-width executions): focused Reports, V21 finances, V16 integrated receiving/repair/POS/WhatsApp and inventory/POS. Focused tests: initial zero sales despite fixtures; 3-unit 290 MAD POS sale, 171 MAD cost estimate, 119 MAD estimated gross margin; price/cost edits preserve snapshot; supplier payments and expenses affect flow but not margin; consumed repair cost 60 MAD; missing-cost sale suppresses margin; navigation, owner role and horizontal overflow. Desktop/mobile visual inspection prompted scoped spacing and KPI layout refinements; reran suites. Synthetic browser storage, no live data or physical hardware.

## Boundaries
Estimated catalog cost is not actual cost of goods sold; no full business profit, historical/online sales analytics, repair profitability, valuation method, refunds or durable reporting. Inventory includes aggregate legacy fixture balances. Authorization is simulated client-side. Production reporting must reconcile against authoritative sales, payments, stock and costing records, including refunds and returns, with date/filter and role policy agreed. Existing QR and receipt provenance release blockers remain open. No production code/deployment changed. Documentation only committed; complete source archive transfer still unverified.

Next: V23 general settings and staff access, using existing controls and keeping daily staff workflows familiar.
