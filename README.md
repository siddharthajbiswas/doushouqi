# Dou Shou Qi

A playable browser version of Dou Shou Qi ("Jungle"), the Chinese animal chess
game, with a minimax AI opponent.

**Play it:** https://biswas.net/sid/doushouqi/

I found the game in my Mandarin class and wanted to know whether I could build
something that would beat me at it, after watching AlphaGo beat the world
champion of Go.

## How the AI works

| File | Role |
|---|---|
| `minimax_engine.js` | Minimax search with alpha-beta pruning |
| `position_evaluator.js` | Static evaluation of a board position |
| `ai_player.js` | Picks a move: drives the search, applies difficulty |
| `move_validation.js` / `piece_moves.js` | Legal move generation and the rank/river/trap rules |
| `move_validation_tests.js` | Tests for the rule edge cases |

The rest of the files handle board rendering, game setup and the character
selector. No framework and no build step: plain JavaScript, loaded directly by
`index.html`.

## Rules

Dou Shou Qi is played on a 7x9 board. Each side has eight animals ranked from
elephant down to rat; a higher rank captures a lower one, except that the rat
beats the elephant. Rivers, traps and the opposing den add the wrinkles that
make the search interesting. `rules_content.html` explains it in full, and the
site has an in-game tutorial.
