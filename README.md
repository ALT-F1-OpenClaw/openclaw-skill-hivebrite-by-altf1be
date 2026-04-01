# openclaw-skill-hivebrite-by-altf1be

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-%3E%3D18-green.svg)](https://nodejs.org/)
[![Hivebrite](https://img.shields.io/badge/Hivebrite-API-purple.svg)](https://hivebrite.com/documentation/api/admin)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-orange.svg)](https://clawhub.ai)
[![ClawHub](https://img.shields.io/badge/ClawHub-hivebrite--by--altf1be-orange)](https://clawhub.ai/skills/hivebrite-by-altf1be)
[![Security](https://img.shields.io/badge/Security_Scan-Benign-green)](https://clawhub.ai/skills/hivebrite-by-altf1be)
[![GitHub last commit](https://img.shields.io/github/last-commit/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be)](https://github.com/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be/commits/main)
[![GitHub issues](https://img.shields.io/github/issues/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be)](https://github.com/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be/issues)
[![GitHub stars](https://img.shields.io/github/stars/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be)](https://github.com/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be/stargazers)

Full Hivebrite Admin API CLI covering users, companies, events, groups, donations, memberships, emailings, mentoring, news, projects, media center, forums, and more.

By [Abdelkrim BOUJRAF](https://www.alt-f1.be) / ALT-F1 SRL, Brussels 🇧🇪 🇲🇦

## Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [Setup](#setup)
- [Commands](#commands)
- [Security](#security)
- [API Coverage](#api-coverage)
- [ClawHub](#clawhub)
- [License](#license)
- [Author](#author)
- [Contributing](#contributing)

## Features

- **Users** — Full CRUD + experiences, educations, notification settings, postal addresses, group membership, bulk ops, find-by-field, notify, activate
- **Companies** — Full CRUD
- **Events** — Events CRUD + cancel/duplicate + tickets, bookings, attendees, RSVPs
- **Groups** — Groups CRUD, group users, topic categories
- **Donations** — Funds, campaigns, donations, gifts, customizable attributes
- **Memberships** — Types, subscriptions, payment options
- **Emailings** — Categories and campaigns CRUD + send
- **Mentoring** — Programs, mentee/mentor profiles, relationships, customizable attributes
- **News** — Categories + posts CRUD + duplicate
- **Projects** — Projects/ventures CRUD + team members
- **Media Center** — Files and folders CRUD + move + download URLs
- **Forums** — Discussion threads CRUD
- **Admins** — Full CRUD for admin accounts
- **And more** — Settings, network, roles, business opportunities, receipts, customizable pages, approvals, versions, comments, posts, engagement scoring, payment accounts, categories, current locations, audit logs, order management, email analytics, notifications, sub-networks, user data fields
- **Auth** — OAuth2 (password grant or refresh token) or static bearer token
- **Security** — `--confirm` required for deletes, no secrets to stdout, rate-limit retry with backoff

## Quick Start

```bash
# 1. Clone
git clone https://github.com/ALT-F1-OpenClaw/openclaw-skill-hivebrite-by-altf1be.git
cd openclaw-skill-hivebrite-by-altf1be

# 2. Install
npm install

# 3. Configure
export HIVEBRITE_BASE_URL=https://yourcommunity.hivebrite.com
export HIVEBRITE_ACCESS_TOKEN=your-token-here

# 4. Use
node scripts/hivebrite.mjs me
node scripts/hivebrite.mjs users list
node scripts/hivebrite.mjs companies read --id 42
node scripts/hivebrite.mjs events list
```

## Setup

### Option 1: Bearer Token (simple)

Set these environment variables (or create `.env` in the skill directory):

```bash
HIVEBRITE_BASE_URL=https://yourcommunity.hivebrite.com
HIVEBRITE_ACCESS_TOKEN=your-oauth-access-token
```

### Option 2: OAuth2 Password Grant

```bash
HIVEBRITE_BASE_URL=https://yourcommunity.hivebrite.com
HIVEBRITE_CLIENT_ID=your-client-id
HIVEBRITE_CLIENT_SECRET=your-client-secret
HIVEBRITE_ADMIN_EMAIL=admin@example.com
HIVEBRITE_ADMIN_PASSWORD=your-password
```

### Option 3: OAuth2 Refresh Token

```bash
HIVEBRITE_BASE_URL=https://yourcommunity.hivebrite.com
HIVEBRITE_CLIENT_ID=your-client-id
HIVEBRITE_CLIENT_SECRET=your-client-secret
HIVEBRITE_REFRESH_TOKEN=your-refresh-token
```

### Optional

```bash
HIVEBRITE_MAX_RESULTS=25  # Pagination default (max 100)
```

### Prerequisites

- Node.js >= 18
- Hivebrite admin account with API access
- OAuth2 credentials or bearer token

## Commands

See [SKILL.md](./SKILL.md) for full command reference with examples.

### 36 domains, 150+ commands:

| Domain | Commands |
|--------|----------|
| Me | `me` |
| Settings | `customizable-attributes`, `fields-of-study`, `industries`, `job-functions`, `currencies` |
| Network | `info`, `sub-networks list/create/update/delete`, `citizenships` |
| Users | `list`, `read`, `create`, `update`, `delete`, `experiences`, `educations`, `notification-settings`, `postal-addresses`, `group-membership`, `find-by-field`, `notify`, `activate` |
| Experiences | `list`, `read`, `update`, `delete` |
| Educations | `list`, `read`, `update`, `delete` |
| Emailings | `categories list/create/read/update/delete`, `campaigns list/create/read/update/delete/send` |
| Groups | `list`, `read`, `create`, `update`, `delete`, `users list/create/delete` |
| Companies | `list`, `read`, `create`, `update`, `delete` |
| News | `categories`, `list`, `read`, `create`, `update`, `delete`, `duplicate` |
| Roles | `list`, `read` |
| Business Opportunities | `list`, `read`, `create`, `update`, `delete` |
| Receipts | `list`, `read`, `update` |
| Pages | `list`, `read`, `create`, `update`, `delete` |
| Approvals | `list`, `read`, `delete`, `reject`, `approve`, `link-to-user` |
| Versions | `list` |
| Comments | `list`, `read`, `create`, `update`, `delete` |
| Posts | `list`, `read`, `create`, `update`, `delete` |
| Events | `list`, `read`, `create`, `update`, `delete`, `cancel`, `duplicate`, `tickets`, `bookings`, `attendees`, `rsvps` |
| Projects | `list`, `read`, `create`, `update`, `delete`, `team-members` |
| Memberships | `types list/create/read/update/delete`, `subscriptions list/create/read/cancel/renew/delete`, `payment-options` |
| Engagement | `rankings`, `user-rank` |
| Payment Accounts | `list`, `read` |
| Categories | `list`, `read`, `create`, `update`, `delete` |
| Current Locations | `list`, `read` |
| Media Center | `files list/read/create/update/delete/move/download-url`, `folders list/read/create/update/delete/move`, `root` |
| Audit Logs | `list` |
| Admins | `list`, `read`, `create`, `update`, `delete` |
| Mentoring | `mentees`, `mentors`, `programs`, `relationships`, `customizable-attributes` |
| Orders | `create`, `update`, `delete` |
| Email Analytics | `deliveries` |
| Forums | `list`, `read`, `create`, `update`, `delete` |
| Notifications | `list` |
| Sub-networks | `list` |
| User Data Fields | `list` |
| Donations | `funds`, `campaigns`, `donations`, `gifts` |

## Security

- OAuth2 authentication (password grant or refresh token) with auto-refresh and disk caching
- Static bearer token mode for simple setups
- No secrets or tokens printed to stdout
- All delete operations require explicit `--confirm` flag
- Built-in rate limiting with exponential backoff retry (3 attempts)
- Respects Hivebrite's 300 req/min rate limit
- OAuth token cache: `~/.cache/openclaw/hivebrite-token.json`
- Lazy config validation (only checked when a command runs)

## API Coverage

Full coverage of the Hivebrite Admin API v2/v3 — all 36 resource domains implemented.

See the [Hivebrite Admin API docs](https://hivebrite.com/documentation/api/admin) for the official reference.

## ClawHub

Published as: `hivebrite-by-altf1be`

```bash
clawhub install hivebrite-by-altf1be
```

## License

MIT

## Author

Abdelkrim BOUJRAF — [ALT-F1 SRL](https://www.alt-f1.be), Brussels 🇧🇪 🇲🇦
- GitHub: [@abdelkrim](https://github.com/abdelkrim)
- X: [@altf1be](https://x.com/altf1be)

## Contributing

Contributions welcome! Please open an issue or PR.
