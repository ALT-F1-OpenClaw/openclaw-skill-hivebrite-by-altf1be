# Pre-Publish Quality Checklist

Run through before every version bump or ClawHub publish.

## Code

- [ ] `node scripts/hivebrite.mjs --help` works without env vars
- [ ] `node scripts/hivebrite.mjs --version` shows correct version
- [ ] All CRUD commands tested against real API
- [ ] `--confirm` required for all delete commands
- [ ] No secrets/tokens in stdout (test with `2>&1 | grep -i token`)
- [ ] Rate-limit retry (429) implemented with exponential backoff
- [ ] Lazy config — `--help` works without `.env`
- [ ] Error messages include status code: `ERROR (404): Not found`

## Files

- [ ] `SKILL.md` frontmatter valid (name, description, homepage, metadata)
- [ ] `SKILL.md` metadata includes `requires.env` and `optional.env`
- [ ] `README.md` has all standard sections (see CONVENTIONS.md)
- [ ] `README.md` badges: License, Node.js, Service, OpenClaw, ClawHub, Security
- [ ] `README.md` author line includes 🇧🇪 🇲🇦
- [ ] `.env.example` has Required + Optional sections with comments
- [ ] `.gitignore` includes: `node_modules/`, `.env`, `*.log`
- [ ] `LICENSE` is MIT
- [ ] `package.json` has `"type": "module"`, `"engines"`, `"bin"`
- [ ] `docs/API-COVERAGE.md` lists covered vs excluded resources
- [ ] `README.md` includes "Usage with OpenClaw" natural language examples

## Git

- [ ] Version bumped in `package.json`
- [ ] Clean `git status` (no uncommitted changes)
- [ ] Commit message follows convention: `feat:`, `fix:`, `docs:`
- [ ] Git tag matches version: `v1.0.0`
- [ ] Pushed to GitHub: `git push origin main --tags`
- [ ] GitHub topics set: `openclaw`, `hivebrite`, `openclaw-skill`

## ClawHub

- [ ] `clawhub whoami` returns your account
- [ ] Slug follows pattern: `hivebrite-by-altf1be`
- [ ] No `license:` field in SKILL.md frontmatter
- [ ] Publish tested: `clawhub publish . --slug hivebrite-by-altf1be --version X.Y.Z`

## Security Review

- [ ] No hardcoded credentials anywhere
- [ ] `.env.example` uses placeholder values only
- [ ] No real URLs/emails in example files

---

*Based on lessons learned from ALT-F1 OpenClaw skills*
