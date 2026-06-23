# Scan Log

| Date | Status | New offers | Notes |
|-----|-------|-----------|------|
| 2026-06-23 | FAILED | 0 | Network egress blocked (3rd consecutive failure) -- see below |
| 2026-06-21 | FAILED | 0 | Network egress blocked -- see below |
| 2026-06-19 | FAILED | 0 | Network egress blocked -- see below |

---

## 2026-06-23 — Scan Failure: Network Egress Blocked (3rd consecutive failure)

**All 82 companies returned HTTP 403.** The remote execution environment's network egress policy continues to deny outbound requests to job-board API hosts. 14 additional companies also require WebSearch which is unavailable in scheduled mode.

### Action required: add these 4 hosts to your egress allowlist

Go to your Claude Code on the web environment settings and add:

- `boards-api.greenhouse.io`
- `api.ashbyhq.com`
- `api.lever.co`
- `apply.workable.com`

Docs: https://code.claude.com/docs/en/claude-code-on-the-web

Until this is resolved, **no automated scanning is possible.** The scanner is working correctly — it just can't reach the job board APIs.

### Also noted

- **career-ops update available**: v1.9.0 → v1.12.0 — start an interactive session and ask Claude to `check for updates`
- Onboarding still needed: `cv.md`, `config/profile.yml` not yet created
- `portals.yml` bootstrapped from template each run (not committed — safe to ignore)

---

## 2026-06-21 — Scan Failure: Network Egress Blocked (repeat)

**All 82 companies returned HTTP 403** (same as 2026-06-19). The remote execution environment's network egress policy continues to deny outbound requests to job-board API hosts.

### Fix required: add these hosts to your egress allowlist

- `boards-api.greenhouse.io`
- `api.ashbyhq.com`
- `api.lever.co`
- `apply.workable.com`

Docs: https://code.claude.com/docs/en/claude-code-on-the-web

### Also noted

- **career-ops update available**: v1.9.0 → v1.12.0 — run `node update-system.mjs apply`
- 14 companies (OpenAI, Salesforce, Gong, Genesys, etc.) need WebSearch and require an interactive `/career-ops scan` pass
- `cv.md` and `config/profile.yml` are not yet set up — onboarding will run on next interactive session
- `portals.yml` and `modes/_profile.md` were bootstrapped from templates this run

---

## 2026-06-19 — Scan Failure: Network Egress Blocked

**All 82 companies returned HTTP 403.** The remote execution environment's network egress policy denies outbound requests to job-board API hosts.

### Fix required: add these hosts to your egress allowlist

- `boards-api.greenhouse.io`
- `api.ashbyhq.com`
- `api.lever.co`
- `apply.workable.com`

Docs: https://code.claude.com/docs/en/claude-code-on-the-web

### Also noted

- **career-ops update available**: v1.9.0 → v1.12.0 — run `node update-system.mjs apply`
- 14 companies (OpenAI, Salesforce, Gong, Genesys, etc.) need WebSearch and require an interactive `/career-ops scan` pass
- `cv.md` and `config/profile.yml` are not yet set up — onboarding will run on next interactive session
