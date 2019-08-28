---
num: Lecture 11
lecture_date: 2019-08-28
desc: "String Formatting, Random"
ready: false
pdfurl:
---

```python
# CS 8, 8-28-19

s = "CS 8: Intro to Programming"
print("Where does the first 'mm' occur in s?")
print(s.find('mm'))
print(s.find('8:'))
print(s.find('jfkldsjfls'))

text = """This
string
has
multiple
lines"""

'''
# .find method
first_newline = text.find("\n")
print("First newline position:", first_newline)
print("First line of text:", text[0:first_newline])
print("String after the first newline:", text[first_newline + 1:])

# .startswith method
print("Check if s starts with 'C':", s.startswith("C"))
print("Check if s starts with 'Computer':", s.startswith("Computer"))

# .endswith menthod
print("Check if s ends with 'P':", s.endswith("P"))
print("Check if s ends with 'ing':", s.endswith("ing"))

# .count method
print("Times 'm' is in s:", s.count("m"))
print("Times 'i' is in 'Mississippi':", "Mississippi".count("i"))
MS = "Mississippi"
print("Times 'ss' is in 'Mississippi':", MS.count("ss"))

# .replace method
print("Change all 'i' to '!' in", MS,":", MS.replace("i", "!"))
print("Change all ':' to '#' in s:", s.replace(":","#"))
print("Remove all 'i' in 'Mississippi':", MS.replace("i", ""))

# Strings are immutable (these methods won't change the string)
print(MS)
print(s)

# Change the value with reassignment
s = s.replace('m', 'M')
print(s)

# upper / lower case
# Useful for dictionary ordering
print(s.lower()) # convert s to all lower-case characters
print(s.upper()) # convert s to all upper-case characters
print(s)

#### Some more examples with String Formatting
price = 18.10
print("The price is ${}. That's cheap!".format(price))
print("The price is ${}. {}.".format(price, "WOW!"))

#print("{} {}".format(price)) #ERROR
print("{} {}".format(price, 1, 2)) # OK, ignores third value

# Format specification
# { : } Left side of colon says which .format parameter # to use
# We can say:

print("{3:} {2:} {1:} {0:}".format('a','b','c','d'))

# This prints out d,c,b,a
# The the right we specify a FIELD WIDTH (i.e., how many spaces
# on the page to devote to this value)

print("-->{}<--".format(price))
print("-->{:20}<--".format(price)) # right justified (int or float)
print("-->{:20}<--".format("18")) # left justified (string)
print("-->{:20}<--".format(True)) # right justified (True == 1)
# We can use '>' or '<' to justify left / right
print("-->{:<20}<--".format("18")) # left justified (string)
print("-->{:>20}<--".format("18")) # right justified (string)

# more examples
price = 12345.6
print("-->{}<--".format(price))
print("-->{:10.2f}<--".format(price)) # 12345.60
print("-->{:10.5f}<--".format(price)) # 12345.60000 (5 decimal spaces)
print("-->{:3.2f}<--".format(price)) # overflows allocated space

# can identify specific types that should be expected with 's' - string,
# 'd' - int, 'f' - float
name = "Chris Gaucho"
age = 21
print("Name is {:12s}; age is {:2d}; price is ${:0.2f}".format(name, age, price))

print("Name is {:12}; age is {:2}; price is ${:0.2}".format(name, age, price))
# still works without s or d (we use these to do safe type checking if we're
# expecting certain types. Removing 'f' will display value in scientific
# notation: 1.2e+04
'''

# Random
from random import randrange

print(randrange(10))

for x in range(100):
    #print(randrange(50))
    print(randrange(100, 200))
```