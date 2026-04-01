# Hivebrite Admin API — Coverage & Limitations

This document lists all API resources, what this skill covers, and what's excluded with reasons.

## ✅ Covered

| Resource | Commands | Notes |
|----------|----------|-------|
| Me | `me` | Current admin info |
| Settings | `customizable-attributes`, `fields-of-study`, `industries`, `job-functions`, `currencies` | Read-only reference data |
| Network | `info`, `sub-networks list/create/update/delete`, `citizenships` | Full CRUD for sub-networks |
| Users | `list`, `read`, `create`, `update`, `delete`, `experiences`, `educations`, `notification-settings`, `postal-addresses`, `group-membership`, `find-by-field`, `notify`, `activate` | Full CRUD + nested resources |
| Experiences | `list`, `read`, `update`, `delete` | Standalone experience management |
| Educations | `list`, `read`, `update`, `delete` | Standalone education management |
| Emailings | `categories CRUD`, `campaigns CRUD`, `send` | Full emailing workflow |
| Groups | `list`, `read`, `create`, `update`, `delete`, `users list/create/delete` | Full CRUD + group membership |
| Companies | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| News | `categories`, `list`, `read`, `create`, `update`, `delete`, `duplicate` | Full CRUD + duplicate |
| Roles | `list`, `read` | Read-only |
| Business Opportunities | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Receipts | `list`, `read`, `update` | No create/delete (API limitation) |
| Pages Customizable | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Approvals | `list`, `read`, `delete`, `reject`, `approve`, `link-to-user` | Full workflow |
| Versions | `list` | List deleted items |
| Comments | `list`, `read`, `create`, `update`, `delete` | v3 API, full CRUD |
| Posts | `list`, `read`, `create`, `update`, `delete` | v3 API, full CRUD |
| Network Events | `list`, `read`, `create`, `update`, `delete`, `cancel`, `duplicate` | Full CRUD + cancel/duplicate |
| Event Tickets | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Event Bookings | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Event Attendees | `list`, `read`, `update`, `delete` | CRUD (no standalone create) |
| Event RSVPs | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Projects/Ventures | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Team Members | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Memberships Types | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Memberships Subscriptions | `list`, `read`, `create`, `cancel`, `renew`, `delete` | Full lifecycle |
| Payment Options | `list`, `create`, `update` | CRUD |
| Engagement Scoring | `rankings`, `user-rank` | Read-only |
| Payment Accounts | `list`, `read` | Read-only |
| Categories | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Current Locations | `list`, `read` | Read-only |
| Media Center Files | `list`, `read`, `create`, `update`, `delete`, `move`, `download-url` | Full CRUD + move + download |
| Media Center Folders | `list`, `read`, `create`, `update`, `delete`, `move` | Full CRUD + move |
| Media Center Root | `root` | Get root folder |
| Audit Logs | `list` | Read-only |
| Admins | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Mentoring Programs | `list`, `read`, `create`, `update`, `duplicate` | CRUD + duplicate |
| Mentee Profiles | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Mentor Profiles | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Mentoring Relationships | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Mentoring Custom Attributes | `list`, `create`, `update`, `delete` | Full CRUD |
| Order Management | `create`, `update`, `delete` | Manual transactions |
| Email Analytics | `deliveries` | v2 endpoint, read-only |
| Forums | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Notifications | `list` | Read-only |
| Sub-networks | `list` | Clusters, read-only |
| User Data Fields | `list` | Read-only |
| Donations Funds | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Donations Campaigns | `list`, `read`, `create`, `update`, `delete`, `duplicate` | Full CRUD + duplicate |
| Donations Orders | `list`, `read`, `create`, `update`, `delete` | Full CRUD |
| Donation Gifts | `list`, `read` | Read-only |

## ❌ Not Covered — With Reasons

### Deprecated Topic Endpoints (`/api/admin/v2/topics/*`)
- **Reason:** Marked as DEPRECATED in the official API docs. Use Groups endpoints instead.

### Bulk User Operations (create/update)
- **Reason:** Available as `users bulk-create` and `users bulk-update` in the CLI but marked as basic implementations. Complex bulk workflows with error handling per-row are better handled via scripts.

### Customizable Attribute Link/Unlink per domain
- **Reason:** Available via the customizable-attributes subcommands where applicable. Not all link/unlink variations are exposed as standalone commands due to complexity.

## 🔮 Candidates for Future Versions

| Resource | Priority | Why |
|----------|----------|-----|
| Webhooks | High | Event-driven integrations |
| SSO Configuration | Medium | Enterprise SSO setup automation |
| Analytics/Reports | Medium | Deeper reporting beyond email analytics |
| Batch Operations | Low | Bulk operations with detailed error handling |

---

*Based on Hivebrite Admin API v3.0.0 specification*
*Last updated: 2026-04-01*
