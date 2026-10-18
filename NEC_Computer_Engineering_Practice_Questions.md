# NEC Computer Engineering — Practice Question Bank (60 Questions)
### 6 questions per chapter: exactly 1 from each sub-chapter, mirroring the real exam pattern (at least 1 question per sub-chapter).

Answers: bold option at the end of each question. Attempt all — no negative marking in the real exam.

---

## Chapter 1 — Electrical & Electronics Engineering

**1. (1.1)** Kirchhoff's Current Law states that at any node, the algebraic sum of:
- A. Voltages is zero
- B. Currents entering and leaving is zero
- C. Powers is zero
- D. Resistances is zero
> **Answer: B**

**2. (1.2)** Maximum power transfer theorem states that maximum power is delivered to the load when load resistance equals:
- A. Half of source resistance
- B. Twice the source resistance
- C. **Thevenin resistance of the network**
- D. Norton current divided by 2
> **Answer: C**

**3. (1.3)** The RMS value of a sinusoidal AC voltage with peak value Vm is:
- A. Vm
- B. Vm/2
- C. **Vm/√2**
- D. Vm/π
> **Answer: C**

**4. (1.4)** A BJT is a:
- A. Voltage-controlled device
- B. **Current-controlled device**
- C. Both voltage and current controlled
- D. Charge-controlled only
> **Answer: B** (A MOSFET is voltage-controlled.)

**5. (1.5)** An oscillator generates AC output from:
- A. AC input of higher frequency
- B. **DC supply only (no input signal)**
- C. Any sine input
- D. Magnetic field only
> **Answer: B**

**6. (1.6)** In a Class-B push-pull amplifier, crossover distortion occurs because:
- A. The power supply is too large
- B. **Both transistors are OFF near zero crossing**
- C. Biasing is too high
- D. Transformer coupling
> **Answer: B**

---

## Chapter 2 — Digital Logic & Microprocessor

**7. (2.1)** The decimal equivalent of binary 1101 is:
- A. 11
- B. 12
- C. **13**
- D. 14
> **Answer: C**

**8. (2.2)** A device that selects one of several data inputs based on select lines is a:
- A. Decoder
- B. Encoder
- C. **Multiplexer**
- D. Latch
> **Answer: C**

**9. (2.3)** The number of flip-flops required to build a 4-bit binary ripple counter:
- A. 2
- B. 3
- C. **4**
- D. 8
> **Answer: C**

**10. (2.4)** In the 8085 microprocessor, how many address lines are present?
- A. 8
- B. **16**
- C. 20
- D. 32
> **Answer: B** (16 address lines → 64 KB address space.)

**11. (2.5)** DMA transfers data without involving the:
- A. Memory
- B. I/O device
- C. **CPU**
- D. System bus
> **Answer: C**

**12. (2.6)** The routine executed when an interrupt occurs is called:
- A. Polling routine
- B. **Interrupt Service Routine (ISR)**
- C. Bootstrap loader
- D. Priority encoder
> **Answer: B**

---

## Chapter 3 — Programming (C/C++)

**13. (3.1)** In C, which loop guarantees at least one execution of the body?
- A. for loop
- B. while loop
- C. **do-while loop**
- D. All loops
> **Answer: C**

**14. (3.2)** `sizeof(struct)` in C generally returns:
- A. Sum of member sizes only
- B. **Size including padding bytes**
- C. Always 0
- D. Smallest member size
> **Answer: B**

**15. (3.3)** A constructor without any parameters is called:
- A. Copy constructor
- B. Parameterized constructor
- C. **Default constructor**
- D. Static constructor
> **Answer: C**

**16. (3.4)** In C++, the operator used to overload unary operator `++` is declared as a member function with:
- A. One argument
- B. **Zero arguments**
- C. Two arguments
- D. Three arguments
> **Answer: B** (member overload of unary takes no explicit args; binary takes one.)

**17. (3.5)** Dynamic binding in C++ is achieved through:
- A. Method overloading
- B. **Virtual functions**
- C. Operator overloading
- D. Inline functions
> **Answer: B**

**18. (3.6)** Which STL container offers the fastest random access and fixed size?
- A. list
- B. deque
- C. **vector (array-like)**
- D. map
> **Answer: C**

---

## Chapter 4 — Computer Organization & Embedded Systems

**19. (4.1)** The addressing mode where the operand is part of the instruction itself is:
- A. Direct addressing
- B. Register addressing
- C. **Immediate addressing**
- D. Indirect addressing
> **Answer: C**

**20. (4.2)** In direct-mapped cache, the block is placed to a cache line determined by:
- A. Replacement algorithm
- B. **Mapping function (modulo of block number)**
- C. Write policy
- D. Cache size only
> **Answer: B**

**21. (4.3)** Which I/O transfer mode gives the I/O device direct access to memory?
- A. Programmed I/O
- B. Interrupt-driven I/O
- C. **DMA**
- D. Polling
> **Answer: C**

**22. (4.4)** An embedded system that must meet hard timing constraints is called:
- A. General-purpose system
- B. **Real-time embedded system**
- C. Batch system
- D. Interrupt-free system
> **Answer: B**

**23. (4.5)** A process-based OS feature that pairs data with a thread of execution is:
- A. Far thread
- B. **Process/thread**
- C. DMA channel
- D. Vector table
> **Answer: B**

**24. (4.6)** VHDL is a:
- A. Assembly language
- B. **Hardware Description Language**
- C. High-level programming only
- D. Query language
> **Answer: B**

---

## Chapter 5 — Computer Networks & Security

**25. (5.1)** Which OSI layer uses routers and logical addressing (IP)?
- A. Transport
- B. Data link
- C. **Network**
- D. Session
> **Answer: C**

**26. (5.2)** IEEE 802.3 standard defines:
- A. Token Ring
- B. **Ethernet (CSMA/CD)**
- C. Wireless LAN
- D. ATM
> **Answer: B**

**27. (5.3)** The default subnet mask of a Class-B IP address is:
- A. 255.0.0.0
- B. **255.255.0.0**
- C. 255.255.255.0
- D. 255.255.255.255
> **Answer: B**

**28. (5.4)** Which transport-layer protocol is connection-oriented and reliable?
- A. UDP
- B. **TCP**
- C. IP
- D. ICMP
> **Answer: B**

**29. (5.5)** The protocol that resolves domain names to IP addresses is:
- A. ARP
- B. **DNS**
- C. DHCP
- D. FTP
> **Answer: B**

**30. (5.6)** In RSA cryptography, the public key consists of:
- A. Private exponent only
- B. **Modulus n and public exponent e**
- C. Same as private key
- D. Random number pair
> **Answer: B**

---

## Chapter 6 — Theory of Computation & Computer Graphics

**31. (6.1)** Which language does a finite automaton recognize?
- A. Context-free language
- B. **Regular language**
- C. Recursively enumerable only
- D. All of the above
> **Answer: B**

**32. (6.2)** A grammar is ambiguous if:
- A. It has unreachable symbols
- B. **A string has more than one parse tree**
- C. It has epsilon productions
- D. It is not in CNF
> **Answer: B**

**33. (6.3)** A Turing Machine that simulates all other Turing Machines is called:
- A. Deterministic TM
- B. **Universal Turing Machine**
- C. Multi-tape TM
- D. Halting TM
> **Answer: B**

**34. (6.4)** Raster-scan displays draw images using:
- A. Random electron beam
- B. **Horizontal scan lines (pixels)**
- C. Laser projection only
- D. Ink jets
> **Answer: B**

**35. (6.5)** The Cohen–Sutherland algorithm is used for:
- A. Filling polygons
- B. **Line clipping**
- C. Hidden surface removal
- D. Anti-aliasing
> **Answer: B**

**36. (6.6)** In which projection do parallel lines remain parallel (no vanishing point)?
- A. Perspective projection
- B. **Orthographic/parallel projection**
- C. Oblique curve
- D. None
> **Answer: B**

---

## Chapter 7 — DS/Algorithm, DBMS, OS

**37. (7.1)** Time complexity of binary search on sorted array of n elements:
- A. O(n)
- B. O(n log n)
- C. **O(log n)**
- D. O(1)
> **Answer: C**

**38. (7.2)** Quick sort has worst-case time complexity:
- A. O(n log n)
- B. **O(n²)**
- C. O(log n)
- D. O(1)
> **Answer: B**

**39. (7.3)** The relation in 3NF but not BCNF has the anomaly because:
- A. Every determinant is a candidate key
- B. **A non-key attribute determines another attribute (not fully key-dependent determinant exists that isn't a superset key)**
- C. No functional dependencies exist
- D. It is not atomic
> **Answer: B**

**40. (7.4)** The "A" in ACID properties stands for:
- A. Availability
- B. **Atomicity**
- C. Accuracy
- D. Abstraction
> **Answer: B**

**41. (7.5)** Which page replacement algorithm suffers from Belady's anomaly?
- A. LRU
- B. Optimal
- C. **FIFO**
- D. Clock
> **Answer: C**

**42. (7.6)** The shortest job next (SJN) scheduling minimizes:
- A. Throughput
- B. **Average waiting time**
- C. CPU utilization
- D. Response time always
> **Answer: B**

---

## Chapter 8 — Software Engineering & OOAD

**43. (8.1)** In the V-Model, testing is:
- A. Done only at the end
- B. **Planned in parallel with each development phase**
- C. Not included
- D. Only unit testing
> **Answer: B**

**44. (8.2)** Client-server architecture is a type of:
- A. Data structure
- B. **Software/system architecture**
- C. Programming language
- D. Testing tool
> **Answer: B**

**45. (8.3)** COCOMO is a:
- A. Testing framework
- B. **Cost estimation model**
- C. Configuration tool
- D. Design pattern
> **Answer: B**

**46. (8.4)** Use cases describe:
- A. Class attributes
- B. **Interactions between actor and system**
- C. Database schema
- D. Compile errors
> **Answer: B**

**47. (8.5)** The UML diagram that shows the static structure of classes and relationships is:
- A. Sequence diagram
- B. **Class diagram**
- C. Activity diagram
- D. State diagram
> **Answer: B**

**48. (8.6)** Exception handling in OO languages helps:
- A. Increase code speed
- B. **Gracefully handle runtime errors**
- C. Remove classes
- D. Hide data only
> **Answer: B**

---

## Chapter 9 — AI & Neural Networks

**49. (9.1)** In AI, the PEAS description of an agent includes:
- A. Program, Error, Action, State
- B. **Performance, Environment, Actuators, Sensors**
- C. Process, Execution, Accuracy, Speed
- D. None of these
> **Answer: B**

**50. (9.2)** The A* search algorithm uses the evaluation function:
- A. f(n) = g(n)
- B. f(n) = h(n)
- C. **f(n) = g(n) + h(n)**
- D. f(n) = g(n) - h(n)
> **Answer: C**

**51. (9.3)** Bayes' theorem is used in AI for:
- A. Search pruning
- B. **Probabilistic reasoning / updating belief**
- C. Sorting data
- D. Compiling code
> **Answer: B**

**52. (9.4)** The main components of an expert system include knowledge base and:
- A. **Inference engine**
- B. Compiler
- C. Kernel
- D. Buffer
> **Answer: A**

**53. (9.5)** A decision tree in machine learning is a:
- A. Clustering method
- B. **Supervised inductive learning model**
- C. Reinforcement policy only
- D. Neural type
> **Answer: B**

**54. (9.6)** In a perceptron, weights are updated using:
- A. Sorting
- B. **Gradient descent / delta rule**
- C. Hashing
- D. Polling
> **Answer: B**

---

## Chapter 10 — Project Planning, Economics, Professional Practice

**55. (10.1)** An isometric drawing shows an object with all three axes inclined at how many degrees?
- A. 30°
- B. 45°
- C. **120° apart from each other (each at 120°)**
- D. 60°
> **Answer: C**

**56. (10.2)** If NPV of a project > 0, the project is:
- A. Rejected
- B. **Accepted (returns above required rate)**
- C. Break-even
- D. None
> **Answer: B**

**57. (10.3)** PERT analysis is useful when activity durations are:
- A. Certain
- B. **Uncertain (probability-based)**
- C. Zero
- D. All same
> **Answer: B**

**58. (10.4)** A contract-based bidding document inviting suppliers to quote is called:
- A. Work order
- B. **Tender**
- C. Timesheet
- D. Ledger
> **Answer: B**

**59. (10.5)** The engineering body representing engineers' profession in Nepal is:
- A. IOE
- B. **Nepal Engineers' Association (NEA)**
- C. TSC
- D. NEB
> **Answer: B**

**60. (10.6)** The Nepal Engineering Council was established under which Act?
- A. Civil Service Act
- B. **Nepal Engineering Council Act, 2055 (1999)**
- C. Companies Act
- D. Education Act
> **Answer: B**

---

### How to use this bank
- These are *sample* style questions. Drill 500+ more on the free platforms in the Study Guide (especially NEC Exam Helper's chapter tests and Computer **Past Year Questions 1/2/3**).
- Retest every question you got wrong — the real exam repeats similar concept patterns every year.