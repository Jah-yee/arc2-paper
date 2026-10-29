# NOTICE

## Scope of the MIT-0 grant

The MIT No Attribution license in `LICENSE` applies to the **repository
packaging**: the documentation files (`README.md`, `DATA_BOUNDARY.md`,
`NOTICE.md`, `SOURCE_PROVENANCE.md`), the hash manifest, and any original
additions by the repository author beyond the inherited code described below.

## Inherited code

The pipeline code in `src/` and the code cells of
`notebook/arc2-public-qwen-lb31-81-anchor-v1.ipynb` are **byte-identical to
the public Kaggle notebook `qiuqiuh/arc-highscore-lb3389-replica`** (verified
cell-by-cell in the faithfulness audit of 2026-10-15, cited in
`SOURCE_PROVENANCE.md`). That notebook is reproduced here for verification of
the official submission 56287444. The upstream notebook's own terms govern the
inherited code; the MIT-0 grant above does not relicense it. If you reuse the
inherited code, comply with the upstream notebook's terms as published on
Kaggle.

## Third-party assets (attached by reference, not redistributed)

| Asset | Reference | License | Handling |
| --- | --- | --- | --- |
| ARC-AGI-2 competition data | Kaggle competition `arc-prize-2026-arc-agi-2` | Apache-2.0 (© ARC Prize Foundation) | Attached at run time; never redistributed here; evaluator-only solution copies are not published |
| Fine-tuned Qwen3-4B variant | Kaggle Model `sorokin/qwen3_4b_grids15_sft139/Transformers/bfloat16/1` | Apache-2.0 | Attached by public model reference; weights not repackaged |
| Bootstrap kernel | Kaggle kernel `sorokin/pip-install-unsloth-flash-patch` | Public Kaggle kernel; upstream terms apply | Attached by kernel reference; no license text bundled |
| Python dependencies (unsloth, transformers, peft, datasets, torch, numpy, tqdm, etc.) | Installed from public package sources at run time | Their respective upstream licenses | Not redistributed; no wheels are shipped in this repository |

## Trademarks and attribution

No endorsement by ARC Prize, Kaggle, Qwen/Alibaba, unsloth, or any model or
dataset author is claimed. Third-party names are used solely to identify the
assets required for reproduction.
