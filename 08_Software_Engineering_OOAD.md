# Chapter 8 — Software Engineering and Object-Oriented Analysis & Design
*(Code ACtE08 — 10 questions)*

---

## 8.1 Software Process and Requirements

### Software characteristics & quality
- **Software characteristics:** developed/engineered, not manufactured; wears out no hardware, but **deteriorates** (maintenance issues); complex (large size/abstraction layers), **non-tangible**, cost of change is high.
- **Software quality attributes:** functionality, reliability, usability, efficiency, maintainability, portability. **Quality = conformance to explicit requirements + implicit characteristics.**

### Software process models
| Model | Description | When to use |
|---|---|---|
| **Waterfall** | Sequential phases (requirements→design→code→test→maintenance); no going back | Simple, well-defined requirements |
| **V-Model** | Development phases each have a **test counterpart** in parallel (verify & validate early) | Safety-critical, regulated |
| **Incremental** | Deliver in increments; partially works early | Large systems, needs early use |
| **Prototyping** | Build quick model; get feedback; refine | Requirements unclear, UI-heavy |
| **Spiral** | Repeated cycle: plan→risk→build→evaluate; risk-driven | Large risky projects |
| **Agile (XP, Scrum, Kanban)** | Iterative/incremental; small sprints (2-4 weeks); adaptive; customer collaboration | Evolving requirements, fast delivery |
| **Big Bang** | No process; code and hope | Very small (hobby) projects |

- **Iterative model:** repeated cycles through development.
- **CASE tools:** Computer-Aided Software Engineering tools automate (design, code generation, testing).

### Requirements
- **Functional requirements:** WHAT the system must do (features, inputs/outputs).
- **Non-functional requirements:** HOW well it performs (performance, security, usability, portability, etc.).
- **User requirements:** high-level, stakeholder view.
- **System requirements:** detailed, technical specifications.
- **Interface requirements:** how system interacts with users, other systems.
- **Software requirements document (SRS):** complete, consistent, verifiable, non-ambiguous description of requirements.

### Requirements process
- **Elicitation:** gather from stakeholders (interviews, workshops, observation, surveys, document analysis).
- **Analysis & modeling:** resolve conflicts, organize requirements; use case models, prototypes.
- **Specification:** write SRS.
- **Validation & management:** check for completeness, consistency, no ambiguity; manage changes via requirements traceability matrix.

---

## 8.2 Software Design

### Design process & concepts
- **Design process:** high-level → low-level (architecture → component → module → interface).
- **Design concepts:** **abstraction**, **modular decomposition**, **information hiding**, **cohesion (strong = good)**, **coupling (loose = good)**, separation of concerns.
- **Modular decomposition styles:** pipe-and-filter, hierarchical, object-oriented, database-centered.
- **Control styles:** sequential, parallel, synchronization, event-driven, client-server.

### Design patterns
- Recurring design solutions to common problems: **Creational** (Factory, Singleton), **Structural** (Adapter, Facade), **Behavioral** (Observer, Strategy).
- **Design heuristic:** evaluate design (strength of cohesion/weakness of coupling).

### Architectural design decisions
- Choice based on: functionality, quality attributes (scalability, availability, security, performance), and constraints.
- **System organization:** decomposition into subsystems and their interactions.

### Architectural styles
- **Multiprocessor architecture**
- **Client-server architectures:** 2-tier, 3-tier (client → app server → DB server); thin/fat clients.
- **Distributed object architectures:** CORBA, .NET remoting, RMI.
- **Inter-organizational distributed computing:** web services, microservices.
- **Real-time software design:** priority-based, deterministic timing, use of RTOS.
- **Component-based software engineering (CBSE):** reusable components; component interface contract.

---

## 8.3 Software Testing, Cost Estimation, Quality Management and Configuration Management

### Testing levels
| Level | What is tested | Performed by |
|---|---|---|
| **Unit testing** | Individual module/function | Developers |
| **Component/module testing** | Single component | Testers/developers |
| **Integration testing** | Combined modules | Testers |
| **System testing** | Entire system | Test team |
| **Acceptance testing** | Meets user requirements | Customer/end users |

- **Testing types:** white-box (internal structure known: statement/decision/condition coverage), black-box (external: input/output, functional), gray-box.
- **Non-functional testing:** performance/load/stress testing, security testing, usability, reliability.
- **Test case design:** ID, inputs, expected outputs, actual results, pass/fail.
- **Test automation:** scripted tools (Selenium, JUnit, PHPUnit) to run tests repeatedly.

### Cost estimation
- **Algorithmic cost models:**
  - **LOC (Lines of Code):** effort = a × (LOC)^b (COCOMO: b ≈ 1.0–1.4).
  - **Function Points (FP):** based on user functionality (inputs/outputs/queries/files/interfaces).
  - **COCOMO (COnstructive COst MOdel):** uses KLOC + cost drivers → effort in person-months; COCOMO II (updated).
- **Project duration & staffing:** related to effort but not linear (Brooks' law: adding people late makes project slower).

### Software quality assurance (SQA)
- **SQA:** systematic activities to ensure quality throughout development.
- **Formal technical reviews (FTR):** inspections, walkthroughs, code reviews; find defects early.
- **Formal approaches to SQA:** mathematical proofs, Z notation.
- **Statistical quality control:** Pareto analysis, control charts.
- **Metrics for analysis/design:** cyclomatic complexity, cohesion/coupling measures.
- **ISO standards:** **ISO 9001/9000** (quality management), ISO 12207 (software lifecycle).
- **CMM/CMMI:** Capability Maturity Model/Integration (CMMI replaces CMM) — 5 maturity levels:
  1. Initial (no process)
  2. Managed (project level)
  3. Defined (org level)
  4. Quantitatively managed
  5. Optimizing (continuous improvement)
- **SQA plan:** documented quality activities for a project.

### Configuration management
- **Configuration management (CM):** controls changes to software artifacts.
  - **Identification:** label all config items (CI).
  - **Version control:** tracks versions, branching, merging.
  - **Change management:** request → evaluation → approval/rejection → implementation.
  - **Release management:** build, test, release process.
- **CASE tools for CM:** Git, SVN, TFS, ClearCase, etc.

---

## 8.4 Object-Oriented Fundamentals and Analysis

### OOAD process
- **OO development cycle:** requirements → analysis → design → implementation → testing → maintenance.

### Use cases
- **Use case:** interaction between actor (external entity) and system achieving a goal.
- Use case diagram: actors, use cases, relationships (`<<include>>`, `<<extend>>`, generalization).
- Use case describes: primary success scenario + extensions/alternative flows.

### UML (Unified Modeling Language)
- UML diagrams:
  - **Structure:** class, object, component, deployment, package, composite structure.
  - **Behavior:** use case, sequence, communication, activity, state machine.

### Building conceptual model
- **Identify classes/entities** from requirements; **nouns → candidate classes**.
- **Adding associations** (relationships between classes): binary, n-ary, aggregation (part-of), composition (strong ownership, lifecycle-dependent).
- **Adding attributes** (properties) and **operations/methods**.
- **Representation of system behavior:** use case interactions, scenarios, state machines.

---

## 8.5 Object-Oriented Design

### Analysis to Design transition
- Transform analysis model to design model; define system architecture, detailed class structure, and behavior.

### Describing and elaborating use cases
- Detailed descriptions of each use case (main flow, alternative flows); refine with interaction diagrams.

### Collaboration diagrams (communication diagrams)
- Show objects and message-passing with links; emphasis on **structural organization** of objects and relationships (vs sequence diagram which is time-ordered).

### Objects and patterns
- Identification of design objects from analysis; apply appropriate design patterns to solve recurring design problems.

### Determining visibility
- Which attributes/methods are visible to which classes: **public, protected, private**; manages encapsulation.

### Class diagrams
- Show classes, attributes, operations, relationships (association, aggregation, composition, inheritance, dependency); multiplicities (0..1, 1, *, 1..*); key design artifact.

---

## 8.6 Object-Oriented Design Implementation

### Programming and development process
- Design → code: choose language (one aligned with OO: Java, C++, Python, C#), implement design.

### Mapping design to code
- Map **class diagram → class definitions** (fields, methods, constructors).
- Map **collaboration diagram methods → code methods** (method calls ↔ message passing in diagram).

### Creating class definitions from design class diagrams
- Translate UML class notation to concrete classes with correct attributes, methods, visibility modifiers.

### Creating methods from collaboration diagrams
- Sequence of method calls in collaboration diagram → function calls / method invocations in code.

### Updating class definitions
- Iterate; add error/exception handling as needed.

### Exception and error handling
- Use try-catch, custom exception classes, error logging; distinguish errors (bugs, crash) vs exceptions (recoverable conditions).
- Design-level: fail gracefully; inform user; log for debugging.

---

## Formula/Concept Box (Chapter 8 — must memorize)
- Software: engineered, not manufactured; cost of change increases over time; complexity is high
- Waterfall = sequential; V-Model = dev ↔ test parallel; Agile = iterative+sprints
- Functional vs non-functional requirements; SRS document standard
- Design: high cohesion + low coupling = good
- 3-tier = client / app server / DB server; real-time = deterministic
- Testing levels: unit → component → integration → system → acceptance
- COCOMO uses KLOC for effort; Function Points use user-facing features
- ISO 9000/9001; CMMI levels (Initial → Optimizing, 5 levels)
- Change management: identification → evaluation → approval → implementation
- Use case: actor + system interaction for a goal; UML diagrams: structure vs behavior
- Class diagram (structure): classes + relationships + attributes/methods
- Collaboration diagram: objects + messages (structural emphasis) vs Sequence (time emphasis)
- Mapping design → code: classes → class defs, messages → method calls, attributes → fields