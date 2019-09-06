---
num: Lecture 15
lecture_date: 2019-09-05
desc: "Recursion"
ready: false
pdfurl:
---

```python
# CS8, 9-5-19

# Recursion
'''
- When a function contains a call to itself
- We're mostly familiar with writing code in an iterative fashion
(i.e. one statement after the other)
    - Several programming languages exist where it's purely based
    on recursion
    - Recursive solutions are useful when the result is dependent
    on the result of sub-parts of the problem

PROPERTIES OF RECURSION
- One or more base cases that provides the "stopping" (base case)
condition
- One or more recursive calls, where the parameters are "closer" to
the base case ("stopping condition")
'''

'''
Example: Factorials
N! = N * (N-1) * (N-2) * ... * 3 * 2 * 1
N! = N * (N-1)!
'''

def factorial(n):
    if n == 0:      # base case
        return 1

    return n * factorial(n-1)

assert factorial(0) == 1
assert factorial(1) == 1
assert factorial(2) == 2
assert factorial(3) == 6
assert factorial(4) == 24

# What happens if we forget the base case?
def factorial2(n):
#    print(n)
    return n * factorial2(n-1)

'''
Infinite recursion! No stopping condition means the functions never
returns the value
'''

# What happens if we never progress to the base case?
def factorial3(n):
    if n == 0:
        return 1
    print(n)
    return n * factorial3(n)

#factorial3(4) == 24

'''
Infinite recursion! the stopping condition is never reached!
'''

# Example: Check if a string is a palindrome
''' A palindrome is a string that is spelled the same forwards and
backwards
Examples of palindromes: racecar, hannah, civic, a, "" '''

def isPalindrome(s):
    ''' Returns true if s is a palindrome, returns false otherwise '''
    if len(s) == 0 or len(s) == 1:
        return True

    if s[0] != s[-1]:
        return False

    return isPalindrome(s[1:len(s)-1]) # s[1:-1] also works

assert isPalindrome("racecar") == True
assert isPalindrome("civic") == True
assert isPalindrome("CS8") == False

# Example: Filter through and return a collection
''' Assuming we have a list of numbers, return a list where all even
numbers are removed '''

def removeEvenNumbers(L):
    ''' For a list of numbers, L, returns a list where all even numbers
        are removed'''
    if len(L) == 0: # base case
        return []

    if L[0] % 2 == 0: # case where 1st element is even
        return removeEvenNumbers(L[1:])
    else:
        return [L[0]] + removeEvenNumbers(L[1:])

assert removeEvenNumbers([1,2,3,4]) == [1,3]
assert removeEvenNumbers([1,1,1,1]) == [1,1,1,1]
assert removeEvenNumbers([2,4,6]) == []

# Example: Fibonnaci
''' A fibonnaci sequence is the nth number in the sequence such that
it is the sum of the previous two numbers in the sequence '''
'''
f(n) = f(n-1) + f(n-2)
f(0) = 0, f(1) = 1
f(2) = f(1) + f(0) = 1
f(3) = f(2) + f(1) = 2
f(4) = f(3) + f(2) = 3
f(5) = f(4) + f(3) = 5
...
'''

def fibonnaci(n):
    if n == 0:
        return 0
    if n == 1:
        return 1

    return fibonnaci(n-1) + fibonnaci(n-2)

assert fibonnaci(0) == 0
assert fibonnaci(1) == 1
assert fibonnaci(2) == 1
assert fibonnaci(3) == 2
assert fibonnaci(4) == 3
assert fibonnaci(5) == 5
assert fibonnaci(6) == 8

# Example: Reverse a string using recursion

def reverseString(s):
    ''' We want to return a string that is in reverse order of s
        "CS8"->"8SC" '''

    if s == "":
        return ""

    return reverseString(s[1:]) + s[0]

assert reverseString("CS8") == "8SC"
assert reverseString("") == ""
assert reverseString("a") == "a"
assert reverseString("hooray!") == "!yarooh"
```