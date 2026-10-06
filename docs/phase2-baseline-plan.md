# Phase 2 Baseline — Target App Confirmed (recorded 2026-10-06, Phase 1 kickoff)

## Target app: CONFIRMED — fusic-com/flask-todo (flagship from Phase 0 shortlist)

Re-verified read-only on 2026-10-06 (GitHub API + full clone, code not executed):

- Upstream: https://github.com/fusic-com/flask-todo — MIT license (LICENSE file
  present in snapshot), 54 stars, not archived.
- Snapshot commit: `909ce22132ed081feca02e2fb255afa08b59611d` (2013-02-20,
  "devops: add favicon.ico") — last meaningful upstream commit; unchanged
  since the 2026-09-28 shortlist.
- Size: 57 tracked files; 2,323 Python LOC total (largest single file is the
  vendored `utils/ext/path.py`, 1,054 lines — first-party app code is ~900
  lines across `backend/`, `config/`, `utils/`).
- Stack (all pinned 2012–13 in `requirements.txt`, 21 packages): Flask==0.9,
  Werkzeug==0.8.3, Jinja2==2.6, SQLAlchemy==0.8.0b2, Flask-SQLAlchemy==0.16,
  Flask-RESTful==0.1.5, Flask-Script==0.5.3 (dead upstream), Flask-Assets==0.8,
  gevent==0.13.8, gunicorn==0.17.2, pycrypto==2.6 (dead), boto==2.8.0, others.
- Runtime: `runtime.txt` pins Python 2.7.3; Heroku Procfile-era deploy
  (`gunicorn ... application:application`). UI: Backbone.js/CoffeeScript
  TodoMVC SPA (`frontend/todo/`), Jinja templates in `backend/templates/`.
- No test suite (confirmed in Phase 0; still true at snapshot commit).
- Backups unchanged and still valid if needed: yubang/cms (Apache-2.0),
  tshirtman/snakenest (MIT) — see `docs/app-shortlist.md`.

Baseline "before" evidence captured Phase 1 (source-level, zero Bobcoins):
this file + the pinned `legacy/flask-todo/` snapshot in the repo at the exact
commit above. Runtime "before" screenshots are deferred: the app targets
Python 2.7 and its code is untrusted third-party code — do not execute it
without a reviewed, isolated environment; a source-level before/after plus a
running "after" demo is the honest evidence pair.

## Phase 2 plan — Oct 7 (ONE deep Bob session, scoped)

1. Bob full-codebase read of `legacy/flask-todo/` in the repo workspace:
   architecture map (entry points, API surface in `backend/api/`, models,
   asset pipeline) → save to `docs/analysis/` in the repo.
2. Bob dependency audit against the 21 pinned packages: current maintained
   replacements, removed/renamed APIs (Flask-Script, Flask-RESTful,
   pycrypto), Python 2 → 3 hazards → `docs/analysis/dependency-audit.md`.
3. Bob tech-debt + modernization scope proposal; human review freezes scope:
   dependency upgrades, framework migration steps, refactor list, API
   changes, test plan (target ≥70% coverage on changed code, Phase 3).
4. Coin guardrails: single session, ask/plan mode first (no file edits in
   Phase 2), session budget cap 8 coins — stop and re-scope if the estimate
   is exceeded. Log the session in `docs/bobcoin-log.md` same day.
5. Trial check at session start: confirm Bob admin still shows Trial active
   (expires Oct 26, 2026) and record the opening Bobcoin balance so the
   session delta is measurable.

## Phase 1 toolchain state (2026-10-06)

- Bob Shell 2.0.5 installed on the VM (`bob --version`, `bob --help`
  verified; gateway `api.us-east.bob.ibm.com` reachable, pre-login 401 as
  expected). SSO browser sign-in delegated at kickoff; smoke query (≤1 coin)
  runs immediately after sign-in completes and is logged in
  `docs/bobcoin-log.md`.
- StackUp registration: @metismuse "Registered" since 2026-09-26; public
  event page re-checked 2026-10-06 (Theme 2, deadline Oct 18 23:59 ET).
  Live logged-in status re-verification delegated with the sign-in pass.
- Repo: `metismuse/bob-modernize-flask-todo` seeded locally from
  `angelhack-ibm-bob/src/` plus the `legacy/flask-todo/` snapshot above.
