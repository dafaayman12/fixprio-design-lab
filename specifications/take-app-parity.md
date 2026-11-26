# Redfix product principle — Take App parity without complexity

Approved by the owner on 2026-11-26.

**Redfix must be at least as functional as Take App for the shop's actual workflows, at least as easy for existing staff to use, and better adapted to electronics sales and repair.**

## Scope discipline
- Preserve familiar navigation, order, catalog, inventory and checkout workflows; preserve approved visual baselines.
- Keep staff daily actions fast and understandable. Reveal owner-only costs, suppliers, finance, reports and administration only where needed and authorized.
- Add QR and WhatsApp improvements for practical value, not feature count. Keep identity, permissions, duplicate prevention, stock consistency and message delivery safeguards behind the interface.
- Prefer existing modules and the smallest reliable change. Apply engineering/design/testing skills selectively when they address a real risk.
- Prioritize product registration, permanent identifiers, bulk labels, receiving, POS and repair device identification. Defer batch/expiry and elaborate location management until justified by real shop needs.

## Release acceptance
For each workflow actually used in Take App, record observed reference behavior and evidence, Redfix behavior and evidence, and one classification: Parity, Improved, Missing, Not needed (owner-approved). Unknown or untested reference behavior remains Unknown; it cannot count as parity.
Verify realistic staff tasks with synthetic data first: create and fulfill an order, record a payment, find/edit a product, receive/count stock, complete POS checkout, find a customer, and use the actual shop's messaging and storefront flows. Add shop-specific workflows when confirmed. Compare task success, mistakes, time and interaction effort; no arbitrary numerical targets without baseline measurements.
Require no unresolved essential missing workflows, owner sign-off on exclusions, staff acceptance on actual devices, and separate production readiness checks for permissions, persistence, recovery, inventory integrity and WhatsApp. A polished prototype or passing browser test is not production parity.

## QR milestone
The V20.1 audit findings remain open. Use one straightforward staff scanning experience; do not introduce extra screens or architecture merely to support hypothetical features. Identity authority and command enforcement need explicit design agreement. No production implementation or deployment is approved by this product principle.

Related: [V20.1 architecture review](../architecture/v20.1-qr-architecture-review.md).
