---
num: Lecture 1
lecture_date: 2019-08-06
desc: "Introduction"
ready: false
pdfurl:
---

```python
# CS 8, 8-6-19

# In python, we can separate English text ("comments") from
# source code by:
# - Preceding them with a pound, number, sharp, hashtag, ...
# - enclosing them in triple single quotes or triple double quotes

'''
This is still considered a comment since it's before and after
triple single quotes
'''

x = 7
print(x)

'''
- A traditional computer system contains:
    - PROCESSOR: Does computations
    - MEMORY / STORAGE: Contains information to act on or instructions to
    execute
    - Peripherals: Keyboard, mouse, monitor, speakers, printers
    - These are examples of HARDWARE
    - SOFTWARE is the instructions that the processor follows
        - Think of a chef following a recipe to make a dish
        - Chef follows instructions to do this.
        - These "instructions" is what a COMPUTER PROGRAM consists of
            - A COMPUTER PROGRAM is a set of instructions written in terms
            a computer can "understand" and follow
        - Computers are basically really complex calculators that can:
            - Perform arithmetic REALLY FAST
            - Copy data from one place to another
            - Store programs and execute them
            - Compare data and perform specific actions
            ...
        - An ALGORITHM is a step-by-step procedure to do something
            - A chef's recipe is an algorithm
            - CODE or SOURCE CODE refers to the text containing algorithms that
            a computer can understand
'''

''' Variables
    - Variables are useful for storing values of any type
    - There are many "types" in Python, programmers can also ceate custom types
    - Types are important depending on what you need to do with the data.
        - Some types support certain functionality while others don't.
    - Using certain types can affect the accuracy / performance of your program
    - Names of variables must...
        - Start with a letter or underscore (the former is more common)
        - Remaining letters in variable names can consist of letters, numbers, or
        underscores
        - Names are case-sensitive (name and NAME are considered two different variables).
'''
x = 10
print(x) #10

x = x * 10 
#(current value of x * 10) replaces existing value of x
# right hand side of assignment operator is evaluated. The value then
# replaces the existing value in the variable x

print(x) #100
```