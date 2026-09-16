# 06 — Scoring Rubric and Hint Levels

This rubric separates **correctness**, **transfer**, and **independence**.

## Error codes

| Code | Meaning |
|---|---|
| E-CALL | Direct caller/callee relationship error |
| E-SEQ | Execution order substituted for call relationship |
| E-ARGPARAM | Argument/parameter confusion |
| E-STATIC-DYNAMIC | Function Map vs. specific Execution Path confusion |
| E-STACK | Active-call / Call Stack model error |
| E-FUNCVAL | Function, function call, returned value, or variable conflated |
| E-BRANCH | Branch-specific execution error |
| E-DATA | Data movement across boundaries traced incorrectly |
| E-STATE | State change or mutation misunderstood |
| E-META | Self-correction or impact reasoning is inconsistent |

## Hint cost

| Level | Description |
|---|---|
| H0 | No hint or outside help |
| H1 | Directional hint; no concept named |
| H2 | Relevant concept named or explained |
| H3 | Local answer, code location, or key relationship supplied |
| H4 | Solution essentially provided |

Record the **highest** level used.

## Transfer levels

| Level | Operational description |
|---|---|
| K0 | Does not recognize the relevant relationship |
| K1 | Recognizes after a cue |
| K2 | Reproduces in a familiar form |
| K3 | Uses it in a changed but near-transfer task |
| K4 | Recognizes it in unfamiliar bounded code |
| K5 | Applies it in an engineering task with guidance |
| K6 | Independently transfers it in an engineering task |
| K7 | Transfers across substantially different contexts |

These levels are working operational categories for this module, not validated psychometric scales.

## M1 closure criteria

A strong M1 delayed-transfer result should show:

- no core direct-call error;
- correct caller/callee reasoning;
- correct argument/parameter reasoning when present;
- static call structure distinguished from one-run execution;
- active unfinished calls understood, including `void` functions;
- relevant relationships retrieved without the worksheet naming them as a checklist;
- prediction compared with runtime/debugger evidence;
- H0 if claiming independent delayed transfer.

Minor transcription or wording imprecision should not automatically fail a result if the operational model is correct.

## Important evidence rule

**Eventually correct is not the same as independent transfer.**

Preserve:

1. first response;
2. first prediction;
3. hint level;
4. evidence observed;
5. first divergence;
6. self-correction;
7. final outcome.

If hint level was not recorded, write **Not recorded**. Never reconstruct H0 later.
