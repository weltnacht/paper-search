---
name: paper-search
description: Search, verify, and summarize academic papers into compact Zotero/arXiv-Archive-style tables. Use when the user asks to search for literature, papers, articles, preprints, DOIs, arXiv records, or recent research on a topic; to build a literature table; to summarize a field's papers; or to create a reusable Markdown literature-search artifact.
---

# Paper Search

## Usage Reference

Read `references/usage.md` when the user asks how to use this skill, wants examples, or needs a reusable prompt template. The file is bilingual with English first and Chinese second.

## Core Workflow

Use this skill for source-backed literature searches and compact paper-summary tables.

1. Infer the scope from the user request: topic, material/system, method, date range, output language, and whether the table should include only arXiv preprints or all scholarly literature.
2. Search with multiple query variants, including synonyms, phase names, method names, and abbreviations. For experimental-method topics, search both the material and the technique.
3. Prefer primary scholarly sources and metadata services: arXiv, Crossref, publisher landing pages, PubMed for biomedical topics, and official repository pages. Do not rely only on search-result snippets.
4. Verify each candidate's metadata before inclusion: title, DOI or arXiv ID, publication date, journal or venue, and whether the paper is in scope.
5. Use abstracts, publisher metadata, or paper text when available to write concise notes. Do not invent claims when only title metadata is available.
6. Deduplicate by DOI, arXiv ID, and normalized title. Prefer the formally published DOI record when the same work appears as a preprint and journal article, unless the user specifically asks for arXiv/preprints.
7. Output a compact table first, then a short synthesis of trends, gaps, and method categories.
8. If the user asks for a durable artifact, or the table is large, create a Markdown file in the current workspace with a descriptive filename.

## Search Strategy

Build query batches rather than one broad search:

- Core concept: exact topic phrase plus `"paper"`, `"review"`, `"DOI"`, or `"arXiv"`.
- Method variants: full method name plus common abbreviations, e.g. `"spectroscopic ellipsometry"`, `"generalized ellipsometry"`, `"GSE"`, `"optical Hall effect"`.
- Material variants: formula, spelled-out name, phase, alloy notation, and common Greek-letter or ASCII variants, e.g. `Ga2O3`, `"gallium oxide"`, `"beta-Ga2O3"`, `"alpha-Ga2O3"`, `"kappa-Ga2O3"`.
- Source-specific searches: publisher domains, Crossref title queries, arXiv API/search, PubMed where appropriate.
- Recent-work searches: include the current year and previous 1-3 years, and verify dates carefully.

For each candidate, decide whether it is central, adjacent, or out of scope. Include central papers in the main table; optionally mention adjacent papers in a note if useful.

## Metadata Verification

Use DOI or arXiv IDs as the strongest anchors.

- For DOI records, query Crossref when possible: `https://api.crossref.org/works/<doi>`.
- For arXiv records, verify title, first posted date, latest version, and link.
- For publisher pages, verify journal, volume/issue/article number when visible.
- If metadata sources disagree, prefer publisher data for journal details and Crossref for DOI normalization; mention uncertainty only when it affects the table.
- Exclude records whose DOI/title cannot be verified unless the user explicitly wants exploratory leads.

## Table Format

Match the user's language. Keep titles in their original language unless the user asks for translated titles.

Chinese all-literature table:

Use these columns, localized into Chinese: `#`, date, DOI/source, journal, title, keywords, note.

English all-literature table:

```markdown
| # | Date | DOI/Source | Journal | Title | Keywords | Note |
|---:|---|---|---|---|---|---|
```

Chinese arXiv-only table:

Use these columns, localized into Chinese: `#`, date, arXiv, title, keywords, note.

English arXiv-only table:

```markdown
| # | Date | arXiv | Title | Keywords | Note |
|---:|---|---|---|---|---|
```

Rules:

- Preserve record ordering from the chosen search/filter order, usually chronological unless the user asks for relevance ordering.
- Put DOI and arXiv IDs as Markdown links.
- Keep `Keywords` as concise phrases separated by semicolons; use Chinese semicolons for Chinese tables.
- Keep `Note` to one short sentence based on the abstract or verified metadata.
- Include `Journal` for journal articles; use `arXiv`, `Conference`, `Thesis`, or repository name when no journal exists.

## Synthesis

After the table, add a short synthesis when the user asks for a summary or when the table has more than five entries:

- Main research lineages or themes.
- Methodological differences and why they matter.
- Chronological trend, if visible.
- Gaps, caveats, and entries that need full-text follow-up.

Keep this synthesis compact. The table is the main deliverable.

## File Output

When creating a file, use Markdown by default and name it clearly:

```text
<topic>_literature_summary.md
<topic>_paper_search.md
```

Include at the top:

- Search date.
- Scope and inclusion criteria.
- A note that metadata was verified from DOI/arXiv/publisher sources where available.

Do not import into Zotero, create citation files, or archive PDFs unless the user explicitly asks for those follow-up actions. If Zotero archiving is requested, use the appropriate Zotero/arXiv archiving skill instead.
