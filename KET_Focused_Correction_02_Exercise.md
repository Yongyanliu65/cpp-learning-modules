# KET Focused Correction #2
## Three Relationship Models — Exercise

**Target Time:** 25–35 minutes  
**Difficulty:** 2.5–3/10

## Training Goal

This exercise focuses on only three relationships:

1. Caller ↔ Callee
2. Argument ↔ Parameter
3. Function Map ↔ Execution Path ↔ Call Stack

The goal is not to memorize definitions. The goal is to look at unfamiliar code and identify the correct relationship without guessing from execution order.

---

# Part 1 — Caller and Callee

## 1A — Direct Call

```cpp
#include <iostream>

void show(int x)
{
    std::cout << x << '\n';
}

void calculate(int x)
{
    show(x * 2);
}

int main()
{
    calculate(6);
}
```

### `main()`

Directly calls: ____________________

Therefore:

`main()` is the ____________________

`calculate()` is the ____________________

### `calculate()`

Directly calls: ____________________

Therefore:

`calculate()` is the ____________________

`show()` is the ____________________

Does `main()` directly call `show()`?

**Yes / No**

Explain using one line of code as evidence:

____________________________________________________________

## 1B — Do Not Use Execution Order

```cpp
int read()
{
    return 5;
}

int transform(int x)
{
    return x + 10;
}

void output(int x)
{
}

int main()
{
    int a = read();
    int b = transform(a);
    output(b);
}
```

The execution happens in this order:

```text
main → read → main → transform → main → output → main
```

Now answer:

Does `read()` call `transform()`? **Yes / No**

Who directly calls `read()`? ____________________

Who directly calls `transform()`? ____________________

Who directly calls `output()`? ____________________

Draw the Function Map:

```text


```

Complete:

> Execution order does **not** tell me ______________________________.

> To identify a caller, I should look for ______________________________.

---

# Part 2 — Argument and Parameter

## 2A — Same Value, Different Names

```cpp
#include <iostream>

void printTemperature(int temperature)
{
    std::cout << temperature << '\n';
}

int main()
{
    int today = 25;
    printTemperature(today);
}
```

At the call site:

```cpp
printTemperature(today);
```

`today` is the: **argument / parameter**

At the function definition:

```cpp
void printTemperature(int temperature)
```

`temperature` is the: **argument / parameter**

Complete:

```text
caller variable: ____________________
argument: ____________________
callee parameter: ____________________
value being passed: ____________________
```

Does the value change from `25` to something else? **Yes / No**

Does the name used to refer to that value change across the call? **Yes / No**

Explain:

____________________________________________________________

## 2B — Reference

```cpp
void increase(int& value)
{
    value += 5;
}

int main()
{
    int total = 10;
    increase(total);
}
```

Identify:

```text
Caller:
Callee:
Argument:
Parameter:
```

Before the call:

```text
total = 10
```

Inside `increase()`, which name is used to access the object?

____________________

After:

```cpp
value += 5;
```

what is the value of `total`?

____________________

Explain this sentence:

> `total` is the argument, while `value` is the parameter.

____________________________________________________________

### STOP 1

Before continuing, check whether you can explain without looking back:

```text
caller =
callee =
argument =
parameter =
```

If not, review the Error Explanation before continuing. If yes, continue.

---

# Part 3 — Three Different Models

From this point forward, **do not use the Error Explanation**. Use only the code.

## 3A

```cpp
#include <iostream>

void success()
{
    std::cout << "success\n";
}

void failure()
{
    std::cout << "failure\n";
}

void evaluate(int score)
{
    if (score >= 60)
        success();
    else
        failure();
}

int main()
{
    evaluate(82);
}
```

### A. Function Map

Draw all direct user-defined function-call relationships.

```text


```

### B. Predicted Execution Path

For this specific run with `82`:

```text


```

### C. Compare

Which function is present in the Function Map but absent from this Execution Path?

____________________

Why?

____________________________________________________________

Does that function still belong in the Function Map? **Yes / No**

Why?

____________________________________________________________

---

# Part 4 — Function Map vs. Call Stack

## 4A

Do not run the code yet.

```cpp
int triple(int x)
{
    return x * 3;
}

int adjust(int x)
{
    int result = triple(x);
    return result + 1;
}

void run()
{
    int answer = adjust(4);
}

int main()
{
    run();
}
```

### Step 1 — Function Map

Draw the Function Map.

```text


```

### Step 2 — Execution Path

Predict the execution path. Include returns when useful.

```text


```

### Step 3 — Call Stack Prediction

Imagine the debugger is currently stopped inside `triple()`, before:

```cpp
return x * 3;
```

Predict the Call Stack from the currently executing function downward:

```text
1.
2.
3.
4.
```

Why is `adjust()` still on the stack?

____________________________________________________________

Why is `run()` still on the stack?

____________________________________________________________

Why is `main()` still on the stack?

____________________________________________________________

Did `main()` directly call `triple()`? **Yes / No**

Then why can both functions appear on the Call Stack at the same time?

____________________________________________________________

### Step 4 — Verify

Now use the debugger. Set a breakpoint inside `triple()`.

Record the actual Call Stack:

```text
1.
2.
3.
4.
```

Was your prediction:

**Correct / Partially correct / Incorrect**

If incorrect, do not erase it.

```text
First point where my mental model was wrong:

Evidence:

Corrected model:
```

---

# Part 5 — Scaffold Removed

No definitions are provided in this section.

## 5A

```cpp
#include <iostream>

bool acceptable(int number)
{
    return number < 20;
}

void report(int value)
{
    if (acceptable(value))
        std::cout << "accepted\n";
}

void process(int input)
{
    report(input);
}

int main()
{
    int number = 12;
    process(number);
}
```

Without using the words printed in previous sections as a checklist, explain the structure and runtime behavior of this program.

Your explanation must include whatever relationships you think are necessary to understand the program.

____________________________________________________________

Now draw any diagram or diagrams that would help you explain it:

```text


```

---

# Part 6 — Final Three Questions

Close the code if necessary. Answer from memory.

### 1.

If function A contains:

```cpp
B();
```

which is the caller and which is the callee?

____________________________________________________________

Explain why:

____________________________________________________________

### 2.

If:

```cpp
int total = 10;
update(total);
```

and:

```cpp
void update(int& value)
```

what are `total` and `value`?

____________________________________________________________

### 3.

Complete these without looking back:

```text
Function Map answers:

Execution Path answers:

Call Stack answers:
```

---

# Self-Check

Do not change your original answers.

```text
Caller / Callee:
□ I can explain it without a definition.
□ I still need the terminology in front of me.

Argument / Parameter:
□ I can explain it without a definition.
□ I still need the terminology in front of me.

Function Map / Execution Path / Call Stack:
□ I can build all three from the same code.
□ I still mix at least two of them together.
```

## End Rule

Do not repeat this worksheet.

If an error remains, record the exact error.

If these relationships are correct without hints, stop practicing them here.

The next test should use different code.
