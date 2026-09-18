# C++ Real-Code Assessment #1
## Error Analysis

### Purpose

This document analyzes the main errors identified after the first real-code assessment. It is not an answer key and does not replace the learner's original response.

The purpose is to establish a baseline for later correction and transfer testing. The assessment score is therefore less important than identifying the specific reasoning problems that should be tested again under changed conditions.

## Baseline Summary

The learner can build a rough structural model of a small unfamiliar procedural program, but the relationships among **function calls, runtime execution, and data/state flow are not yet consistently connected**.

The first assessment revealed four main error patterns.

---

## E-CALL — Call Relationship Error

### Observed Error

The initial reasoning incorrectly associated functions used by `play_machine()` with `play_player()`.

For example, `random_move()` and `possibility_victory()` were initially treated as if they were called by `play_player()`.

### Corrected Relationship

```text
play_player()
├── ask_column()
├── ask_line()
├── available()
│   ├── table_print()
│   ├── ask_column()
│   └── ask_line()
└── table_print()
```

By contrast:

```text
play_machine()
├── random_move()
├── possibility_victory()
├── possibility_victory()
└── table_print()
```

Another initial problem was treating an internal loop as though it were a function. The relevant user-defined function is `available()`; a loop inside that function is control flow, not another function.

### What This Error Shows

The learner could identify many important functions but did not yet consistently distinguish functions that execute near one another from functions that directly call one another.

This means the Function Map was partly being constructed from perceived execution order rather than strictly from direct call relationships.

### Evidence of Correction

The revised Function Map placed `available()` in the appropriate relationship with `play_player()` and recognized its calls to `table_print()`, `ask_column()`, and `ask_line()`.

This suggests that the call-relationship model was **correctable**, rather than absent.

### Retest Target

Use different short programs to test whether the learner can independently distinguish:

- Caller / Callee
- Function Map / Execution Path
- Direct call / Nearby execution

The Tic-Tac-Toe program itself should not be used as the primary retest because the correct relationships are now familiar.

---

## E-DATA — Data-Flow Identification Error

### Observed Error

The first selected "data" was:

```text
"Your turn!"
"Machine turn!"
```

These strings describe information presented to the user, but they do not provide a useful trace of the program's internal data movement for the selected player-move behavior.

### Why This Matters

This error shows a more fundamental problem than simply choosing an inconvenient example.

The learner was not yet consistently distinguishing information displayed by the program from data created, returned, passed, modified, stored, and later consumed by the program.

For KET, this is one of the most important baseline weaknesses because understanding unfamiliar code requires following data across function boundaries and state changes.

### Better Data-Flow Target

A more useful trace in this program is the player's move:

```text
user input
↓
ask_column() / ask_line()
↓
returned values
↓
move[]
↓
available(...)
↓
tabletop[][]
↓
updated board state
↓
later game-state / victory checking
```

### Retest Target

The next correction task should explicitly test whether the learner can identify and trace genuine program data through input, return values, local variables or arrays, function arguments and parameters, state modification, and downstream reads.

---

## E-FUNCVAL — Function / Return-Value Confusion

### Observed Error

After abandoning the output-string trace, the learner selected `if_victory()` but described it as a variable.

### Correct Model

`if_victory()` is a **function**. A call to that function produces a **return value**.

```text
board state
↓
if_victory()
↓
checks the current game state
↓
returns 'm', 'p', or 'n'
↓
caller uses that returned value
↓
program continues or reports a result
```

Different calls can produce different results because the board state may have changed:

```text
Call 1: if_victory() → 'n'
board changes
Call 2: if_victory() → 'n'
board changes
Call 3: if_victory() → 'm'
```

The function itself does not change from `'n'` to `'m'`. Each invocation computes and returns a value based on the current program state.

### What This Error Shows

The learner had not yet stabilized the distinction:

```text
function
↓
function call
↓
returned value
↓
caller uses returned value
```

This should not be treated merely as imprecise terminology. It affects the ability to reason about data flow across functions.

### Retest Target

Use new, short programs that require the learner to identify separately:

- Function
- Function call
- Argument
- Parameter
- Local variable
- Return value
- Program state

The learner should then explain how the returned value is consumed by the caller.

---

## E-META — Self-Correction Inconsistency

### Observed Error

The Function Map was later corrected, but the response to Q11 still stated:

```text
"It's correct."
```

That statement was inconsistent with the corrections already made elsewhere.

### Better Diagnosis

```text
Incorrect.

I originally thought play_player() called random_move() and
possibility_victory(), but those functions are called by
play_machine().

I also missed some of the direct calls made through available()
and if_victory().
```

### What This Error Shows

The learner was able to modify the answer after receiving evidence or feedback, but was less successful at explicitly reconstructing:

```text
What did I originally believe?
↓
What exactly was wrong?
↓
What evidence showed that it was wrong?
↓
What is my corrected model?
```

A corrected final answer alone does not show whether the learner understands why the original mental model failed.

### Retest Target

Future exercises should preserve the original prediction and require four separate fields:

```text
Original model:
Evidence:
Exact error:
Corrected model:
```

The original response should never be silently replaced.

---

# Overall Baseline

Assessment #1 does **not** indicate that the learner is unable to read unfamiliar code.

The learner could locate important functions, identify the general purpose of the program, construct a partial structural model, use execution and debugging evidence, and revise parts of the model after errors were identified.

However, the assessment showed that three layers of program understanding were not yet reliably integrated:

```text
Static call relationships
        ↓
Dynamic execution
        ↓
Data and state flow
```

The central baseline finding is therefore:

> **The learner can construct a rough structural model of small unfamiliar procedural code, but has not yet consistently connected call relationships, dynamic execution, and data/state flow into one accurate and verifiable mental model.**

---

# Priority for Correction

The next stage should not repeat the complete Tic-Tac-Toe assessment. Instead, correction should target three specific areas.

### 1. Caller / Callee vs. Execution Order

Use two or three short unfamiliar programs. For each program:

```text
Draw the Function Map.
Predict one Execution Path.
Explain why the two diagrams are not necessarily identical.
```

### 2. Function / Variable / Return Value / State

Use small examples in which one function computes a value and another function consumes it. The learner should identify each program element by role and explain the movement of the returned value.

### 3. Data Flow

Require a complete trace beginning with actual program data rather than terminal output:

```text
input
→ return value
→ local storage
→ argument
→ parameter
→ state modification
→ downstream read
→ program behavior
```

---

# Retest Principle

Correction on the original Tic-Tac-Toe program is not sufficient evidence that the underlying problem has disappeared.

Once the targeted correction is complete, the same concepts should be tested using **different code**.

The key question is not:

> Can the learner now give the correct answer for this Tic-Tac-Toe program?

The more useful question is:

> Can the learner independently retrieve and apply the corrected knowledge when the code, names, structure, and immediate support have changed?

That distinction provides the basis for the next KET correction and transfer tasks.

---

## Baseline Status

**Current strength:** Can begin independently navigating and modeling small unfamiliar procedural code.

**Primary weakness:** Does not yet reliably integrate function relationships, runtime behavior, and data/state movement.

**Next evidence needed:** Successful correction followed by accurate performance on changed code without relying on the corrected Tic-Tac-Toe example.

**No claim of mastery or programming-transfer ability is made from Assessment #1 alone.**
