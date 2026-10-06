# Bobcoin Log — AngelHack "Building with IBM Bob"

Every Bob invocation is scoped and logged here before the next one is planned.
One deep session per day beats many small ones.

## Budget

- Trial grant: 50 Bobcoins / 30 days (IBM Bob trial, metalinelabs@gmail.com account;
  verified on bob.ibm.com/admin 2026-09-29: Plan Trial, 100% unused).
- Project hard cap: **40 Bobcoins total** (kickoff task body — stricter than the
  50-coin trial grant, so 40 governs). Escalate before exceeding; never buy coins
  or upgrade tiers under the $0 rule.
- Promo `BOBANGEL26-*` (Pro+ benefit): NOT redeemed — redemption needs MFA
  enrollment + card on file at MyIBM checkout; user decision pinned separately.
  It is not counted in this budget unless the user redeems it.

## Log

| Date (CDT) | Invocation | Scope | Coins | Running total | Notes |
|---|---|---|---|---|---|
| 2026-10-06 | Bob Shell install (v2.0.5) + `bob --version` + `bob --help` | Toolchain verify | 0 | 0 | Local CLI only; no query sent. |
| 2026-10-06 | `bob run` (headless, no API key set) | Auth probe | 0 | 0 | Failed fast: "Bob API key is required." No query reached the model. |
| 2026-10-06 | `bob chat` SSO starts (x3 probes) | SSO login flow | 0 | 0 | Gateway profile check returned 401 as expected pre-login; browser sign-in delegated; no prompt sent. |
| 2026-10-06 | Smoke query (1 small query, ask mode, max 1 turn) | Phase 1 smoke test | PENDING | — | Runs only after SSO completes. Cap: 1 coin. Result + measured delta appended here. |

## Rules

- Log every invocation the day it happens, including 0-coin failures.
- If a session's cost is not directly measurable, record the admin-panel
  balance delta at next sign-in and mark the estimate as such.
- Stop conditions: unexpected coin burn (>2 coins for a scoped small task),
  any paywall/upgrade prompt, or trial expiry warning → stop and escalate.
