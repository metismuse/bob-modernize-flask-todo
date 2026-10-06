# Flask App Shortlist — AngelHack "Building with IBM Bob"

Research completed 2026-09-28 (read-only; GitHub API + raw file reads, no clones, no installs).

Hard gates enforced for all candidates: **permissive license** (verified from the raw LICENSE file),
**no test suite** (confirmed via recursive tree, catching nested test files that root-only checks miss),
**≤~10k LOC**, **Flask 1.x-era or older stack**, **real demoable UI**.

## Candidate 1 — fusic-com/flask-todo (flagship)

- **Repo:** https://github.com/fusic-com/flask-todo
- **Stars:** 54 · **Last meaningful commit:** 2013-02-20
- **License:** MIT (verified from raw LICENSE)
- **LOC:** ~1,900 Python (`backend/` + `frontend/`)
- **Stale deps:** everything pinned to 2012–13 — `Flask==0.9`, `Werkzeug==0.8.3`,
  `Jinja2==2.6`, `SQLAlchemy==0.8.0b2`, `Flask-Script==0.5.3`, `Flask-Assets==0.8`,
  `gevent==0.13.8`, `gunicorn==0.17.2`; `runtime.txt` pins **Python 2.7.3**; Heroku-Procfile-era deploy.
- **No test suite:** confirmed (no `tests/` dir, no test files, recursive tree).
- **UI demoability:** high — TodoMVC-style Backbone.js SPA with login, Flask-RESTful API backend,
  asset pipeline (CoffeeScript/SCSS).
- **Modernization hooks:** Flask 0.9→3.x (dead Flask-Script/Flask-Assets/Flask-RESTful extensions;
  app factory + blueprints), Werkzeug 0.8.3→3.x (removed APIs), SQLAlchemy 0.8 beta→2.x declarative
  rewrite, Python 2.7→3. Broad, demo-rich surface for a Theme 2 "Modernize What Matters" Bob narrative.

## Candidate 2 — yubang/cms

- **Repo:** https://github.com/yubang/cms
- **Stars:** 11 · **Last meaningful commit:** 2015-03-22
- **License:** Apache-2.0 (verified from raw LICENSE)
- **LOC:** ~745 (two files: `index.py`, `lightWeightORM.py`)
- **Stale deps:** no `requirements.txt` at all; Python 2-isms in code (`import StringIO`,
  `session.has_key("uid")` — both removed in Py3); hand-rolled `lightWeightORM` instead of SQLAlchemy;
  hardcoded MySQL creds (`root`/`root`); `app.secret_key="root"`.
- **No test suite:** confirmed (no tests dir/files, recursive tree).
- **UI demoability:** good — 7 Jinja templates (admin panel, message edit, index), QR-code feature.
- **Modernization hooks:** Python 2→3 migration, hand-rolled ORM → SQLAlchemy, credentials/secret-key
  → env config, password/session handling review.
- **Caveat:** code comments are Chinese — Python is readable, but demo narration needs translation awareness.

## Candidate 3 — tshirtman/snakenest

- **Repo:** https://github.com/tshirtman/snakenest
- **Stars:** 4 · **Last meaningful commit:** 2014-11-14
- **License:** MIT (verified from raw `LICENSE.txt`)
- **LOC:** ~270 + 5 Jinja templates (`forum.html`, `thread.html`, `login.html`, `new_forum.html`, `new_thread.html`)
- **Stale deps:** `INSTALL` prescribes `pip install flask` (unpinned, 2014 = Flask 0.10-era) and
  **`pip install mongokit`** — an ODM abandoned ~2014, incompatible with modern pymongo;
  requires a running MongoDB server.
- **No test suite:** confirmed (no tests dir/files, recursive tree).
- **UI demoability:** decent — minimal but real forum UI; smallest of the three, fastest to read.
- **Modernization hooks:** mongokit → pymongo/SQLAlchemy (the dependency is effectively unresolvable on
  modern Python — a strong "rescue" story); `utils.py` has a literal `#XXX Must use hashing/salting`
  comment with plaintext password comparison → werkzeug security hashing; MongoDB requirement →
  SQLite option for demo portability.

## Rejected candidates

| Repo | License | Reason |
|---|---|---|
| josesaribeiro/flask-wiki | BSD-2 | nested test files exist (recursive tree caught them) |
| cfmeyers/fatbaby | MIT | `tests/` dir + Flask-Testing/nose in requirements |
| eugenkiss/Simblin (159★) | BSD | `test/` dir exists |
| proudlygeek/proudlygeek-blog | MIT | `tests/` dir; vendors flask/jinja2/werkzeug copies in-repo |
| catsky/rebang (42★) | MIT | has view/test.py; polluted with vendored `.svn`; Sina AE-specific |
| gigq/flasktodo (75★) | MIT | vendors whole `flask.py`/`jinja2`/`werkzeug` in-repo; GAE-tied |
| chriszf/flask_todolist | — | no license file (hard gate) |
| stueken/FSND-P3_Music-Catalog-Web-App | — | no license file (hard gate) |
| shekhargulati/todo-flask-login-openid-openshift-quickstart | — | empty OpenShift scaffold, no real app |

## Recommendation

Lead with **fusic-com/flask-todo** (richest UI, deepest modernization story);
keep **yubang/cms** and **tshirtman/snakenest** as backups. Final app selection happens Oct 6–7
(Phase 1/2 boundary) — quick re-verify then in case repo states changed.
