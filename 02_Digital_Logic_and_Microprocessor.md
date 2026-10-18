# Chapter 2 — Digital Logic and Microprocessor
*(Code AExE02 — 10 questions)*

---

## 2.1 Digital Logic

### Number systems
| System | Base | Digits | Example |
|---|---|---|---|
| Binary | 2 | 0,1 | 1011₂ |
| Octal | 8 | 0–7 | 57₈ |
| Decimal | 10 | 0–9 | 47 |
| Hexadecimal | 16 | 0–9, A–F | 2F₁₆ |

- **Conversions:** binary→decimal (sum of 2ⁿ), decimal→binary (repeated divide by 2, remainder), binary↔hex (group 4 bits), binary↔octal (group 3 bits).
- **BCD** (8421): each decimal digit encoded as 4-bit binary (e.g., 25 → 0010 0101). NOT same as hex.
- **1's complement:** invert all bits. **2's complement = 1's complement + 1.** Used for signed arithmetic (range for n bits: −2ⁿ⁻¹ to +2ⁿ⁻¹−1).
- **Gray code:** adjacent values differ by 1 bit; used in encoders/shift position.

### Logic gates (truth tables positive logic)
| Gate | Output (A,B) | Mnemonic |
|---|---|---|
| AND | 1 only if all 1 | AB |
| OR | 1 if any 1 | A+B |
| NOT | invert | Ā |
| NAND | NOT of AND | (AB)' |
| NOR | NOT of OR | (A+B)' |
| XOR | 1 if inputs differ | A⊕B |
| XNOR | 1 if inputs same | (A⊕B)' |

- **NAND and NOR are universal gates** (can build any logic).
- **XOR = odd function** (output 1 when odd number of 1s); used in adders & parity checkers.

### Boolean algebra
- A + 0 = A; A·1 = A; A + Ā = 1; A·Ā = 0; A·A = A; A + A = A.
- **De Morgan's laws:** `(A·B)' = A' + B'` and `(A+B)' = A'·B'`.
- A + A·B = A (absorption); A + Ā·B = A + B.
- **SOP** (sum of products): groups of 1s in K-map; **POS** (product of sums): groups of 0s.
- **K-map:** minimize Boolean expressions; groups of 1,2,4,8… adjacent cells (power of 2); cells differ in 1 variable; can wrap around edges (±1 rule: cells differ in exactly 1 bit).

---

## 2.2 Combinational and Arithmetic Circuits

Combinational circuits have **no memory**; output depends only on current inputs.

### Basic building blocks
- **Half adder:** sum = A⊕B, carry = A·B (2 inputs).
- **Full adder:** adds two bits + carry-in; produces sum + carry-out.
- **Half subtractor / Full subtractor** (with borrow).
- **Multiplexer (MUX):** many inputs → 1 output, selected by select lines. **n select lines → 2ⁿ inputs.** (4:1 MUX has 2 select lines.)
- **Demultiplexer (DEMUX):** 1 input → many outputs.
- **Decoder:** n inputs → 2ⁿ outputs (binary → one-hot). **Encoder:** reverse (priority encoder outputs code of highest-priority active input).
- **3-to-8 decoder, 2-to-4 decoder.**

### Binary arithmetic
- **Unsigned:** straight binary addition/subtraction.
- **Signed:** usually 2's complement. Subtraction A−B = A + (2's complement of B).
- **Overflow** occurs if two positive sum → negative (sign bit flip), etc.
- Ripple-carry adder, carry-lookahead adder (faster).

---

## 2.3 Sequential Logic Circuits

Sequential circuits **store state** (memory + clock).

### Flip-flops
| Type | Behavior |
|---|---|
| **SR** | Set (S), Reset (R); S=R=1 → invalid/race |
| **JK** | J=K=1 → **toggle**; eliminates SR race |
| **D** | Data latch; Q follows D on clock; used in registers |
| **T** | T=1 → toggle; T=0 → hold |

- **Gated/latch:** level-sensitive. **Edge-triggered:** respond only at clock edge (positive or negative). **Master-slave:** two latches, avoids race, edge behavior.

### Registers & shift registers
- **Register:** group of flip-flops storing n bits.
- **Shift register types:** SISO, SIPO, PISO, PIPO.
- Applications: serial–parallel conversion, delay, ring counter, Johnson counter.

### Counters
- **Asynchronous (ripple):** slower, flip-flop clocked by previous stage output; propagation delay accumulates.
- **Synchronous:** all flip-flops share clock; faster.
- **Mod-N counter:** counts 0 → N−1. n flip-flops → up to **2ⁿ** states. **Mod-8 = 3 flip-flops.**
- **Ring counter:** 1 of n; Johnson (twisted ring): 2n states with n ffs.

---

## 2.4 Microprocessor

### 8085 architecture (8-bit µP)
- **Registers:** A (accumulator), B, C, D, E, H, L (8-bit); PC (program counter, 16-bit), SP (stack pointer, 16-bit).
- **ALU:** arithmetic & logic operations on A.
- **Flags (S,Z,AC,P,CY):** sign, zero, auxiliary carry, parity, carry.
- **Address bus 16-bit** → 64 KB memory; **data bus 8-bit**; control signals (RD', WR', ALE, IO/M').
- Clock 3 MHz typical; status flags updated by arithmetic ops.
- **Accumulator** is the main working register; results stored in A.

### Instruction set & addressing modes
- Instruction = **opcode + operand**. Opcode fetched first (M1 cycle).
- **Addressing modes:** immediate (operand in instruction), register, direct, indirect (via H-L pair or XTHL), register pair, implied (no operand), indexed (only in 8086).
- Common instructions: MOV (transfer), MVI (move immediate), LDA/STA (load/store accumulator), ADD/SUB/INR/DCR, JMP/JNZ (jumps), CALL/RET (subroutine), PUSH/POP (stack), XRA (xor → clears A & carry), HLT.
- **Memory addressing in 8085:** 8085 is an **8-bit** processor; 8086 is **16-bit**, 20-bit address → **1 MB** memory, 6-byte prefetch queue.

### Assembly programming
- Program = sequence of mnemonics; assembled to machine code; stored starting at an address; execution starts from PC.

---

## 2.5 Microprocessor Systems

### Memory classification & hierarchy
- **Primary memory:** semiconductor — RAM (volatile): SRAM (fast, no refresh, cache), DRAM (cheap, needs refresh). ROM (non-volatile): Masked ROM, PROM, EPROM (UV erasable), **EEPROM/Flash** (electrically erasable).
- **Secondary storage:** magnetic (HDD), optical (CD/DVD), SSD.
- **Hierarchy (top→bottom):** registers → cache → main memory → secondary → offline; **speed decreases, capacity & access time increase, cost per bit decreases.**

### I/O and memory interfacing
- **Memory-mapped I/O** vs **isolated I/O**.
- **Programmable Peripheral Interface (PPI) 8255:** 3 ports (A, B, C); modes 0/1/2; used to interface keyboard, display, LEDs.
- **Serial interface:** synchronous vs **asynchronous** (start/stop bits), UART/USART; **RS-232** standard (serial communication between DTE/DCE).
- **DMA (Direct Memory Access):** dedicated controller (e.g., **8237**) transfers data between memory and I/O **without CPU** involving the address/data buses; DMAC holds resources via HOLD/HLDA.

### 8255 modes
- Mode 0 (basic I/O), Mode 1 (strobed I/O), Mode 2 (bidirectional).

---

## 2.6 Interrupt Operations

### Interrupt concepts
- An interrupt is a signal that **suspends normal program execution** to service an event.
- Process: request → acknowledge → save PC/context → execute **Interrupt Service Routine (ISR)** → return (RET) → restore → continue.
- **Interrupt vector:** address of ISR; **vectored interrupts** have fixed addresses.

### 8085 interrupts
| Type | Priority | Maskable | Vector | Notes |
|---|---|---|---|---|
| TRAP | 1 (highest) | **Non-maskable** | 0024H | Power failure, edge+level |
| RST 7.5 | 2 | maskable | 003CH | edge-triggered |
| RST 6.5 | 3 | maskable | 0034H | level |
| RST 5.5 | 4 | maskable | 002CH | level |
| INTR | 5 (lowest) | maskable | supplied externally | general-purpose |
- **Software interrupts:** RST 0–7 (executed by instruction).
- Enable/disable: EI / DI instructions; SIM/RIM for masking.

---

## Formula Box (Chapter 2 — must memorize)
- 2ⁿ states for n flip-flops; MUX: n select → 2ⁿ inputs
- NAND/NOR = universal gates; XOR = odd detector
- De Morgan: (AB)' = A'+B'
- 8085: 8-bit data bus, 16-bit address bus → 64 KB; 8086: 20-bit → 1 MB
- 2's complement = 1's + 1; subtraction via 2's complement
- DMA bypasses CPU; 8255 = PPI with ports A,B,C; RS-232 = serial standard
- TRAP = only non-maskable interrupt of 8085