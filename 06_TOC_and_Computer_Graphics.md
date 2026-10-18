# Chapter 6 — Theory of Computation and Computer Graphics
*(Code ACtE06 — 10 questions)*

---

## 6.1 Introduction to Finite Automata

### Concepts
- **Finite Automaton (FA):** abstract machine with finite states, reads input, changes state, may accept/reject. Model of machines with **finite memory**.
- **Finite State Machine (FSM):** FA with output (Moore: output depends on state only; Mealy: output depends on state + input).
- **Components:** set of states Q, input alphabet Σ, transition function δ, start state q₀, set of accepting states F.
- **DFA (Deterministic FA):** exactly **one transition per (state, symbol)**; deterministic.
- **NFA (Nondeterministic FA):** multiple/epsilon (ε) transitions possible; can be in several states at once.

### DFA ↔ NFA
- **DNFAs are equal in power** — every NFA can be converted to an equivalent DFA (subset construction).
- Language accepted = set of strings reaching a final state.

### Minimization of FSMs
- Remove **unreachable states**, then merge **equivalent/indistinguishable states** (partitioning method). Result: **minimal DFA** (unique).

### Regular expressions & pumping lemma
- **Regular expression:** notation describing regular language: `a, a|b, a·b, a*, (a|b)*, a+` (a+ = aa*).
- **Kleene star * :** zero or more; `+`: one or more; `?`: zero or one.
- Regular expressions and FAs are **equivalent** (both describe regular languages); conversion both ways.
- **Pumping lemma for regular languages:** if L is regular, ∃p such that any string w∈L with |w|≥p can be written **w = xyz**, |xy|≤p, y≠ε, and **xyᵏz ∈ L for all k≥0**.
- Use: **prove a language is NOT regular** (e.g., aⁿbⁿ, balanced parentheses are not regular).
- Closure properties: regular languages closed under union, intersection, complement, concatenation, star, reversal.

---

## 6.2 Introduction to Context-Free Languages

### Context-Free Grammar (CFG)
- **CFG = G(N, T, P, S):** nonterminals N, terminals T, productions P (A → α), start symbol S.
- **Derivation:** replace nonterminals per productions.
  - **Leftmost derivation:** replace leftmost nonterminal each step.
  - **Rightmost derivation:** replace rightmost nonterminal each step.
  - Top-down (start → terminals) / bottom-up (terminals → start) approaches.
- **Language of grammar L(G):** all terminal strings derivable from S.

### Parse tree
- Root = S, interior = nonterminals, leaves = terminals. **Ambiguous grammar:** same string has **≥2 distinct parse trees** (or ≥2 leftmost derivations).
- **Eliminating ambiguity:** factor, precedence levels.

### Normal forms
- **CNF (Chomsky Normal Form):** every production is `A → BC` or `A → a` (no ε unless S→ε). Substrings length 2.
- **GNF (Greibach Normal Form):** every rule `A → aα` (terminal first).
- **BNF (Backus-Naur Form):** notation for CFG used in language specs (::=, |, <>).

### Pushdown Automata (PDA)
- **PDA = FA + stack** (unbounded LIFO). Accepts by **final state** or **empty stack**.
- **Equivalence:** a language is context-free **iff** accepted by some PDA. Convert CFG ↔ PDA.
- **Pumping lemma for CFL:** if L is CFL, ∃p such that w = uvxyz, |vy|≥1, |vxy|≤p, and **uvⁱxyⁱz ∈ L ∀i**.
- **Properties of CFLs:** closed under union, concatenation, Kleene star, reversal; **NOT closed under intersection and complement.** CFLs include all regular languages.

---

## 6.3 Turing Machines

### Turing Machine (TM)
- Model of computation: **tape (unbounded), read/write head, finite control, transition function δ**. Captures "mechanical computation".
- **Instantaneous description/notation:** configuration (state, head position, tape content).
- **Acceptance of a string:** TM reaches a final/accepting (or halting) state.
- Roles:
  - **Language recognizer** (decision problems).
  - **Computing function** (transducers) — computes partial/total functions.
  - **Enumerator:** lists strings of a language.
- **Variants:**
  - **Multiple tracks:** tape cells with stacked symbols (no more power).
  - **Multiple tapes:** more convenient, same power.
  - **Non-Deterministic TM (NDTM):** multiple choices; same power as DTM.
  - **Semi-infinite tape:** same power.

### Church–Turing thesis
- **Church–Turing thesis:** every effectively computable function is computable by a Turing machine. (Not a theorem — an accepted thesis.)
- **Universal Turing Machine (UTM):** can simulate any TM by **encoding the TM** on its tape; basis of stored-program computers.

### Decidability & complexity
- **Halting problem:** "Does TM M halt on input w?" is **undecidable** (Turing's proof by diagonalization). Recursively enumerable but not recursive.
- **Time & space complexity of a TM** measured in terms of input length.
- **Intractability:** problems with no polynomial-time algorithm (under assumption P ≠ NP).
- **Reducibility:** problem A reduces to B (A ≤ B) → solving B solves A; used to prove undecidability/NP-hardness.
- Hierchy: **regular ⊂ context-free ⊂ recursive (decidable) ⊂ recursively enumerable**; complement of RE not necessarily RE.

---

## 6.4 Introduction to Computer Graphics

### Overview
- **Computer graphics:** creation, manipulation, and display of images using a computer.
- Pipeline: modeling → transformation → projection → clipping → rasterization → display.

### Graphics hardware
- **Display technology:**
  - **CRT:** electron beam; **raster-scan** (beam sweeps row by row, refreshing pixels) vs **vector/random-scan** (beam draws lines directly).
  - **Flat panel:** LCD, LED, OLED, plasma.
- **Architecture of raster-scan displays:** frame buffer (bitmap of pixels, refresh rate ~60 Hz), video controller, scan conversion, refresh.
- **Display processors:** handle drawing primitives to relieve CPU.
- **Output devices:** monitor, **printer (dot-matrix, inkjet, laser)**, plotter.
- **Input devices:** mouse, keyboard, **digitizer/tablet, joystick, trackball, lightpen, scanner, touch screen**.
- **Graphics software & standards:** OpenGL, DirectX, GKS, PHIGS, XWindow; device-independent libraries.

### Pixels & frame buffer
- **Resolution:** width × height in pixels. **Aspect ratio, bit depth (color depth = 2ⁿ colors for n bits/pixel).**
- **Refresh rate & flicker.**

---

## 6.5 Two-Dimensional Transformations

### Basic 2D transformations (homogeneous coordinates, 3×3 matrices)
- **Translation:** `x' = x + tx, y' = y + ty`
  ```
  [1 0 tx; 0 1 ty; 0 0 1]
  ```
- **Rotation (anticlockwise, angle θ about origin):**
  ```
  [cosθ −sinθ 0; sinθ cosθ 0; 0 0 1]
  ```
- **Scaling:** `[sx 0 0; 0 sy 0; 0 0 1]` — about origin; uniform if sx=sy.
- **Reflection (mirror):** about x-axis: `[1 0; 0 −1]`; about y-axis: `[−1 0; 0 1]`; origin: `[−1 0; 0 −1]`; about line y=x: swap.
- **Shear:** `x' = x + a·y` (x-shear: `[1 a 0; 0 1 0; 0 0 1]`), `y' = y + b·x` (y-shear).

### Composite transformation
- Multiply individual matrices **in sequence**: `P' = T·R·S·P` — **matrix multiplication order matters** (transformations applied right-to-left).
- (Basic transforms are not commutative: TR ≠ RT in general.)

### 2D viewing pipeline
- **World → View (window-to-viewport mapping / normalization) → Device.**
- **Window:** region of world you see; **viewport:** region on screen. Mapping: linear interpolation of coordinates (scaling + translation).
- **Clipping:**
  - **Cohen–Sutherland line clipping:** 4-bit region codes (top=10, bottom=01, left=00… each bit = above/below/right/left); trivial accept if both codes 0000; trivial reject if AND ≠ 0; else intersect & subdivide.
  - **Liang–Barsky line clipping:** parametric (t) form, efficient, uses 4 inequalities.

---

## 6.6 Three-Dimensional Transformations

### 3D basic transformations (4×4 matrices)
- **Translation:** `[1 0 0 tx; 0 1 0 ty; 0 0 1 tz; 0 0 0 1]`.
- **Rotation:**
  - About x: `[1 0 0 0; 0 cosθ −sinθ 0; 0 sinθ cosθ 0; 0 0 0 1]`
  - About y: `[cosθ 0 sinθ 0; 0 1 0 0; −sinθ 0 cosθ 0; 0 0 0 1]`
  - About z: `[cosθ −sinθ 0 0; sinθ cosθ 0 0; 0 0 1 0; 0 0 0 1]`
- **Scaling:** diagonal `[sx, sy, sz, 1]`.
- **Reflection & shear** analogous to 2D, extended to z.
- **Composite:** product of matrices in order.

### 3D viewing pipeline
- Model → World → View/Camera → Projection → Clip → Rasterize → Device.
- **Camera/viewing parameters:** position, look-at, up vector; view transformation places camera at origin.

### Projection concepts
| Type | Property |
|---|---|
| **Orthographic/projection** | Projectors **parallel**, perpendicular to plane; no perspective foreshortening; preserves relative dimensions (engineering drawings) |
| **Parallel projection** | Projectors parallel (orthographic is a special case with perpendicular projectors); oblique (parallel but not perpendicular) |
| **Perspective projection** | Projectors converge at a **vanishing point/center of projection**; objects far look smaller; realistic (viewing) |

- Also: isometric, dimetric, cavalier/cabinet (oblique), one/two/three-point perspective.

---

## Formula Box (Chapter 6 — must memorize)
- DFA = NFA (power); NFA → DFA subset construction
- Pumping lemma (regular): ∃p; w=xyz, |xy|≤p, xy^k z ∈ L
- CFG: S → aSb | ε (aⁿbⁿ, not regular); ambiguity = 2+ parse trees
- CNF: A→BC or A→a; GNF: A→aα; BNF notation
- PDA = FA + stack ↔ CFG equivalence
- CFL not closed under intersection/complement
- TM = recognizer + computing function + enumerator; UTM simulates all TMs
- Halting problem is UNDECIDABLE
- Hierarchy: regular ⊂ CF ⊂ recursive ⊂ RE
- Homogeneous coords: 2D=3×3 matrices, 3D=4×4
- 2D rotation via cos/sin; reflection/reflection and shear matrices
- Cohen–Sutherland (region codes, 4-bit); Liang–Barsky (parametric)
- Orthographic: parallel & perpendicular; Perspective: vanishing point, depth correct