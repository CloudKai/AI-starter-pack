# Architecture

Boundaries and invariants. Skip a tour of files the agent can see with `ls`.

## Stack

One table for the repo. Keep it in sync with `AGENTS.md`.

| Layer | Technology | Role |
| --- | --- | --- |
| Framework |  |  |
| Auth |  |  |
| Database |  |  |
| Background / agents |  |  |
| Styling |  |  |

## Folder structure

Intended shape for new files, not a dump of every path that exists.

```
/
├── AGENTS.md
├── CLAUDE.md
├── scope.md
├── context/
├── app/            → pages and route handlers
├── components/     → UI
├── lib/            → clients and shared utils
└── ...
```

## System boundaries

| Folder | Owns | Must not |
| --- | --- | --- |
| `app/` | Pages, thin route handlers | Business logic, provider SDKs |
| `components/` | Rendering | Data fetching, DB, secrets |
| `lib/` | Clients, parsing, shared utils | React |
|  | Long-running or model work | UI |

## Storage model

- **Database:** metadata, ownership, relationships
- **Blob / object store (if any):** generated artifacts; DB stores the URL
- **Realtime (if any):** presence, not billing or auth source of truth

## Auth and tenancy

- Who owns a record:
- How membership is checked before a mutation:
- Browser never holds:

## Data flow

### UI mutations

Where form saves and clicks go (server actions / route handlers).

### Background / model work

Jobs, scrapers, agents. Request handlers must not block on this.

## Invariants

Numbered laws the agent must not violate.

1. Request handlers do not run long-lived model or scrape work.
2. UI displays stored data. It does not call providers.
3. Auth and ownership are enforced at every mutation boundary.
4.
