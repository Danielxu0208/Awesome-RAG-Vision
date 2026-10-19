# Contributing a paper

Please add a paper or correction through a pull request or the paper issue template. The catalog is a targeted research guide, not a leaderboard.

## Required evidence

1. Provide the complete title, ordered authors, year, and a primary paper URL (publisher/proceedings, author manuscript, or arXiv).
2. Provide a **direct DBLP record** or **direct Google Scholar paper record**. A Scholar search URL, author profile or a repository name alone is not identity verification. The current catalog uses DBLP records; a Scholar-only proposal needs curator review before being represented in this schema.
3. Give one primary category and a role: Method, Component, Benchmark, Analysis, Survey, Shared-task report, or Background. For a method, identify the candidate collection, retrieved unit and downstream use. A retriever or token selector should not automatically be labeled a complete RAG system.
4. Check whether an earlier version is already present. Merge conference/journal and preprint versions, record renamed titles as aliases, and use the formal version when the identity is established.
5. Support a formal venue claim with a proceedings/journal record. Mark preprints as preprints. Use conference event year when publication/imprint year differs, preserving both fields.
6. Add code only when a paper, author project page or official repository establishes the connection. Set `code_source` to that evidence URL; do not guess a repository address.

## Editing the catalog

The source of truth is [`data/papers.json`](data/papers.json). Keep full author names and the direct DBLP URL. Use a DBLP record key as the stable `id`; `dblp_records` records merged versions. Keep publication evidence and verification dates. `legacy_row_indices` refer to the fixed import snapshot and must not be reused for new proposals. New papers normally use empty `manuscript_citation_keys` and `legacy_row_indices` arrays.

Save bibliographic query responses or an equivalent evidence record in a dated `metadata/` directory. The existing manuscript audits are fixed historical snapshots; a catalog addition does not change them.

```sh
python3 scripts/render_catalog.py
python3 scripts/render_catalog.py --check
```

Commit the JSON source together with the generated README, CSV and BibTeX. The checker validates identities, duplicate titles/version records, author presence, publication evidence, category values, local README links, anchors and preservation of the fixed manuscript subset. It does not certify experimental claims or check that remote links are live.

If an identity is still uncertain, use an issue or the review queue; do not invent missing metadata. Corrections to an erroneous link should explicitly record what the source actually identifies.
