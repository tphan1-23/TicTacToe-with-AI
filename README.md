# TicTacToe-with-AI

A classic, terminal-based Tic-Tac-Toe game written in Python. What sets this game apart is its artificial intelligence: the computer opponent uses the **Minimax algorithm** to calculate the optimal move every single turn. This makes the computer mathematically unbeatable—the best you can hope for is a tie!

## Features

* **Unbeatable AI:** Powered by a recursive Minimax algorithm that evaluates all possible future board states.
* **Interactive CLI:** A clean, easy-to-read command-line interface.
* **Numpad Mapping:** The game board aligns perfectly with your keyboard's number pad (1-9) for intuitive input.
* **Randomized Starts:** The game flips a coin to decide whether you or the computer goes first.

## Prerequisites

All you need is Python installed on your system. This script relies only on built-in Python libraries (specifically the `random` module), so no external dependencies are required.

## How To Play

**1. Choose your letter:** When prompted, type X or O to choose your player piece.
**2. Make your move:** The board is numbered 1 through 9, corresponding to the layout of a standard keyboard number pad.

7, 8, 9 = Top row

4, 5, 6 = Middle row

1, 2, 3 = Bottom row

**3.** Type the number of the empty space where you want to place your letter and press Enter.
**4.** Try your best to beat the algorithm!
## Usage

Navigate to the directory containing your script and run it using Python:

```bash
python TictactoewAI.py
