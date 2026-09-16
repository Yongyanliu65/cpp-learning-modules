# 05 — Delayed Blind Transfer
## Changed Code, Reduced Cueing

**Suggested delay:** 48–72 hours after focused correction.  
**Target time:** 25–35 minutes.  
**Difficulty:** approximately 3–3.5/10 for a novice who has completed the preceding work.

### Rules

1. Do not review the earlier correction immediately before starting.
2. Do not use AI.
3. Complete predictions before running or debugging.
4. Do not erase an incorrect prediction after verification.
5. Use runtime/debugger evidence only when the task asks for verification.
6. Do not search for a concept merely because it appeared in an earlier worksheet.

### Program

```cpp
#include <iostream>

int convert(char level) {
    if (level == 'H') return 3;
    return 1;
}

void unusedMessage() {
    std::cout << "unused\n";
}

void addBonus(int& score, int amount) {
    score += amount;
}

bool qualified(int score) {
    return score >= 12;
}

void evaluate(char level, int& points) {
    int bonus = convert(level);
    addBonus(points, bonus);

    if (qualified(points))
        std::cout << "qualified\n";
    else
        std::cout << "not qualified\n";
}

void start(int initial) {
    int total = initial;
    evaluate('H', total);
}

int main() {
    start(10);
}
```

### Task 1 — Understand the program

Without running the code, explain how the program is organized. Do not describe every line. Explain the relationships you think are important.

### Task 2 — Represent the structure

Draw one diagram showing the important relationships among the functions. Choose the form yourself.

Should `unusedMessage()` appear in the relationship diagram you chose? Explain.

### Task 3 — Follow data across boundaries

Trace the value beginning as `10` in `start(10)` until the program finishes.

Explain where it is stored, when another name is used, whether the value changes, what causes the change, and where the final value matters.

### Task 4 — Predict runtime state

Before running the program:

1. predict the output;
2. write the important execution path;
3. imagine a debugger is stopped inside `addBonus()` before `score += amount;`;
4. predict the active user-defined calls at that moment.

Then verify the call-stack prediction with a debugger and preserve both prediction and evidence.

### Task 5 — Changed input

Change only:

```cpp
start(10);
```

to:

```cpp
start(8);
```

Before running:

- predict the output;
- explain what changes;
- explain which structural relationships remain unchanged.

Run the program and compare the evidence with the prediction.

### Final record

- Time used:
- Highest help level: H0 / H1 / H2 / H3 / H4
- First divergence between prediction and evidence, if any:
- Revised model, if needed:
