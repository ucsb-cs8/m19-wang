---
num: Lecture 13
lecture_date: 2019-09-03
desc: "Sets and Dictionaries"
ready: false
pdfurl:
---

```python
# CS8, 9-3-19

'''
# Dictionaries
- Otherwise known as TABLES or MAPS
    - Works where a KEY maps to a VALUE
    - Use Dictionaries mainly for two reasons...
        - Gives us more precise indexing than lists
            - L['someString'] - allows us to index elements based on a
            value
        - Performance is MUCH better than searching through Lists
            - KEYS are HASHED to a specific index value
            - Provides DIRECT ACCESS to the value given some key
        - Details of hashing not discussed in this class...

- Syntax:
DICT = {<key1>:<value1>, <key2>:<value2>, ... , <keyN>:<valueN>}
'''

'''
D = {} # Empty dictionary. Notice the curly braces instead of []
print(D)
print(len(D))
'''

D = {'Jane':18, 'Jen':19, 'Joe':20, 'John':21}

'''
print(D)
print(len(D))
print("Jane's age is:", D['Jane'])

# Simple way to get key / value
for x in D:
    print(x) # Prints the key
    print(D[x]) # Prints the value
'''

'''
Restrictions on using Dictionaries
- Keys must be an immutable type (int, str, namedtuples, tuples, ... not
lists for example).
- Values can be any type (immutable or mutable)
- For our purposes, KEYS are UNIQUE. Don't define {'Joe':17, 'Joe':18}
    - Python is actually OK with duplicate keys in the definition, and it
    will keep the last key / value in the dictionary
'''

'''
Dictionary Methods
- D.pop(key) # remove and return the key / value from the dictionary
- D.update(D2) # Combine values in D and D2
- D.get(key) # returns item if it exists. If not, returns None or some
default value.
- Dictionary Views
    - D.keys() # dict_keys([List of keys])
    - D.values() # dict_values([List of values])
    - D.items() # dict_items([ List of key, value])
'''

'''
print(D)
value = D.pop('Joe')
print(value)
print(D)

D.update({'Jen':30, 'Jess':25, 'Jerry':27})
print(D) # Note that 'Jen' already exists in D, so D is updated with
         # 'Jen':30

# What happens if something is not in the dictionary and we try to access
# it.

# print(D["CS8"]) # ERROR
print(D.get("CS8")) # No error, returns None by default
print(D.get("CS8","not in dictionary"))
'''

print(D.keys())
print(D.values())

for item in D.keys():
    print(item)

keys = D.keys()

print(type(keys))
#print(keys[2])
print(list(keys)[2])

'''
Views are NOT LISTS!
- Some properties of views
    - They are like "windows" to the contents of the dictionary
    - They are self-updating and shows what the current state is
'''

'''
print(D.items())
x = D.items()
D.pop('Joe')
print(x) # Does not have 'Joe' even though x was assigned before pop()
'''

'''
# SETS: Like a mathematical set
- A collection of items with:
    - No duplicates
    - Order and position does not matter
- Useful for certain problems:
    - Keep track of unique items (student PERMs, Social Security Numbers,
    Driver's License)
- Under the hood, similar to the implementation of dictionaries
    - Uses hashing to map a set's value to a particular index
        - Instant lookup times (better than "walking down" the collection
        until you find the item)
'''


# Some syntax on how to initialize sets and dictionaries
s = {1,2,3,4}
d = {'a':1, 'b':2}
print(type(s))
print(type(d))
empty_dict = {}
empty_set = set()
print(type(empty_set))

# create a set from a list
s2 = set([2,4,6])
print(s2)
print(type(s2))

# Common set operators
# in / not in

print(3 in s2)
print("?" in s2)
print(5 not in s2) # True
print(len(s2))

# Combine values from two sets
s3 = set([4,5,6])
combined_set = s2 | s3
print(combined_set)

# Get the common elements from two sets
intersecting_set = s2 & s3
print(intersecting_set)

# Remove elements of a set from another set
difference_set = s2 - s3
print(difference_set)
difference_set = s3 - s2
print(difference_set)
    
# Get unique items in two sets
symmetric_difference_set = s2 ^ s3
print(symmetric_difference_set)
symmetric_difference_set = s3 ^ s2
print(symmetric_difference_set)

# Set comparisons:
print(s2 == s2)         # True
print(s2 == s3)         # False
print(s2 != s3)         # True
print({1,2} < {1,2,3})  # True, < indicates a "proper" subset
print({1,2,3} < {1,2,3}) # False
print({1,2} > {1})          # True
print({1,2,3} <= {1,2,3})   # True, <= indicates a subset
print({1,2,3} >= {2})       # True

# Set methods
s2.add(100)
print(s2)
s2.add(2)
print(s2)
s2.remove(4)
print(s2)
# s2.remove(101) ERROR, 101 does not exist
s2.discard(101) # No error, same as remove, but doesn't crash if element isn't there.
print(s2)
s2.clear()
print(s2)
```