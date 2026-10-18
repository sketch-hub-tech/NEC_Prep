# Chapter 9 — Artificial Intelligence and Neural Networks
*(Code ACtE09 — 10 questions)*

---

## 9.1 Introduction to AI and Intelligent Agents

### What is AI?
- **AI:** the branch of computer science concerned with building intelligent systems that can think, reason, learn, and act — simulating human cognition.
- **AI Perspectives:** acting/thinking humanly/rationally.
  - Thinking humanly: cognitive science.
  - Acting humanly: Turing test approach.
  - Thinking rationally: logic-based (laws of thought).
  - Acting rationally: rational agents (modern definition).
- **History:** 1950s Dartmouth workshop, Turing test (Alan Turing), expert systems (70s-80s), machine learning boom, deep learning, generative AI.
- **Applications:** NLP, computer vision, robotics, autonomous vehicles, games (chess/Go), medical diagnosis, recommendation systems, smart assistants.

### Foundations of AI
- Philosophy, mathematics, economics, neuroscience, psychology, computer engineering, linguistics.

### Intelligent agents
- **Agent:** perceives environment via **sensors** and acts via **actuators**.
- **Agent function:** maps percept sequence → action. **Agent program:** implementation.
- **Structure of the agent:** architecture (program runs on it) + agent program.
- **Properties:** autonomy, reactivity, proactivity, social ability.
- **PEAS description:** **P**erformance measure, **E**nvironment, **A**ctuators, **S**ensors.

### Types of agents
| Agent type | Behavior |
|---|---|
| **Simple reflex** | Condition-action rules only, no memory |
| **Model-based** | Keeps internal state (model of world) |
| **Goal-based** | Considers goals, searches plan |
| **Utility-based** | Measures desirability, maximizes utility |

### Environment types
- **Deterministic** (next state fully determined) vs **Stochastic** (randomness)
- **Static** (unchanging while agent thinks) vs **Dynamic** (changes)
- **Fully observable** vs **Partially observable** (sensors limited)
- **Episodic** vs **Sequential**
- **Discrete** vs **Continuous**
- **Single-agent** vs **Multi-agent**

---

## 9.2 Problem Solving and Searching Techniques

### Problem formulation
- **State space search:** states, initial state, actions, transition model, goal test, path cost.
- **Well-defined problems:** single/multiple state.
- **Constraint satisfaction problems (CSP):** variables, domains, constraints (map coloring, 8-queens, Sudoku).

### Uninformed (blind) search — no domain knowledge
| Algorithm | Strategy | Completeness | Optimality |
|---|---|---|---|
| **BFS (Breadth-First)** | FIFO queue, shallow first | Complete (finite) | Optimal if all costs equal |
| **DFS (Depth-First)** | Stack, deep first | Incomplete (infinite trees) | Not optimal |
| **Depth-Limited (DLS)** | DFS with depth limit | Limit ≥ depth → complete | No |
| **Iterative Deepening (IDS)** | DLS with increasing limit | **Complete** | **Optimal** (uniform costs) |
| **Bidirectional** | BFS from both ends | Complete | Optimal |

- Time BFS: O(b^d); space BFS O(b^d); DFS space O(b·d).

### Informed (heuristic) search
- **Heuristic (h(n)):** estimate of cost from node n to goal.
- **Greedy best-first:** expand node with smallest h(n) — fast but **not optimal**.
- **A\* search:** `f(n) = g(n) + h(n)` (cost-so-far + heuristic). **Optimal and complete** if heuristic is **admissible** (never overestimates). Dominance between heuristics.
- **Hill climbing:** local gradient ascent; progress downhill issues — stuck at local maxima/plateaus/ridges; variations: stochastic hill climbing, random-restart.
- **Simulated annealing:** like hill climbing but accepts worse moves with decreasing probability over time (cooling schedule) — escapes local minima; converges to good solutions.
- **Simulated annealing:** escapes local minima by accepting worse solutions probabilistically (cooling schedule).

### Game playing — adversarial search
- **Game theory / game tree:** MAX vs MIN.
- **Minimax:** choose move maximizing worst-case outcome; computes min of max values.
- **Alpha-beta pruning:** prunes branches that cannot affect the result; reduces search; same result as minimax.

---

## 9.3 Knowledge Representation

### Representation
- **Knowledge representation:** how to encode knowledge in a machine-processable form. Mapping from reality to representation.
- **Approaches:** logical (formal logic), procedural (rules), relational, structured (semantic nets, frames), non-monotonic.
- **Issues in KR:** expressive richness, inference efficiency, inadequacy of logic for commonsense (defaults).

### Structured representations
- **Semantic nets:** nodes = objects/concepts; arcs = relations ("is-a", "part-of", "has").
- **Frames:** structured objects with slots (named attribute-value pairs) + defaults, inheritance.

### Formal logic
- **Propositional logic (PL):** statements (propositions) with connectives **∧ ∨ ¬ → ↔**; atoms; truth tables.
  - **Syntax & semantics;** **tautology** (always true), **validity**, **well-formed formula (WFF)**.
  - **Inference using resolution** (clauses, contradiction → refutation).
- **First-order predicate logic (FOPL):** variables, quantifiers **∀ (universal), ∃ (existential)**, predicates, functions, constants.
  - Syntax & semantics, **rules of inference** (MP, modus tollens), **unification** (matching substitutions), **resolution refutation** (CNF + resolution + skolemization).

### Uncertainty
- **Bayes' rule:** `P(H|E) = P(E|H)·P(H) / P(E)` (posterior = likelihood × prior / evidence).
- **Bayesian networks (belief networks):** DAG of random variables with conditional probability tables (CPTs); efficient inference by exploiting conditional independence.
- **Reasoning in belief networks:** propagate evidence, compute posterior probabilities.

---

## 9.4 Expert Systems and Natural Language Processing

### Expert systems
- **Expert system:** AI program emulating a human expert's decision-making in a domain.
- **Architecture:**
  - **Knowledge base** (domain facts + rules).
  - **Inference engine** (forward/backward chaining).
  - Working memory, user interface, explanation facility, knowledge acquisition subsystem.
- **Knowledge acquisition:** extracting knowledge from experts (interviews, document analysis).
- **Declarative knowledge** (facts, "what is") vs **Procedural knowledge** ("how to do").
- **Development of expert systems:** identify domain → extract → represent → implement → validate.
- Applications: MYCIN (medical diagnosis), DENDRAL (chemistry).

### Natural language processing (NLP)
- **NLP:** enabling machines to understand & generate human language.
- **NLU (Understanding):** analyze input. **NLG (Generation):** produce output.
- **Steps of NLP:** morphological/lexical analysis → **syntactic** (parsing sentences) → **semantic** (meaning) → **discourse/pragmatic** (context and intent).
- **Challenges:** ambiguity, context, sarcasm, rare words.
- **Applications:** translation, chatbots, sentiment analysis, search, summarization.

### Computer vision & robotics
- **Machine vision:** extracting meaning from images; stages: image acquisition → pre-processing → feature extraction → segmentation → recognition → interpretation.
- **Robotics:** AI-controlled machines with sensors/actuators; perception, planning, control, localization/mapping (SLAM).

---

## 9.5 Machine Learning

### Learning basics
- **Learning:** system improves performance E on task T with measure P from experience.
- **Types:**
  - **Supervised:** labeled data (input→output); classification & regression.
  - **Unsupervised:** unlabeled data; clustering (K-means), dimensionality reduction.
  - **Reinforcement learning:** learn via rewards/punishments from environment (agent-action).

### Algorithms
- **Inductive learning (Decision tree):** ID3/C4.5; split on attribute; **information gain** & **entropy**; uses divide-and-conquer; handles categorical data; prone to overfitting (pruning).
- **Statistical-based learning (Naive Bayes):** applies Bayes' rule assuming **conditional independence** of features; simple, fast, works on text classification (spam filtering).

### Fuzzy systems
- **Fuzzy logic:** degree of truth in [0,1] (not just true/false); linguistic variables (e.g., temperature: cold/warm/hot).
- **Fuzzy inference system (FIS):** fuzzification → rule evaluation → aggregation → **defuzzification** (centroid/MOM).
- **Fuzzy inference methods:** Mamdani (linguistic output) / Sugeno (functional output).
- Applications: washing machines, HVAC control, ABS.

### Genetic algorithms (GA)
- Inspired by natural selection; populations of chromosomes (strings).
- **GA operators:** **selection** (roulette wheel/tournament), **crossover** (single/multi-point), **mutation** (bit flip small probability).
- **GA encoding:** binary, permutation, value, tree encoding.
- **Fitness function:** evaluates solutions; drives selection.
- **Parameters:** population size, crossover & mutation rates, generations/number of iterations.

---

## 9.6 Neural Networks

### Biological vs artificial
- **Biological NN:** neurons with dendrites/soma/axon/synapses; learning via synaptic weights.
- **ANN:** artificial neurons (nodes) with weighted inputs + activation function; arranged in layers.

### Neuron model
- **McCulloch-Pitts neuron:** binary threshold unit; inputs weighted-summed; output 1 if sum ≥ threshold else 0. Simplicity; linear only.
- **Mathematical model:** `output = f(Σ wᵢ·xᵢ + b)`.
- **Activation functions:** step, **sigmoid (0-1)**, tanh (−1..1), **ReLU (max(0,x))**, linear.

### Architectures
- **Single-layer** (perceptron), **multi-layer** (MLP with hidden layers), **recurrent** (feedback — Hopfield), shallow vs deep.

### Learning rules
- **Perceptron learning rule:** adjust weights for linearly separable problems only.
- **Learning rate (η):** step size for weight updates; too high → divergence; too low → slow.
- **Gradient descent:** minimize error function (mean squared error); weight update: `w ← w − η·(∂E/∂w)`.
  - **Batch GD:** full dataset per step; **Stochastic GD:** one sample per step; **Mini-batch.**
- **Delta rule (LMS/Widrow-Hoff):** uses (d − y)·x to update weights (gradient of squared error); basis of ADALINE.
- **Hebbian learning:** "neurons that fire together wire together" — weight ∝ product of activations.
- **ADALINE (Adaptive Linear Neuron):** linear neuron + delta rule.

### Multilayer Perceptron & backpropagation
- **MLP:** input + ≥1 hidden + output layers; can solve **XOR** (not linearly separable) with hidden layers.
- **Backpropagation algorithm:** forward pass computes outputs; backward pass propagates error to update weights of all layers via chain rule of gradient descent; iterative until convergence.
- **Hopfield neural network:** **recurrent**, associative memory; stores patterns as attractors; energy minimization; content-addressable memory; can retrieve patterns from noisy/corrupted input.

---

## Formula Box (Chapter 9 — must memorize)
- Agent: sensors + actuators; PEAS = Performance, Environment, Actuators, Sensors
- Agent types: simple reflex < model-based < goal-based < utility-based
- BFS complete+optimal (uniform cost); DFS space-wise good; IDS both complete+optimal
- A*: f = g + h; optimal if admissible h
- Minimax + alpha-beta pruning (optimal, faster)
- PL connectives; FOPL quantifiers ∀ ∃; resolution refutation; unification
- Bayes: P(H|E) = P(E|H)P(H)/P(E)
- Expert system: knowledge base + inference engine; forward/backward chaining
- NLP steps: lexical → syntactic → semantic → discourse
- Supervised = labels; Unsupervised = clustering; RL = rewards
- Naive Bayes assumes conditional independence; decision tree splits on info gain
- Fuzzy: fuzzify → infer → defuzzify (Mamdani/Sugeno)
- GA: selection, crossover, mutation; fitness function
- Perceptron: linear-separable only; MLP solves XOR; backprop trains MLP
- Delta rule: w := w + η(d−y)x; Hebbian: w ∝ x·y
- Hopfield: recurrent associative memory, energy minimization