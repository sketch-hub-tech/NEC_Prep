# NEC (Nepal Engineering Council) — Computer Engineering License Exam
## Complete Study Pack & Preparation Guide

---

## 1. Exam Snapshot (current format — NEC notice, Bhadra 2082 revision)

| Item | Detail |
|---|---|
| Exam name | General Registered Engineer Registration Examination (12th / ongoing batch) |
| Subject | Computer Engineering (syllabus code **ACtE**) |
| Mode | Paper-based, objective (MCQ) |
| Total questions | **100** |
| Marks | **100 (1 mark each)** |
| Pass mark | **50 (50%)** |
| Duration | **2 hours** |
| Negative marking | **None** — attempt ALL 100 questions |
| Question distribution | **10 questions per chapter × 10 chapters** |
| Sub-chapter rule | Each chapter has 6 sub-chapters; **at least 1 question guaranteed from each sub-chapter** (6 guaranteed per chapter, 4 more from anywhere in the chapter) |
| Official site | https://nec.gov.np |
| Online application | https://register.nec.gov.np/ |
| Exam frequency | At least twice per year (Kathmandu & Pokhara centers) |
| Registration fee | ~Rs. 2,500 (check current notice) |

> The older format (60 one-mark + 40 two-mark questions) was **replaced** by this one. Always check the latest notice on nec.gov.np before your exam date.

---

## 2. Full Official Syllabus (Computer Engineering — ACtE, 10 chapters)

### Chapter 1 — Concept of Basic Electrical & Electronics Engineering
1. Basic concepts: Ohm's law, voltage/current/power/energy, conducting & insulating materials, series-parallel circuits, star-delta conversion, Kirchhoff's laws, linear/non-linear & bilateral/unilateral, active/passive circuits
2. Network theorems: superposition, Thevenin, Norton, max power transfer; R-L, R-C, R-L-C circuits; resonance (AC series & parallel); active & reactive power
3. AC fundamentals: generation of AC, equations & waveforms, average/peak/rms values, 3-phase system
4. Semiconductor devices: diode characteristics, BJT configuration & biasing, small & large signal models, MOSFET & CMOS
5. Signal generators: oscillator principles, RC/LC/Crystal oscillators, waveform generators
6. Amplifiers: output stage classes (A, B, AB), biasing, power BJTs, push-pull, tuned amplifiers, op-amps

### Chapter 2 — Digital Logic & Microprocessor
1. Digital logic: number systems, logic levels, gates, Boolean algebra, SOP/POS, K-map
2. Combinational & arithmetic circuits: MUX, DEMUX, decoder, encoder, binary addition/subtraction, signed & unsigned numbers
3. Sequential logic: RS/gated/edge-triggered/master-slave flip-flops, registers, shift registers, async & sync counters
4. Microprocessor: internal architecture & features, assembly language programming
5. Microprocessor system: memory classification & hierarchy, I/O & memory interfacing, PPI, serial interface, standards, DMA & DMA controllers
6. Interrupts: interrupt, ISR, interrupt processing

### Chapter 3 — Programming Language & Its Applications (C/C++)
1. C basics: tokens, operators, formatted/unformatted I/O, control statements, loops, functions, recursion, arrays, strings
2. Pointers, structures, data files: pointer arithmetic, arrays & pointers, structure vs union, file I/O, sequential/random access
3. C++ constructs: namespace, function overloading, inline, default args, pass/return by reference, classes & objects, access specifiers, constructors/destructors, `this`, static members, const members, friend function/class
4. OOP features: operator overloading, data conversion, inheritance (single/multiple/multilevel/hybrid/multipath), constructors in inheritance
5. Virtual functions & file handling: virtual, dynamic binding, file open/close, error handling, stream class hierarchy, formatted/unformatted I/O, manipulators
6. Templates & exception handling: function/class templates, STL (containers, algorithms, iterators), try/catch/throw, multiple & rethrow, exceptions with args, exception specification

### Chapter 4 — Computer Organization & Embedded Systems
1. CPU & control unit: control memory, addressing sequencing, microinstruction format, ALU, instruction formats, addressing modes, RISC vs CISC, pipelining, parallel processing
2. Computer arithmetic & memory: arithmetic & logical ops, memory hierarchy, cache (principles, size, mapping, replacement, write policy), memory composition
3. I/O & multiprocessors: peripherals, I/O modules, modes of transfer, DMA, multiprocessor characteristics, interconnection structures, inter-processor communication & sync
4. Embedded systems: overview, classification, custom single-purpose processor design & optimization, basic architecture, dev environment, ASIPs
5. RTOS & control: OS basics, task/process/thread, multiprocessing/multitasking, scheduling, task synchronization, device drivers, open/closed-loop control
6. VHDL & IC technology: VHDL overview, data representation, combinational/sequential design in VHDL, pipelining in VHDL

### Chapter 5 — Computer Networks & Network Security
1. Intro & physical layer: networking models, protocols & standards, OSI & TCP/IP models, devices (hub/bridge/switch/router), transmission media
2. Data link layer: error detection/correction, flow control, multiple access protocols, ARP, Ethernet (802.3), Token Bus (802.4), Token Ring (802.5), CSMA/CD, WLANs, PPP
3. Network layer: IP addressing (classful), subnetting, routing protocols (RIP, OSPF, BGP), routing algorithms (shortest path, flooding, distance vector, link state), ARP/RARP/ICMP, IPv6
4. Transport layer: services, protocols, ports & sockets, connection establishment/release, flow control & buffering, multiplexing, congestion control
5. Application layer: HTTP/HTTPS, FTP, e-mail, DNS, P2P, socket programming, SNMP, packet tracer, Wireshark
6. Network security: security types, attacks, cryptography principles, RSA, digital signatures, PGP, SSL, IPSec/VPN, WEP, firewalls

### Chapter 6 — Theory of Computation & Computer Graphics
1. Finite automata: DFA/NDFA, equivalence, minimization, regular expressions, pumping lemma
2. Context-free languages: CFG, derivation trees, ambiguity, CNF, GNF, BNF, PDA, pumping lemma for CFL
3. Turing machines: notations, language recognizer, computing function, multiple tracks/tapes, NDTM, Church-Turing thesis, universal TM, complexity, intractability, reducibility
4. Graphics intro: hardware (display tech, raster/vector, processors), software & standards
5. 2D transforms: translation, rotation, scaling, reflection, shear, composite, viewing pipeline, clipping (Cohen-Sutherland, Liang-Barsky)
6. 3D transforms: 3D transformations, viewing pipeline, projections (orthographic, parallel, perspective)

### Chapter 7 — Data Structures & Algorithms, Database, Operating System
1. Data structures, lists, linked lists, trees: ADT, Big-O/omega/theta, stacks & queues, infix/postfix, linked lists (singly/doubly/circular), binary trees, AVL trees
2. Sorting, searching, graphs: insertion/selection/exchange/merge/radix/shell/heap sort, sequential/binary/tree search, hashing & collisions, graphs, Warshall, DFS/BFS, topological sort, MST (Prim's, Kruskal's), Dijkstra
3. Data models, normalization, SQL: abstraction & independence, E-R model, keys, normal forms (1NF-3NF, BCNF), functional dependencies, DDL/DML, views, relational algebra, query optimization
4. Transactions, concurrency & recovery: ACID, serializability, locking protocols, deadlock, failure classification, log-based recovery
5. OS & process management: OS evolution & types, process states, threads, scheduling, concurrency, critical section, semaphores/mutex, monitors, classical sync problems
6. Memory management, file systems, administration: swapping, virtual memory, demand paging, page replacement, file systems & allocation, user account mgmt

### Chapter 8 — Software Engineering & OOAD
1. Process & requirements: software characteristics & quality attributes, process models (Agile, V, Iterative, Prototype, Big Bang), functional/non-functional requirements, elicitation & validation
2. Design: design process & concepts, patterns, heuristics, architecture (client-server, distributed, real-time), component-based engineering
3. Testing, estimation, quality, config mgmt: unit/integration/system/acceptance testing, test case design, cost models (COCOMO), SQA, metrics, ISO standards, CMM/CMMI, change & version management
4. OO analysis: models, use cases, OO development cycle, UML, conceptual model, associations & attributes, system behavior
5. OO design: analysis→design, elaborating use cases, collaboration diagrams, class diagrams, patterns, visibility
6. OO implementation: design→code, class definitions, methods from collaboration diagrams, exception & error handling

### Chapter 9 — AI & Neural Networks
1. AI & agents: concept, history, applications, foundations, agent structure & properties, PEAS, agent types (reflexive, model-based, goal-based, utility-based), environments
2. Problem solving & search: state-space search, uninformed (DFS, BFS, DLS, IDS, bidirectional), informed (greedy, A*, hill climbing, simulated annealing), game playing, minimax, alpha-beta pruning
3. Knowledge representation: mappings, semantic nets, frames, propositional & predicate logic, resolution, Bayes' rule, Bayesian networks
4. Expert systems & NLP: expert system architecture, knowledge acquisition, NLP understanding/generation, machine vision, robotics
5. Machine learning: supervised/unsupervised/reinforcement, decision trees, Naive Bayes, fuzzy systems, genetic algorithms
6. Neural networks: biological vs artificial, McCulloch-Pitts neuron, activation functions, architectures, perceptron, gradient descent, delta rule, Hebbian, MLP, backpropagation, Hopfield networks

### Chapter 10 — Project Planning, Design & Implementation (Common)
1. Engineering drawings: standard sheets, dimensions, scale, line/orthographic/isometric/pictorial/sectional drawings
2. Engineering economics: cash flow, discount rate, time value of money, discounted payback, NPV, IRR, MARR, depreciation, taxation in Nepal
3. Project planning & scheduling: project lifecycle, bar charts, CPM, PERT, resource levelling & smoothing, monitoring & control
4. Project management: information systems, risk analysis, financing, tendering & contracts
5. Professional practice: environment & society, ethics, regulatory environment, OHS, roles of Nepal Engineers' Association (NEA)
6. Regulatory body: Nepal Engineering Council Act & Regulations

---

## 3. Scoring Strategy (per the revised pattern)

- **Every chapter = exactly 10 marks** → NO chapter is more important than another. Cover all 10.
- **Each chapter has 6 sub-chapters → at least 6 of your 10 marks per chapter are "guaranteed targets."** Know the key definition/fact from every one of the 60 sub-chapters.
- The 4 extra questions per chapter are drawn from anywhere — so read MCQ-style facts across each chapter too.
- **No negative marking**: answer every single question, even if you have to guess. Your floor is ~25%.
- Target **70+ / 100** for a comfortable margin. 50 passes, but aim higher for safety.

### Effort split per chapter (all 10 marks each, so split evenly):
- Ch 3 (C/C++) — practical; you'll score high. Spend medium.
- Ch 5, 7, 8 — heavy but high-yield factual. Spend most time.
- Ch 1, 2, 4, 6, 9 — textbook-recall + some formula. Medium.
- Ch 10 (common) — easiest marks; memorize NPV/IRR/CPM/PERT/NEC Act basics.

---

## 4. Curated Resources

### Official / syllabus
- NEC official site: https://nec.gov.np
- General Registration Exam Guidelines: https://nec.gov.np/page/general-registration-exam-guidelines
- Apply / check eligibility: https://register.nec.gov.np/
- Computer Engineering Syllabus (ACtE) PDF (the one embedded in this pack's facts): https://api.panaacademy.com/api/v2/resources/3/download/
- All NEC syllabi (mirror): https://www.panaacademy.com/resources

### Notes (free, syllabus-aligned)
- GitHub revision guide (chapter/sub-topic notes per official NEC syllabus): https://github.com/srijankarki07/Nepal-Engineering-License-Exam-Preparation-Guide

### Free MCQ / mock test platforms
- NEC Exam Helper — chapter-wise MCQs + Mock Tests + Computer Engineering **Past Year Questions 1/2/3**: https://necexamhelper.com/ (computer engineering tests: https://necexamhelper.com/mock-tests/computer-engineering)
- NEC License Preparation (15,000+ question bank, subject-wise + daily tests): https://neclicenseexam.dollarboysushil.com/
- NEC License quiz (full-length timed mock, 100-mark sets): https://nec-license.nepalidev.com.np/
- Gyanmark (free Nepali MCQ bank): https://gyanmark.com

### Coaching / books (optional, paid)
- Pana Academy (Maitighar, Kathmandu) — prep courses & mocks: https://www.panaacademy.com
- N.I.E. Nepal Institute of Engineering — "NEC License Booster" book (2500+ past questions) + 3000+ MCQ course: https://nienepal.com

---

## 5. Recommended Study Plan (6 weeks)

**Week 1** — Ch 1 (electrical/electronics) + Ch 2 (digital logic & microprocessor)
- Memorize: Kirchhoff laws, Thevenin/Norton, RMS vs avg, op-amp basics, K-map rules, flip-flop types, counters, 8085 registers/pins.
- Do 30–40 MCQs.

**Week 2** — Ch 3 (C/C++) + Ch 4 (COA & embedded)
- Practice: pointer/array questions, constructor/destructor ordering, virtual vs static binding; instruction formats, cache mapping, addressing modes, RISC vs CISC, DMA.
- Do 30–40 MCQs.

**Week 3** — Ch 5 (networks) — memorization-heavy
- OSI layers & devices, subnetting calcs, TCP/UDP, routing protocols, RSA + firewalls.
- Do 40–50 MCQs (this chapter is Q-dense).

**Week 4** — Ch 6 (TOC & graphics) + Ch 9 (AI & NN)
- Pumping lemma, CFG/CNF/GNF, TM variants; minimax, A*, Bayes, perceptron/backprop basics, agents & PEAS.
- Do 40–50 MCQs.

**Week 5** — Ch 7 (DSA, DBMS, OS) + Ch 8 (SE & OOAD)
- Complexity, sorting/searching, hashing; normalization & SQL; page replacement & scheduling; testing levels, COCOMO, CMMI, UML diagrams.
- Do 50–60 MCQs.

**Week 6** — Ch 10 (common: drawings, econ, PM, ethics, NEC Act) + full mocks
- Memorize engineer economics formulas (NPV, IRR, payback), CPM/PERT, NEC Act essentials.
- Attempt 3–5 full-length timed mocks; retest every wrong answer.

**Daily**: 1 hr chapters + 30 min MCQs. On weekends, one full mock.

---

## 6. Exam-Day Tips to Maximize Score

1. Bring: admit card + photo ID; be 30 min early (Kathmandu/Pokhara centers).
2. Work 3 passes: (a) answer all questions you know instantly; (b) solve the numerical ones; (c) guess everything else (no negative marking).
3. Pace: 100 questions / 120 min → about 1 min per question; flag tough ones and return.
4. Clean OMR marking — bubbled answers, no overstrikes.
5. Don't leave anything blank. A blind guess beats a blank.
6. Revise the 60 sub-chapter "one-liners" the night before (your guaranteed 60+ marks).

---

## 7. Next steps

1. Apply online at https://register.nec.gov.np/ when the next notice opens (watch nec.gov.np/notices).
2. Download the official syllabus PDF (link above) — this guide mirrors it exactly.
3. Start Week 1 today. Practice MCQs daily; the platform with past-year questions for Computer Engineering is the single highest-value resource.
4. Re-check the exam date/format notice before the exam — format was revised in Bhadra 2082 to the 100×1-mark scheme above.