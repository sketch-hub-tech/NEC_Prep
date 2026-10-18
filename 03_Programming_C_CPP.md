# Chapter 3 — Programming Language and Its Applications (C/C++)
*(Code ACtE03 — 10 questions)*

---

## 3.1 Introduction to C Programming

### Tokens
Smallest meaningful unit: **keywords** (int, if, while…), **identifiers** (variable/function names), **constants**, **strings**, **operators**, **separators**.

### Operators
| Type | Examples |
|---|---|
| Arithmetic | + − * / % (modulus: integer remainder) |
| Relational | < > <= >= == != |
| Logical | && || ! |
| Bitwise | & \| ^ ~ << >> |
| Assignment | = += -= *= /= %= |
| Conditional | `(cond) ? a : b` |
| Increment/Decrement | ++ -- (prefix vs postfix) |
| Comma, sizeof, pointer (*, &) | — |

- **`%` (modulus) works only on integers.**
- `/` (integer division truncates for ints: 7/2 = 3).
- **Precedence:** `()` highest → arithmetic → relational → logical → assignment lowest. Unary > binary.

### Formatted / unformatted I/O
- **Formatted:** `printf("...%d", x)` — %d(int), %f(float), %c(char), %s(string), %x(hex), %o(octal), %u(unsigned), **%lf(double)**, %e (scientific).
- `scanf("%d", &x)` — **& for variables**, no & for arrays/strings.
- **Unformatted:** `getchar(), putchar() (char)`, `gets(), puts() (strings)`, `getch()`.
- Escape sequences: `\n` newline, `\t` tab, `\\` backslash, `\"` quote, `%` → `%%`.

### Control statements
- **Selection:** if, if-else, else-if ladder, **switch-case** (switch works on int/char, not float/string; `break` exits case; default optional).
- **Looping:** `for` (known count), `while` (entry-controlled), `do-while` (**exit-controlled — executes at least once**).
- `break` (exits loop), `continue` (skips to next iteration), `goto`, `return`.

### Functions
- User-defined functions: declaration (prototype), definition, call.
- **Recursion:** function calls itself; needs **base/termination case**; uses stack. Classic: factorial, Fibonacci, GCD.
- Parameter passing: **call by value** (copy — original unchanged) & **call by reference** (pointer — original modified).
- `main()` always returns int (or void). Static variables keep value between calls.

### Arrays & strings
- **Array:** contiguous homogeneous elements; index starts at **0**; bounds not checked in C.
- 1-D: `int a[10]`; 2-D: `int m[3][4]` (row-major storage); multi-dimensional.
- **String = char array terminated by `\0` (null).** `strlen` (no of chars, not counting \0), `strcpy, strcat, strcmp, strchr, strstr, atoi, atof`.
- Array name = **base address (constant pointer)**.

---

## 3.2 Pointers, Structures and Data Files in C

### Pointers
- Store **address** of a variable. `int *p; p = &x; *p` = value at address (dereference).
- **Pointer arithmetic:** p+1 advances by `sizeof(type)` bytes.
- **Pointer and array:** `a[i] ≡ *(a+i)`; pointer can iterate array.
- **Passing pointer to function:** enables modifying the caller's variables (call by reference).
- `NULL` pointer (0), void pointer (generic), pointer to pointer `int **pp`.
- **malloc/calloc/realloc/free** in stdlib → dynamic memory; `sizeof` returns bytes.

### Structure vs Union
| Structure | Union |
|---|---|
| Members each get **own memory** | Members **share same memory** |
| `sizeof` ≥ sum of members | `sizeof` = size of largest member |
| All members valid at once | Only one member valid at a time |
| `.` dot operator (struct var) / `->` (pointer) | same syntax |

- **Array of structures:** `struct student s[50];`
- **Passing structure to function:** by value or by pointer; **structure and pointer** → `s->name`.
- Self-referential structures → used for **linked lists**.

### Data files
- File operations: `fopen("file", "mode")` → returns `FILE *`; **NULL if fail**.
- Modes: `r` read, `w` write (overwrite), `a` append, `r+`, `w+`, `a+`, **`rb`/`wb` binary**.
- Functions: `fscanf, fprintf, fgetc, fputc, fgets, fputs, fread, fwrite, feof, fclose`.
- **Sequential access:** read/write from start in order. **Random access:** `fseek(fp, offset, SEEK_SET/CUR/END)`, `ftell()`, `rewind()`. Use with binary files/fread.

---

## 3.3 C++ Language Constructs

### OOP concepts (pillars)
**Encapsulation** (data + functions together), **Abstraction** (hide details), **Inheritance** (reuse), **Polymorphism** (many forms).

### Constructs
- **Namespace:** groups identifiers to avoid naming conflicts; `std`; `using namespace std;`.
- **Function overloading:** same name, different parameter lists (type/count). Return type alone does NOT distinguish.
- **Inline function:** request to expand code at call site (faster, no call overhead); compiler may ignore.
- **Default argument:** `int f(int a, int b=5);` — defaults from **right to left**.
- **Pass/Return by reference:** `void f(int &x)` — no copy, modifies original; reference is alias.
- **Class & object:** class = user-defined type (blueprint); object = instance.
- **Access specifiers:** `public` (anywhere), `private` (only within class — default), `protected` (class + derived).
- **Member functions:** defined inside/outside with `::` scope resolution operator.
- **Constructor:** same name as class, no return type, auto-called on object creation; types: **default, parameterized, copy**.
- **Destructor:** `~ClassName`; auto-called when object destroyed (releases resources).
- **`this` pointer:** points to the invoking object; used to resolve name conflicts.
- **static members:** one copy shared by all objects; static member function can access only static members.
- **const member functions & const objects:** cannot modify data members.
- **friend function/class:** access to private members without being a member.

---

## 3.4 Features of Object-Oriented Programming

### Operator overloading
- Redefine operator for user types: `operator+`, `operator<<`, etc.
- **Unary operator** (e.g., ++, --): member function takes **0 args**; friend takes 1.
- **Binary operator:** member function takes **1 arg** (other operand); friend takes 2.
- Cannot overload: `::`, `.`, `.*`, `?:`, `sizeof`, `#`, `##`, `->` (partially).
- **Data conversion:** user-defined type ↔ basic type (conversion operators / constructors).

### Inheritance (types)
| Type | Base classes |
|---|---|
| **Single** | one base, one derived |
| **Multiple** | derived from 2+ bases |
| **Multilevel** | A→B→C (chain) |
| **Hybrid** | combination (multiple + multilevel) |
| **Hierarchical / Multipath** | diamond problem — resolved by **virtual base class** |

- Visibility of base members in derived: public/protected/private inheritance.
- **Constructor/destructor order in single inheritance:** base constructor runs **first**, derived destructor runs **first** (reverse order).
- In multilevel: constructors run top-down, destructors bottom-up.

---

## 3.5 Pure Virtual Functions and File Handling

### Virtual functions & polymorphism
- `virtual` keyword enables **dynamic binding (runtime polymorphism)**.
- **Pure virtual function:** `virtual void f()=0;` → makes class **abstract** (cannot instantiate); derived must override.
- Base-class pointer can call derived-class overridden functions (vtable/vptr mechanism).
- Static binding = compile-time (overloading); dynamic binding = runtime (virtual).

### File handling (C++ iostream-based)
- `ofstream` (write), `ifstream` (read), `fstream` (read+write); `open()`/`close()`.
- `<<` to write, `>>` to read.
- **Stream Class Hierarchy:** `istream`, `ostream` ← `iostream`; streambuf classes for storage.
- **Unformatted I/O:** `get(), getline(), put(), read(), write(), gcount()`.
- **Error handling:** stream state flags — `good(), bad(), fail(), eof(), clear()`.
- **Formatted I/O with ios member functions & flags:** `setf()`, `unsetf()`, width(), precision(), fill().
- **Manipulators:** `endl, ends, flush, setw, setprecision, setfill, setiosflags, hex, oct, dec, setbase`.
- `getline(cin, str)` handles spaces in strings.

---

## 3.6 Generic Programming and Exception Handling

### Templates
- **Function template:** generic function for many types. `template <class T> T max(T a, T b)`.
- **Overloading a function template:** multiple templates / template + normal function.
- **Class template:** generic class (e.g., Stack<T>, Vector<T>). `template <class T> class Stack {...};` — instantiation: `Stack<int> s;`.
- Function definition of class template outside class needs `template <class T>` prefix and `Class<T>::`.

### Standard Template Library (STL)
- **Containers:** sequence — `vector, list, deque`; associative — `set, multiset, map, multimap`; adapters — `stack, queue, priority_queue`.
- **Algorithms:** `sort, search, find, merge, count, reverse, copy, for_each, binary_search` (in `<algorithm>`).
- **Iterators:** pointer-like objects to traverse containers: begin(), end(), random-access.

### Exception handling
- Constructs: `try { } catch (type) { } throw;`
- **try** block encloses risky code; **throw** raises an object; **catch** handler matches type.
- **Multiple catch handlers** (different types); catch order matters (base after derived).
- **Rethrowing exception:** `throw;` inside catch.
- **Catching all:** `catch(...)`.
- **Exception with arguments:** throw objects with data.
- **Exception specification:** `void f() throw(type1, type2);` (deprecated in C++11 but asked).
- **Uncaught/unexpected exceptions:** terminate() called → program ends.

---

## Code/Formula Box (Chapter 3 — must memorize)
- `%` int-only; 7/2=3 (int); do-while runs ≥1 time; array index from 0
- `a[i] ≡ *(a+i)`; sizeof(a)/sizeof(a[0]) = element count
- Structure: own memory each; Union: largest member
- strcmp → 0 if equal; strings end with `\0`
- fprintf/fscanf, fseek/ftell/rewind → random access
- Constructor order: base→derived; destructor reverse (derived first)
- Unary member overload: 0 args; Binary: 1 arg
- Pure virtual `=0` → abstract class
- `catch(...)` catches all; `throw;` rethrows
- Exceptions: try → throw → catch (match by type)