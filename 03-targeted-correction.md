# 03 — Targeted Correction
## Controlled Relationship Practice

**Purpose:** repair observed baseline errors.  
**Suggested size:** use 3–5 questions, not every possible exercise.

### Question 1 — Direct calls

```cpp
void display(int x) {
    std::cout << x << '\n';
}

void calculate(int x) {
    display(x * 2);
}

int main() {
    calculate(6);
}
```

Answer:

1. Who directly calls `calculate()`?
2. Who directly calls `display()`?
3. Does `main()` directly call `display()`?
4. Give one line of code as evidence.

### Question 2 — Same value, different names

```cpp
void printAge(int age) {
    std::cout << age << '\n';
}

int main() {
    int userAge = 20;
    printAge(userAge);
}
```

Identify:

- caller;
- callee;
- argument;
- parameter;
- value passed.

Does the value change? Does the name used to access it change?

### Question 3 — Static vs. one run

```cpp
void pass() { std::cout << "pass\n"; }
void fail() { std::cout << "fail\n"; }

void evaluate(int score) {
    if (score >= 60)
        pass();
    else
        fail();
}

int main() {
    evaluate(82);
}
```

A. Draw all direct user-defined call relationships.  
B. Write the actual execution path for this run.  
C. Does `fail()` belong in A even though it does not execute in B? Explain.

### Question 4 — Active nested calls

```cpp
int triple(int x) {
    return x * 3;
}

int adjust(int x) {
    int result = triple(x);
    return result + 1;
}

void run() {
    int answer = adjust(4);
}

int main() {
    run();
}
```

Imagine execution is stopped inside `triple()` before `return x * 3;`.

Predict the active call stack from the current function downward. Explain why `run()` and `main()` are still active.

### Correction rule

After feedback, do not simply repeat the same question with different numbers. Move to the focused correction only if the learner can explain the corrected relationship.
