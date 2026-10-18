# Chapter 7 — Data Structures & Algorithm, Database System and Operating System
*(Code ACtE07 — 10 questions)*

---

## 7.1 Data Structures, Lists, Linked Lists and Trees

### Fundamentals
- **Data type:** set of values + operations (int, char, float).
- **Data structure:** organized way to store data (arrays, lists, trees, graphs).
- **Abstract Data Type (ADT):** logical description of operations without implementation (Stack ADT → array/linked implementation).
- **Time & space complexity / Big-O/Ω/Θ:**
  - **O(f(n)):** upper bound (worst-case).
  - **Ω(f(n)):** lower bound (best-case).
  - **Θ(f(n)):** tight bound (average/good case).
  - Common: O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ).

### Linear data structures

**Stack (LIFO — Last In First Out):**
- Operations: `push`, `pop`, `peek/top`, isEmpty, isFull.
- Applications: function call stack, expression evaluation, undo, recursion.
- **Infix → Postfix conversion** (using stack, operator precedence, parentheses).
- **Postfix evaluation:** push numbers, pop two and apply operator when operator seen.

**Queue (FIFO — First In First Out):**
- Operations: `enqueue` (rear), `dequeue` (front), isEmpty, isFull.
- Variants: circular queue (uses mod), priority queue (dequeue highest priority), double-ended queue (deque).
- Array implementation vs linked implementation.

**Array implementation of lists:** contiguous; O(1) access by index; O(n) insert/delete.

### Linked lists
- **Dynamic implementation** of lists (no fixed size, non-contiguous).
- Each node: **data + pointer** to next node.
- **Types:**
  - **Singly:** →NULL
  - **Doubly:** data + next + prev (two pointers; insert/delete needs handling both directions)
  - **Circular:** last → first.
- **Basic operations:** create (initialize head = NULL), insert (beginning/end/position), delete (beginning/end/position), search, traverse, length.
- Time: O(n) search; O(1) insert/delete at ends if pointer known; insert at beginning O(1).
- Doubly linked lists applications: browsers (back/forward), music playlists.

### Trees
- **Tree:** hierarchical, one root, edges between parent-children; **n nodes, n-1 edges.**
- **Binary tree:** each node has ≤ 2 children (left, right).
- **Tree terminology:**
  - Root, internal, leaf (terminal) nodes.
  - Height = length of longest root-to-leaf path (root height = 0 or 1 depending on convention).
  - Level, depth, degree of node, degree of tree (max degree).
- **Binary tree operations:** search, **insertion, deletion** (deletion replaces with in-order successor/predecessor or last node).
- **Tree traversals:**
  - **Pre-order (NLR):** root, left, right (used for copy/prefix).
  - **In-order (LNR):** left, root, right (**for BST: gives sorted order**).
  - **Post-order (LRN):** left, right, root (for deletion/prefix evaluation).
- **AVL balanced tree:** self-balancing BST; height diff between children ≤ 1; rotations (LL, RR, LR, RL) to maintain balance after insert/delete.

---

## 7.2 Sorting, Searching and Graphs

### Sorting algorithms
| Algorithm | Type | Average | Worst | Stable? | Notes |
|---|---|---|---|---|---|
| **Insertion** | comparison | O(n²) | O(n²) | Yes | good for nearly sorted, small n |
| **Selection** | comparison | O(n²) | O(n²) | No | finds min each pass |
| **Exchange (Bubble)** | comparison | O(n²) | O(n²) | Yes | swaps adjacent, fastest if already sorted (optimized) |
| **Merge** | comparison | O(n log n) | O(n log n) | Yes | divide & merge, stable |
| **Quick** | comparison | O(n log n) | O(n²) | No | partitioning, in-place, fastest average |
| **Heap** | comparison | O(n log n) | O(n log n) | No | max-heap; sort tree |
| **Radix** | non-comparison | O(nk) | O(nk) | Yes | sort by digits (base-b), k digits |
| **Shell** | comparison | O(n log²n) | — | No | insertion sort with diminishing gaps |

- **Internal vs external sorting:** internal in RAM; external (tape/disk) for large data, multi-pass merge.
- **Big-O notation for algorithms** — choose fastest appropriate for situation; **selection sort** always O(n²) comparisons regardless of data.

### Search techniques
- **Sequential/linear search:** O(n); no order required; first occurrence.
- **Binary search:** O(log n) on **sorted** array; compare with mid; fast but requires sorted data.
- **Tree search:** BST O(h) where h = tree height.

### Hashing
- **Hash function:** maps key → table index (bucket). Good hash: uniform distribution, minimal collisions.
- **Collision resolution:**
  - **Open addressing:** linear probing, quadratic probing, double hashing.
  - **Separate chaining:** linked list per bucket.
  - **Rehashing** (resize + rehash).
- Load factor = n/m (elements/slots); higher → more collisions.

### Graphs
- **Undirected graph:** edges have no direction. **Directed graph (digraph):** edges have direction.
- **Representation:**
  - **Adjacency matrix:** n×n matrix; O(1) edge lookup; O(n²) space.
  - **Adjacency list:** per-vertex list of neighbors; O(|V|+|E|) space; better for sparse.
- **Transitive closure of graph** matrix (reachability): all pairs connected — **Warshall's algorithm** (O(n³)).
- **Depth First Traversal (DFS):** stack (or recursion); explores as deep as possible first.
- **Breadth First Traversal (BFS):** queue; explores neighbors first.
- **Topological sorting** (DAG only): linear order such that for all u→v, u before v.
  - **DFS-based:** reverse of DFS finishing order.
  - **BFS-based (Kahn's):** repeatedly remove vertices with indegree 0.
- **Minimum spanning trees (MST):**
  - **Prim's:** grow MST from a vertex; add lightest edge from tree to outside; O(E log V).
  - **Kruskal's:** sort all edges; add edges in increasing order if no cycle forms (use union-find).
  - **Round-Robin** — (not a standard MST algorithm in textbooks; likely refers to a variant; focus on Prim/Kruskal).
- **Shortest-path algorithms:**
  - **Greedy:** for positive-edges graphs (Dijkstra's — greedy relaxation; O((V+E)log V) with heap).
  - **Dijkstra's algorithm:** start at source; greedily settle nearest unvisited; update neighbors; no negative weights.

---

## 7.3 Data Models, Normalization and SQL

### Data abstraction & independence
- **Logical level:** what data, relationships. **Physical level:** how stored. **External level:** user views.
- **Data independence:** changing logical schema without altering physical (logical independence) or vice versa (physical independence).

### Schema and instances
- **Schema:** logical description of database (static). **Instance:** state at a particular time (dynamic snapshot).

### E-R model
- **Entity** (real-world object), **Attribute** (properties), **Relationship** (association between entities).
- **Entity sets, relationship sets.**
- **Keys:** super key, candidate key, **primary key** (minimal super key), foreign key.
- **Strong vs weak entity sets** (weak: identified by owner entity + partial key).
- **E-R Diagram:** rectangles (entities), diamonds (relationships), ovals (attributes), double ovals (derived/multivalued).

### Functional dependencies & constraints
- **Functional dependency (FD):** A → B (A determines B).
- **Keys** are minimal sets of attributes determining all attributes.
- **Integrity constraints:** entity integrity (no PK null), referential integrity (FK matches PK), domain constraints.

### Normal forms
| Form | Condition | What it eliminates |
|---|---|---|
| **1NF** | Atomic values (no repeating groups, no lists) | Repeating groups |
| **2NF** | In 1NF + **no partial dependency** (non-key depends on whole composite PK) | Partial dependency |
| **3NF** | In 2NF + **no transitive dependency** (non-key → non-key) | Transitive dependency |
| **BCNF** | Every **determinant is a candidate key** (not just non-key) | All remaining anomalies from dependencies |

- **Normalization process:** identify FDs → candidate keys → eliminate dependencies by decomposing into BCNF/3NF.

### SQL basics
- **DDL (Data Definition Language):** `CREATE TABLE, ALTER TABLE, DROP TABLE, CREATE INDEX`.
- **DML (Data Manipulation Language):** `INSERT, UPDATE, DELETE, SELECT`.
- `SELECT * FROM table WHERE condition GROUP BY col HAVING condition ORDER BY col;`
- **Joins:** INNER JOIN, LEFT/RIGHT/FULL OUTER JOIN, NATURAL JOIN, Cartesian product (CROSS).
- **Views:** virtual tables defined by query (`CREATE VIEW v AS SELECT ...`); simplify, security.
- **Assertions and triggers:** assertions = global constraints; triggers = event-driven actions on table.

### Relational algebra
- `σ (select), π (project), ∪ (union), − (set diff), × (cartesian), ⋈ (natural join), ⟕ LEFT JOIN, ∩ (intersection)`.
- Query operations → cost estimation → optimization (choose join order, choose indexes) → decomposition.

---

## 7.4 Transaction Processing, Concurrency Control and Crash Recovery

### ACID properties
- **A**tomicity: transaction fully committed or fully rolled back.
- **C**onsistency: DB goes from one consistent state to another.
- **I**solation: concurrent transactions are isolated; intermediate states not visible.
- **D**urability: committed data persists even after crash.

### Concurrency & serializability
- **Concurrent execution:** interleaved operations from multiple transactions (improves throughput).
- **Serializability:** schedule is equivalent to some serial execution. **Conflict-serializable** if graph (precedence graph) has no cycles.
- **Serial execution:** simplest but slowest.

### Lock-based protocols
- **Shared (S) lock** for reads; **Exclusive (X) lock** for writes.
- **Two-phase locking (2PL):** growing phase (acquire locks) then shrinking phase (release); guarantees conflict-serializability.
- **Deadlock:** circular waiting; prevention (wait-for, timeout, priorities), detection (wait-for graph), recovery (abort victim).
- **Lock upgrades/downgrades.**

### Recovery and atomicity
- **Failure classification:** transaction, system, media (disk).
- **Log-based recovery (WAL — Write-Ahead Logging):**
  - **Before image** (old value) & **after image** (new value) logged.
  - To undo: restore before image. To redo: restore after image.
  - Checkpointing; for serial vs parallel logs, parallel logs (with time stamps) are more useful.
  - **Recovery at restart:** undo uncommitted, redo committed (as in ARIES).

---

## 7.5 Operating System and Process Management

### OS basics
- **OS:** system software managing resources; interface between user/hardware. **Kernel:** core; system calls interface.
- **Types of OS:** batch, multitasking (time-sharing), real-time, distributed, networked, embedded, multi-user, multiprocessor.
- **OS structure:** monolithic, modular, **microkernel** (small kernel, services in user space), layered.
- **OS services:** process mgmt, memory mgmt, file mgmt, I/O mgmt, security, networking.

### Processes and threads
- **Process:** program in execution with own address space (PCB = process control block: PID, state, registers, priority, memory map).
- **Process states:** new, ready, running, waiting (blocked), terminated. Transitions: ready→running (scheduler), running→waiting (I/O), waiting→ready (I/O complete).
- **Thread:** light-weight process; shares address space/files; own stack/register. **Advantage:** concurrency, less overhead, better communication.
- **User threads vs kernel threads.**

### Scheduling
- **Schedulers:** long-term (job), short-term (CPU/dispatcher), medium-term.
- **Scheduling algorithms:**
  - **FCFS (First-Come):** simple, convoy effect (long process blocks short ones).
  - **SJF (Shortest Job First):** minimal average waiting time (optimal for avg wait); **preemptive version = SRTF**.
  - **Priority scheduling:** may starve low-priority; aging (increasing priority over time) solves starvation.
  - **Round Robin:** quantum time slice; fair but overhead; small quantum → context switch overhead; large quantum → FCFS.
  - **Multilevel feedback queue:** multiple queues with different priorities/quantums; dynamic.
- **Performance metrics:** throughput, turnaround time, waiting time, response time.

### Concurrency
- **Critical section:** code accessing shared resources; **race condition:** outcome depends on timing.
- **Mutual exclusion:** only one process in critical section at a time.
- **Peterson's solution:** two-process mutual exclusion using flags.
- **Hardware solutions:** test-and-set, compare-and-swap (atomic).
- **Semaphores:** integer; **P(S)** (wait/decrement, block if ≤0); **V(S)** (signal/increment, wake). Types: binary (0/1), counting.
- **Mutex:** binary semaphore (owned by thread that locked it).
- **Message passing:** processes communicate via messages (no shared memory).
- **Monitors:** higher-level abstraction; one process in monitor at a time; condition variables.
- **Classical synchronization problems:**
  - Producer-Consumer (bounded buffer),
  - Readers-Writers,
  - Dining Philosophers (deadlock with naive solution; odd philosopher picks left first).

---

## 7.6 Memory Management, File Systems and System Administration

### Memory management
- **Address mapping:** logical (virtual) → physical address.
- **Swapping:** swap entire process between memory and disk; done by OS.
- **Managing free space:** bitmap, free list, first-fit, best-fit, worst-fit, buddy system.

### Virtual memory
- **Concept:** use disk as extension of RAM; process only partly in memory → **demand paging**.
- **Demand paging:** page loaded only when referenced (page fault → trap to OS → fetch from disk).
- **Page replacement algorithms** (replace a page when memory is full):
  - **Optimal (Belady):** replace page not used for longest future; impossible to implement, theoretical.
  - **FIFO:** first in first out; **suffers Belady's anomaly** (more frames → more faults).
  - **LRU (Least Recently Used):** replace least recently used; good approximation of optimal; no Belady's anomaly.
  - **Clock/Second Chance:** near-LRU, efficient; FIFO with check bits.
- **Segmentation:** logical division of process into segments (code, data, stack); each segment has base + limit; external fragmentation.

### File systems
- **File:** named collection of data; directory structure.
- **Directory/file paths:** absolute vs relative; tree structure.
- **File system implementation:** inode/directory entries, allocation methods:
  - **Contiguous allocation:** simple, fast, external fragmentation.
  - **Linked allocation:** no external fragmentation, slow access, FAT.
  - **Indexed allocation:** index block (direct pointers + multi-level).
- **Impact of allocation policy on fragmentation.**
- **Mapping file blocks on disk platter** (physical location; physical/logical views).
- **File system performance:** caching, buffering, read-ahead, disk scheduling (FCFS, SSTF, SCAN/Elevator).
- **File systems:** FAT, NTFS, ext2/ext3/ext4.

### System administration
- **Administration tasks:** install OS, manage users/groups, backup/restore, performance monitoring, log management.
- **User account management:** accounts, permissions, authentication (passwords, PAM).
- **Startup procedures:** BIOS/UEFI → bootloader (GRUB) → kernel load → init/systemd → services.
- **Shutdown procedures:** orderly → save state, unmount, power off.

---

## Formula Box (Chapter 7 — must memorize)
- Stack LIFO (push/pop); Queue FIFO (enqueue/dequeue)
- In-order BST = sorted output; Pre-order: root first; Post-order: leaves first
- AVL tree: balance factor |height| ≤1; rotate to fix
- Sorting best-case for optimized bubble/insertion: O(n); worst: O(n²); quicksort avg O(n log n)
- Binary search: O(log n), needs sorted data
- Hashing load factor = n/m; collision = chaining/open addressing
- Prim/Kruskal = MST; Dijkstra = shortest path (no negative edges); Warshall = transitive closure
- E-R: entity=rectangle, attribute=oval, relationship=diamond; PK, FK
- 1NF atomic; 2NF no partial; 3NF no transitive; BCNF every determinant is candidate key
- SQL: σ=select, π=project, ⋈=natural join
- ACID = Atomicity, Consistency, Isolation, Durability
- 2PL guarantees conflict-serializable schedules; deadlock via wait-for graph
- Process states: new/ready/running/waiting/terminated; SJF avg wait optimal; Belady = FIFO anomaly
- Semaphore P (decrement) V (increment); dining philosopher problem
- LRU page replacement = no Belady's anomaly; Optimal = best possible
- Page fault: page not in memory → trap → disk fetch; demand paging