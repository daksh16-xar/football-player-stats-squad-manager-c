# Football Player Stats & Squad Manager

A menu-driven ANSI C / C99 command-line application built for football roster administration, match performance logging, automated player rating calculations, and persistent flat-file data analytics. 

This project fulfills the practical evaluation requirements for the **Computer Programming (26CAH-101)** course in the **BCA (Data Science)** program at **Chandigarh University**.

---

## 🎓 Academic Attribution & Student Details
* **Student Name:** Daksh
* **University ID (UID):** 26BCD10117
* **Program & Specialization:** BCA (Data Science) — 1st Semester
* **Class Section:** 26BCD 2-B
* **Faculty Supervisor:** Prof. Mehak Bhatia (Assistant Professor, UIC)
* **Academic Term:** End-Semester Practical Mini-Project | Odd Semester (2026–2027)

---

## 📋 Project Documentation
📄 **[View the Full 15-Page Project Report (PDF)](./Football_Player_Stats_Squad_Manager_Report_261031_064808.pdf)**

---

## ⚡ Core Features & Functional Decomposition
The program splits presentation layers, core business analytics, and storage engines into 7 modular sub-systems:
1. **File Data Synchronization (`loadFromFile` & `saveToFile`):** Automatic initialization and backup to a custom pipe-delimited flat-file engine (`squad_records.txt`). Falls back to seeding an 8-player benchmark database featuring international legends (Messi, Ronaldo, Chhetri, Mbappé) on its very first launch.
2. **Dynamic Squad Roster Management (`addPlayer`):** Roster expansion capabilities for up to 100 squad members with automated primary-key tracking to completely prevent duplicate jersey numbers.
3. **Formatted Console Outputs (`displayAllPlayers`):** Builds real-time tabular ASCII representations of performance matrices with precise fixed-precision formatting.
4. **Dual-Mode Search Engine (`searchPlayer`):** Offers instant search query lookups via an exact integer matching algorithm (by jersey number) or an intuitive case-sensitive partial string substring search (`strstr`).
5. **Match Performance Logging (`updatePlayerStats`):** Multi-stat accumulation logic (`+=`) to record added matches, goals, and assists directly inside live volatile memory.
6. **Leaderboard Sort Optimization (`displayTopScorersAndAnalytics`):** Clones data arrays to run a non-destructive dual-key Bubble Sort algorithm, compiling Golden Boot standings ranked by total goals (with total assists serving as a secondary tie-breaker factor).
7. **Roster Cleaning Engine (`deletePlayer`):** Deletes array items in $O(N)$ time complexity, shifting succeeding memory offsets leftwards before instantly rewriting database text files.

---

## 📊 Analytics Engine & Mathematical Formulas
Whenever records are registered or updated, metrics are automatically re-calculated using an analytical processing subsystem:
* **Goals Per Match (G/M):** Computed automatically to protect against division-by-zero bounds:
  $$\text{Goals Per Match} = \frac{\text{Goals}}{\text{Matches}}$$
* **Weighted Contribution Index:** Evaluates player impact values by balancing finish completions alongside operational assists:
  $$\text{Contribution Per Match} = \frac{(\text{Goals} \times 2) + \text{Assists}}{\text{Matches}}$$
* **Algorithmic Performance Rating:** Sets a baseline tracking floor of $6.00$ scaling proportionally to a fixed analytical cap of $9.90$:
  $$\text{Rating} = 6.00 + (\text{Contribution Per Match} \times 2.20)$$

---

## 🛠️ Data Structure Schema (`typedef struct`)
The program encapsulates heterogeneous profiles inside a single contiguous 100-byte block:
* `int jerseyNo` — Unique identifier key bounded between $1 \le \text{jerseyNo} \le 99$
* `char name[50]` — Full name string array supporting whitespace inputs via `fgets`
* `char position[20]` — Tactical role classifications (`Forward`/`Midfielder`/`Defender`/`Goalkeeper`)
* `int age` — Chronological age parameter (validated for $\ge 15$)
* `int matches` / `int goals` / `int assists` — Numerical sports metric trackers
* `float goalsPerMatch` / `float rating` — Derived system variables

---

## 🚀 Requirements & Compilation Execution
### Technical Specs
* **Compiler Base:** GNU Compiler Collection (GCC 11+ recommended) with `-Wall -Wextra` flags
* **Libraries:** Standard ANSI C standard imports (`<stdio.h>`, `<stdlib.h>`, `<string.h>`, `<ctype.h>`)

### Command Terminal Execution
```bash
# 1. Compile the project file
gcc -Wall -Wextra football_squad_manager.c -o football_squad_manager

# 2. Launch the menu application loop
./football_squad_manager
```

---
