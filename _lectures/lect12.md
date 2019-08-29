---
num: Lecture 12
lecture_date: 2019-08-29
desc: "More on Random, File I/O"
ready: false
pdfurl:
---

```python
# CS 8, 8-29-19

'''
from random import randrange

def rollDie():
    return randrange(1,7)

diceTally = [0,0,0,0,0,0,0]

for rolls in range(400):
    value = rollDie()
    diceTally[value] += 1

print(diceTally)

def printDistribution(distributionList):
    for x in range(1,7):
#        print(x, ": ", distributionList[x], sep='')
        print("{:2d}: ".format(x), '*' * distributionList[x])

printDistribution(diceTally)
'''
'''
FILES
- FILES are a valuable tool to help us solve many types of problems

FILES give us PERSISTENCE
- So far, we've been rerunning our programs
- Between each run, our data is cleared and everything has to be
reloaded again.
- With PERSISTENCE, our data can be "saved" between each program
execution

FILE BASICS
- We can read from files
- We can write to files
- We can store files in many different formats
    - Examples: .xls, .docx, .pdf, .jpg, ...
    - For this class, we'll only deal with "plain text" files (.txt)
    - These CHARACTERS are represented in something called ASCII
    (American Standard Code for Information Interchange).
    - This was a dominant / simple way to represent text where each
    character is 8 bits of data
        - This is only 256 different combinations of 0's and 1's, which
        doesn't serve all international characters
        - Modern standard is UTF-8 (most web browsers use this) in order
        to recognize all different characters in many languages
- File: A document
- Directory: A folder containing files or other folders
- File System: A collection of all the files and folders on the computer
- For this class, we'll deal with reading and writing files that are
in the same folder as our .py files (known as our "working directory")

File I/O
- I/O stands for input / output
- We read data from a file into our programs
- We write data from our program to a file.
- Steps to do this...
1. Open the file (creates a "connection" between your program and the
file).
    - Choose if the connection will be for reading, writing, or
    appending to a file
2. Read the data / write the data

3. Close the file (close the "connection"). This generally needs to be
done once per file.

# Common ways to read data from files
1. read() method: Reads the entire file into one string
    - Good for small data (large files may be too big to store into
    memory)
2. read(n): Read the next n characters from the file
    - Good for larger files since you only need to store n characters
    in memory at a time.
3. readline() method: Read everything from the current position to the
next \n character (or to the end of the file). If nothing is left
to read, this will return an empty string
4. readlines() method: Read all lines in the file and puts it in a list
5. for a_line in infile:
    a_line represents a line in the file.
'''

'''
# Example reading from 'example.txt'
infile = open('example.txt', 'r')
data = infile.read()
print(data)
infile.close()

# Example writing to 'output.txt'
outfile = open('output.txt', 'w')
outfile.write(data)
outfile.close()

# Create a list of lines in the file
infile = open('example.txt', 'r')
#data = infile.read()
#datalines = data.split('\n')
datalines = infile.readlines() #returns a list of strings (with \n)
print(datalines)
infile.close()
'''

'''
# Write "overwrites" the existing file
outfile = open('example.txt', 'w')
outfile.write("Something new!")
outfile.write("Another line")
outfile.close()
'''

'''
# Append to an existing file
outfile = open('example.txt', 'a')
outfile.write("\nSomething new!\n")
outfile.write("Another line")
outfile.close()
'''

'''
# read(n) example
infile = open('example.txt', 'r')
data = infile.read(3)
print(data)
data = infile.read(6)
print(data)
data = infile.read(1000)
print(data)
infile.close()
'''

'''
#readline() example
infile = open('example.txt', 'r')
line = infile.readline()
print(line)
line = infile.readline()
print(line)
line = infile.readline()
print(line)
infile.close()
'''

# Example copying / writing from a file to another file
infile = open('example.txt', 'r')
outfile = open('copy.txt', 'w')
for line in infile:
    outfile.write(line)
infile.close()
outfile.close()

```

