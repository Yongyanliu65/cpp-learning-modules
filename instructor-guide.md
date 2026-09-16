# Instructor Guide
## KET Module 1 v0.1

### 1. What this module is for

M1 targets foundational code-reading relationships: direct function calls, function boundaries, static structure, one-run execution, and active runtime calls.

It should be used before asking a novice to navigate a complex repository.

### 2. Administration sequence

Use:

**Baseline → Diagnose → Explain observed errors → Targeted correction → Scaffold fading → Delay → Blind transfer**

Do not turn every error into a long lesson. Repair the smallest model that explains the observed mistake.

### 3. Task-generation rule

A correction set should usually contain **3–5 clear questions**.

Each question should map to an observed error. Increase difficulty only slightly. A useful internal planning record is:

```text
Observed Error
→ Hypothesized Gap
→ Target Skill
→ Previous Passed Level
→ One New Difficulty
→ Task
→ Pass Evidence
```

### 4. Difficulty is multidimensional

Do not use code length as the only difficulty measure.

Consider:

- prerequisite load;
- code size;
- file distance;
- concept novelty;
- navigation freedom;
- tool burden;
- task openness.

**N+1 rule:** after a passed task, add at most one major complexity dimension in the next clean transfer assessment.

### 5. Separate task types

**Diagnostic:** expose the learner's first model. No teaching.

**Correction:** explanation and scaffolding are allowed.

**Transfer:** changed surface/context, reduced cueing, preferably delayed.

Correct performance during correction is not sufficient evidence of transfer.

### 6. Prediction before evidence

When verification is part of a task:

1. preserve the prediction;
2. collect runtime/debugger evidence;
3. identify the first divergence;
4. revise the model.

Do not allow the learner to overwrite the original prediction.

### 7. Real-code caution

Do not treat "real GitHub code" as automatically better.

If a task simultaneously introduces unfamiliar language mechanisms, libraries, build systems, repository navigation, and toolchain problems, poor performance becomes difficult to interpret.

Before a real-code transfer task, check whether the core mechanisms required for a correct answer have already been learned.

### 8. What to do after a failed transfer task

Do not immediately repeat it.

Use:

**first divergence → specific gap → minimal correction → delay → same-level, different-surface transfer**

Do not automatically downgrade the learner or reteach the entire topic.

### 9. Public vs. private data

Public releases should contain redesigned tasks, scoring rules, and anonymized examples only.

Keep raw learner responses, identifiable longitudinal records, timestamps, and individual performance trajectories in a private research archive.

### 10. Claims

Appropriate:

> "This is an early-stage instructional module developed and iterated through an initial longitudinal pilot."

Not appropriate from one learner:

> "This module has been validated to improve programming transfer."

### 11. Transition after M1

M1 completion does not imply repository-level engineering independence.

A later module may target data/state flow, debugging/verification, unfamiliar-code navigation, or modification. Real-environment difficulty should increase only after prerequisite knowledge has accumulated.
