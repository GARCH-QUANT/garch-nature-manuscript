---
name: nature-manuscript
description: >-
  Full Nature/high-impact journal manuscript preparation pipeline. Use when preparing,
  polishing, citing, illustrating, presenting, or revising academic papers for
  Nature-family journals or similar high-impact venues. Covers citation management,
  data availability, figure creation, paper-to-slides conversion, prose polishing,
  and reviewer response drafting. Triggered by: manuscript drafting, paper figures,
  citation finding, data availability statements, slide creation, academic prose
  editing, or reviewer response letters.
---

# Nature Manuscript Preparation

A complete pipeline for Nature-family journal manuscript preparation — from initial
draft through publication-ready submission.

## Pipeline Overview

| Stage | Skill | What It Does |
|---|---|---|
| **Citations** | `nature-citation` | Find Nature/CNS/Science citations; export ENW/RIS/RDF |
| **Data Availability** | `nature-data` | Data availability statements, repo selection, FAIR metadata |
| **Figures** | `nature-figure` | Python/R publication figures, SVG/PDF/TIFF export |
| **Slides** | `nature-paper2ppt` | Paper → Chinese PPTX for journal club / group meeting |
| **Prose** | `nature-polishing` | Academic English polishing, restructure, translate |
| **Review Response** | `nature-response` | Point-by-point reviewer response letter |

## Skill Details

### nature-citation
Add strict Nature/CNS citations to manuscript text. Segments text into citable units,
searches accepted Nature Portfolio + AAAS Science + Cell Press journal lists,
exports EndNote/RIS/Zotero RDF. Supports Chinese-user mode with Chinese input/output.
- **Trigger keywords**: "分段引用", "自动给出引用", "Nature系列引用", "CNS及子刊",
  "支撑文献", "补引用", "找引用", "EndNote", "RIS", "Zotero"
- **Script**: `scripts/nature_citation.py`
- **References**: `references/search-strategy.md`, `references/journal-scope.md`,
  `references/ris-endnote.md`
- **Long-article strategy**: Batch mode for >10 segments; `--batch-size 10`

### nature-data
Prepare, audit, or revise Nature-ready Data Availability statements. Repository
selection, accession numbers, restricted/sensitive data handling, DataCite-style
dataset citations, FAIR metadata checklists.
- **Trigger keywords**: "数据可用性声明", "数据获取声明", "原始数据", "数据存储库",
  "FAIR", "DataCite", "repository"
- **References**: `references/policy-principles.md`, `references/chinese-author-alignment.md`,
  `references/statement-patterns.md`, `references/repository-and-identifiers.md`,
  `references/fair-metadata-checklist.md`, `references/source-basis.md`

### nature-figure
Submission-grade Nature/high-impact journal figures. Python (matplotlib/seaborn) or R
(ggplot2/patchwork/ComplexHeatmap). SVG/PDF/TIFF export. Requires backend selection
(Python or R) as a blocking gate before any generation.
- **Trigger keywords**: "paper figure", "Nature style", "publication figure",
  "multi-panel", "journal-ready", "SVG", "PDF export"
- **Backend policy**: Python or R — ask user before generating; do not cross-render
- **References**: `references/figure-contract.md`, `references/backend-selection.md`,
  `references/r-workflow.md`, `references/r-template-index.md`, `references/qa-contract.md`,
  `references/design-theory.md`, `references/api.md`, `references/common-patterns.md`,
  `references/nature-2026-observations.md`, `references/tutorials.md`,
  `references/chart-types.md`
- **Assets**: `assets/gallery/`, `assets/chart-atlas/`

### nature-paper2ppt
Build Nature-style Chinese PPTX from a scientific paper/preprint/PDF. Identifies
paper type and argument, selects key figures, writes Chinese slide content with
speaker notes, creates the actual `.pptx` deck. Cross-platform Python tooling.
- **Trigger keywords**: "journal club", "group meeting", "paper sharing",
  "thesis seminar", "PPT", "PPTX", "slides"
- **Output**: `output/final_presentation_cn.pptx` + QA report + extracted figure assets
- **Toolchain**: PyMuPDF + Pillow + python-pptx
- **Style**: Nature-style asymmetric layouts, figure-first result slides, dark BG
  `#0D1117` for image plates

### nature-polishing
Polish, restructure, or translate academic prose into Nature-leaning English.
Paper architecture + writing-strategy + phrase-level support from Academic Phrasebank.
Covers all paper sections; Chinese-to-English translation mode available.
- **Trigger keywords**: "polish manuscript", "academic writing", "Nature style",
  "translate Chinese", "英文润色", "学术写作"
- **References**: `references/section-moves.md`, `references/phrasebank-playbook.md`,
  `references/style-guardrails.md`
- **Section logic**: Introduction → Results → Discussion → Conclusion → Methods → Abstract

### nature-response
Draft, audit, or revise point-by-point reviewer response letters for Nature-family
manuscript revisions. Converts editor/reviewer comments into an auditable response
package with manuscript change mapping.
- **Trigger keywords**: "审稿意见回复", "逐点回复", "修回信", "大修回复", "小修回复",
  "reviewer response", "rebuttal"
- **References**: `references/intake-and-routing.md`, `references/source-basis.md`,
  `references/response-structure.md`, `references/comment-taxonomy.md`,
  `references/action-mapping.md`, `references/tone-and-stance.md`,
  `references/chinese-author-alignment.md`, `references/difficult-cases.md`,
  `references/qa-checklist.md`
- **Output states**: `ready_to_submit`, `draft_with_placeholders`,
  `needs_author_input`, `blocked`
