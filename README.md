# 🧬 GameOfLifeEncryption

**GameOfLifeEncryption** is a reversible, deterministic encryption algorithm that creatively combines the classic **XOR cipher** with the evolving patterns of **Conway’s Game of Life** — implemented entirely in **32-bit x86 Assembly** using **AT&T syntax**.

This project was created as a **college-level systems programming assignment**, and demonstrates efficient use of low-level operations, bit masking, and memory-optimized data storage.

---

## 🔐 How It Works

### 1. 🔑 XOR Cipher
- The input plaintext is converted into binary using ASCII encoding.
- A keyword (also in binary) is repeatedly XORed against the plaintext to produce a ciphered bitstream.
- The keyword loops as needed to match the input length.

### 2. 🧬 Game of Life Grid Transformation
- The XORed binary is seeded into a 2D matrix where each **bit** represents a single **cell**.
- The matrix evolves over **N generations** according to the **Game of Life** rules.
- The final matrix state becomes the **encrypted output**.

### 3. 🔁 Reversibility
- The process is completely **deterministic and reversible**.
- Using the correct keyword and generation count, the original plaintext can be decrypted from the final matrix.

---

## 🧠 Memory & Performance Highlights

- 🔲 **Bit-Level Matrix Storage**  
  Every **single bit** in memory represents a cell in the Game of Life grid — drastically reducing memory usage.
  
- 🎯 **Mask-Based Bit Manipulation**  
  Bit masks are used to efficiently **set, clear, and check** individual bits within bytes.

---

## 🧾 Assembly Structure

This repository contains **three `.s` files**, each representing a different version of the program:

| File                      | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| `generation.s`            | Only runs the Game of Life logic and prints the final grid.  |
| `generation_encryption.s` | Adds XOR encryption and decryption of words using a keyword. |
| `generation_decryption.s` | Full program with file input/output, keyword, and evolution. |

---

## ⚙️ Compilation Instructions

Make sure you have GCC with 32-bit support installed:

```bash
sudo apt install gcc-multilib
Then compile using:

bash
gcc -m32 -no-pie file.s -o output_binary
```

## 📜 Game of Life Rules
The Game of Life is a "zero-player game" created by mathematician John Conway. Each cell on a 2D grid is either alive (1) or dead (0) and evolves based on its neighbors.

#Rules:
Birth: A dead cell with exactly 3 live neighbors becomes alive.

Survival: A live cell with 2 or 3 live neighbors stays alive.

Death:

Fewer than 2 neighbors → dies (underpopulation)

More than 3 neighbors → dies (overpopulation)

The result is complex, emergent behavior from very simple rules.

## 🔗 Learn more on Wikipedia Or Play the Game Yourself

https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life

https://playgameoflife.com/

## 🧪 Project Purpose
This project was developed as part of a college systems programming course, to:

Explore the fundamentals of low-level programming

Implement efficient bit-level memory handling

Understand cellular automata as computational models

Combine theoretical concepts with practical encryption
