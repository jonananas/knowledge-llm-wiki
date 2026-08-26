# Developer knowledge

A personal wiki on development and programming, built and maintained by Claude or Codex following the pattern described in [llm-wiki.md](llm-wiki.md). Read that file first for the philosophy — this file is the concrete schema for *this* wiki: directory layout, page conventions, and workflows.

## Purpose

The wiki accumulates knowledge across everything that has to do with software development, languages, tools, ai, etc. The goal is primarily a place to dump interesting url:s for later retrieval, a reference archive.

Secondly opinionated best-in-class tools, practices, algorithms etc will emerge in separate files, that will be done at a later stage on the users request once we have references supporting these opinions.


## Directory layout

```
raw/                  Immutable source documents (articles, papers, transcripts, images). Only created once by the LLM or user, never updated by LLM only by user.
  assets/             Downloaded images from clipped articles (Obsidian attachment folder).
wiki/
  entities/           Tools, languages, Companies, products, hardware platforms, people, research labs, etc.
  concepts/           Algorithms, methods, techniques, engineering patterns.
  sources/            One summary page per ingested raw source.
  comparisons/        Comparison pages generated on request (e.g. "X vs Y for Z").
opinions/             Base directory for opinions, there will be one file per category.
index.md              Catalog of every wiki page, organized by category.
log.md                Append-only chronological record of ingests, queries, lints.
AGENTS.md             This file.
llm-wiki.md           The abstract pattern this wiki instantiates.
```

Create subdirectories under `wiki/` lazily — the first page of a given kind creates the folder.

## Page conventions

- **Filenames**: kebab-case, matching the page title (`boston-dynamics-spot.md`, `model-predictive-control.md`).
- **Wiki-links**: use Obsidian-style `[[page-name]]` links (no `.md`, no path) so graph view and backlinks work.
- **Raw capture links**: a `wiki/sources/` page and its `raw/` file intentionally share the same base filename, so a bare `[[page-name]]` wiki-link can't tell them apart. When a source page cites its raw capture, use a relative markdown link instead so it's clickable in both Obsidian and VS Code: `[raw/evroc-roc.md](../../raw/evroc-roc.md)`, not backticked plain text.
- **Frontmatter** on every wiki page (not on raw sources):
  ```yaml
  ---
  type: entity | concept | source | comparison
  tags: [robotics, actuators]
  updated: 2026-08-24
  ---
  ```
- **Follow-ups**: interesting links surfaced while reading a source (a paper it cites, a competitor's repo, a spec sheet) go inline on the most relevant existing or new wiki page, under a `## Follow-ups` heading, as a checkbox list. There's no central link inbox — discoverability comes from the page itself and from `index.md`.
  ```markdown
  ## Follow-ups
  - [ ] [Paper title](url) — why it matters, one line
  ```
  When a follow-up is eventually ingested, check the box and replace it with a normal citation/link to the new source page.

## Workflows

### Ingest
1. Read the new raw source; discuss key takeaways with the user before writing anything. If user is not naming the source, do use git to find out what is new.
2. If the source has no link/URL/DOI on record (e.g. a pasted excerpt or a clipped file with no origin noted), ask the user for a link to the actual source before proceeding. Every source page needs a citation back to where it came from — don't guess or omit it.
3. Write (or update) a page in `wiki/sources/` summarizing it, with the source link in its frontmatter or opening line.
4. Create or update relevant `wiki/entities/` and `wiki/concepts/` pages — add citations back to the source page.
5. Note any interesting but tangential links as `## Follow-ups` on the most relevant page (see above).
6. Update `index.md` with the new/changed pages.
7. Append an entry to `log.md`.

Default to ingesting one source at a time, staying in the loop with the user on emphasis. Batch-ingest only if asked.

#### Sourcing from a bare link

Often there's no document to parse — just a link the user wants filed. In that case:
1. Visit the link and write a new markdown file in `raw/` that distills the main points — not a full scrape, a readable capture of what matters. Name it kebab-case after the site/subject (e.g. `raw/evroc-roc.md`). Record the source URL and fetch date at the top.
2. From here on this file is a normal raw source: the LLM never edits it again. The user may append their own notes to it later — that's the one exception to raw immutability, and it's the user's edit, not the LLM's.
3. Continue with the regular ingest flow (steps 3-8 above) using this file as the source, respecting any categorization the user already gave (e.g. "file under cloud providers, European-friendly").

### Query
1. Read `index.md` to find relevant pages; drill into them.
2. Synthesize an answer with citations to wiki pages (not raw sources directly, unless the wiki doesn't cover it yet).
3. If the answer is worth keeping — a comparison, an analysis, a new connection — offer to file it back as a page (e.g. `wiki/comparisons/`) rather than letting it disappear into chat.
4. Append an entry to `log.md`.

### Lint
Run when asked, or proactively suggest when it's been a while. Check for:
- Contradictions between pages (and whether `thesis.md` reflects them).
- Stale claims superseded by newer sources.
- Orphan pages with no inbound links.
- Concepts mentioned repeatedly but lacking their own page.
- Follow-up links that have been sitting unaddressed.

Append an entry to `log.md` summarizing findings and any fixes made.

## Tools

- Primary editors: VS Code and Obsidian (graph view, backlinks). No Obsidian-specific plugins assumed beyond that.
- PDFs in `raw/` are tracked via git-lfs (`.gitattributes`: `*.pdf`). Run `git lfs install` once per clone.
- Ingesting PDFs requires **poppler** (`brew install poppler`) — provides `pdftotext` (bulk text extraction; sufficient for text-layer PDFs like slide decks exported from Google Slides/PowerPoint) and `pdftoppm` (page-image rendering, used by the Read tool for scanned/image-heavy PDFs, max 20 pages per call). Try `pdftotext -layout` first; fall back to page-image reading only if the text layer is missing or garbled. For heavy scanned/table-dense documents, consider Docling as a future upgrade.
- No dedicated search engine (e.g. qmd) yet — `index.md` is the search mechanism at this scale. Revisit if the wiki grows past ~100 sources.
