# Wizards of Worderly Place - README

## Overview
**Wizards of Worderly Place** is a terminal-based word puzzle game where players guess words formed from a given set of letters. The game features a dynamically generated crossword puzzle grid centered around a 6-letter word, with additional words intersecting it. Players earn points by revealing hidden words while managing limited lives.

---

## Features
### Core Gameplay
- **Dynamic Puzzle Generation**: A 15x25 grid is generated with a 6-letter word placed diagonally in the center, surrounded by 20+ intersecting words.
- **Word Guessing**: Players guess words using shuffled letters from the base word.
- **Scoring**: Earn 1 point per revealed letter. Bonus points for remaining lives upon completion.
- **Lives System**: 5 lives are deducted for invalid guesses.

### Bonus Features
- **Main Menu**: Start game, view leaderboard, reset leaderboard, or exit.
- **Leaderboard**: Tracks top scores persistently across sessions.
- **Colored Terminal UI**: Enhanced visuals using `termcolor`.
- **Input Validation**: Handles invalid guesses gracefully.

---

## Installation
### Prerequisites
- Python 3.x
- `termcolor` library (install via `pip` if not present).

### Steps
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the game:
   ```bash
   python3 worderly.py
   ```
   *Optional*: Specify a custom word list file:
   ```bash
   python3 worderly.py custom_lexicon.txt
   ```

---

## How to Play
1. **Start the Game**: Select "Start Game" from the main menu.
2. **Game Screen**:
   - **Grid**: Hidden words are represented by `#` or `.`. Correct guesses reveal letters.
   - **Letters**: Shuffled letters from the base word are displayed.
   - **Input**: Enter a valid word guess or `q` to quit to the menu.
3. **Rules**:
   - Valid words must be 3-5 letters long and formed from the given letters.
   - Guessing an invalid word costs a life.
   - The game ends when all words are found or lives are exhausted.
4. **Leaderboard**: High scores are saved and displayed in the menu.

---

## Code Structure
### Key Files
- `worderly.py`: Main game logic, UI, and leaderboard handling.
- `improved_tests.py`: Unit tests for core functions (run with `pytest`).

### Functions
- **Grid Generation**: `generate_puzzle()`, `place_baseword()`.
- **Word Validation**: `is_valid_guess()`, `words_corncob()`.
- **Leaderboard**: `load_leaderboard()`, `save_to_leaderboard()`.

---

## Testing
Run unit tests to verify functionality:
```bash
pytest improved_tests.py
```
**Test Coverage**:
- File handling (e.g., loading lexicons).
- Grid manipulation (word placement, overlaps).
- Game logic (scoring, guess validation).
- Leaderboard operations (saving/loading scores).

---

## Bonus Features Implementation
- **Leaderboard**: Scores are stored in `scores.txt` and sorted by value.
- **UI Enhancements**: Colored text highlights game state (e.g., red for low lives).
- **Input Flexibility**: Commands like `q` to quit or `r` to retry.

---

## Example Gameplay
1. **Start**:
   ```
   Letters: R T A S E E
   Lives: 5 | Points: 0
   Enter guess: tease
   ```
2. **Correct Guess**:
   - Letters in "tease" are revealed.
   - Points increase by 5 (1 per letter).
3. **Game Over**:
   - Final score and leaderboard prompt displayed.

---

## Notes
- The default lexicon file (`corncob-lowercase.txt`) must be in the same directory.
- For debugging, set `max_attempts` in `generate_puzzle()` to a higher value.

Enjoy the magic of words! ✨
