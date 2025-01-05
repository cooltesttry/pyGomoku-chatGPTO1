# Gomoku-O1 (Five in a Row)

A **Python-based Gomoku (Five in a Row)** game with an MCTS-based AI. This Python project, ALL done by ChatGPT o1, with about 40 round conversation within 3 hours, to explore the potential of o1 model, allowing you to play against an AI with selectable difficulty levels, switch languages on the fly, and experience additional features like undo, timers, and more. It would take me about a week to build similar project. When will ai replace human?

### Download the Windows Executable

You can download the pre-built Windows executable of this program for easy setup and use. Simply click the link below to get started:

**[Download Gomoku for Windows (EXE)](https://github.com/cooltesttry/Gomoku-O1/releases/download/Gomoku/Gomoku-O1.exe)**

#### Instructions:

1. Download the `.exe` file from the link above.
2. Run the file to start the Gomoku game.
3. Enjoy playing against AI with multiple difficulty levels or test your skills against friends.

<img src="https://github.com/cooltesttry/Gomoku-O1/blob/main/screenshot.png" alt="Gomoku Example Board" width="500"/>

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Game Rules](#game-rules)
- [AI Difficulty](#ai-difficulty)
- [Multi-language Support](#multi-language-support)
- [Undo and Timers](#undo-and-timers)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Features

- **MCTS-Based AI**  
  Features a Monte Carlo Tree Search (MCTS) algorithm to determine the best move. Allows for different levels of difficulty.

- **Multiple Difficulty Levels**  
  Select from "Simple", "Medium", or "Hard" AI difficulty, each with different time limits and simulation counts.

- **Multi-language Support**  
  Built-in support for English (EN), Chinese (ZH), Spanish (ES), and French (FR). Switch languages in real-time from the UI.

- **Graphical User Interface**  
  Powered by Tkinter, providing an intuitive visual board with real-time updates.

- **Timers and Undo**  
  Each move (player or AI) is timed. You can also undo your moves (one undo action removes both the player's and AI's last moves).

- **Configurable Player Turn**  
  Choose whether to play first as Black or let the AI move first.

---

## Requirements

- **Python 3.10** 
- **Tkinter** (usually included by default in most Python distributions)

No additional third-party GUI libraries are required; the standard library `tkinter` is sufficient. However, the MCTS parallelization uses the [`multiprocessing`](https://docs.python.org/3/library/multiprocessing.html) module, which is also part of the Python standard library.

---

## Installation

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/cooltesttry/Gomoku-O1.git
   cd Gomoku-O1
   ```

2. **(Optional) Create a Virtual Environment**  
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Linux/macOS
   # or
   venv\Scripts\activate     # On Windows
   ```

3. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

---

## Usage

1. **Run the Gomoku Game**  
   ```bash
   python main.py
   ```

2. **Select Language**  
   - In the bottom-left corner of the main window, choose the language radio button (e.g., “中文”, “EN”, “ES”, “FR”).  
   - The interface text will update accordingly.

3. **Select AI Difficulty**  
   - In the bottom-right corner, click the “Difficulty” button to open a pop-up window.  
   - Choose **Simple**, **Medium**, or **Hard**.  
   - Confirm by clicking “OK”.

4. **Start the Game**  
   - Upon launching, a dialog box will ask if you want to move first (Black).  
   - Answer **Yes** to play Black first, or **No** to let the AI move first.

5. **Making a Move**  
   - Simply click on the board to place a stone on your turn.  
   - The AI will automatically take its turn afterwards.

6. **Undo a Move**  
   - Click the “Undo” button to reverse both your and the AI’s last moves.  
   - If no moves are available or the game has ended, you will see a message accordingly.

7. **Restart the Game**  
   - Use the “Restart” button at any time to reset the board and choose sides again.

---

## Game Rules

- **Board Size**: 15x15 grid.
- **Winning Condition**: First player to place **5 consecutive stones** in a row, column, or diagonal wins.
- **Turns**: Players alternate turns, placing one stone per turn.
- **Undo Feature**: Undoes the last move of each side (if the AI already moved).

---

## AI Difficulty

This project uses **Monte Carlo Tree Search (MCTS)** under different simulation limits and time constraints for each difficulty:

| Difficulty | Simulations | Time Limit (seconds) | Description                      |
|------------|------------:|---------------------:|----------------------------------|
| Simple     |         500 |                    2 | Faster but weaker AI.           |
| Medium     |        1000 |                    5 | Balanced level of AI thinking.  |
| Hard       |        3000 |                   12 | Deeper search, stronger AI.     |

---

## Multi-language Support

You can switch between English, Chinese, Spanish, and French at runtime. All UI text, including dialog messages, button labels, and status updates, will change immediately upon switching languages.

---

## Undo and Timers

- **Undo**:  
  - Each undo action removes the most recent moves of both the player and the AI (if the AI’s move occurred).  
  - Undo is disabled if no moves are made or if the game has ended.

- **Timers**:  
  - Each turn (player or AI) has its own step timer in seconds.  
  - When the turn switches, the previous player's timer stops, and the next player's timer starts.  
  - Displays **“Black Time”** and **“White Time”** with the duration in seconds and milliseconds.

---

## Project Structure

A possible structure (if the code is one file, you can list just that file):
```
.
├── main.py                  # Main entry point for the Gomoku game
├── README.md                # Project documentation
└── LICENSE                  # Open-source license file
```

**Key Components in `main.py`:**
- **`Gomoku` class**  
  Handles the main UI logic, board rendering, player interactions, timers, language switching, etc.

- **`mcts_search` function**  
  Orchestrates the MCTS simulations to pick the best move for the AI.

- **`simulate` function**  
  Handles the random playouts for each simulation, along with backpropagation.

- **`MCTSNode` class**  
  Represents a single node in the MCTS tree, storing board state, children nodes, and visit/win counts.

---

## Contributing

Contributions are welcome! If you’d like to help:

1. **Fork** the repository and **clone** it locally.
2. Create a new **feature branch** for your changes:
   ```bash
   git checkout -b feature-YourFeatureName
   ```
3. Make your changes or additions.
4. **Commit** and **push** to your branch.
5. Open a **Pull Request** describing your changes, and we’ll review it.

Please read our [CONTRIBUTING.md](CONTRIBUTING.md) (if available) for more details.

---

## License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

---

## Contact

If you have any questions, suggestions, or feedback, feel free to open an [issue](https://github.com/cooltesttry/Gomoku-O1/issues)

We hope you enjoy playing Gomoku with our AI and welcome any contributions you might make!
