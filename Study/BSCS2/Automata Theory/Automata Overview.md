---
created: 2025-01-30 00:12
parent-subject: Automata Theory
cssclasses:
  - daily
  - friday
---


# Lecture 01: Central Concepts of Automata Theory

## Overview
- **Automata theory** is the study of abstract computational devices or "machines."
- Abstract devices are simplified models of real computations.
- Automata theory studies the computational power and limitations of these machines.

---

## Applications of Automata Theory
1. **Software for designing and checking the behavior of digital circuits.**
2. **The "lexical analyzer" of a typical compiler.**
3. **Software for scanning large bodies of text** (e.g., the Web) to find occurrences of words, phrases, or other patterns.
4. **Software for verifying systems** of all types that have a finite number of distinct states (e.g., communication protocols).

---

## Finite Automata (FA)
- Useful models for many kinds of hardware and software.
- **Example 1:** FA modeling an on/off switch.
- **Example 2:** FA that could be part of a lexical analyzer (recognizing the keyword "then").

---

## Grammars and Regular Expressions
- Play an important role in structuring data in the study of automata and their applications.
- Useful models when designing software that processes data with a recursive structure (e.g., parsers).
- A simple notation for describing many of the patterns that arise naturally in practice (e.g., `[A-Z][a-z]*[ ][A-Z][A-Z]`).

---

## Limits of Computation
- Automata are essential for studying the limits of computation:
  - **What can a computer do?**
  - **What can a computer do efficiently?**

---

## Types of Automata
1. **Finite Automata:** Devices with a finite amount of memory, used to model "small" computers.
2. **Push-down Automata:** Devices with infinite memory that can be accessed in a restricted way, used to model parsers, etc.
3. **Turing Machines:** Devices with infinite memory, used to model any computer.
4. **Time-bounded Turing Machines:** Infinite memory but bounded running time, used to model any computer program that runs in a "reasonable" amount of time.

---

## Example Problems
- Given a word `s`, does it contain the subword "fool"?
- Given a number `n`, is it divisible by 7?
- Given a pair of words `s` and `t`, are they the same?
- Given an expression with brackets (e.g., `(()())`), does every left bracket match with a subsequent right bracket?

All of these problems have "yes/no" answers.

---

## Sets and Elements
- A **set** is an unordered collection of objects or elements.
  - **Example:**  
    - `A = {a, b, c}`
    - `B = {b, c, b, a, a}` (same as `A`)
    - `Z = {..., -2, -1, 0, 1, 2, ...}`
    - `Z+ = {0, 1, 2, 3, ...}`

---

## Alphabets
- An **alphabet** is a finite set of fundamental units called letters or symbols.
  - **Examples:**
    - `∑ = {a, b, c, ..., z}`
    - `∑ = {0, 1, 2, ..., 9}`
    - `∑ = {a, b}`
    - `∑ = {0, 1}`

---

## Strings
- A **string** over an alphabet is a finite sequence of symbols from the alphabet.
  - **Examples:**
    - `cat`, `food`, `c`, `tattz` are strings over `∑ = {a, b, c, ..., z}`.
    - `0131` is a string over `∑ = {0, 1, 2, ..., 9}`.

---

## Length of a String
- The **length** of a string `s`, denoted `|s|`, is the number of symbols in `s`.
  - **Example:**
    - `length(mom) = |mom| = 3`
    - `α = abcb`, `|α| = 4`

---

## Empty String
- The **empty string**, denoted by `ε`, is the string consisting of no symbols (`|ε| = 0`).

---

## Kleene Star (`∑*`)
- For a given alphabet `∑`, `∑*` denotes the set of all possible strings (including `ε`) over `∑`.
  - **Example:**
    - If `∑ = {a, b}`, then `∑* = {ε, a, b, aa, ab, ba, bb, aaa, aab, aba, abb, ...}`.

---

## Lexicographic Order
- A sequence of strings `w1, w2, ...` over an alphabet `∑` is in lexicographic order if:
  1. Shorter strings always appear before longer strings.
  2. Strings of the same length appear in alphabetical order.
  - **Example:**
    - If `∑ = {0, 1}`, then `∑* = {ε, 0, 1, 00, 01, 10, 11, 000, 001, 010, 011, 100, ...}`.

---

## Concatenation of Strings
- Given two strings `u` and `v`, the **concatenation** of `u` and `v` is the string `uv`.
  - **Examples:**
    - `u = abb`, `v = ab` → `uv = abbab`
    - `u = ε`, `v = ab` → `uv = ab`
    - `u = bb`, `v = ε` → `uv = bb`

---

## Power of a String
- For a string `w`, we define `w^n` for `n ≥ 0` inductively as follows:
  - `w^0 = ε`
  - `w^n = w^(n-1)w` for any `n ≥ 1`
  - **Example:**
    - `w = dog` → `w^0 = ε`, `w^1 = dog`, `w^2 = dogdog`, `w^3 = dogdogdog`.

---

## Substrings
- A **substring** of a string `s` is any contiguous part of `s`.
  - **Example:**
    - `s = 472` → substrings are `ε`, `4`, `7`, `2`, `47`, `72`, `472`.

---

## Languages
- A **language** is a set of strings over an alphabet.
  - **Examples:**
    - Set of "syntactically correct" C programs.
    - Set of palindromes over `∑ = {0, 1}`.

---

## Examples of Languages
- **Example 1:**  
  - `∑ = {x}`  
  - `L0 = {ε, x, xx, xxx, xxxx, ...} = {x^n | n = 0, 1, 2, 3, ...}`  
  - `L1 = {x^n | n ≥ 1}`  
  - `L2 = {x, xxx, xxxxx, xxxxxxx, ...} = {x^(2n+1) | n = 0, 1, 2, 3, ...}`

- **Example 2:**  
  - `∑ = {0, 1, 2, ..., 9}`  
  - `L3 = {any string of symbols that do not start with zero}`  
  - `L4 = {any finite string, i.e., if it has length more than one, it does not start with zero}`  
  - `L5 = {any finite string, i.e., if it starts with zero, it has no symbols after the first}`

---

## Empty Set vs. Empty String
- The **empty set** (`∅`) is the set consisting of no elements.
  - `ε ∉ ∅` since `∅` has no elements.
  - `∅ ≠ {ε}` since `∅` has no elements.

---

## Set Operations
1. **Union (`S ∪ T`):** All elements in either `S` or `T` or both.
   - **Example:**  
     - `S = {ab, bb}`, `T = {aa, bb, a}` → `S ∪ T = {ab, bb, aa, a}`.

2. **Intersection (`S ∩ T`):** All elements in both `S` and `T`.
   - **Example:**  
     - `S = {ab, bb}`, `T = {aa, bb, a}` → `S ∩ T = {bb}`.

3. **Difference (`S - T`):** All elements in `S` but not in `T`.
   - **Example:**  
     - `S = {a, b, bb, bbb}`, `T = {a, bb, bab}` → `S - T = {b, bbb}`.

4. **Complement (`S'`):** All elements not in `S`.
   - **Example:**  
     - Let `S` be the set of strings over `∑ = {a, b}` that begin with `b`. Then `S'` is the set of strings over `∑` that do not begin with `b`.

---

## Cartesian Product
- The **Cartesian product** of two sets `S` and `T` is the set of pairs `(x, y)` where `x ∈ S` and `y ∈ T`.
  - **Example:**  
    - `S = {a, ba, bb}`, `T = {ε, ba}` → `S × T = {(a, ε), (a, ba), (ba, ε), (ba, ba), (bb, ε), (bb, ba)}`.

---

## Power Set
- The **power set** of a set `S` is the set of all possible subsets of `S`.
  - **Example:**  
    - `S = {a, bb}` → `P(S) = {∅, {a}, {bb}, {a, bb}}`.

---

## Kleene Closure (`S*`)
- The **Kleene closure** of a set of strings `S` is the set of all strings formed by concatenating zero or more strings from `S`.
  - **Example:**  
    - `S = {ba, a}` → `S* = {ε, a, aa, ba, aaa, aba, baa, aaaa, aaba, ...}`.

---

## Positive Closure (`S+`)
- The **positive closure** of a set of strings `S` is the set of all strings formed by concatenating one or more strings from `S`.
  - **Example:**  
    - `∑ = {x}` → `∑+ = {x, xx, xxx, ...}`.




























---
> [!info] see also [[Automata Theory]] 
---



	