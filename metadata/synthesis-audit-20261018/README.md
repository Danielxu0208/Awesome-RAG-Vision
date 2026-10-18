# Configuration-level source audit — 18 October 2026

This is the evidence register for the revised ACL synthesis. It separates the existing 81 DBLP-matched identities from a completed, focused extraction of 21 analytical studies and eight supporting full texts. The other 52 references retain contextual roles. It is a purposive qualitative review, not an exhaustive database search or a prevalence estimate.

## Files and scope

| File | Contents |
| --- | --- |
| `screening-register.csv` | All 81 retained identities, primary bibliographic role, analytical/supporting/contextual tier, and selection rationale |
| `configurations.json` | 21 analytical records: source and unit, indexed/consumed representation, selection and integration, execution and learning, evaluation contract, versioned primary URL, hash, section/table locator, observation and inference limit |
| `supporting-sources.json` | Eight inspected sources supporting survey positioning, resource contracts, and compression/architecture boundaries |
| `published-contrasts.json` | Four within-paper contrasts, including exact conditions, transcribed values, locators and interpretation limits; the first three appear in the new main-text figure |
| `search-and-selection-log.json` | Actual discovery queries, retained-set selection, access failures and procedures not performed |
| `audit-summary.json` | Counts, extraction scope, process and annotation-release caveat |

The 21 studies are MuRAG, FLMR, SURf, VisRAG, M3DocRAG, VideoRAG, Goldfish, CARVE, multimodal graph RAG/KG4VD, BERAG, RULE, MMed-RAG, the SMALLCap robustness study, ImageRAG, Phidias, ReDream, Embodied-RAG, TrajRAG, mRAG, Retrieval or Representation?, and When Good OCR Is Not Enough. These include diagnostic studies as well as complete systems. They are not 21 interchangeable architectures evaluated under one benchmark.

The eight supporting full texts are Ask in Any Modality, Mei et al.'s multimodal survey, Scaling Beyond Context, ColPali, Visual-RAG, DocVQA, FrameFusion and Video-Panda. The knowledge-base taxonomy is compared at its stated scope using the official institutional abstract; its full-text download timed out and is not included in the 29-source count.

## Important numerical boundaries

- mRAG: frozen EVA-CLIP, InfoSeek 5,000 cases and a sampled 50K-article collection; Table 3 values are retrieval Recall@5.
- VideoRAG: ACL Findings 2025, Table 1, Qwen2.5-VL-3B, WikiHowQA/HowTo100M, visual-only conditions. Retrieved versus associated oracle video gives ROUGE-L 23.24/21.53 and G-Eval 1.899/1.912. The oracle is a pre-associated video, not an exhaustively annotated sufficient set. The official result page was also visually checked.
- CARVE: arXiv v2, Table 3, within-video retrieval and the main Qwen3-VL-8B ablation. Text frame+clip has higher recall but lower answer pass rate than visual frame. Representations change at both retrieval and reading.
- SURf: Table 3's original and 1,000k-ranked irrelevant-pair conditions are kept separate from Table 4's different baseline. Its trained consumer differs from Vanilla-RAG.
- Visual-RAG: the official repository reports corrected labels/QA and a 374-question release, whereas the inspected v1 manuscript describes 400 questions. Historical v1 model scores are **excluded from quantitative synthesis**. No corrected-release scores are claimed.

## What this audit establishes

Each named record has source-linked support for the stated extraction. No source-paper PDFs or restricted datasets are redistributed. Hashes identify the downloaded source bytes; public HTML or publisher-hosted files can change, so source versions and passage locators remain necessary.

Extraction was AI-assisted with passage reinspection and deterministic consistency checks. It has not undergone independent human double-coding, does not reproduce all configurations or hardware details, and contains no newly executed model experiment. The bounded counterexamples establish possible divergences, not their frequency, statistical significance, or a universal ranking of methods. Independent author review remains appropriate before submission.
