---
# AmeNoOhobari Chess Engine

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Language](https://img.shields.io/badge/Language-x86_64_Assembly-blue?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**AmeNoOhobari v.1.2.4 – The God-Slayer**  
_A pure assembly chess engine with cutting-edge move ordering, policy network hooks, and tactical search._

---

## 🚀 Features (v.1.2.4)

- **Written in x86_64 Assembly:** Ultimate speed, total hardware control, zero dependencies.
- **Move Ordering:**  
  - MVV-LVA scoring for tactical sharpness.
  - Killer moves and history heuristics for quiet move prioritization.
  - **NEW:** Policy network hook (ready for CNN integration).
- **Quiescence Search:**  
  - Explores only tactical moves at leaf nodes for stable evaluation.
- **Negamax Search:**  
  - Alpha-beta pruning, principal variation search (PVS), late move reductions (LMR).
- **Efficient Move Generation:**  
  - Piece-specific and generic slider logic, basic pawn moves.
- **Minimalist Board Representation:**  
  - 64-byte array, bitwise color/type encoding.
- **Output:**  
  - UCI-style best move (e.g., `bestmove g1f3`) for GUI compatibility.
- **No external libraries** required—just NASM and LD.

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

- **Board & Pieces:** 64 squares; constants for piece type and color.
- **Evaluation:** Material, piece-square tables, mirrored squares for black.
- **Move Generation:**  
  - Knights, kings, bishops, rooks, queens, pawns.
  - Sliders use precomputed offsets and wrap-around checks.
- **Move Ordering:**  
  - MVV-LVA for captures.
  - Killer moves/history table for quiet moves.
  - **Policy Network Hook:** Integrate a CNN for move probability scoring (currently a placeholder).
- **Search:**  
  - Negamax with alpha-beta, PVS, LMR, and node count.
  - **Quiescence search** at leaf nodes for tactical stability.
- **Output:**  
  - UCI-style `bestmove` in algebraic notation.

---

## 🔥 What's New in v.1.2.4

- **Policy Network Integration:**  
  - Added hooks for CNN-based move probability scoring (`policy_scores` array).
  - Ready for external C/Python/TensorFlow integration.
- **Quiescence Search:**  
  - Tactical filtering for stable leaf node evaluation.
- **Improved Move Ordering:**  
  - Policy scores, killer moves, history, and MVV-LVA are combined for best move selection.
- **Search Optimizations:**  
  - Principal Variation Search (PVS) and Late Move Reductions (LMR) for deeper, faster pruning.
- **Cleaner Output, Structure, and Comments.**

---

## ⚠️ Limitations

- Pawn logic: No promotions/en passant yet.
- No castling or advanced rules.
- Policy network is a stub—needs external integration for neural move ordering.
- Not a complete chess engine yet; ideal for learning, hacking, and experimentation.

---

## 📃 License

MIT License  
© [Tonmoy KS](https://github.com/Tonmoy-KS)

---

## 🤝 Contributing

Pull requests, optimizations, and bug fixes are very welcome!  
Open an issue for feature requests or ideas.

---

## 📬 Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*May your moves be as sharp as AmeNoOhobari’s blade!*

---