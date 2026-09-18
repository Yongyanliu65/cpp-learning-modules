# **C++ Real-Code Assessment #1** 

**Time:** 90 minutes **Difficulty:** 3/10 

**Goal:** Test whether you can independently understand the structure and execution of unfamiliar C++ code. 

**Repository:** use the assigned GitHub Tic-Tac-Toe repository. **File:** main.cpp 

# **Rules** 

You may use: 

- GitHub code navigation/search 

- VS Code 

- compiler 

- debugger 

- LearnCpp or documentation to look up unfamiliar C++ syntax 

Do **not** use: 

- ChatGPT/AI to explain the repository 

- online analyses of this specific project 

- generated call graphs 

- somebody else's explanation 

You do **not** need to understand every line. 

# **0–15 min — First Read: Build the Big Picture** 

Do **not** run the program yet. 

Read main.cpp from beginning to end. 

Answer: 

**Q1.** Where does execution begin? 

**Q2.** List all user-defined functions you can identify. 

Use: 

Function: Purpose: Describe each purpose in **your own words** . One sentence is enough. **Q3.** What do you think the overall program flow is? Maximum 5–8 lines. Example format only: Program starts → ... → ... → ... 

Do not worry yet whether your prediction is completely correct. 

# **15–30 min — Function Relationships** 

Now focus on **who calls whom** . 

For every important function answer: 

Function: 

Caller(s): Callee(s): 

Then draw a **Function Map** . 

Use a structure such as: 

main 

├── functionA │ ├── functionB │   └── functionC └── functionD 

# **Q4** 

Are there any functions that: 

- are called from several places? 

- call several other functions? 

- do not call any user-defined functions? 

Identify them. 

# **Important** 

Do **not** draw functions underneath each other simply because they execute one after another. 

Your arrows must mean: 

A actually calls B. 

# **30–45 min — Predict an Execution Path** 

Choose **one player's move** . 

Start from the point where the program is waiting for the player to make a move. 

Without running the program, answer: 

**Q5.** What functions do you predict will execute? 

Write the sequence. 

Execution Path: 

→ ... 

→ ... 

Include returns when useful: 

A 

→ B 

→ C 

→ B 

→ A 

**Q6.** Identify at least one function that exists in your Function Map but that you predict will **not** execute during this particular path. 

Explain why. 

This tests whether you understand: 

Function Map ≠ Execution Path. 

# **45–60 min — Data Flow** 

Choose **one important piece of data** yourself. 

Good candidates might include: 

- player's chosen position 

- board state 

- current player 

- game result 

Do not choose based on what you think the instructor wants. Choose what seems important to understanding the program. 

# **Q7** 

Trace that data. 

Answer: 

Where is the data first created/read? 

↓ 

Which variable holds it? 

↓ 

Which function receives it? 

↓ 

Which functions read it? 

↓ 

Which function modifies it? 

↓ 

Where is the changed value used afterward? Then draw a simple **Data Flow diagram** . Example format: 

input ↓ variable A ↓ function X ↓ variable/state B ↓ function Y 

# **Q8** 

Was there any point where the same data changed: 

- variable name, 

- scope, 

- representation, 

- or value? 

Explain. 

# **60–75 min — Run and Debug** 

Only now clone/download the repository and compile it locally. First run it normally. 

Compare the actual behavior with what you predicted. Then choose a useful function and place a breakpoint inside it. Perform the same player action you analyzed earlier. 

When execution stops: 

# **Q9** 

Record: 

Current function: 

Call Stack: 

1. 2. 

3. ... Then answer: 

# **Why is each function currently on the Call Stack?** 

# **Q10** 

Use Step Into / Step Over as appropriate. 

Check whether your predicted Execution Path was correct. 

Write: 

My original prediction: 

Actual execution: 

Difference: 

**Do not erase the original prediction.** 

# **75–90 min — Diagnose Your Own Understanding** 

This is the most important section. 

Return to your original Function Map, Execution Path and Data Flow. 

Mark corrections rather than silently replacing the originals. 

# **Q11 — Function Map** 

Was your original Function Map correct? 

Correct: 

Incorrect: 

Missing: 

If something was wrong, explain **why you originally misunderstood it** . 

# **Q12 — Execution Path** 

What was the biggest difference between your predicted execution and the actual execution? 

If there was no meaningful difference, say so and explain how you verified it. 

# **Q13 — Data Flow** 

Could you trace your selected data from beginning to end? 

If you lost track of it somewhere, identify the exact line/function where that happened. 

# **Q14 — Hardest Function** 

Which function was hardest to understand? 

Why? 

Do not just say "the code was complicated." 

For example: 

I could identify its callers, but I could not understand 

how ___ affected ___. 

# **Q15 — Your Navigation Method** 

Suppose tomorrow I give you another unfamiliar C++ program. 

Write the steps **you would actually use** to understand it. 

Do not copy the terminology from the assignment unless that really reflects what you would do. 

# **What to submit** 

Submit **one answer document** containing: 

1. Function list + responsibilities 

2. Original Function Map 

3. Original predicted Execution Path 

4. Data Flow 

5. Debugger Call Stack 

6. Actual Execution Path 

7. Corrected Function Map (if needed) 

8. Answers to Q11–Q15 

Also include approximately how long you spent: 

Reading: Function Map: Execution Path: Data Flow: Debugger: 

Total: 

Do not spend more than **90 minutes** trying to make the submission perfect. 

