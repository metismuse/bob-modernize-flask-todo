# bob-modernize-flask-todo

Modernizing a 2013-era Flask todo app with **IBM Bob** — AngelHack
"Building with IBM Bob", **Theme 2: Modernize What Matters** (Experienced
Developers). Submission deadline Oct 18, 2026, 23:59 ET; this project
submits Oct 17.

## Target app

- Upstream: [fusic-com/flask-todo](https://github.com/fusic-com/flask-todo)
  (MIT License) — vendored under `legacy/flask-todo/` at upstream commit
  `909ce22132ed081feca02e2fb255afa08b59611d` (2013-02-20). Upstream LICENSE
  is preserved in place; see `docs/phase2-baseline-plan.md` for provenance.
- Why this app: Flask==0.9 / Python 2.7.3 pins, 21 dependencies frozen in
  2012–13 (several dead upstream), no test suite, and a real demoable UI
  (Backbone.js TodoMVC SPA + Flask-RESTful API). Deep, honest modernization
  surface — exactly what Theme 2 scores.
- Backups considered: yubang/cms, tshirtman/snakenest (`docs/app-shortlist.md`).

## Repository layout

- `legacy/flask-todo/` — untouched upstream snapshot ("before" state).
  Not executed as-is: Python 2 code, reviewed statically only.
- `src/` — modernization workspace (seeded from the project scaffold;
  the modernized app lands here during Phase 3, Oct 8–10).
- `docs/` — `bobcoin-log.md` (every Bobcoin spent, 40-coin project cap),
  `phase2-baseline-plan.md` (confirmed target + Oct 7 analysis plan),
  `app-shortlist.md` (Phase 0 selection record).

## Toolchain

- IBM Bob Shell 2.0.5 on Linux (Bob is the core workflow tool; judging
  weights depth of Bob adoption at 30%). Bobcoin discipline: one deep
  session per day, every coin logged in `docs/bobcoin-log.md`.
- Free 30-day IBM Bob trial (no card) covers the Oct 6–17 build window;
  live demo targets a free no-card host (Render free tier; fallback:
  recorded demo).

## Status

- Phase 0 (Sep 28): shortlist, installer + host verification — done.
- Phase 1 (Oct 6): toolchain install + smoke test, this repo — in progress.
- Phase 2 (Oct 7): Bob full-codebase analysis + frozen modernization scope.
- Phases 3–6 (Oct 8–17): modernize, test (≥70% on changed code), document,
  deploy, pitch deck + ≤3-min demo video, submit Oct 17.

Team: Metis Builds (solo). Built with IBM Bob as the primary agent —
session evidence lands in `docs/` as the build proceeds.
