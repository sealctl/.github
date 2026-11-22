# sealctl/.github spec

This repository holds the `sealctl` organisation's public profile, the brand, and the default community health files for every repository that has none of its own. It must stay public: GitHub reads `profile/README.md` and the default files only from a public `.github` repository.

## Contents

| Path | What | Status |
| --- | --- | --- |
| `README.md` | What this repository is | Exists |
| `profile/README.md` | Organisation profile shown on github.com/sealctl | Exists |
| `brand/README.md` | Mark, wordmark, colour, type, voice | Exists |
| `brand/tokens.css` | Colour and type tokens, light and dark | Exists; source of truth |
| `brand/mark.svg`, `mark-dark.svg`, `mark-mono.svg` | The mark | Exists |
| `brand/app-icon.svg` | App icon source, 1024 px | Exists |
| `brand/avatar.png` | 512 px avatar | Exists |
| `brand/social-preview.svg`, `.png` | 1280×640 link preview | Exists |
| `brand/export.sh` | Renders the PNGs from the SVGs | To add |
| `SECURITY.md` | Vulnerability reporting | Exists; to update |
| `CONTRIBUTING.md` | How to contribute | To add |
| `CODE_OF_CONDUCT.md` | Contributor Covenant 2.1 | To add |
| `SUPPORT.md` | Where to ask what | To add |
| `.github/ISSUE_TEMPLATE/` | Bug and feature forms, contact links | To add |
| `.github/pull_request_template.md` | PR checklist | To add |

No `FUNDING.yml`. sealctl is paid for with `sealctl buy`; a GitHub Sponsors button would be a second payment channel and would read as a donation for a product that has a price.

## Profile README

- No mark: the org avatar already shows it above the README. The headline, one paragraph, an install line, the repository table, the security line. Under 30 lines.
- Same claims rules as the website: true and checkable; no counts, badges or quotes.
- Add a line on the closed part: "The relay that carries sealed requests is closed source. Its API is public in [`docs/protocol.md`](https://github.com/sealctl/sealctl/blob/main/docs/protocol.md#relay-api), and your data opens without it."
- Add the website and `security.txt` once `sealctl.com` is live.
- Update when:
  - an install channel is added or removed (the install line points at Homebrew, the `sealctl` README and `sealctl.com/docs#install`; it names no version);
  - a public repository is added, renamed or archived;
  - the headline changes on the website (they must match).
- Images are referenced by `raw.githubusercontent.com/sealctl/.github/main/...` so they render on the org page.

## Brand assets

- `brand/tokens.css` is the source of truth for colour and type. The website copies it byte for byte and its CI fails on a difference; the apps generate their colour sets from it (Swift asset catalogue, Kotlin `Color` constants) with a script in the `app` repository.
- Palette: cool neutrals (white and blue-grey surfaces, navy ink) with one sealing-wax crimson, a clearer red in dark mode. No cream, beige or coral: the warm neutrals were dropped to keep the brand distinct from other AI tools.
- Change a colour here first, in one pull request that updates `tokens.css`, the table in `brand/README.md` and the contrast figures. Check contrast (WCAG AA) in both themes before merging.
- Candidates to add when a second consumer needs them (they live in the website's `site.css` today): `--ok`, `--ok-soft`, `--wait`, `--focus`, `--shadow`, `--shadow-lg`, terminal colours. The brand README already says semantic colours stay separate from the accent; keep that.
- SVGs are hand-edited and kept small (no editor metadata). After any change, `brand/export.sh` regenerates `avatar.png` and `social-preview.png` with `rsvg-convert` (or headless Chrome for the social preview's text), and the PNGs are committed with the SVG.
- The social preview carries the website's headline and summary ("Keys for developers and their AI agents"; "API keys, SSH keys, encrypted volumes and backups, approved on your phone."); update it when they change.
- Fonts: none are bundled; the brand uses system fonts. The social preview PNG is rendered on macOS so SF Mono is used.

## Community health files

These apply to every repository in the org that has no file of its own. A repository's own file wins.

### `CONTRIBUTING.md`

- Start with an issue for anything larger than a typo, so nobody writes code that won't be merged.
- Specs come before code: changes to the protocol, key handling, the store format or the relay API start as a pull request to `docs/protocol.md`.
- Every commit is signed off (`git commit -s`, Developer Certificate of Origin).
- `sealctl` (MIT): DCO only.
- `app` (AGPL-3.0): the app is distributed through the App Store and Google Play. Outside contributions need terms that allow that: either a contributor licence agreement or an additional permission in the licence. Decided before the first outside pull request is merged; until then, `CONTRIBUTING.md` in `app` says contributions are welcome as issues and that code contributions open once this is settled.
- How to run tests in each repository: a pointer to each repository's README, not a copy.
- Security issues: never in a public issue or pull request; see `SECURITY.md`.
- Code written with AI tools is welcome; the contributor is responsible for every line and says in the pull request which parts were generated.

### `CODE_OF_CONDUCT.md`

Contributor Covenant 2.1, unchanged. Enforcement contact: `support@sealctl.com`.

### `SUPPORT.md`

| Need | Where |
| --- | --- |
| How do I…? | Docs at `sealctl.com/docs` |
| Leaving sealctl | `sealctl.com/docs/leaving` |
| Bug | Issue in the repository it concerns (`sealctl` if unsure) |
| Feature request | Issue in `sealctl` |
| Licence, invoice, refund | `support@sealctl.com` |
| Security problem | `SECURITY.md`, never an issue |

Never post your 24 words, secret values, `.sealed` files or logs with keys in an issue. sealctl never asks for them.

### Issue templates (`.github/ISSUE_TEMPLATE/`)

- `config.yml`: `blank_issues_enabled: false`; contact links to private security advisories, `support@sealctl.com` for payments, and the docs.
- `bug_report.yml` (form): what you ran; what you expected; what happened; `sealctl --version`; OS and version; phone OS and app version; agent and version if one was involved; output of `sealctl status` with names removed if you prefer. A checkbox: "This contains no secret values, words or keys."
- `feature_request.yml` (form): the problem, in a sentence; what you do today; what you'd like. A dropdown for frequent requests so they can be counted: team stores, reading keys from 1Password, Vault or Doppler, other.

### Pull request template

- What and why, in two sentences; linked issue.
- Checklist: tests added or updated; docs or `CHANGELOG.md` updated; touches crypto, key handling, relay authentication or payments (yes or no; yes needs a maintainer's line-by-line review); DCO sign-off.

### `SECURITY.md` update

Keep today's text and add:

- `security@sealctl.com` as a second channel, once email routing on `sealctl.com` works.
- Supported versions: the latest release only.
- The `security.txt` URL.
- "What happens next": acknowledgement within three working days, a fix plan within 14 days for confirmed issues, a GitHub advisory and CVE when the fix ships.

## Manual GitHub settings

Done by an org owner in the web UI. None of these can be set from this repository.

| Setting | Where | Value |
| --- | --- | --- |
| Avatar | Org settings → Profile | `brand/avatar.png` |
| Display name, URL, email, description | Org settings → Profile | `sealctl`; `https://sealctl.com`; `support@sealctl.com`; "Secrets for AI coding agents, approved on your phone" |
| Verified domain | Org settings → Verified and approved domains | `sealctl.com` (TXT record in Cloudflare DNS); shows "Verified" on the org page |
| Pinned repositories | Org profile → Customize pins | `sealctl`, `app`, `homebrew-tap`, `website` |
| Social preview | Each public repo → Settings → General → Social preview | `brand/social-preview.png` (GitHub has no org-wide setting) |
| Two-factor authentication | Org settings → Authentication security | Required for all members and outside collaborators |
| Base permission | Org settings → Member privileges | Read; repository creation by owners only |
| Private vulnerability reporting | Org settings → Code security → Global settings, and each public repo | On, including for new public repositories |
| Dependabot alerts and security updates | Same | On for all repositories |
| Secret scanning and push protection | Same | On for public repositories (free) |
| Actions permissions | Org settings → Actions → General | Allow GitHub-made actions, verified creators and an explicit list; `GITHUB_TOKEN` read-only by default; require approval for workflows from first-time contributors |
| Rulesets on `main` | Each public repo → Settings → Rules | Require a pull request and passing checks; block force pushes and deletion; org owners on the bypass list. Code owner review on crypto, key-handling, relay-auth and payment paths (`CODEOWNERS` in each repository). Private repositories on the Free plan cannot enforce rulesets, so `relay` relies on the owner's own review |
| Discussions | Each repo | Off; issues only |

Re-check this table when the org changes plan or adds a member.
