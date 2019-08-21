---
num: Lecture 7
lecture_date: 2019-08-20
desc: "Iterating through lists, Accumulator Pattern, Nested Loops, While Loops"
ready: false
pdfurl:
---

```python

# CS 8, 8-20-19

# Midterm will cover everything up to last Thursday's lecture (8/15)
# h06 (strings) and h08 topics will be on the midterm, h07 topics
# will be covered in the final.

sentence = """
This is a pretty long sentence, with many many words and letters, and
a bad example of what good sentence structure would look like, so
don't do this
"""

'''
# strip() string method
# Removes the whitespace at the beginning and end of strings

print(sentence.split())
x = "   abc   "
print("---" + x + "---")
print("---" + x.strip() + "---") # remove whitespaces at the end

y = "--,!'fj,ka--!,"
print(y.strip("-,!'")) # removes these characters from the beginning / end

def countLongWords(someString):
    """ Counts words longer than 5 characters and returns the count"""
    count = 0
    words = someString.split()
    for w in words:
        if len(w.strip(",.;!?")) > 5:
            print(w.strip(",.;!?")) # visual test
            count += 1
    return count

print(countLongWords(sentence))
'''

'''
# Nested-for loop example
# Count vowels in list of strings
listOfStrings = ["this", "is", "a", "list", "of", "strings"]

def countVowels(strList):
    """ Counts the number of vowels in a list containing strings.
        Returns the number of vowels."""
    numVowels = 0
    vowels = "aeiouAEIOU"
    for s in strList:           # s is an element in strList
        for c in s:             # c is a character in s
            if c in vowels:
                numVowels += 1
    return numVowels

print(countVowels(listOfStrings))
'''

'''
# While Loops
- Another looping construct we'll use is called a while loop
- Note: The number of times that goes through the loop is independent
on the number of elements in a collection

Syntax:

while BOOLEAN_EXPRESSION:
    STATEMENT(S)

- if BOOLEAN_EXPRESSION is True, perform statements in the body of the loop
- if BOOLEAN_EXPRESSION is False, skip the body of loop entirely and continue
execution
'''

'''
# Infinite Loop
while True:
    print("Weee!!!")
'''

'''
# Keyword break
# It's possible to change your mind in the middle of a loop and jump out of it
# using the "break" statement

# Example
x = 0
while True:
    x = x + 1
    print("Start of while body, x =", x)
    if x > 3:
        break
    print("End while body, x =", x)
print("outside while loop")
'''

'''
# Keyword continue
# It's possible to also check and see if you want to continue executing
# the loop body, or go back and evalute the boolean expression and start the
# statements over

x = 0
while True:
    x = x + 1
    print("Start of while body, x =", x)
    if x % 2 == 0: # x is even
        continue
    if x >= 5:
        break
    print("End of while body, x =", x)
print("Outside while loop")
'''

# Keyword pass

# Considered a "no-op" (no-operation). Doesn't do anything, but some functions /
# conditions require a statement for legal syntax

'''
def f():
    pass # remove this and we'll get a syntax error
'''
'''
# equivalent to
def f():
    return
'''
x = 6
if x > 5:
    pass
else:
    print("x <= 5")

# In general, pass statements aren't used.
# We can write our code to avoid pass statements.
```