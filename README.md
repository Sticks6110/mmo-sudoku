# Overview
A Massively Multiplayer Sudoku game that lets you play on a Sudoku board with users from across the world. Uses a database and server framework built for MMO games to allow for thousands of concurrent users with little to no lag.
https://sticks6110.github.io/mmo-sudoku/

# Frameworks, Languages, and Tools Used
- SpacetimeDB (Rust)
- React TypeScript
- p5.js
- Tailwind
- Git

# Controls and How to Play
- Select a cell and or use arrow keys to navigate the board.
- Green highlighted cells are cells that affect the currently selected cell.
- Blue highlighted cells are cells with the same number as the selected one.
- Dark blue cells are either cells others currently have selected or a cell with a note in it.
- To play select a empty cell, type in a number, and press enter.
- Press backspace if you make a mistake typing.
- There is a short cooldown before guesses.
- The clock shows how long the current board has been alive.
- The completed counter displays the total number of completed boards on this website.
- The note taking feature allows you to write down a number without submitting it.

# Revisions
During development I came across a major issue, SpacetimeDB is mostly single-threaded because of how WASMs work. To work around this issue, I built a sidecar user that authoritatively did computationally heavy tasks to prevent slowdown on the main server. This sidecar solved the problem by generating a puzzle at startup, and after one gets sent out, this keeps the game downtime as low as possible and just relies on how fast the game can receive the puzzle from the sidecar.
