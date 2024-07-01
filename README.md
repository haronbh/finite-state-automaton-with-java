# finite-state-automaton-with-java

## Description
The Java program implements a finite state automaton (FSA) to validate whether a given string is a valid identifier based on specific rules. An identifier can start with a letter and can contain letters, digits, and underscores. It cannot start with a digit or underscore and cannot contain any other characters. The program checks each character in the input string against predefined rules to determine its validity as an identifier.

## Automaton Method
The program uses a state-based approach to validate identifiers:

Q0: Initial state
Q1: State after reading the first character (letter)
Q2: State for continuing valid characters (letters or digits)
Q3: State for digits after the first character (letter)
Q4: State for underscores after a letter or digit
Q5: Trap state (invalid state)
| Current State | Letter (0) | Digit (1) | Underscore (2) | Other (3) |
|---------------|------------|-----------|----------------|-----------|
| Q0            | Q1         | Q5        | Q5             | Q5        |
| Q1            | Q1         | Q2        | Q4             | Q5        |
| Q2            | Q2         | Q2        | Q4             | Q5        |
| Q3            | Q2         | Q2        | Q4             | Q5        |
| Q4            | Q4         | Q4        | Q4             | Q5        |
| Q5            | Q5         | Q5        | Q5             | Q5        |

