# PI-MAPPO IEEE TVT Final Reviewer Package

This is a non-destructive, allow-list snapshot of the final manuscript, executable code, frozen five-seed checkpoints, locked protocols, raw/derived CSV files, figures, and audit records. The source project remains unchanged.

## Start here

1. Read `docs/EVIDENCE_MAP.md` and `docs/REPRODUCIBILITY.md`.
2. Verify every archived byte with `python tools/verify_release.py`.
3. Compile `manuscript/paper.tex` or inspect `manuscript/paper.pdf` (12 pages).
4. Use `FILE_INVENTORY.csv` to locate each experiment and `SHA256SUMS.csv` to verify it.

## Evidential boundary

- Publication seeds: 23, 37, 49, 61, 73. Seed 11 is pilot-only and is excluded.
- Checkpoint selection: frozen safety-first lexicographic rule recorded in each manifest.
- Nominal comparison: 100 locked conditions per training seed.
- Graded stress: 72 locked conditions; the complete tail-risk experiment comprises 1,944 rollouts.
- The terminal-gap diagnostic is post-hoc and descriptive. It does not alter checkpoint selection or confirmatory endpoints.
- Files named `*.partial.csv`, resume/latest checkpoints, smoke runs, caches, logs, and superseded draft/result trees are deliberately excluded.

The package does not contain a public repository URL/DOI or author metadata. Replace the red `[TOFILL]` fields before submission.
