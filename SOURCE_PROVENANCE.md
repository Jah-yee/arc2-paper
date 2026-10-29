# Source provenance

Prepared 2026-10-29, binds ARC-AGI-2 submission 56287444 (sha256
`cc9a5e0c…f15420`). Every hash below was computed with SHA-256 over the exact
staged bytes; `SHA256SUMS` pins the same values for the whole tree.

## Official submission

| Field | Value |
| --- | --- |
| Competition | ARC-AGI-2 (`arc-prize-2026-arc-agi-2`) |
| Submission ID | `56287444` |
| Submitted at | 2026-09-16 21:08:35 UTC |
| Terminal status | `COMPLETE` (official scoring finished; no runtime, format, or dependency failure) |
| Public score | 28.89 (exact-match pass@2, public leaderboard) |
| Private score | not published |
| `submission.json` SHA-256 | `cc9a5e0ca979c67dd79b7136c09051cb23a38543db317df32f15ee41d8f15420` |
| `submission.json` size | 23,253 bytes |
| Local copy | `receipts/submission.json` (byte-identical to the submitted file) |

`submission.json` contains 120 task entries; each entry carries exactly
`attempt_1` and `attempt_2` grids, per the competition's output schema. It is
the owner's own model output, published as the score-binding receipt (see
`DATA_BOUNDARY.md`).

## Scored public notebook

| Field | Value |
| --- | --- |
| Kaggle ref | `jahyee/arc2-public-qwen-lb31-81-anchor-v1` |
| Kernel ID | 134648497 |
| Version | 1 (the version that produced submission 56287444) |
| Notebook SHA-256 | `95c9274c8c17d69e2e91867bfc6ef93d9ce1f046eec2a85a3cc6148bf961bcbe` |
| Local copy | `notebook/arc2-public-qwen-lb31-81-anchor-v1.ipynb` (byte-identical) |
| Internet | disabled |
| Accelerator | NVIDIA L4 ×4 |
| Private dry run | identical notebook, 1,697 s (28 m 17 s), completed before the official rerun |

## Module sources (`src/`)

| File | SHA-256 |
| --- | --- |
| `src/arc_loader.py` | `2c62526daba3fdd9da317e3dcb689acca8e24018e56e4c7f2c33ed15381ed8c6` |
| `src/arc_decoder.py` | `b38b6b1bdd5f47dbd587a9809ad2ec20cdf9ce5723736a7fb7470e9b1ce61f1d` |
| `src/arc_solver.py` | `236a6c7e7e76d2c2ff3396514392d209c618f1b683b98ebe2416243d6853f112` |
| `src/starter.py` | `c519adef918335338558da6da97f6c0bbe2e80cb0f395315706da68ee4b56956` |

These files are the modules the scored notebook wrote to disk with
`%%writefile` and then executed. Compared with the notebook cell bodies,
`arc_loader.py` and `arc_decoder.py` differ by exactly one byte: a trailing
newline at end of file (extraction artifact). `arc_solver.py` and
`starter.py` are byte-identical to their cells. No behavioral difference
exists between the notebook and `src/`.

## Upstream derivation and faithfulness audit

- The code cells of the scored notebook are **byte-identical** to the public
  Kaggle notebook `qiuqiuh/arc-highscore-lb3389-replica`.
- A faithfulness audit dated 2026-10-15 compared all code cells cell-by-cell:
  8 source code cells, 8 frozen code cells, 8 identical, 0 differing
  (`BYTE_IDENTICAL_CODE_CELLS`).
- The upstream page displays 31.81 as a third-party claim that was never
  independently reproduced. Because the code is byte-identical, the 28.89 →
  31.81 delta cannot be attributed to code differences; the residual is
  attributed to platform/data drift or to unrevealed configuration of the
  source run. Re-running the identical code again was judged to have no
  falsifiable mechanism and was not done.

## Run-context facts (from the frozen receipts)

- One official submission was spent on this run; it completed with the score
  above, 0.11 percentage points below the project's pre-registered 29.0 gate,
  and was archived as a terminal anchor.
- The score gate outcome, budget accounting, and failure attribution are
  recorded in the project's internal evidence registry; this file restates
  only the public-facing facts.
