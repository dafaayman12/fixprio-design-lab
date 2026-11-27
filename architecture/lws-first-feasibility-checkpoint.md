# LWS-first architecture feasibility — 2026-11-27

Owner clarified that previous designs, code and technologies are reusable candidates, not fixed implementation commitments. Target best sustainable value for the single shop, ideally no additional hosting subscription. Do not sacrifice security, reliability, staff acceptance or actual functionality for hosting savings.

## Direction, not final architecture
Evaluate one Laravel modular monolith with PostgreSQL and existing LWS file hosting. Compare adapting existing Redfix transactional SQL versus equivalent native Laravel transactions; retain existing Supabase/Laravel baseline as reference, and separate Laravel deployments as an alternative if consolidation is not worthwhile. No full rewrite, repo merge, schema choice or deployment approved. Use existing modules and tests where useful. One authoritative stock ledger, explicit commerce/repair ownership, protected customer portal and staff authorization. No generic RPC proxy. Do not push storefront main (automatic deployment).

## Next task
Finish V27 G0 reconciliation first. Then in disposable local synthetic environments compare a thin vertical slice: login, authorized product and receipt, concurrent last-unit sale, payment, repair stock allocation, public catalog, persistent operation recovery, queue and backup restore. Verify rollback, idempotency, actor-scoped recovery, role denial and no private data leakage. Use 1,400 synthetic products and provisional 1/3/5 concurrent staff scenarios; report measured results and limits, not inferred LWS capacity. Compare engineering effort, maintenance and 12-month cost using grounded estimates. Stop for owner review.

## Hosting gates
Nov 17 LWS probe passed Laravel CLI, PostgreSQL row locking/migrations, dump/restore, minute cron and one-shot worker separately. Secure web root, PHP 8.4, supported PostgreSQL (13 upstream EOL), cron-launched worker, actual resource limits and backup recovery remain unproven. Hosted synthetic pilot requires explicit approval. No live data or messages, remote mutations or infrastructure purchases. Provider fees and external backups are separate from the zero-additional-hosting target.

## Artifacts
Local architecture review: fixprio-lws-first-architecture-review.html. Local Codex feasibility addendum: fixprio-lws-first-feasibility-task.md, SHA-256 35f606761f76be926cd726788dcf221f129fc46b0537ba42a878a47f0d1238b5. Documentation only; no new feasibility tests executed or application changes made. G0–G7 production gates remain pending.
