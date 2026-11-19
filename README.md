# tiny-chess-01-v3

A chess engine in 4 KB of Python, written from scratch for the make.fun
tiny-chess-01 bounty.

## How it plays

- 0x88 board, alpha-beta negamax with iterative deepening.
- Fixed node budget (120k nodes/move) instead of a clock, so every trial
  replays deterministically.
- Transposition table, MVV-LVA capture ordering, killer moves.
- Quiescence search over captures, promotions and replies to check.
- Evaluation: material (P100 N320 B330 R500 Q900) plus piece-square
  tables and a bishop-pair bonus.

`main.py` is the whole engine (an lzma payload with a tiny unpacker, 3630
bytes). It talks to the env at `MAKEFUN_ENV_URL`: `/game` to start the next
game, `/move` to play a move in UCI.

## Files

- `main.py` — the engine
- `README.md` — this file
- `LICENSE` — MIT
