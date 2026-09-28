# KET Focused Correction #2
## Original Response Record

> **Record note:** This file preserves the learner's responses from the completed Focused Correction #2 worksheet. Wording and conceptual errors are intentionally retained. This is not a model answer.

---

# Part 1 — Caller and Callee

## 1A — Direct Call

### `main()`

Directly calls:

> calculate()

Therefore:

> `main()` is the caller.  
> `calculate()` is the callee.

### `calculate()`

Directly calls:

> show()

Therefore:

> `calculate()` is the caller.  
> `show()` is the callee.

Does `main()` directly call `show()`?

> No

Evidence:

> `int main() {calculate(6);}`

---

## 1B — Do Not Use Execution Order

Does `read()` call `transform()`?

> No

Who directly calls `read()`?

> main()

Who directly calls `transform()`?

> main()

Who directly calls `output()`?

> main()

Function Map:

```text
main()
├── read()
├── transform()
└── output()
```

Complete:

> Execution order does **not** tell me **function map**.

> To identify a caller, I should look for **the function map**.

---

# Part 2 — Argument and Parameter

## 2A — Same Value, Different Names

At the call site, `today` is the:

> argument

At the function definition, `temperature` is the:

> parameter

```text
caller variable: today
argument: today
callee parameter: temperature
value being passed: 25
```

Does the value change from `25` to something else?

> No

Does the name used to refer to that value change across the call?

> Yes

Explanation:

> It is first stored in the variable "today", but when the main() function calls printTemperature() function, it is used in the variable "temperature".

---

## 2B — Reference

```text
Caller: main()
Callee: increase()
Argument: total
Parameter: value
```

Before the call:

```text
total = 10
```

Inside `increase()`, which name is used to access the object?

> value

After `value += 5;`, what is the value of `total`?

> 15

Explanation:

> Total is the direct actual variable used in the function when being called. The parameter is the variable used in the function when being defined first.

### STOP 1 — From Memory

```text
caller = main()
callee = increase()
argument = total
parameter = value
```

---

# Part 3 — Three Different Models

## 3A — Function Map

```text
main()
└── evaluate()
    ├── success()
    └── failure()
```

## Predicted Execution Path

```text
main() → evaluate(82) → success()
```

Which function is present in the Function Map but absent from this Execution Path?

> failure()

Why?

> When the score is greater than 60, success() will be executed, else failure. The score is 82, so success().

Does that function still belong in the Function Map?

> Yes

Why?

> Yes, since all defined functions have to be included in the function map.

---

# Part 4 — Function Map vs. Call Stack

## Step 1 — Function Map

```text
main()
└── run()
    └── adjust()
        └── triple()
```

## Step 2 — Execution Path

The recorded prediction was approximately:

```text
main()
↓
run()
↓
adjust(4)
↓
triple(4)
↓
return 13 to result
↓
return 13 to answer
```

> **Preservation note:** This reproduces the learner's recorded wording. The return-value wording is not silently corrected here.

## Step 3 — Call Stack Prediction

> `triple(), adjust(), run(), main()`

Why is `adjust()` still on the stack?

> Because the result has not been returned yet. Triple has not been returned yet.

Why is `run()` still on the stack?

> Because the adjust function has not been returned a value yet to give to the answer variable.

Why is `main()` still on the stack?

> Because adjust() function has not been returned a value to give to the answer variable, there is not value returned main() either.

Did `main()` directly call `triple()`?

> No

Then why can both functions appear on the Call Stack at the same time?

> Because main() called run(), run() called adjust(), and adjust() called triple().

## Step 4 — Debugger Verification

Actual Call Stack:

```text
1. triple()
2. adjust()
3. run()
4. main()
```

Prediction:

> Correct

The fields for an incorrect prediction were left blank because the learner marked the prediction as correct.

---

# Part 5 — Scaffold Removed

Learner explanation:

> The function map is main() calling process(), process calling report(), report() calling acceptable(). If we used 12 as the number value, the path will be main() calling process(), process(12) will call report(12), report(12) will call and check whether acceptable(value) is true. Since 12 is < 20, acceptable(12) is true. Cout will print “acceptable”, which is the output of the whole program.

Learner diagrams:

```text
Function map:
main()
→ process()
→ report()
→ acceptable()

Execution path:
main()
→ process(12)
→ report(12)
→ acceptable(12) is true
→ cout "accepted"
```

---

# Part 6 — Final Three Questions

## 1. Caller / Callee

> Function A is the caller, and B() is the callee.

Explanation:

> A is using B() inside it directly, so it is calling the B function.

## 2. Argument / Parameter

> Total is the argument, and value is the parameter.

## 3. From Memory

```text
Function Map answers:
The map of all defined functions

Execution Path answers:
How the program will actually run with an imaginary input.

Call Stack answers:
What functions have not been returned a value yet.
```

---

# Self-Check

The source worksheet contains the self-check choices, but the preserved parsed record does not show a selected checkbox. No selection is reconstructed here.

---

## Record Boundary

This file preserves the responses available in the completed worksheet. It intentionally does not convert them into corrected answers. Conceptual errors and imprecise wording are analyzed separately in the Error Analysis file.
