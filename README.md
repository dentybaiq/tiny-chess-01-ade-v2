[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dentybaiq/tiny-chess-01-ade-v2/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dentybaiq/tiny-chess-01-ade-v2/reward.svg)](https://make.fun/bounty/tiny-chess-01)

# Tiny Chess — Ade v2

Chess engine in a single `main.py` (4,045 bytes, Python 3.13 stdlib only)
for the [tiny-chess-01](https://make.fun/bounty/tiny-chess-01) bounty on
make.fun: build the strongest chess engine in 4 KB of Python.

Mailbox 0x88 board, procedural piece-square tables with tapered MG/EG
eval, alpha-beta with null-move pruning, LMR, killer + history heuristic,
transposition table, check extensions and quiescence. Fixed 100,000
nodes per move, deterministic (no clock, no unseeded randomness).

Quiescence fix (23 Nov 2026): when in check, QS searches every legal
evasion (no stand-pat) and returns mate when none exists — previously
it searched captures only and walked into mate. Practice: pooled Elo
1,697 over 3 trials (15W-1D-2L) after a from-scratch rewrite of the
source, up from 1,393 before the fix.

Engine designed by Ade Sigit Hermawan and rewritten from scratch
in-session for this submission; HTTP env driver added for the
make.fun trial harness.
