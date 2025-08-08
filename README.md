---

# Ame-No-Ohobari Chess Engine

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Language](https://img.shields.io/badge/Language-x86_64_Assembly-blue?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**Ame-No-Ohobari v.1.4.7 – The God-Slayer**  
_A pure hand-crafted assembly chess engine with advanced pruning, hashing, and full pawn promotion support._

---

## 🚀 Features (v.1.4.7)

- **Written in x86_64 Assembly:** No dependencies, maximum speed and control.
- **Iterative Deepening with Aspiration Windows:** Smarter root search for best move.
- **Transposition Table (TT):** 1 million-entry hash table for fast position lookup.
- **Zobrist Hashing:** Fast and robust position identification.
- **Full Static Exchange Evaluation (SEE):** Superior capture ordering, tactical blunder avoidance.
- **Pawn Promotion:** Both white and black pawns can promote to Queen, Rook, Bishop, or Knight.
- **Opening Book (stub):** Ready for binary opening book integration.
- **Comprehensive Move Generation:** Knights, bishops, rooks, queens, kings, pawns, including all captures and promotions.
- **King Safety Evaluation:** Assesses king zone for threats.
- **UCI Output:** Prints the best move in standard UCI format (`bestmove g1f3`).
- **No external libraries needed:** Just NASM and LD.

---

## 🛠️ Compilation & Running

**Requirements:**  
- [NASM](https://www.nasm.us/)  
- GNU LD linker (Linux x86_64)

**How to Compile and Run:**
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

- **Board Representation:** 64-square array, bitwise piece/color encoding.
- **Evaluation:** Material, piece-square tables, passed pawn bonuses, king safety, and more.
- **Move Generation:**  
  - Handles all normal moves and all pawn promotions.
  - Accurate capture and quiet move generation.
- **Search:**  
  - Iterative deepening with aspiration windows for robust move selection.
  - Alpha-beta negamax with principal variation and TT lookups.
  - Quiescence search for tactical stability at leaf nodes.
- **SEE for Captures:**  
  - Orders captures by tactical safety using recursive static exchange logic.
- **Hashing:**  
  - Zobrist hash for fast and reliable transposition table indexing.
- **Output:**  
  - UCI-style move output for easy GUI integration.

---

## 🔥 What's New in v.1.4.7

- **Full Pawn Promotion Support:** Both colors, all major pieces.
- **Improved SEE and Capture Ordering:** Minimizes tactical errors.
- **Robust Transposition Table:** 1M entries for deep search acceleration.
- **King Safety Evaluation:** Penalizes exposed kings in the zone.
- **Opening Book Path and Loading (stubbed):** Ready for integration.
- **Assembly Macros for Move Generation:** Fast and flexible.
- **Better Modularization and Comments:** Easier for you (and others) to hack and extend.

---

## ⚠️ Limitations

- Castling, en passant, and some advanced rules are not yet implemented.
- Opening book, Syzygy tablebase, and some evaluation components are stubbed.
- Several functions are placeholders and can be implemented for full strength.
- Not a finished competitive engine—ideal for learning, hacking, and extending.

---

## 📃 License

MIT License  
© [Tonmoy KS](https://github.com/Tonmoy-KS)

---

## 🤝 Contributing

Pull requests, optimizations, and bug fixes are welcome!  
Open an issue for feature requests or suggestions.

---

## 📬 Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*May your moves be as sharp as Ame-No-Ohobari’s blade!*

---