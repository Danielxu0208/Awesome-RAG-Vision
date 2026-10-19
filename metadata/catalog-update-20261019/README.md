# Public catalog verification — 19 October 2026

The catalog contains **175 unique papers**: 108 proceedings papers, six journal papers and 61 preprints, across 12 primary categories. Every paper has a direct DBLP identity record. Three MAGMaR papers additionally use official ACL Anthology proceedings for formal publication metadata because the matching DBLP identities currently describe their preprints.

This is a targeted update of the previous homepage plus the fixed 81-reference manuscript bibliography and selected newer work. It is **not an exhaustive systematic search**, a claim that every paper has been read in full, or a claim of coverage through every publication released on the update date.

## What changed

- The old homepage had 157 linked or unlinked paper-table rows. 148 rows map to 142 canonical papers after consolidating six repeated rows. Nine author-only survey rows remain unresolved and are preserved in the review queue. The full previous homepage is archived.
- 33 further verified identities are added beyond those mapped historical rows. This includes papers already present in the fixed manuscript bibliography but missing from the homepage, as well as new targeted additions. These are not all newly published papers.
- Conference/preprint records are merged by exact title. Explicitly reviewed renamed variants include UniversalRAG ("over Multiple Corpora with Diverse…" / "over Corpora of Diverse…"), MRAMG-Bench ("A BeyondText Benchmark…" / "A Comprehensive Benchmark…"), and FrameFusion ("Visual" / "Vision Language Models"). Variant DBLP records and titles are retained in JSON.
- Formal records replace stale arXiv labels for entries including UniversalRAG, HeteroRAG, Multi-RAG, MV-RAG, DocReRank, VDocRAG, ViDoRAG, VimoRAG, MOTOR, RANa, SafeDriveRAG and RAD. All publication metadata remains traceable to DBLP or the specific proceedings page.
- **Wrong-link correction:** the legacy "Retrieval-Augmented VQA for Scientific Figures (RAVQA-VLM), Li et al." entry linked to AAAI article 34653. That primary source actually identifies **Retrieval-Augmented Visual Question Answering via Built-in Autoregressive Search Engines**, by Xinwei Long et al. (ReAuSE). The catalog records the actual linked publication, with the erroneous label retained only as an import alias and a correction note. It does not assert a separate RAVQA-VLM paper exists.
- **Scope correction:** IRDiff is *Interaction-based Retrieval-augmented Diffusion Models for Protein-specific 3D Molecule Generation*, not protein 3D generation. It is retained under related techniques, outside the core computer-vision method count. Label-Retrieval-Augmented Diffusion concerns noisy-label learning, rather than generic image synthesis.
- Complementary Retrieval-Augmented Prompting now has a DBLP record and moves from pending to verified identity. This does not alter the manuscript's earlier fixed bibliography.
- Complete, ordered author signatures replace author-only shorthand. DBLP disambiguation suffixes (such as "0001") are omitted in display names. The latest query replaces older author-signature metadata rather than appending it.

## Evidence and publication policy

The saved `.rq` files are exact public DBLP SPARQL queries; the corresponding `.json` files are successful raw responses. `author-part-*` and `final-authors` contain ordered signatures. Previously verified manuscript entries also use the preserved [15 October records](../dblp-audit-20261015/verified-records.json). `manifest.json` records response/query hashes and sizes. No Google Scholar search URL is treated as verification.

Titles, authors and formal venue/event years use the chosen DBLP record. Preprint labels use publication year. Conference event year is preferred over a later volume imprint year; both year fields remain in JSON. The following formal workshop sources supplement DBLP preprint identities:

- [MARQUIS](https://aclanthology.org/2026.magmar-main.13/)
- [TRACE](https://aclanthology.org/2026.magmar-main.14/)
- [CRAFT](https://aclanthology.org/2026.magmar-main.15/)

Code links are only included where an author repository or primary paper establishes the association. Missing code links mean uncurated, not unavailable. The checker validates structure and local links; remote URL availability is not exhaustively tested.

## Review queue

The following legacy entries cannot be uniquely established from author shorthand and a broad topic alone. They are not counted as verified papers. Their original context and links are preserved in [review-queue.json](review-queue.json); they have not been declared nonexistent.

| Legacy shorthand | Topic | Original resource |
|---|---|---|
| Hu *et al.* (2024) | LLMs / NLP | [Resource](https://github.com/2471023025/RALM_Survey) |
| Zhao *et al.* (2024) | RAG in AIGC | [Resource](https://github.com/PKU-DAIR/RAG-Survey) |
| Yu *et al.* (2024) | LLMs / NLP | [Resource](https://github.com/YHPeter/Awesome-RAG-Evaluation) |
| Zhou *et al.* (2024) | Trustworthiness AI | [Resource](https://github.com/smallporridge/TrustworthyRAG) |
| Singh *et al.* (2025) | AI Agent | [Resource](https://github.com/asinghcsu/AgenticRAG-Survey) |
| Ni *et al.* (2025) | Trustworthiness AI | [Resource](https://github.com/Arstanley/Awesome-Trustworthy-Retrieval-Augmented-Generation) |
| Zhao *et al.* (2024) | LLMs / NLP | No primary paper link provided |
| Gupta *et al.* (2024) | LLMs / NLP | No primary paper link provided |
| Procko *et al.* (2024) | Graph Learning | No primary paper link provided |

## Reproduce catalog validation

From the repository root:

```sh
python3 scripts/render_catalog.py --check
```

The source of truth is `data/papers.json`. README, CSV and BibTeX are generated together. The historical 81-reference identity audit and 21-study/eight-supporting-text analytical audit are unchanged. Catalog inclusion alone does not transfer an entry into either manuscript subset.
