# Chapter 4 — Computer Organization and Embedded System
*(Code ACtE04 — 10 questions)*

---

## 4.1 Control and Central Processing Units

### Basic computer configuration (Von Neumann)
- **CPU (ALU + CU + Registers) + Memory + I/O**, connected by a **system bus** (address, data, control).
- **Stored program concept:** program + data in same memory.
- **Fetch → Decode → Execute** cycle; PC holds next instruction address.

### Control unit & microprogramming
- **Hardwired control:** logic circuits; fast, inflexible.
- **Microprogrammed control:** control signals stored in **control memory** as microinstructions; flexible (easy to modify = RISC/CISC tradeoff).
- **Control memory:** stores microprogram. **Microinstruction format:** control fields + next-address field.
- **Address sequencing:** increment microprogram counter or branch to next microinstruction; conditions select addresses.
- **Instruction cycle sub-cycles:** fetch, indirect, execute, interrupt; each broken into smaller steps driven by timing signals (T-states).

### CPU structure & functions
- **ALU:** arithmetic (add/sub/mul/div/increment) & logic (AND/OR/EXOR/compare/shift) operations.
- **Registers:** PC, IR (instruction register), MAR, MBR/DR, AC (accumulator), status/flags.
- **Instruction formats:** opcode + operands; fixed/variable length.
- **Addressing modes:** immediate, direct, indirect, register, register-indirect, indexed, relative, base.
- **Data transfer & manipulation instructions.**

### RISC vs CISC
| RISC | CISC |
|---|---|
| Few, simple, fixed-length instructions | Many, complex, variable-length |
| **Load/store architecture** | Ops on memory allowed |
| Large register set | Fewer registers |
| Hardwired control (fast) | Microprogrammed control |
| Pipeline-friendly, 1 cycle/instruction | Multi-cycle instructions |

### Pipelining & parallel processing
- Pipeline: overlap stages (Fetch, Decode, Execute, Memory, Writeback); improves **instruction throughput**.
- **Hazards:** structural, data (RAW), control/branch.
- **Parallel processing:** multiple units/processors (SIMD, MIMD; Flynn's classification).

---

## 4.2 Computer Arithmetic and Memory System

### Computer arithmetic
- **Signed number representation:** sign-magnitude, 1's complement, **2's complement** (standard).
- **Addition/subtraction:** in 2's complement; overflow detection via carry-in/out mismatch of sign bit.
- **Multiplication:** shift-and-add, **Booth's algorithm** (handles signed numbers, efficient with runs of 1s).
- **Division:** restoring & non-restoring.
- **Floating point:** sign + exponent + mantissa (IEEE 754: single 32-bit, double 64-bit); normalization.

### Memory hierarchy
- Registers → Cache → Main (RAM) → Secondary disk → Offline. (Speed ↓, Capacity ↑, Cost/bit ↓)

### Cache memory principles
- **Locality of reference:** temporal (reuse recently used) & spatial (nearby addresses).
- **Elements of cache design:**
  - **Cache size:** larger → higher hit ratio but cost/speed tradeoff.
  - **Mapping functions:**
    - **Direct mapping:** block → fixed line (`(block) mod lines`); fast, low hardware, misses on conflict.
    - **Fully associative:** any block anywhere (search all tags); flexible, most hardware.
    - **Set-associative:** compromise; block maps to a set of lines.
  - **Replacement algorithms:** LRU (commonly used), FIFO, random, optimal (Belady's — LRU/near).
  - **Write policy:** **write-through** (write to cache + memory, slower, consistent) vs **write-back** (write cache only, dirty bit, update memory on replacement).
  - **Number of caches:** L1/L2/L3, unified vs split (I/D).
- **Memory write ability & storage permanence:** RAM writeable/volatile; ROM non-writeable(mostly)/permanent.
- **Composing memory:** use smaller chips to build larger memory (address/data bus expansion) — e.g., 8K×8 from 2K×8 chips.

---

## 4.3 Input–Output Organization and Multiprocessors

### Peripheral devices & I/O modules
- I/O module contains registers, adapter logic, device interface; CPU communicates via **ports**.
- **Programmed I/O:** CPU polls device status — wastes CPU time.
- **Interrupt-driven I/O:** device interrupts CPU when ready — more efficient.
- **Direct Memory Access (DMA):** DMA controller handles bulk transfer between memory & I/O **without CPU**; CPU released by HOLD/HLDA; handshake in one bus cycle per transfer (cycle stealing).

### Multiprocessors
- **Characteristics:** multiple CPUs sharing memory/bus; higher throughput, reliability, fault tolerance.
- **Interconnection structures:** time-shared bus, multi-port memory, **crossbar switch**, multistage networks, hierarchical.
- **Inter-processor communication & synchronization:** shared memory (semaphores) and message passing.

---

## 4.4 Hardware–Software Design Issues on Embedded Systems

### Overview & classification
- **Embedded system:** dedicated computer system inside a larger system; constrained (power, cost, memory, real-time).
- **Classification** by:
  - **Performance/function:** general-purpose, real-time, standalone, networked.
  - **Complexity:** small (single 8-bit MCU), medium, complex (multi-core, RTOS).
  - **Timing:** **hard real-time** (deadline violation = failure; airbag), **soft real-time** (tolerable; video streaming).
  - **Safety:** safety-critical vs non-critical.

### Custom single-purpose processor design
- Dedicated hardware (datapath + controller) for one function; best performance, worst flexibility.
- **Design (FSM-Datapath):** requirements → algorithm (C-like) → FSM/DF (datapath + control FSM) → RT-level VHDL → gates.
- **Optimizing:** scheduling operations, resource sharing, balancing hardware vs time.
- **Basic architecture & programmer's view:** instruction set, registers, memory map. **Development environment:** cross-compiler, simulator, debugger, target + host.
- **Application-Specific Instruction-Set Processors (ASIPs):** programmable but tuned to application domain (DSPs); compromise between general-purpose and custom.

---

## 4.5 Real-Time Operating and Control Systems

### RTOS basics
- **Operating System Basics:** kernel, memory mgmt, file system, scheduling.
- **Task / Process / Thread:
  - **Task:** a unit of execution (in RTOS context).
  - **Process:** running program with own address space.
  - **Thread:** light-weight; threads of same process share address space.
- **Multiprocessing & multitasking:** multiple CPUs / concurrent tasks (single CPU, time share).

### Task scheduling
- **Schedulers:** preemptive (priority/highest ready runs) vs cooperative (task yields).
- **Algorithms:** Rate Monotonic (RM — static priority by period), **Earliest Deadline First (EDF — dynamic)**, Round Robin, priority-based.
- **Task synchronization:** semaphores, mutexes, **message queues, mailboxes**, event flags — prevent race conditions & priority inversion.
- **Device drivers:** software to control hardware devices; interrupt handlers.

### Control systems
- **Open-loop control:** no feedback; output not measured (washing machine timer). Simple, less accurate.
- **Closed-loop control:** feedback; sensor measures output, controller compares with setpoint (thermostat, cruise control). More accurate.
- PID controller: proportional + integral + derivative terms.

---

## 4.6 Hardware Description Language and IC Technology

### VHDL overview
- **VHDL = VHSIC Hardware Description Language** (VHSIC = Very High Speed Integrated Circuit).
- Files: **entity** (inputs/outputs/ports) + **architecture** (behavior).
  ```
  entity NAND2 is port (a,b: in bit; y: out bit); end;
  architecture beh of NAND2 is begin y <= a nand b; end;
  ```
- **Data representation:** `bit, boolean, std_logic ('0','1','Z','X','-')`, `integer`, `std_logic_vector` (bus).
- **Modeling styles:**
  - **Dataflow:** concurrent signal assignment (`y <= a and b;`) — combinational.
  - **Behavioral:** process + sequential statements (if/case) — registers/FSMs.
  - **Structural:** instantiate components (gates/chips).
- **Design of combinational logic in VHDL** (mux, decoder, adder) via concurrent or process.
- **Design of sequential logic** (D flip-flop, counters, FSM) via `process(clk)` + `rising_edge(clk)`.
- **Pipelining in VHDL:** registers between stages.

---

## Formula Box (Chapter 4 — must memorize)
- von Neumann = shared memory for program & data
- Fetch–Decode–Execute cycle; PC → next instruction
- RISC: load/store, hardwired, 1 cycle; CISC: microprogrammed
- Cache mappings: direct (line= block mod n), fully associative, set-associative
- Write-through vs write-back (dirty bit)
- 2's complement arithmetic, Booth's algorithm for multiply
- I/O modes: programmed (polling) < interrupt < DMA (no CPU)
- Multiprocessor topologies: bus, crossbar, multistage
- Hard vs soft real-time; EDF/RM scheduling
- Open-loop (no feedback) vs closed-loop (feedback, PID)
- VHDL: entity + architecture; dataflow vs behavioral (process) vs structural