# C++ Real-Code Assessment #1 --- Response

**Assessment:** `C++_Real_Code_Assessment_01`\
**Response file:** `C++_Real_Code_Assessment_01_Response.md`

> This file preserves my original assessment responses in a separate
> document so that the assessment prompt remains reusable and the
> response can be reviewed independently.

## Q1. Where does execution begin?

It begins with the `int main()` function on line 352.

## Q2. User-defined functions and purposes

-   `reset_table()` --- It resets the whole table for the next game.
-   `table_print()` --- Prints the table to the user.
-   `ask_column()` --- It asks the user to select the column they want
    to play and returns their valid choice.
-   `ask_line()` --- It asks the user to pick the line they want to play
    and returns the valid choice.
-   `available(int *line, int *column)` --- Keeps asking the user until
    the chosen unit is still available.
-   `play_player()` --- First asks the user to type in the column and
    line they want to put and uses the available function to check
    whether it's usable. Records the user's move and prints the table.
-   `possibility_victory()` --- Checks the possibility that one user can
    win and returns the result.
-   `random_move(int *line, int *column)` --- Fills in the corners first
    and then checks all other spaces to move.
-   `play_machine()` --- Lets the user know it is the machine's turn and
    tests whether either the user can win next round or the machine can
    win this round. After the move, it prints out the table.
-   `check_victory()` --- Checks if anyone in the game won; if not,
    returns false.
-   `if_victory()` --- If the O player won, tells the player they won.
    If the X player won, returns machine. Otherwise, returns `n` for
    nobody.
-   `player_first()` --- Makes the player move first, responds to the
    user by defense, and returns corresponding output if anyone wins the
    game or there is a draw.
-   `machine_first()` --- Lets the machine move first and outputs the
    corresponding sentence if anyone wins the game.
-   `who_starts()` --- Asks the user whether he/she wants to start first
    until it gets a valid response.
-   `play_again()` --- Asks whether the user wants to play again until
    it gets a valid response.
-   `main()` --- Determines who starts first, lets both players play,
    determines whether to play again, and ends.

## Q3. Predicted overall program flow

Program starts\
→ `who_starts()` decides who starts first\
→ `player_first()` / `machine_first()` prints the table first\
→ loop `play_player()` / `play_machine()` to simulate a real game\
→ `play_player()` asks the user's move, and `play_machine()` checks
whether it or the user can win and makes the move\
→ `if_victory()` checks whether either the user or machine won and
outputs the corresponding announcement\
→ `play_again()` asks the user whether to start a new game and repeats;
if not, the program ends

## Q4. Function relationships

`table_print()` is called from `player_first()`, `play_player()`,
`play_machine()`, and `machine_first()`.

`player_first()` calls `table_print()`, `play_player()`,
`play_machine()`, and `if_victory()`.

`machine_first()` calls the same functions as `player_first()`.

`play_player()` and `play_machine()` both call `random_move()`,
`possibility_victory()`, and `table_print()`.

Basic functions like `reset_table()`, `table_print()`, `ask_column()`,
`ask_line()`, `available()`, `possibility_victory()`, `random_move()`,
`check_victory()`, `who_starts()`, and `play_again()` don't use any
other user-defined functions.

### Original Function Map

``` text
main
├── who_starts
├── player_first()
│   ├── table_print()
│   ├── play_player()
│   │   ├── ask_column()
│   │   ├── ask_line()
│   │   ├── check_available loop
│   │   │   ├── table_print
│   │   │   ├── ask_column
│   │   │   └── ask_line
│   │   └── table_print
│   ├── play_machine()
│   │   ├── random_move
│   │   ├── possibility_victory
│   │   └── table_print
│   └── if_victory
│       └── check_victory
│
├── machine_first
│   ├── table_print
│   ├── play_player()
│   ├── play_machine()
│   └── if_victory()
│
├── play_again() Y/N
if no
└── reset_table
```

## Q5. Predicted execution path

I chose player first.

``` text
main()
→ who_starts()
→ player_first()
→ table_print()
→ play_player()
→ check whether (2,2) is taken
→ play_machine()
→ play_player()
→ table_print()
→ play_machine()
→ play_player()
→ if_victory()
→ play_machine()
→ if_victory()
→ play_player()
→ if_victory()
→ play_machine()
→ if_victory()
→ machine won
```

## Q6. Function predicted not to execute

For example, the `play_player()` in line 267 will not execute, since I
assume the player will lose to the machine, so he/she won't have the
next step. Although this function is included in `player_first()`, it
will not execute when running.

## Q7. Data flow

I chose the `if_victory()` variable. It's first created in line 201 and
used in line 248 to determine whether it is the user win in function
`player_first`. The `if_victory()` variable will hold it always. In
function `play_first`, the `if(if_victory == "m")` function will read
it. It will still be the `if_victory()` function to modify itself from
either `m` to `p` or `p` to `m`.

## Q8. How the data changes

Honestly, the data will not change, since when this data comes out, it
is already determined who wins the game. There will be several checks,
but only one change from empty to either `m` or `p` and announce the
result.

## Q9. Debugger call stack

I set `play_player()` as the breakpoint, and it stops at:

``` cpp
printf("Your turn!")
```

It shows:

``` text
main()
→ player_first()
→ play_player()
```

`main()` is the first function of all. `player_first()` stands after
`main()` and calls the more basic function `play_player()` when it is
the player's turn. Then it outputs the message.

## Q10. Predicted vs. actual execution

My original prediction is `main()` to `player_first()`, then to
`play_player()`, because `player_first()` calls the `play_player()`
function to specify every step of the player.

## Q11. Was the original Function Map correct?

It's correct.

## Q12. Biggest difference between predicted and actual execution

I examined it by call stack flow and by actually running it.

## Q13. Could I trace the selected data from beginning to end?

The output on terminal is printed every time it is my turn, so I didn't
lose it.

## Q14. Hardest function

It's the `play_machine()` function. Since I don't know the tic-tac-toe
algorithm too much, I cannot determine why it's the machine's best
choice after every user's pick on the board.

How does the designer know the machine should go this way to try its
best?

## Q15. My navigation method

I would go by order in the `main()` function first to see the greatest
branches. Then I'll go to every big function to see what other small
functions it called and go into those more specific small functions
again to examine the actual algorithms inside them.

Lastly, I'll run and debug it to see the actual workflow and examine how
the algorithm reflects on the output I see.
