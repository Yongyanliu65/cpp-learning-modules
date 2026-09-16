# 01 — Baseline Assessment
## First Mental Model of Function Relationships

**Purpose:** diagnostic only. Do not teach definitions before administration.  
**Target time:** 25–35 minutes  
**Help:** record all help; do not assume H0 if help was not recorded.

### Program

```cpp
#include <iostream>

int getStep(int mode) {
    if (mode == 1) return 2;
    return 1;
}

void show(int value) {
    std::cout << value << '\n';
}

int update(int value) {
    return value + getStep(1);
}

void run(int start) {
    int result = update(start);
    show(result);
}

void unused() {
    std::cout << "unused\n";
}

int main() {
    run(5);
}
```

### Task 1 — Explain the program

Without running the code, explain how the program is organized. Focus on the relationships you think matter.

### Task 2 — Draw the structure

Draw one diagram that helps you explain the important relationships among the functions. Choose the diagram form yourself.

Does `unused()` belong in the relationship diagram you drew? Explain.

### Task 3 — Follow one run

For the run shown in `main()`, describe what actually happens from program start to output.

What does the program print?

### Task 4 — Function boundary

In:

```cpp
run(5);
```

and:

```cpp
void run(int start)
```

explain what `5` and `start` are doing. Use your own words.

### Task 5 — Active calls

Imagine execution is stopped inside `getStep()` before it returns. Which user-defined functions have started but not yet finished?

Explain why each one is still active.

---

## Instructor record

Preserve the first response before correction.

Record only what is observed:

- direct-call relationship errors;
- execution-order vs. call-relationship errors;
- argument/parameter errors;
- active-call/stack errors;
- function/value confusion;
- branch errors;
- hint level, if known.

Do **not** convert missing hint data into H0.
