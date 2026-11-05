# Wayrin plugin — listing checklist (prepare only, NOT submitted)

Updated 2026-11-05 (UTC+8). Repo: https://github.com/Wayrin/wayrin-plugin (public). MCP: https://wayrin.com/mcp (OAuth, DCR + CIMD).
Legend: ✅ 已就绪 / Ready · 🧑 待 TIm 本人做 / TIm must do · ⚠️ 需要 TIm 决定 / Decision needed

## A. OpenAI (ChatGPT / Codex plugin directory)
Sources: [Submission](https://developers.openai.com/plugins/deploy/submission) · [Build plugins](https://developers.openai.com/codex/plugins/build) · [Plugin guidelines](https://developers.openai.com/plugins/plugin-guidelines)

| # | Requirement | Status | Source |
|---|---|---|---|
| A1 | Package: root `plugin.json` (Agent Plugins) + `mcp.json` + skills; zipped for upload; no hooks | ✅ (`codex plugin add` tested from public repo) | [Build](https://developers.openai.com/codex/plugins/build) |
| A2 | Remote MCP on a stable public HTTPS endpoint, submitted via **With MCP** | ✅ https://wayrin.com/mcp | [Submission §1](https://developers.openai.com/plugins/deploy/submission) |
| A3 | OAuth: DCR via discovery (no client credentials in package) | ✅ discovery serves `registration_endpoint`; Codex reached the authorize page | [Submission – auth](https://developers.openai.com/plugins/deploy/submission#configure-authentication-for-submission) |
| A4 | Privacy policy + terms URLs public and from the same publisher | ✅ https://wayrin.com/privacy · https://wayrin.com/terms (in `plugin.json`) | [Submission §2](https://developers.openai.com/plugins/deploy/submission) |
| A5 | Tool annotations (readOnly/destructive/idempotent/openWorld) on every tool | ✅ see `listing/README.md` §1 | [Guidelines](https://developers.openai.com/plugins/plugin-guidelines) |
| A6 | 5 positive + 3 negative test cases | ✅ in `plugin.json` → `extensions.com.openai.review.test_cases` | [Submission §3](https://developers.openai.com/plugins/deploy/submission) |
| A7 | Organization + role (owner, or Apps Management Write) | 🧑 | [Submission §1](https://developers.openai.com/plugins/deploy/submission) |
| A8 | Developer identity verification (individual or business) | 🧑 | [Org settings](https://platform.openai.com/settings/organization/general) |
| A9 | Domain verification for wayrin.com | 🧑 + dev | [Domain verification](https://developers.openai.com/plugins/deploy/submission#domain-verification) |
| A10 | Video walkthrough URL (`review.demo_recording_url`) | 🧑 | [Submission §3](https://developers.openai.com/plugins/deploy/submission) |
| A11 | Reviewer test account: works immediately, **no MFA, no email/SMS codes, no magic links** | ✅ review@wayrin.com fixed passcode (WAYRIN_REVIEW_PASSCODE); disable by deleting the secret | [Submission §3](https://developers.openai.com/plugins/deploy/submission) |
| A12 | Screenshots (`interface.screenshots`), optional dark icon | ✅ 5 shots in `listing/screenshots/` wired in `plugin.json` | [Build – metadata](https://developers.openai.com/codex/plugins/build) |
| A13 | Release notes, policy attestations at submit time | 🧑 | [Submission §3](https://developers.openai.com/plugins/deploy/submission) |

**TIm steps (OpenAI)**
1. Sign in at https://platform.openai.com → pick/create the organization that should own the listing (you must be Owner).
2. Settings → Organization → General → **Verify** (individual with ID, or business with company documents). Wait for approval.
3. Plugins page → **Submit new → With MCP** → upload the ZIP (dev prepares `wayrin-plugin-0.1.0.zip` on request) → choose Developer identity.
4. In **MCPs → Connect**, the portal shows a challenge token. Send it to dev; dev serves it as plain text at `https://wayrin.com/.well-known/openai-apps-challenge` (a code change + deploy; needs your OK). Then click Verify → Connect → sign in with the reviewer account and approve.
5. Record the video (A10): 3–5 min, run the 5 positive + 3 negative prompts in ChatGPT with the plugin; upload unlisted (YouTube/Drive “anyone with link”) and paste the URL.
6. Review details → enter reviewer credentials (C) → **Submit for review** → accept attestations.

## B. Anthropic (Claude plugin directory)
Sources: [Submit your plugin](https://claude.com/docs/plugins/submit) · [Pre-submission checklist](https://claude.com/docs/plugins/pre-submission-checklist) · [Publish (Claude Code docs)](https://code.claude.com/docs/en/plugins/publish) · [Publish to the directory](https://claude.com/docs/directory/publish)

| # | Requirement | Status | Source |
|---|---|---|---|
| B1 | GitHub repo with `.claude-plugin/plugin.json`; public before going live | ✅ public | [Submit](https://claude.com/docs/plugins/submit) |
| B2 | Name lowercase/hyphens, not reserved, not a brand you don't own | ✅ `wayrin` | [Checklist – manifest](https://claude.com/docs/plugins/pre-submission-checklist) |
| B3 | README ≥ 40 words; LICENSE | ✅ README (zh/en), MIT | [Checklist – README/license](https://claude.com/docs/plugins/pre-submission-checklist) |
| B4 | `.mcp.json` remote server: `type` http + https URL; no secrets | ✅ | [Checklist – MCP](https://claude.com/docs/plugins/pre-submission-checklist) |
| B5 | No hooks/scripts/launchers/binaries other than images | ✅ (2 PNG only) | [Checklist – files](https://claude.com/docs/plugins/pre-submission-checklist) |
| B6 | `claude plugin validate --strict` passes | ✅ | [Publish](https://code.claude.com/docs/en/plugins/publish) |
| B7 | README discloses everything it sends/fetches (security scan) | ✅ “What is sent where” | [Checklist – security scan](https://claude.com/docs/plugins/pre-submission-checklist) |
| B8 | Paid Claude plan (Pro/Max/Ultra, or Team/Enterprise Owner) | 🧑 | [Publish to the directory](https://claude.com/docs/directory/publish) |
| B9 | GitHub account with push access connected on claude.ai | 🧑 | [Submit](https://claude.com/docs/plugins/submit) |
| B10 | Data-handling questions (personal data, other destinations, retention, under-18) | ⚠️ 🧑 (answers drafted below) | [Submit – step 4](https://claude.com/docs/plugins/submit) |
| B11 | Optional: also submit https://wayrin.com/mcp as an **MCP connector** listing | ⚠️ | [Submit – note](https://claude.com/docs/plugins/submit) |

**TIm steps (Claude)**
1. Subscribe to Claude Pro (or higher) on the account that should own the listing (first org to submit a repo folder owns it).
2. claude.ai → Settings → connect GitHub (account `1924902988hu-del`, an owner of the `Wayrin` org) and grant the Claude GitHub app access to the `Wayrin` organization.
3. Open https://claude.ai/directory/manage → **Submit new → Plugin bundle** → Repository `Wayrin/wayrin-plugin`, path empty, branch `main` → **Validate**. Send any Blocking finding to dev.
4. Data handling (suggested answers, per /privacy): reads personal data only through the user's own OAuth sign-in; sends data only to wayrin.com; retention: until the user deletes it, 30 days after account closure, logs 30 days; not intended for under-18 → **TIm decides** (privacy policy currently says 13).
5. Submit; watch the plugin page for the security scan and review result; publish when approved.

Note: main is protected (PR + 1 approving review, admins included). Any fix the portal asks for needs a PR that someone other than the author approves — or TIm temporarily relaxes `enforce_admins`.

## C. Reviewer test account (OpenAI A11; also useful for Claude)
**Implemented (v2p58, TIm approved 2026-11-05):** review-only fixed passcode login.

- Email: `review@wayrin.com` (configure Cloudflare Email Routing → support/your inbox if you want mail to that address; do **not** change DNS without TIm approval — if routing already exists, reuse it).
- Secret: `WAYRIN_REVIEW_PASSCODE` on Worker `wayrin-m1-preview`. Feature is **off** when the secret is missing.
- Rate-limited; seeds 3 public sample works (1 featured) + 1 follow + 1 private draft; **cannot publish**.
- **Disable after review:** `wrangler secret delete WAYRIN_REVIEW_PASSCODE --name wayrin-m1-preview` (then redeploy not required — missing secret disables the route).
- Passcode is never committed; give it to OpenAI reviewers only via the submission form / a secure channel.

## D. Cursor Marketplace
Sources: [Plugins](https://cursor.com/docs/plugins) · [Plugins reference](https://cursor.com/docs/reference/plugins) · [Marketplace security](https://cursor.com/help/security-and-privacy/marketplace-security)

| # | Requirement | Status | Source |
|---|---|---|---|
| D1 | Agent Plugins format loads in Cursor (root `plugin.json` + `mcp.json`) | ✅ (not installed in Cursor on the box — no Cursor app here) | [Plugins](https://cursor.com/docs/plugins) |
| D2 | Distributed as a Git repository | ✅ public repo | [Plugins – marketplace](https://cursor.com/docs/plugins) |
| D3 | Submitted through the Cursor team; manual review | 🧑 contact Cursor (marketplace page) | [Plugins – marketplace](https://cursor.com/docs/plugins) |
| D4 | Community alternative: list on cursor.directory | ⚠️ optional | [cursor.directory](https://cursor.directory) |

**TIm steps (Cursor):** 1) Install the plugin locally in Cursor from the repo and confirm the OAuth sign-in opens. 2) Submit/contact via https://cursor.com/marketplace (publish link) with repo URL, privacy/terms URLs and the description from `listing/README.md`.

## E. Assets
| Item | Status |
|---|---|
| Logo/icon 512 PNG (`assets/logo.png`, `assets/icon.png`) | ✅ |
| Store screenshots (3–5: search results, reading a work, private draft link, /connect) | ✅ drafted in listing/screenshots (TIm can swap) |
| Video walkthrough | 🧑 |
| Short/long descriptions zh+en | ✅ `plugin.json`, README |

## Summary — what TIm has to do
1. OpenAI: org owner + identity verification; start the submission; pass the domain token to dev; record the video; enter reviewer credentials; submit.
2. Claude: buy Pro (or use an org Owner), connect GitHub, validate + submit in the portal, answer data handling (decide the age question).
3. Reviewer account: ✅ C1 live; give reviewers email+passcode at submit time; delete secret when review ends.
4. Cursor: install-test in Cursor, then contact Cursor via the marketplace.
5. Approve screenshots.
