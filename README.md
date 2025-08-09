---

# Ame-No-Ohobari Chess Engine (v1.5.4)

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Language](https://img.shields.io/badge/Language-x86_64_Assembly-blue?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**Ame-No-Ohobari v.1.5.4 – The God-Slayer**  
_A pure hand-crafted assembly chess engine featuring advanced search, hashing, tactical evaluation, and full pawn promotion support._

---

## 🚀 Features (v.1.5.4)

- **Written in x86_64 Assembly:** No dependencies, maximum speed and control.
- **Iterative Deepening with Aspiration Windows:** Smarter root search for optimal move selection.
- **Transposition Table (TT):** 1 million-entry hash table for fast position lookup and pruning.
- **Zobrist Hashing:** Fast, robust position identification for TT and repetition detection.
- **Full Static Exchange Evaluation (SEE):** Orders captures by tactical safety, reducing blunders.
- **Pawn Promotion:** Both colors, all major pieces supported (Queen, Rook, Bishop, Knight).
- **Opening Book Ready:** Binary opening book path integrated (stub for future expansion).
- **Advanced Move Generation:** Knights, bishops, rooks, queens, kings, pawns. All captures and promotions, tactical and quiet moves.
- **King Safety Evaluation:** Evaluates threats in the king’s zone.
- **UCI Protocol Support:** Communicates using standard UCI commands (`bestmove <move>`).
- **Syzygy Tablebase Stub:** Structure in place for future integration.
- **Optimized Assembly Macros:** Fast and flexible move generation.
- **Modular & Commented Code:** Easier for contributors to extend and modify.
- **No external libraries:** Just NASM and LD required to build and run.

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
- **Evaluation:** 
  - Material, piece-square tables (PST), passed pawn bonuses, king safety, and more.
- **Move Generation:**  
  - Handles all standard moves and all pawn promotions.
  - Accurate generation for tactical, quiet, and special moves.
- **Search:**  
  - Iterative deepening with aspiration windows for robust move selection.
  - Alpha-beta negamax, principal variation search, and transposition table lookups.
  - Quiescence search for stable tactical evaluation at leaf nodes.
- **SEE for Captures:**  
  - Recursive static exchange logic for tactical move ordering.
- **Hashing:**  
  - Zobrist hash for fast, reliable transposition table indexing.
- **Tablebases:**  
  - Basic structure for Syzygy probing (stubbed, ready for future implementation).
- **Output:**  
  - UCI-style move output for easy GUI and tool integration.

---

## 🔥 What's New in v.1.5.4

- **Improved Search Algorithm:**
  - Enhanced alpha-beta, principal variation search, and pruning techniques.
  - Late Move Reductions (LMR) and Null Move Pruning (NMP) for deeper, faster search.
- **Full Pawn Promotion Support:** Both colors, all promotion pieces.
- **Optimized SEE and Capture Ordering:** Minimized tactical errors.
- **Robust Transposition Table:** 1M entries for deep search acceleration.
- **King Safety Evaluation:** More accurate risk assessment in the king's zone.
- **Opening Book Integration Path:** Ready for binary opening book loading.
- **Syzygy Tablebase Probe Structure:** In place for future endgame tablebase support.
- **Assembly Macros:** Speedier and more flexible move generation.
- **Better Modularization & Comments:** Easier for contributors to hack, extend, and maintain.

---

## ⚠️ Limitations & TODO

- Opening book, and some evaluation components are currently stubs.
- Some functions are placeholders – can be improved for competitive strength.
- Not a finished competitive engine—ideal for learning, hacking, and further development.

---

## 📃 License

MIT License  
© [Tonmoy KS](https://github.com/Tonmoy-KS)

---

## 🤝 Contributing

Pull requests, optimizations, and bug fixes are welcome!  
Open an issue for feature requests, suggestions, or questions.

---

## 📬 Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*May your moves be as sharp as Ame-No-Ohobari’s blade!*

---
