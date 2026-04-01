# Publishing to ClawHub

## Prerequisites

1. ClawHub account + CLI: `npm install -g clawhub`
2. Login: `clawhub login`
3. Verify: `clawhub whoami`

## Slug Convention

Format: `hivebrite-by-altf1be`

## Publish Command

```bash
clawhub publish . \
  --slug hivebrite-by-altf1be \
  --name "Hivebrite by altf1be" \
  --version 1.0.0 \
  --changelog "Initial release: full Hivebrite Admin API CLI with 36 domains"
```

## Version Updates

```bash
# 1. Bump version
npm version minor --no-git-tag-version

# 2. Commit + tag
git add -A
git commit -m "feat: description of changes"
git tag v1.1.0
git push origin main --tags

# 3. Publish update
clawhub publish . \
  --slug hivebrite-by-altf1be \
  --version 1.1.0 \
  --changelog "Added: feature X, Y. Fixed: bug Z"
```

## Important Rules

- **License:** ClawHub enforces MIT-0 for all published skills. Do NOT add `license:` to SKILL.md frontmatter.
- **SKILL.md** is required — it's what ClawHub reads for metadata.
- **`scripts/` dir** must contain the executable CLI file.

## After Publishing

- Verify on ClawHub: `https://clawhub.ai/skills/hivebrite-by-altf1be`
- Install test: `clawhub install hivebrite-by-altf1be`
- Search test: `clawhub search hivebrite`

## Files Included in Publish

ClawHub packages these files:
- `SKILL.md` (required)
- `scripts/` directory
- `package.json`
- `README.md`
- `.env.example`

Files excluded (via `.gitignore`):
- `node_modules/`
- `.env`
- `*.log`

---

*See also: [CHECKLIST.md](./CHECKLIST.md) for pre-publish quality gates*
