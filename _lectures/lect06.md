---
num: Lecture 6
lecture_date: 2019-08-15
desc: "Nested Control Statements, Python Modules"
ready: false
pdfurl:
---

```python
# CS 8, 8-15-19

"""
# Another example by manually updating a variable in the loop
intList = [2,4,8,16,32,64,128,256,512,1024]
power = 1
for x in intList:
    print("2 **", power, "=", x)
    power = power + 1
"""

"""
# A larger example of Nested Control Structures
    - We can nest statements within each control structure (if / for)
    - This helps define "control" of statement execution in many different
    ways
    - Each block of statements within a control structure is defined by
    indentation
"""
"""
listOfNames = ["Bender", "Fry", "Leela", "Morbo"]
robots = ["Bender", "Calculon"]
humans = ["Hermes", "Fry", "Amy"]
aliens = ["Morbo", "Lurr"]

print("Checking Futurama characters with species")

for name in listOfNames:
    if name in robots:
        print(name + " is a robot")
    else:
        if name in humans:
            print(name + " is a human")
        else:
            if name in aliens:
                print(name + " is an alien")
            else:
                print("Not sure what " + name + " is.")

# Another way to write the same algorithm (but cleaner) ...
# is by using an "else if" statement (elif)

print("---")
for name in listOfNames:
    if name in robots:
        print(name + " is a robot")
    elif name in humans:
        print(name + " is a human")
    elif name in aliens:
        print(name + " is an alien")
    else:
        print("Not sure what " + name + " is.")
"""
"""
User-defined Modules
- Recall how we can import other people's code (including our own) in our
own programming (.py) files
- If you read a lot of python files, you may notice something like:

if __name__=="__main__":

- This line of code makes importing modules easier and doesn't include
code that may not want to be executed (or reused)
- Good for importing function definitions, but not anything like print
statements, testing functions, etc.

https://ucsb-cs8.github.io/ptopics/main_blocks

### Example temp.py ###
def hasOddNumber(list):
    ''' Returns True if list has an odd number.
        Returns False otherwise '''
    for x in list:
        if x % 2 != 0:
            return True
    return False

if __name__=="__main__": # anything below this does not get imported
    numbers1 = [2,4,5,6,8]
    numbers2 = [0,10,20,30]
    numbers3 = []

    print("lala")
    print(hasOddNumber(numbers1))
    print(hasOddNumber(numbers2))
    print(hasOddNumber(numbers3))
##############

### temp2.py ###
import temp # does not contain print statements from temp.py

# from temp import hasOddNumber
# (if we use this, then we can just call hasOddNumber
# (without temp.))

print("in temp2.py")
print(temp.hasOddNumber([1]))
"""
"""
Accumulator Pattern
- Have seen this already, but let's go into more detail
- Useful for "accumulating" something while traversing a collection
    - Example: Count the number of occurences, count the number of
    characters in list of strings, ...
"""

# Example of using an accumulator variable
# (numOfElements)

listOfStrings = ["this", "is", "a", "list", "of", "strings"]
numList = [8,2,6,4,0]

def computeLengthManually(someList):
    ''' Return the number of elements in someList '''
    numOfElements = 0
    for e in someList:
        numOfElements += 1 #numOfElements = numOfElements + 1

    return numOfElements

print(computeLengthManually(listOfStrings))
print(computeLengthManually(numList))

print(len(listOfStrings))
print(len(numList))

#Example - splitting strings

sentence = '''
This is a pretty long sentence, with many many words and letters, and
a bad example of what good sentence structure would look like, so don't
do this.
'''

print(sentence)
print(sentence.split())
# split() "splits" a string into a list of strings
# separated by ' ' or \n (whitespace)

print(sentence.split(","))
# split(",") "splits" the string into a list of strings
# separated by ','
# Notice that the commas are removed from the actual values
# This may be useful for comma separated value (csv) formats
```