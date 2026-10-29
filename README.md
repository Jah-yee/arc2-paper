# ARC-AGI-2 public anchor — exact source for submission 56287444

Prepared 2026-10-29, binds ARC-AGI-2 submission 56287444 (sha256 `cc9a5e0c…f15420`).

This repository holds the exact source code, the scored notebook, and the
machine-readable output receipt for one official ARC-AGI-2 code submission, so
that the linked Paper Track entry can be verified against a public notebook.
It is an audited anchor run, not a leaderboard-leading result.

## Question

Can a 4B-parameter open-weights language-model pipeline produce exact-match
ARC-AGI-2 solutions inside the competition's fixed compute envelope (at most
12 hours, internet disabled), and can its official score be bound verifiably to
a public notebook, a source repository, and a hash-pinned `submission.json`?

## Inputs

- ARC-AGI-2 competition files, attached through the Kaggle competition source
  `arc-prize-2026-arc-agi-2` (data © ARC Prize Foundation, Apache-2.0).
- Fine-tuned Qwen3-4B model variant, attached as the public Kaggle Model
  `sorokin/qwen3_4b_grids15_sft139/Transformers/bfloat16/1` (Apache-2.0).
- Public Kaggle kernel `sorokin/pip-install-unsloth-flash-patch` as a bootstrap
  kernel source (installs the unsloth training/patch stack used at run time).
- Runtime: 4× NVIDIA L4, internet disabled. A private dry run of the identical
  notebook completed in 1,697 s (28 m 17 s) before the official rerun.

## Method

The scored notebook writes four Python modules (`arc_loader.py`,
`arc_decoder.py`, `arc_solver.py`, `starter.py`, copied under `src/`), then
runs them across four workers:

1. Per-task LoRA fine-tuning of the model on augmented task-time examples,
   with tokenization restricted to a 12-token ARC grid vocabulary.
2. Constrained depth-first decoding (`turbo_dfs`) over that vocabulary with
   per-position NLL thresholds; normalization stays on GPU and only the 12 ARC
   token values return to the CPU.
3. Teacher-forced NLL rescoring of candidates over augmented views
   (`calc_scores`), plus an aggregation/selection step that emits exactly
   `attempt_1` and `attempt_2` for every test task.

Derivation: the code cells are byte-identical to the public Kaggle notebook
`qiuqiuh/arc-highscore-lb3389-replica` (see `SOURCE_PROVENANCE.md` and the
2026-10-15 faithfulness audit cited there).

## Evidence

| Item | Value |
| --- | --- |
| ARC-AGI-2 submission ID | `56287444` |
| Submitted at | 2026-09-16 21:08:35 UTC |
| Terminal status | `COMPLETE` |
| Public score | **28.89** (exact-match pass@2, public leaderboard) |
| Private score | not published |
| `submission.json` SHA-256 | `cc9a5e0ca979c67dd79b7136c09051cb23a38543db317df32f15ee41d8f15420` (23,253 B) |
| Scored notebook | `jahyee/arc2-public-qwen-lb31-81-anchor-v1`, kernel 134648497, version 1 |
| Notebook SHA-256 | `95c9274c8c17d69e2e91867bfc6ef93d9ce1f046eec2a85a3cc6148bf961bcbe` |

The output receipt is copied at `receipts/submission.json`. Everything is
pinned in `SHA256SUMS`.

Score context: the upstream public page for the parent notebook displays 31.81
as a third-party claim that was never independently reproduced; this
identical-code rerun scored 28.89. A code-level mechanism for the gap is
excluded (byte-identical cells), so the residual is attributed to platform or
data drift or to unrevealed configuration of the source run.

## Reproduction path

1. Open the public notebook on Kaggle
   (`https://www.kaggle.com/code/jahyee/arc2-public-qwen-lb31-81-anchor-v1`,
   version 1) and confirm the attached competition source, model source, and
   bootstrap kernel match the list above; internet stays disabled.
2. Run all cells. The notebook writes the four modules, runs the 4-worker
   pipeline within the 12-hour budget, and emits `submission.json` with
   `attempt_1`/`attempt_2` for 120 test tasks.
3. Verify artifacts locally: `src/` modules match the notebook's written files
   (the only difference is a trailing newline at end of file — see
   `SOURCE_PROVENANCE.md`), and all hashes are pinned in `SHA256SUMS`.
4. A fresh rerun may differ: the run above reflects the 2026-09 platform and
   data state (see Known limits).

## Known limits

- Single anchor run; the public score 28.89 is below the project's
  pre-registered 29.0 gate, so the run was archived as a terminal anchor
  rather than extended.
- Not a state-of-the-art result; no rank, prize, or SOTA claim is made.
- Augmentation counts, LoRA parameters, and decode thresholds were tuned for
  this specific run and are not ablated here.
- The license status of the upstream public notebook lineage is declared in
  `NOTICE.md`; inherited code is governed by the upstream notebook's terms.
- No hidden test labels, evaluator-only material, model weights, or private
  competition data are included (see `DATA_BOUNDARY.md`).

## License

Repository packaging and documentation: MIT-0 (see `LICENSE`). Inherited
code and third-party assets keep their upstream terms (see `NOTICE.md`).
