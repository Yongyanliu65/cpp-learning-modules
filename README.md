# KET Module 1 v0.1
## Function Relationships and Execution Reasoning

> **Status:** Early-stage instructional module developed through an initial longitudinal pilot.  
> **Evidence boundary:** KET v0.1 has **not** been validated as an effective intervention across learners or settings.

## What is KET?

**KET (Knowledge-to-Engineering Transfer)** is an early-stage framework for examining and supporting whether a novice programmer can **independently retrieve and use previously learned knowledge in changed or unfamiliar code**.

The central question is not simply:

> Did the learner eventually get the answer right?

KET instead asks:

> Can the learner recognize what knowledge is relevant, make a prediction, apply that knowledge without unnecessary prompting, and verify the result with evidence?

Module 1 focuses narrowly on **function relationships and execution reasoning** in small C++ programs.

## Why this exists

A learner may be able to define a concept or complete a familiar exercise without being able to use that knowledge when the surface form changes.

KET therefore separates three things that are often collapsed:

1. **Knowledge** — can the learner explain or recognize the concept?
2. **Transfer** — can the learner retrieve and apply it in changed code?
3. **Independence** — how much help was required?

A correct answer after substantial help is useful learning progress, but it is not the same evidence as an independently correct delayed-transfer response.

## How it works

```text
Learn
  ↓
First Attempt
  ↓
Diagnose Error
  ↓
Targeted Repair
  ↓
Scaffold Fading
  ↓
Delay
  ↓
Changed Task
  ↓
Predict → Verify
  ↓
Independent Transfer?
```

The instructional sequence used in M1 is:

**Baseline → Diagnose → Explain → Targeted Correction → Scaffold Fading → Delay → Blind Transfer → Score correctness + hint cost**

Correction and transfer are deliberately separated. Performance during a teaching exercise is not treated as sufficient evidence that transfer has occurred.

## Start here

### If you are an instructor

Start with **`01-baseline-assessment.md`**.

1. Do **not** show the learner the correction materials first.
2. Preserve the learner's first response rather than replacing it after feedback.
3. Diagnose the specific relationship error.
4. Use only the correction material needed for that error.
5. Fade the scaffold rather than repeatedly drilling the same item.
6. After correction, use a delay—M1 suggests **48–72 hours**.
7. Administer **`05-delayed-blind-transfer.md`** with changed code.
8. Record both correctness and the highest hint level used.

Read **`instructor-guide.md`** before adapting the tasks or increasing difficulty.

### If you are a learner

These files are designed to be administered in sequence. Reading the correction and scoring files before taking the baseline or delayed-transfer assessment can contaminate the evidence. If possible, have another person administer the module.

### Try Assessment #1 Yourself

Want to try it yourself?

1. Open the Assessment file only.
2. Complete the assessment within 90 minutes without AI assistance.
3. Preserve your first answers.
4. After finishing, compare your reasoning with the First Response and Error Analysis.
5. Do not treat the provided response as an answer key; it is one learner's first attempt and contains errors.

## Module 1: What is being assessed?

M1 targets a bounded set of foundational relationships:

- **Caller vs. callee** — who directly invokes whom?
- **Argument vs. parameter** — what is supplied at a call site and what receives it at the function boundary?
- **Function Map** — what direct user-defined call relationships exist in the code?
- **Execution Path** — what actually happens for one particular run/input?
- **Call Stack** — which calls are active and unfinished at a particular moment?
- **Prediction vs. evidence** — does the learner form a model before execution and then compare it with runtime/debugger evidence?

M1 intentionally does **not** try to measure all of C++ or all of software engineering.

## What counts as evidence?

KET records both **correctness** and **hint cost (H0–H4)**.

| Hint level | Meaning |
|---|---|
| **H0** | No hint or outside help |
| **H1** | Directional hint; target concept not named |
| **H2** | Relevant concept named or explained |
| **H3** | Local answer, code location, or key relationship supplied |
| **H4** | Solution essentially provided |

For M1, **H0 delayed transfer** means that the learner applies the target relationship correctly in changed code after a delay without hints.

It does **not** mean that the learner has achieved general C++ proficiency or engineering independence.

The module also preserves:

**First response → First prediction → Hint level → Tool evidence → First divergence → Self-correction → Outcome**

This matters because **eventually correct ≠ independently transferred**.

See **`06-scoring-rubric-and-hint-levels.md`** for the operational rubric.

## What this does NOT prove

This release should not be interpreted as evidence that:

- KET is a validated pedagogy;
- KET improves learning across populations or settings;
- completing M1 demonstrates general C++ proficiency;
- completing M1 demonstrates repository-level engineering independence;
- an H0 result in one bounded task automatically generalizes to real software projects.

The current release was developed and iterated through an **initial longitudinal pilot**. The public materials are redesigned instructional artifacts rather than a published experimental dataset.

Future validation would require additional learners, predefined procedures, systematic comparison, and appropriate research methods.

## Repository structure

```text
module-01-function-relationships/
├── README.md
├── 01-baseline-assessment.md
├── 02-error-explanation.md
├── 03-targeted-correction.md
├── 04-focused-correction-scaffold-fading.md
├── 05-delayed-blind-transfer.md
├── 06-scoring-rubric-and-hint-levels.md
├── instructor-guide.md
└── LICENSE
```

## File guide

| File | Purpose |
|---|---|
| `01-baseline-assessment.md` | Expose the learner's initial mental model without teaching |
| `02-error-explanation.md` | Explain only relationship distinctions implicated by observed errors |
| `03-targeted-correction.md` | Provide controlled repair practice |
| `04-focused-correction-scaffold-fading.md` | Test repaired relationships while reducing prompts |
| `05-delayed-blind-transfer.md` | Test retrieval and application in changed code after a delay |
| `06-scoring-rubric-and-hint-levels.md` | Record errors, transfer level, and assistance cost |
| `instructor-guide.md` | Explain administration, adaptation, difficulty control, and evidence boundaries |

## Design principles

### Diagnose before teaching

Preserve the first reasoning attempt and identify the first meaningful divergence before correction.

### Correction is not transfer

Correct performance while definitions, examples, or prompts are visible is not sufficient transfer evidence. M1 therefore uses changed code and delayed assessment.

### Prediction before verification

When runtime or debugger evidence is used:

**Prediction → Evidence → First divergence → Revised model**

The original prediction should remain visible.

### Control difficulty

Task difficulty can increase through several dimensions:

**Code size × File distance × Concept novelty × Navigation freedom × Tool burden × Task openness**

After a passed task, a clean transfer assessment should normally add only **one major new complexity dimension**.

Real GitHub code is not automatically a better assessment if it introduces several unlearned mechanisms at once.

## Status and roadmap

### v0.1 — Module 1

**Function Relationships and Execution Reasoning**

Current status: public pilot module.

### Planned directions

Later modules may address:

- data and state flow;
- debugging as verification;
- unfamiliar-code reading;
- progressively more authentic engineering tasks.

Modules should be added only when prerequisite knowledge and evidence chains are sufficiently developed. The roadmap is therefore **capability-gated rather than calendar-gated**.

## Use and adaptation

Instructors may adapt the surface details of tasks, but should preserve the evidence logic:

- do not teach before the baseline;
- preserve first responses;
- record assistance;
- separate correction from transfer;
- change the surface form of transfer tasks;
- avoid introducing multiple unlearned prerequisites at once.

## Privacy

The public repository contains redesigned teaching materials only. Identifiable learner responses and private longitudinal performance records should remain outside the public repository.

## License

MIT License. See `LICENSE`.

---

**Version:** v0.1  
**Release stage:** Early pilot / instructional prototype  
**Last updated:** September 2026
