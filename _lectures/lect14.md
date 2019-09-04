---
num: Lecture 14
lecture_date: 2019-09-04
desc: "More on Sets and Dictionaries"
ready: false
pdfurl:
---

```python
# CS 8, 9-4-19

# Example - Performance searching through lists vs dictionaries
# wordlist.txt (a list of words, one per line)
# PeterPan.txt (Peter Pan novel in a .txt file)

# Gutenberg.org - classic books in text!
# https://www.gutenberg.org/browse/scores/top

'''
DICT = {}
infile = open("wordlist.txt", 'r')
for x in infile:
    DICT[x.strip()] = 0 # Creates an entry in DICT with key x.strip() and value
                        # 0
print(len(DICT))
infile.close()

WORDLIST = []
for y in DICT:
    WORDLIST.append(y)
print(len(WORDLIST))

from time import perf_counter # Gives us a "timestamp" (fractional seconds)
                              # when we call this function

# Algorithm1 - Dictionaries
infile = open("PeterPan.txt", 'r')
largeText = infile.read()
infile.close()

words = largeText.split()
counter = 0
start = perf_counter()
for x in words:
    x = x.strip("\"\'()[]{},.?<>:;-").lower()
    if x in DICT: # Searching through the DICT
        counter += 1
end = perf_counter()
print(counter)
print("Time elapsed with DICT (in seconds):", end - start) # 0.02 seconds

# Algorithm 2 - Lists
infile = open("PeterPan.txt", 'r')
largeText = infile.read()
infile.close()
counter = 0
words = largeText.split()
start = perf_counter()
for x in words:
    x = x.strip("\"\'()[]{},.?<>:;-").lower()
    if x in WORDLIST:
        counter += 1
end = perf_counter()
print(counter)
print("Time elapsed with WORDLIST (in seconds):", end - start)
'''

# Dictionaries within Dictionaries!
# We want to keep track of all students who are enrolled in specific courses
# Schedule is a Dictionary with the class name as the key and another dictionary
# containing studentIDs mapping to Student namedtuples as the value.

from collections import namedtuple

Student = namedtuple('Student', 'name id')
s1 = Student("Richert", 12345678)
s2 = Student("John Doe", 87654321)
s3 = Student("Jane Doe", 55555555)
s4 = Student("Mr. E", 11111111)
s5 = Student("Chris Gaucho", 22222222)

# schedule is mapped by course keys to a dict of students
# inner-dict has student IDs mapping to student namedtuples

schedule = {'CS8':{}, 'CS16':{}, 'CS24':{}}

def print_schedule():
    ''' Iterate through the schedule and print out courses / students
        in a nice formatted way '''
    # 1st variable is key, 2nd variable is the value for the schedule dict.
    for course, students in schedule.items():
        print("{:6s}:\n\t".format(course), end="")
        for studentId, student in students.items():
            print("ID: {:8d}, Name: {}\n\t".format(studentId, student.name),end="")
        print()

def add_student(course, student):
    ''' Adds a student to the appropriate class in schedule '''
    enrolled_students = schedule.get(course)

    if enrolled_students == None:
        print("Course does not exist")
        return

    enrolled_students[student.id] = student
    return

'''
# Sanity checks
add_student('CS8', s2)
add_student('CS8', s1)
add_student('CS16', s3)
print_schedule()
'''

def add_course(course):
    ''' Adding a course to the schedule '''
    if schedule.get(course) == None:
        schedule[course] = {}
    else:
        print("course already exists")
        return

def remove_course(course):
    ''' Remove a course from the schedule '''
    if schedule.get(course) != None:
        schedule.pop(course)
    else:
        print(course, "does not exist")

def remove_student(course, student):
    ''' Removes a student namedtuple from the course '''
    enrolled_students = schedule.get(course)

    if enrolled_students == None:
        print(course, "does not exist")
        return

    if enrolled_students.get(student.id) != None:
        enrolled_students.pop(student.id)
    else:
        print(student.name, "is not enrolled in", course)

print_schedule()
print('*' * 20)
add_student("CS8", s1)
add_student("CS8", s2)
add_student("CS16", s3)
add_student("CS24", s4)
print_schedule()
print('*' * 20)
add_course('CS32')
add_student("CS32", s5)
print_schedule()
print('*' * 20)
remove_course('CS8')
print_schedule()
print('*' * 20)
remove_student("CS16", s3)
print_schedule()
```
