---

# AmeNoOhobari Chess Engine

![MIT License](https://img.shields.io/badge/license-MIT-FF4136?labelColor=gray)
![Language](https://img.shields.io/badge/Language-x86_64_Assembly-blue?labelColor=gray)
![Creator](https://img.shields.io/badge/Creator-Tonmoy_KS-7DF9FF?labelColor=gray)

**AmeNoOhobari V.1.1.0 – The God-Slayer Chess Engine**  
_A pure assembly chess engine focused on speed, clarity, and low-level control._

---

## Features

- **Written in x86_64 Assembly:** Ultra-efficient, minimal dependencies, direct hardware control.
- **Classic Chess Logic:** Implements piece values, piece-square tables, and tapered king evaluation.
- **Transposition Table:** Fast hashing and caching for deep, repeated searches.
- **Optimized Move Generation:** Bitwise move generation for all piece types.
- **NegaMax Search:** Recursive search with alpha-beta pruning for strong tactical decisions.
- **Self-contained:** No external libraries required; just NASM and LD.
- **UCI-like Output:** Prints `bestmove` in algebraic notation (e.g., `bestmove g1f3`) for GUI integration.

---

## Compilation & Running

**Requirements:**  
- [NASM](https://www.nasm.us/) (Netwide Assembler)
- GNU `ld` linker (Linux x86_64)

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

## How It Works

- **Board Representation:** 64-byte array, with constants for each piece and color.
- **Evaluation:** Piece values, game phase calculation, and piece-square tables for accurate scoring.
- **Move Generation:** Efficient macros and routines for all piece types.
- **Search:** NegaMax with alpha-beta pruning and a transposition table for rapid deep analysis.
- **Output:** Prints the best move found in UCI format.

---

## Customization

- **Depth:** Default search depth is set to 5 (can be changed in `_start`).
- **Piece Values & PSTs:** Easily modifiable in the `.data` section.
- **Transposition Table Size:** Set with `TT_SIZE` (default: 65536 entries).

---

## License

MIT License  
© [Tonmoy KS](https://github.com/Tonmoy-KS)

---

## Contributing

Pull requests, optimizations, bug fixes, and new features are welcome!  
Please open an issue first for major changes.

---

## Contact

GitHub: [Tonmoy-KS](https://github.com/Tonmoy-KS)

---

*May your moves be as sharp as the God-Slayer’s blade!*

---