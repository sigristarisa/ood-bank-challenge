## Requirements

You should be able to interact with your code via a JavaScript REPL - Node REPL or browser console (You don't need to implement a command line interface that takes input from STDIN.)
Deposits, withdrawal.
Account statement (date, credit or debit amount, balance) printing.
Data can be kept in memory (it doesn't need to be stored to a database or anything).

### Acceptance criteria

Given a client makes a deposit of 1000 on 10-01-2012
And a deposit of 2000 on 13-01-2012
And a withdrawal of 500 on 14-01-2012
When she prints her bank statement
Then she would see:

date || credit || debit || balance
14/01/2012 || || 500.00 || 2500.00
13/01/2012 || 2000.00 || || 3000.00
10/01/2012 || 1000.00 || || 1000.00

## Noun & Verb

### Noun

date, credit or debit amount, balance

### Verb

deposit, withdrawal, print

## Domain Model

| Class | Properties                         | Methods                     | Outputs                           | Memos                                                   |
| ----- | ---------------------------------- | --------------------------- | --------------------------------- | ------------------------------------------------------- |
| Bank  | balance @Number                    |                             |                                   |                                                         |
|       | transactions @Array [@transaction] |                             |                                   |                                                         |
|       |                                    | deposit (amount @Number)    | No output                         | adds @amount to @balance, push to @transactions[]       |
|       |                                    | withdrawal (amount @Number) | No output                         | subtract @amount from @balance, push to @transactions[] |
|       |                                    | date()                      | dd/mm/yyyy @String                | returns the current date                                |
|       |                                    | print()                     | transactions @Array[@transaction] | loop through and print out the transactions             |