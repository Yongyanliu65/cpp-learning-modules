# 04 — Focused Correction and Scaffold Fading

**Purpose:** confirm repaired relationships and then remove the terminology scaffold.  
**Target time:** 25–35 minutes.

### Part A — Relationship check

```cpp
int read() {
    return 5;
}

int transform(int x) {
    return x + 10;
}

void output(int x) {
    std::cout << x << '\n';
}

int main() {
    int a = read();
    int b = transform(a);
    output(b);
}
```

1. Does `read()` call `transform()`?
2. Who directly calls `read()`, `transform()`, and `output()`?
3. Draw the direct-call structure.

### Part B — Reference boundary

```cpp
void increase(int& value) {
    value += 5;
}

int main() {
    int total = 10;
    increase(total);
}
```

Identify caller, callee, argument, and parameter.

What is `total` after the call? Explain how the function boundary relates to that result.

### Part C — Three models from one program

```cpp
void success() { std::cout << "success\n"; }
void failure() { std::cout << "failure\n"; }

void evaluate(int score) {
    if (score >= 60)
        success();
    else
        failure();
}

int main() {
    evaluate(82);
}
```

Produce:

1. the direct-call structure;
2. the actual path for this run;
3. a short explanation of why the two are not identical.

### Part D — Predict, then verify

```cpp
int triple(int x) { return x * 3; }

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

Before using a debugger, predict the active calls when execution is stopped inside `triple()`.

Then verify with the debugger. Preserve the prediction. If it differs from the evidence, record the first divergence.

### Part E — Scaffold removed

```cpp
bool acceptable(int number) {
    return number < 20;
}

void report(int value) {
    if (acceptable(value))
        std::cout << "accepted\n";
}

void process(int input) {
    report(input);
}

int main() {
    int number = 12;
    process(number);
}
```

Without using earlier terminology as a checklist, explain the structure and runtime behavior of this program in whatever way you think is necessary.

### Stop rule

If the target relationships are correct without hints, stop focused practice. The next assessment should use changed code after a delay.
