# Tests — tiny-chess-01 (passed-pawn v1, main.py 4,062/4,096 B)

## Correctness (vs python-chess)
- Perft + legal moves (startpos d1–3, Kiwipete d2–3, EP/promo/castle): OK.
- Make/unmake + random-game board check; incremental eval consistency: OK.
- Best move vs pre-shrink engine, 26 positions: 0 mismatches.

## Practice trials (official scorer, 6-game gauntlets)
- Baseline trial-0: Elo 1,279 (2W 2D 2L). Trial-1: 1,191 (2W 1D 3L).
- Baseline trial-2: Elo 1,451 (3W 2D 1L, 640 s).
- Passed-pawn v1, trial-3 (trial-2 gauntlet): Elo 1,364 (3W 1D 2L).
- Passed-pawn v1, trial-4 (trial-1 gauntlet): Elo 1,364 (3W 1D 2L, spare 254).
- v1 mean 1,364 on both gauntlets; sunfish baseline mean 1,365; floor 1,154.
- Swap rule met (1,364 vs trial-1 baseline 1,191, every game same/better); v1 in main.py since 2026-11-17.

## Timing / determinism
- Fixed 150k nodes/move, no clock; ~1.9 s avg, max ~3.2 s (limit 10 s).
- 6-game trial 640–938 s (limit 1,800 s). Fixed-seed Zobrist: deterministic.
