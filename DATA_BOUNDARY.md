# Data boundary declaration

This repository intentionally contains **no data, no weights, and no labels**.
Specifically, it contains none of the following:

1. **No ARC-AGI-2 task data.** No training, evaluation, or test challenge or
   solution files are included. The scored notebook reads competition files at
   run time from the Kaggle competition source `arc-prize-2026-arc-agi-2`;
   the data itself remains © ARC Prize Foundation under Apache-2.0 and must be
   obtained from the official source.
2. **No hidden test labels or evaluator-only material.** No solution or
   grading label for any hidden or evaluation split is present in any file.
3. **No model weights.** The Qwen3-4B fine-tuned variant is attached by its
   public Kaggle Model reference and is not redistributed here.
4. **No credentials or environment material.** No API keys, tokens, cookies,
   machine paths, environment dumps, logs, caches, or unrelated personal data
   are included.
5. **No private competition code.** The published notebook's code cells are
   byte-identical to a public Kaggle notebook (see `SOURCE_PROVENANCE.md`);
   nothing derived from private competition material is exposed.

## What `receipts/submission.json` is

The single JSON file under `receipts/` is the **repository owner's own
submitted predictions** for the hidden test tasks of ARC-AGI-2 (120 tasks,
each with `attempt_1` and `attempt_2` grids), published as the
machine-readable receipt that binds the official score of submission 56287444.
It is model output, not competition data, and it contains no labels.

## Third-party data terms

- ARC-AGI-2 data: © ARC Prize Foundation, Apache-2.0. Link to the official
  distribution; do not redistribute evaluator-only solution copies.
- Qwen3-4B base model and the `sorokin/qwen3_4b_grids15_sft139` fine-tuned
  variant: Apache-2.0, attached by public reference.
- All other dependencies (unsloth, transformers, peft, torch, etc.) are
  installed at run time from public package sources; their upstream licenses
  apply and none are redistributed here.
