# Repository Architecture

How the Agentic Organisations Collective organizes its GitHub repositories. This
is the neutral, org-wide reference for *where content belongs and why*. Each
repository's own packages and governance are documented in that repository's
`README.md`; this document only covers the cross-cutting model.

## Target State

The collective is operated as a GitHub organization with several clearly
separated monorepos. The separation is driven first by protection needs and
write permissions, not by topic alone.

Each repository is a monorepo that bundles a set of packages. The repository
defines who may read and write its content. The packages inside it define the
versioned, reusable units of work within that single access level.

The core rule is:

- different permissions mean different repositories
- packages exist for versioning, reuse, and interface boundaries
- packages do not replace repository-level access control

## Naming Principles

Repository names should be easy to read in daily use and clear about their
purpose. Visibility is controlled by repository permissions, not by overloading
the name with access labels, unless a label is genuinely needed to disambiguate
two repos with the same purpose.

The current repositories:

| Repository | Visibility | Purpose |
| --- | --- | --- |
| [`aoc-governance`](https://github.com/Agentic-Organisations-Collective/aoc-governance) | Public | Statutes, bylaws, resolutions, public minutes, releases |
| [`aoc-communications`](https://github.com/Agentic-Organisations-Collective/aoc-communications) | Public | Outward-facing communication and announcements |
| [`aoc-foundations`](https://github.com/Agentic-Organisations-Collective/aoc-foundations) | Public | Reusable neutral building blocks |
| [`aoc-members`](https://github.com/Agentic-Organisations-Collective/aoc-members) | Member | Member-readable operational working content |
| [`aoc-board`](https://github.com/Agentic-Organisations-Collective/aoc-board) | Board | Board-only administration and sensitive records |
| [`aoc-curation`](https://github.com/Agentic-Organisations-Collective/aoc-curation) | Curation/Board | Event curation and editorial planning |

See each repository's `README.md` for its packages and governance.

## Principles

1. Access boundaries are drawn at repository level, not only through folder
   names.
2. Items with the same access level can live together in one monorepo as
   separate packages.
3. Items with different access levels should be separated, even when they are
   related by topic.
4. Public formal documents should use strict versioning and append-only change
   history.
5. Personal, financial, or otherwise highly sensitive data should not live in
   public repositories.
6. Shared building blocks should live in a reusable package or in a neutral
   shared repository.

## Protection Levels

### 1. Public

Readable by everyone, writable only by a small set of maintainers. Used for
statutes, public communication, and released legal documents.

### 2. Members

Readable and editable by members, not fully public. Used for operational working
content, conference contributions, and internal documentation.

### 3. Board

Readable and writable only by the board. Used for canonical member master data,
finances, and formal administrative records.

### 4. Secret / External Vault

Highly sensitive secrets such as banking credentials or access tokens are not
stored in any repository. They are referenced from an external secret manager.

## When a Package Is Enough and When a Repo Is Needed

Use a new package inside an existing repo when the new content shares the same
access level and only needs its own versioning, interface, or reuse boundary.

Use a new repository when the content requires a different read or write
permission, a different release discipline, or isolation of sensitive data.

In short: packages separate concerns within one access level, repositories
separate access levels.

## Canonical Data vs Derived Views

Some data exists once as a canonical source and is then presented in different
places as a derived view.

- The canonical member registry lives in `aoc-board`.
- A member-facing directory in `aoc-members` is a derived view of that registry,
  limited to what members may see.
- Public website content in `aoc-communications` is a derived view of governed
  source material, never the canonical source itself.

Derived views should be generated from the canonical source, not maintained as
independent duplicates.

## Generic Placement Rules

1. Decide placement by access level first, topic second.
2. Keep canonical data in exactly one place.
3. Derive public and member-facing views instead of duplicating data.
4. Keep legally relevant public documents under strict versioning.
5. Keep personal and financial data board-only.
6. Keep secrets out of repositories and reference an external vault.
7. Put reusable, non-sensitive building blocks in `aoc-foundations`.
8. Keep operational event work in `aoc-curation`.
9. Keep formal event approvals as board minutes or resolutions in `aoc-board`.
10. Publish outward-facing output through `aoc-communications`.
11. Treat a conference as a type of event, not a separate top-level family.
12. Store change history next to the artifact it describes.
13. Prefer references over broad duplication of sensitive detail data.

## Placement Quick Reference

| Content | Repository | Package / Path | Access |
| --- | --- | --- | --- |
| Statutes, contribution rules, official resolutions | `aoc-governance` | one package/release folder per document | public read, admin write |
| Event teasers and public summaries | `aoc-communications` | `event-teasers` / `website-content` | public read, contributor write |
| Full conference contributions | `aoc-members` | one package per conference/topic | member read, contributor write |
| Internal conference documentation | `aoc-members` | `events/<event-id>` | member read, contributor write |
| Member master data (addresses, fee status) | `aoc-board` | `members`, `dues` | board read/write |
| Payment status, banking references | `aoc-board` (+ external vault) | `dues` / `payments` | board read/write, secrets external |
| Templates, schemas, wording building blocks | `aoc-foundations` | versioned utility packages | public/internal per content |
| Media from a member-only event | `aoc-members` | `events/<event-id>/media` | member read, organizer write |
| Operational event curation | `aoc-curation` | `topics`, `events/<event-id>/...` | curation read/write, board read |
