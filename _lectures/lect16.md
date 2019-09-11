---
num: Lecture 16
lecture_date: 2019-09-10
desc: "Final Review"
ready: false
pdfurl:
---

```python
# CS 8, 9-10

''' CS 8 Final Review
- Exam is cumulative (covers everything throughout the session with an
emphasis on post midterm material).
- Logistics
    - Bring a writing utensil
    - No electronic devices
    - Closed book / notes
- Structure of final is similar to the midterm. Types of questions:
    - Evaluate expressions / types
    - Given code, what is the output
    - Short answer / definitions
    - Read / write assert statements
    - Complete function definition
    - Fill-in-the-blank
    - True / False (if false briefly state why)
- General advice for the exam
    - Read instructions carefully - pay close attention to what is being
    asked
    - Double-check your work

Advice on how to prepare
- Lecture notes (important to know topics, examples, concepts)
- Understanding labs and being able to implement them
- Reading the text book for additional details / understanding
    - Additional practice problems at the end of each chapter is good.
- Homework exercises
- Prototyping - "I wonder how python behaves when ...", write simple
examples.
    - Helps with code practice as well as understanding the language and
    edge cases.
'''

''' Overview of topics after midterm
- Double (Nested) for loops
    - for within a for loop
    - Good for traversing a 2D list, characters in a list of strings, ...
- While Loop
    - while BOOLEAN_EXPRESSION:
        statement(s)
    - Similar to for loop, but can loop forever
    - break, continue, pass
- 2D Lists
    - Lists within lists
    - Useful for embedding data or having a "grid" format
    - Examples: tic-tac-toe, screen of pixels,
    - Double for loops are useful for iterating through all the "coordinates"
- String methods
    - find, startswith, endswith, count, replace, upper, lower, ...
    - string formatting
        - .format method, { : }
- Random
    - randrange, shuffle, sample, etc.
- File I/O
    - Read file (infile = open('example.txt', 'r'))
        - infile.read() - reads the entire file
        - infile.read(n) - reads n characters
        - infile.readlines() - reads lines into a list
        - infile.readline() - reads one line at a time
        - for a_line in infile (a_line represents a line in the file)
    - Write file (outfile = open('example.txt', 'w'))
    - Appending file (outfile = open('example.txt', 'a'))
- Dictionaries
    - key / value pairs
    - Creating a dictionary
    - Adding to a dictionary
    - Dictionary methods
        - D.pop(key) # remove key/value and return the value
        - D.update(D2) # combines values in D and D2
        - D.get(key) # returns item if it exists. If not, returns None or
            some default value
        - D.keys() # dict_values([LIST OF KEYS])
        - D.values() # dict_values([LIST OF VALUES])
        - D.items() # dict_items([LIST OF KEY, VALUES])
    - Performance of Dictionary vs. a list
- Sets
    - Collection of items with no duplicates
    - Creating an empty set (set())
    - Set operators
        - in, not in, combine(|), intersection(&), difference(-), unique(^)
    - Set comparators
        - ==, !=, proper subsets (<,>), subset(<=,>=)
    - Set methods
        - .add, .remove (what happens if it doesn't exist), .discard, .clear
- Embedded structures
    - Dictionary map to dictionary, dictionary map to set, etc.
- Recursion
    - Properties
        - Base case
        - Recursive calls getting "closer" to base case
    - Example (in class and lab)
        - Print values
        - Reconstruct lists and strings (reverse or in order)
        - compute values (factorial, fibonnaci, ...)
        - ...
'''

''' Topics covered before midterm
* Python data types
* Arithmetic operators
* Python functions
* Comparison operators
* Boolean operators
* Strings
* Lists
* Tuples
* User-defined functions
* Namedtuples
* Testing (assert / pytest)
* Conditional statements
* For loops
* Nested control structures
* Accumulator Patterns
'''
```