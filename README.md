# Advanced Python Code Snippets Collection

A curated repository of intermediate-to-advanced Python exercises, complete with concepts, implementations, and architectural explanations. Each directory focuses on demonstrating core mechanisms, optimizations, and internal protocols within Python.

## 📂 Repository Layout

```text
.
├── py-mro/                 # Method Resolution Order & Diamond Inheritance
│   └── mro_demo.py
├── py-decorators/          # Parameterized Wrapper Closures
│   └── repeat_decorator.py
├── py-context-managers/    # Exception Handling & Context Protocols
│   └── custom_manager.py
├── py-arrays/              # Type Safety & Memory Optimization with C-Arrays
│   └── array_demo.py
├── py-strings/             # Memory Profiling & String Interning
│   └── interning_demo.py
└── py-loops/               # Loop Structures & Pattern Printing
    └── star_pattern.py
```

---

## 🚀 Concept Summaries & Usage

### 1. Method Resolution Order (`py-mro`)
* **Concept:** Resolves the Diamond Inheritance problem using **C3 Linearization**. It establishes a clear, predictive order for method lookups when multiple parent classes share a common ancestor.
* **Key Takeaway:** Using `super()` inside a parent class shifts execution dynamically to its sibling class based on the calculated MRO chain, rather than blindly leaping straight to the root base class.

### 2. Parameterized Decorators (`py-decorators`)
* **Concept:** Implements decorators capable of accepting custom configurations.
* **Key Takeaway:** Requires a triple-nested closure function structural layout. The top layer digests configuration variables, the middle layer accepts the target function object, and the inner layer processes arguments via `*args` and `**kwargs`.

### 3. Context Managers Protocol (`py-context-managers`)
* **Concept:** Custom resource lifecycle hooks entirely managed without external `contextlib` wrappers.
* **Key Takeaway:** Uses the `__enter__` and `__exit__` magic methods. Returning `True` from `__exit__` effectively suppresses exceptions, while returning `False` allows them to cleanly cascade outward.

### 4. Low-Level Single-Type Arrays (`py-arrays`)
* **Concept:** Employs the built-in `array` module for highly compressed, uniform data grouping.
* **Key Takeaway:** Stores contiguous, raw C-style representations of primitive attributes. This provides massive memory reductions compared to pointers used by list constructs, while enforcing a static variable data structure.

### 5. String Interning Memory Mechanics (`py-strings`)
* **Concept:** Maps exact, repeating variable string identities to the identical space within heap storage allocations.
* **Key Takeaway:** While compile-time constants are handled implicitly, dynamic string patterns assigned during system runtimes can be manually assigned into optimization tables via `sys.intern()`.

### 6. Pattern Generation (`py-loops`)
* **Concept:** Clean procedural rendering using built-in sequence mechanics.
* **Key Takeaway:** Combines basic integer increment loops with native Python string multiplication variables (`"*" * i`) to sidestep nested complexity.

---

## 🛠️ Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd python-advanced-snippets
   ```

2. **Execute any snippet directly:**
   ```bash
   python3 py-mro/mro_demo.py
   python3 py-strings/interning_demo.py
   ```

No external dependencies are required. All examples strictly utilize standard library modules (`sys`, `array`, `functools`).
