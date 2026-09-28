# KET Focused Correction #2
## Error Analysis

### Purpose

This document analyzes Focused Correction #2 in relation to the baseline errors identified in Assessment #1. It is not an answer key and does not replace the learner's original response.

The main question is not whether every worksheet item was correct. The question is which earlier reasoning problems improved, which remained imprecise, and which were not actually retested.

---

# 1. E-CALL — Call Relationship Error

## Baseline

Assessment #1 showed confusion between functions that execute near one another and functions that directly call one another.

## Evidence in Correction #2

The learner correctly identified:

```text
main() → calculate()
calculate() → show()
```

and correctly rejected a direct `main() → show()` relationship.

The learner also correctly represented:

```text
main()
├── read()
├── transform()
└── output()
```

rather than converting execution order into a chain of direct calls.

In the final memory check, the learner again correctly stated:

> Function A is the caller, and B() is the callee.

## Remaining Precision Issue

The statement:

> To identify a caller, I should look for the function map.

is imprecise. The source-code evidence is the call expression inside the caller's body.

### Status

**E-CALL: substantially improved in this correction task.**

A changed-code retest is still needed before treating the correction as transfer.

---

# 2. Argument ↔ Parameter

The learner consistently identified:

```text
argument: today
parameter: temperature
```

and:

```text
argument: total
parameter: value
```

including the reference example where modifying `value` changes `total`.

The verbal explanation remained informal, but the relationship was reproduced correctly from memory.

### Status

**Argument/Parameter distinction: largely stable in this correction task.**

---

# 3. Function Map vs. Execution Path

The learner correctly constructed a Function Map containing both possible branches:

```text
main()
└── evaluate()
    ├── success()
    └── failure()
```

while correctly predicting the specific path for `82`:

```text
main() → evaluate(82) → success()
```

This is meaningful improvement: the learner could distinguish a static call relationship from a path taken in one run.

## E-MAPDEF — Remaining Definition Error

The learner wrote:

> Yes, since all defined functions have to be included in the function map.

and later:

> The map of all defined functions.

This is overgeneralized. A Function Map in this exercise represents **direct function-call relationships**, not merely the existence of definitions.

A defined-but-never-called function is the cleanest changed-code retest for this error.

### Status

**Function Map construction: improved.**  
**Function Map verbal definition: not yet fully stable.**

---

# 4. Call Stack

The learner predicted:

```text
triple()
adjust()
run()
main()
```

while stopped inside `triple()`, and debugger verification matched the prediction.

The learner also correctly explained that `main()` and `triple()` can both be active even though `main()` does not directly call `triple()`.

## E-STACKDEF — Remaining Definition Error

The learner later defined Call Stack as:

> What functions have not been returned a value yet.

This is too narrow. `void` functions can also remain active on the stack.

A more accurate model is:

> The Call Stack shows active function calls that have started but have not yet returned.

### Status

**Call Stack construction: correct in this task.**  
**Call Stack verbal model: still imprecise.**

---

# 5. Scaffold-Removed Evidence

Without the earlier definitions as a checklist, the learner independently used both Function Map and Execution Path to explain the `acceptable()` example.

This is stronger evidence than simple terminology fill-ins, but it remains **same-session correction evidence**. It is not delayed transfer evidence.

---

# 6. Relationship to Assessment #1 Error Codes

## E-CALL

**Improved.** Direct caller/callee relationships were handled correctly across several examples.

## E-DATA

**Not sufficiently retested.** Argument/parameter work touches data movement, but the worksheet did not require the full chain:

```text
input
→ return value
→ local storage
→ argument/parameter
→ state modification
→ downstream read
```

## E-FUNCVAL

**Some positive evidence, but not resolved.** The learner reasoned about function calls and values, but the original function-versus-returned-value confusion was not directly retested in a comparable way.

## E-META

**Not adequately retested.** The debugger prediction happened to be correct, so the exercise did not strongly test whether the learner could diagnose an incorrect prediction as:

```text
original model
→ evidence
→ exact error
→ corrected model
```

---

# 7. Overall Interpretation

A defensible conclusion is:

> **After focused practice, the learner showed substantially better performance in identifying direct caller/callee relationships, distinguishing arguments from parameters, separating Function Maps from specific Execution Paths, and constructing a Call Stack for a short unfamiliar example. However, verbal definitions of Function Map and Call Stack remained somewhat imprecise, and the earlier Data Flow, Function/Return-Value, and self-correction problems were not fully retested.**

Successful correction within the same training session is not the same as transfer.

---

# 8. Next Retest

Do **not** repeat this worksheet.

The next changed-code task should ideally contain:

1. a function that is defined but never called;
2. a conditional branch not taken in the selected run;
3. both `void` and value-returning functions in one nested call chain;
4. a returned value passed to another function or used to update state.

The learner should reconstruct, with reduced scaffolding:

```text
direct call relationships
↓
specific execution path
↓
active call stack
↓
data/value movement
```

---

# Correction #2 Status

**Clearly improved**
- Caller / Callee
- Argument / Parameter
- Function Map construction
- Execution Path construction
- Call Stack construction

**Still imprecise**
- Function Map definition
- Call Stack verbal model

**Not sufficiently retested**
- Full Data Flow
- Function vs. returned value
- Self-diagnosis after an incorrect prediction

## Evidence Boundary

This record documents performance during a focused correction exercise. It does not establish mastery, general programming ability, or transfer to substantially different code.

The next meaningful evidence must come from a changed-code retest.
