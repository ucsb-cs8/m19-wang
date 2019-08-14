---
num: Lecture 5
lecture_date: 2019-08-14
desc: "Boolean Expressions, Conditionals"
ready: false
pdfurl:
---

```python
# CS 8, 8-14-19

""" Boolean
x = True
y = False

print(not x)
print(not y)

print(x and y)
print(x or y)

Conditional Statements
- The ability to tell the computer to perform one thing in a situation
vs another thing in another situation.
    - Enables programmers to customize the "flow" of execution

Syntax:

if BOOLEAN_EXPRESSION:
    STATEMENT(s)

- 1st evaluate if BOOLEAN_EXPRESSION is True or False
- If true, execute the STATEMENT(s)
- If False, skip the statements and continue executing the code after
the if statement
- INDENTATION is important! It tells python which statements are
executed in certain conditions.

# Example
milesDriven = 100
print("Should you pull over and fill up you gas tank?")
if milesDriven > 200:
    print("Yes, you need gasoline") # Part of the if statement
print("Drive safe") # Not part of if statement (not indented)
"""

# If we want to only do something in the event that the boolean
# condition is false, then we can include an else: portion

'''
if BOOLEAN_EXPRESSION:
    STATEMENT(s) #1
else:
    STATEMENT(s) #2

- 1st evaluate BOOLEAN_EXPRESSION
- if true, execute statements #1 and then continue execution after
if / else blocks
- if false, execute statements #2 and then continue execution after
if / else blocks


# Example of nest expressions / functions / etc to form your
# boolean expression

if int(input("What's your age?")) >= 21:
    print("You can drink alcohol, but do so responsibly")
else:
    print("Can't drink alcohol yet ... how about some OJ")
print("Enjoy the party")
'''
"""
Repetition and Loops
- Besides conditions, another useful task for a program is to repeat
the same thing over and over and over ...
- A FOR loop is like looping through a collection and doing something
for each item.

Syntax of FOR loops

for VARIABLE in COLLECTION:
    STATEMENT(s)

- Assigns an element in the collection to the variable (starts
with the 1st item COLLECTION[0])
    - Executes the STATEMENT(s)
- Assigns the next item in the collection to the variable
    - Executes the STATEMENT(s)
    ... and so on...
- Continues program execution when there are no more items in the
collection

# A simple example using a "For" loop
name = "Richert"
for c in name:
    print(c)
    # print(c, end=" ") can use if we want each character in one line...

# Another example with multiple types in a list (collection)
list = [[1,2], "Rich", 4.2, 100, True]
for var in list:
    print(var)
    print("----")
print("out of for loop")
print("continuing execution")

# Another example by manually updating a variable in the loop

def hasOddNumber(list):
    ''' Returns True if the list has an odd number.
        Returns False otherwise.'''
    for x in list:
        if x % 2 != 0: # can also use if x % 2 == 1:
            return True
        # else:
        #   return False
        # ERROR, will only check the first element since True or False is
        # immediately returned
    return False # Will return False after every element in the list is checked

numbers1 = [2,4,5,6,8]
numbers2 = [0,10,20,30]
numbers3 = []
print(hasOddNumber(numbers1))
print(hasOddNumber(numbers2))
print(hasOddNumber(numbers3))

assert hasOddNumber(numbers1) == True
assert hasOddNumber(numbers2) == False
assert hasOddNumber(numbers3) == False
"""
"""
Range
- range() is a function used for looping if we know the number of
iterations we want to make.
- range(x) returns a collection of numbers from 0 up to (but not
including) x.
- range(x,y) returns a collection of numbers starting at x up to
(but not including) y.
- Example: range(4) --> [0,1,2,3]

# Example using range()
for x in range(4):
    print("Hello!" * x)
    print("---")

# Example looping from numbers [2,3,4,5]
for x in range(2,6):
    print(x)
    print("---")

# Example using range with steps, [0,3,6,9]
for x in range(0,10,3):
    print(x)
    print("---")
"""
```
