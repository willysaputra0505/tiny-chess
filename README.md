# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/willysaputra0505/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/willysaputra0505/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4 KB of Python. It plays the make.fun house gauntlet with a 0x88 board, negamax alpha-beta on a fixed node budget, capture/promotion/check quiescence, a transposition table, killer/history move ordering, null-move pruning, and material plus piece-square evaluation with an endgame king table.

Entry for the make.fun **tiny-chess-01** bounty ($500; deadline 25 Nov 2026, 00:00 WIB).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18080 python3 -P -s main.py
```

Requires Python 3.13, standard library only. No dependencies. `main.py` is the kit's `makefun compress` packing of the readable source in `engine.py` (same bytes, 3,772 of the 4,096 allowed).

## Strength

Practice trials (6 games each, first 6 of the house gauntlet) at a fixed 100,000-node budget, about 1.7 s per move on 1 CPU:

| Trial | Elo | W–D–L |
| --- | --- | --- |
| 0 | 1,364 | 3–1–2 |
| 1 | 1,451 | 3–2–1 |
| 2 | 1,279 | 2–2–2 |

Mean practice Elo 1,365, at the house sunfish baseline (~1,365) and above the 1,154 floor to enter the final. Beats the depth-2 and depth-3 anchors in every trial and draws the nodes-100k anchor. Fully deterministic: the same trial run twice in fresh processes produces byte-identical game records (fixed node budget, no wall clock, no unseeded randomness).

---

<sub>Entered on [make.fun](https://make.fun/?ref=ph5sj25b&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
