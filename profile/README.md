# Agentic Organisations Collective

Welcome — whether you are simply curious about the collective, a member, or part
of the board. This page is the entry point to everything we do: it explains how
we are organised and lists all of our repositories.

We are a collective exploring how organisations can be designed, governed, and
operated with agentic, AI-native workflows — transparent by default and
versioned end to end.

Our work is split across focused repositories, each with a clear permission
boundary, so that legal records, member data, editorial planning, and public
communication never bleed into one another.

## How we are organised

We operate as a GitHub organization made up of several focused monorepos. The
boundary between repositories is drawn by **access level first, topic second**:

- **Separation of concerns** — each repository owns a single domain and its own
  permission model.
- **Versioned and auditable** — legally relevant texts move through review and
  produce immutable, tagged releases.
- **Public by default, private where it must be** — sensitive member and board
  data stay isolated from outward-facing work.

We use four protection levels:

| Level | Who can read | Used for |
| --- | --- | --- |
| **Public** | Everyone | Statutes, public communication, released documents |
| **Member** | Members | Operational working content and internal documentation |
| **Board** | Board | Member master data, finances, formal administration |
| **Secret / Vault** | Referenced externally | Credentials and tokens — never stored in any repo |

For the full model of where content belongs and why, see the
[repository architecture charter](https://github.com/Agentic-Organisations-Collective/.github/blob/main/docs/repository-architecture.md).

## All repositories

Everyone can see this map of how we work. Repositories marked **Member** or
**Board** are private — their names and purpose are listed here for transparency,
but you need the corresponding access to open them.

### Public — readable by everyone

- **[aoc-governance](https://github.com/Agentic-Organisations-Collective/aoc-governance)**
  — Legal and constitutional documents: statutes, bylaws, resolutions, public
  minutes, and released snapshots.
- **[aoc-communications](https://github.com/Agentic-Organisations-Collective/aoc-communications)**
  — Public-facing communication: event teasers, announcements, press, website
  content, and social posts.
- **[aoc-foundations](https://github.com/Agentic-Organisations-Collective/aoc-foundations)**
  — Reusable neutral building blocks: brand kit, forms, templates, schemas, and
  taxonomies.

### Member — readable by members of the collective

- **[aoc-members](https://github.com/Agentic-Organisations-Collective/aoc-members)**
  — Member-readable operational working content: conference contributions,
  member guides, talks, notes, and templates.

### Curation — event curation and editorial planning

- **[aoc-curation](https://github.com/Agentic-Organisations-Collective/aoc-curation)**
  — Operational event curation and editorial planning: events and topics, with
  board oversight.

### Board — board-only administration

- **[aoc-board](https://github.com/Agentic-Organisations-Collective/aoc-board)**
  — Board-only administration and sensitive records: member registry, dues,
  payments, compliance, and board minutes.

## Get in touch

Interested in the collective or in agentic organisation design? Open an issue in
one of the public repositories above to start a conversation.
