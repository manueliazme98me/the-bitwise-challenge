# The Bitwise Challenge: 2048

A terminal-based implementation of the classic 2048 puzzle game, built with Bash and designed to be quick to run, easy to share, and deterministic when you want to replay or transmit a game state.

![image](banner.png)

## Overview

The Bitwise Challenge brings the addictive tile-merging gameplay of 2048 directly to your terminal. Combine matching tiles, chase higher values, and keep your board alive as long as possible.

This project is intentionally lightweight: no external dependencies, no installation steps beyond Bash, and a small deterministic state model that makes sharing game positions simple.

## Features

- Classic 2048 gameplay in a terminal UI
- Lightweight Bash implementation
- Deterministic board generation when a state seed is supplied
- Shareable game state via a single numeric value
- Randomized fresh state if no environment variable is set

## How to Play

Use the following keys to move the board:

- `w` — move up
- `a` — move left
- `s` — move down
- `d` — move right

The game ends when no valid moves remain.

## Deterministic State Sharing

The board state and future spawned cells can be reproduced from a single integer stored in the `$STATE` environment variable.

- If `$STATE` is not set, the game generates a fresh random state.
- If `$STATE` is set, the board and subsequent tile spawns are deterministic.

This makes it easy to share a game state with friends by sending the numeric value rather than a full board snapshot.

## Run the Game

```bash
bash 2048.bash
```

## Example: Replaying a Shared State

```bash
STATE=123456789 bash 2048.bash
```

Using the same `STATE` value will recreate the same board and future random outcomes.

## Requirements

- Bash
- A terminal that supports ANSI escape sequences

## License

This project is provided as-is for personal and educational use.
