---

# AmeNoOhobari Chess Engine

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Language](https://img.shields.io/badge/Language-x86_64_Assembly-blue?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**AmeNoOhobari V.1.2.3 – The God-Slayer Chess Engine**  
_A pure assembly chess engine focused on performance, move ordering heuristics, and low-level elegance._

---

## 🚀 Features (v.1.2.3)

- **Written in x86_64 Assembly** for ultimate speed and control.
- **Classic Chess Logic:** Piece values, piece-square tables, simple pawn logic.
- **Improved Move Ordering:**  
  - Added killer moves and history heuristics for alpha-beta pruning.
  - MVV-LVA (Most Valuable Victim - Least Valuable Attacker) for captures.
- **Root and Recursive Search:**  
  - Negamax with alpha-beta, killer/history, and move scores for efficient tree pruning.
- **Efficient Move Generation:**  
  - Piece-specific routines, generic slider logic, basic pawn moves.
- **Minimalist Board Representation:**  
  - 64-byte array, bitwise color/type encoding.
- **Output:**  
  - Prints the best move in UCI format (`bestmove g1f3`).
- **No external dependencies** required—just NASM and LD.

---

## 🛠️ Compilation & Running

**Requirements:**  
- [NASM](https://www.nasm.us/) (Netwide Assembler)
- GNU LD linker (Linux x86_64)

**Steps:**
```sh
nasm -f elf64 -g AmeNoOhobari.asm -o AmeNoOhobari.o
ld AmeNoOhobari.o -o AmeNoOhobari
./AmeNoOhobari
```

**Expected Output:**
```
bestmove g1f3
```

---

## 🧠 How It Works

- **Board & Pieces:** 64 squares, constants for piece type and color.
- **Evaluation:** Material, piece-square tables, and mirrored squares for black.
- **Move Generation:**  
  - Knights, kings, bishops, rooks, queens, and pawns.
  - Sliders use precomputed offsets and wrap-around checks.
- **Move Ordering:**  
  - MVV-LVA for captures.
  - Killer moves and history table for quiet moves.
  - Move scores for optimal search order.
- **Search:**  
  - Negamax with alpha-beta, killer/history, and node count.
- **Output:**  
  - UCI-style bestmove in algebraic notation.

---

## 🗝️ Changes in v.1.2.3

- **Heuristics Added:** Killer moves, history heuristic, and move scores for improved pruning and speed.
- **Move List Structure Updated:** 4 bytes per move for richer data.
- **Alpha/Beta Improvements:** More robust recursive search and cutoff logic.
- **Root Search Refined:** Better best-move selection loop and heuristic updates.
- **More Efficient Output:** UCI notation, easy for GUI integration.

---

## ⚠️ Limitations

- Pawn move generation is simplified (no promotions, en passant).
- No castling or advanced chess rules (focus is on search, heuristics, and move ordering).
- Not a complete chess engine yet—perfect for learning and hacking!

---

## 📝 License

MIT License  
© [Tonmoy KS](https://github.com/Tonmoy-KS)

---

## 🤝 Contributing

Pull requests, optimizations, and bug fixes are welcome!  
Open an issue for feature requests or ideas.

---

## 📬 Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*May your moves be as sharp as AmeNoOhobari’s blade!*

---