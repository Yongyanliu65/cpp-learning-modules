# 02 — Error Explanation
## Five Relationship Distinctions

Use this file **after** the baseline has exposed a relevant error. It is an explanation, not a transfer test.

### 1. Caller and callee

If function `A` contains:

```cpp
B();
```

then `A` is the **caller** and `B` is the **callee** for that direct call.

Do not infer direct calls from execution order. If `main()` calls `A()` and `A()` calls `B()`, `main()` does not directly call `B()`.

### 2. Argument and parameter

At the call site:

```cpp
printTemperature(today);
```

`today` is the **argument**.

At the function definition:

```cpp
void printTemperature(int temperature)
```

`temperature` is the **parameter**.

The same value may cross a function boundary while the name used to access it changes.

### 3. Function Map

A Function Map answers:

> Which user-defined function directly calls which other user-defined function?

It is a **static relationship model**. It is not a list of every defined function, and it is not the order of one particular run.

### 4. Execution Path

An Execution Path answers:

> What actually happened in this particular run?

Branches matter. A function can belong to the Function Map even when a particular input does not execute it.

### 5. Call Stack

At a particular moment, the Call Stack represents active calls that have started but have not yet finished.

A function does **not** need to return a value to have a stack frame. `void` functions can remain active while a nested call is running.

### Quick contrast

```text
Function Map   = direct-call structure allowed by the code
Execution Path = calls/branches actually taken in one run
Call Stack     = calls currently active at one moment
```

### Instructor note

Explain only the distinctions implicated by the learner's observed errors. The goal is repair, not vocabulary memorization.
