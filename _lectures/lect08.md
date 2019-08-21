---
num: Lecture 8
lecture_date: 2019-08-21
desc: "More on while Loops, Midterm Review"
ready: false
pdfurl:
---

```python
# CS 8, 8-21

# A number guessing game

"""
magicNumber = 40
guess = input("Guessing Game!\nPlease enter an int between 0  - 100 \
(type 'exit' to end game): ")

while True:
    if guess == "exit":
        print("Game Over")
        break
    number = int(guess)
    if number < 0 or number > 100:
        guess = input("Invalid number. Please try again: ")
        continue
    if number < magicNumber:
        guess = input("Too small. Please try again: ")
        continue
    if number > magicNumber:
        guess = input("Too large. Please try again: ")
        continue
    if number == magicNumber:
        print("Winner winner chicken dinner! You guessed", magicNumber)
        break
print("Done.")
"""

'''
Midterm Review

- Logistics
    - Bring your studentID and a writing utensil
        - preferably in ink or dark led
    - No electronic devices
    - No book
    - No notes

- Format
    - Will be a mix of questions
    - read code / write output
         - You need to tell me what Python will output
    - Some short answer
    - Some fill in the blank
    - Write a segment of code that does ...
        - Complete a function definition according to the specs...

Python Data Types
    - int, float, bool, list, tuples, namedtuples (custom), str, ...
    - type(x)
    - print("str") # print() removes quotes, but quotes are necessary
                    # to express string types
        - There is a difference between "2" and 2

Arithmetic operators
    - +, -, *, /, **, //, %, ...
    - Depending on the operator, different types can be returned
        - 2 / 2 # float
        - 2 * 2 # int
        - 2.0 * 2 # float
        - ...

Python Functions
    - print, len, str, int, float, input, ...

Comparison operators
    - ==, !=, >=, <=, >, <, ...

Boolean Operations
    - not, and, or
    - x < 100 and x > 90 (90 - 100)

Strings
    - Collections of characters
    - indexing [1], [-1]
    - slicing [1:3]
        - "UCSB"[1:3] # 'CS'
    - indexing errors
        - "UCSB"[4]
    - Concatenation +
    - Multiply * (int)

Collections
    - Lists (Mutable)
        - Functions (.append, .sort, .pop, ...)
    - Tuples (Immutable)
    - "in" operator (check if something is in a collection)

Functions
    - Defining a function: def NAME(PARAMETER(s)):
    - Indentation of statements within functions
    - Return statements
        - returning a value vs. returning "None"

Namedtuples
    - Defining / Modeling objects with namedtupoes
    - Constructing namedtuples
    - Accessing namedtuples with attribute's name
    - Immutable

Testing
    - pytest
        - pytest functions start with "test_" and use assert
        - Won't require command line knowledge for the midterm

Conditional Statements
    - if, else, elif (else if)

For Loops
    - for VARIABLE in COLLECTION:
        STATEMENT(s)
    - range
        - range(4), range(2,4), range(1,4,1)

Nested Control Structures
    - for within an if within another within a for ...

Accumulator Pattern
    - counting elements (or aggregating values)
    - keep track of certain conditions (largest, smallest, min, ...)
    - assert
'''
```