---
num: Lecture 10
lecture_date: 2019-08-27
desc: "2D Lists"
ready: false
pdfurl:
---

```python
# CS8, 8-27-19

'''
Normal Lists: One number is used to index an item
    - Think of it as a straight line of elements indexed from 0 to N-1.
Table: Two numbers (two dimensions), represented by a row and column
    - This is done by having a "list in a list". The first index accesses
    the element in the list, the second index accesses the element that the
    first index returns.
'''

# 2D List
x = [[1,2,3],[4,5],[6]]
print(x[1]) #[4,5]
print(type(x[1])) # list
print(x[1][1]) # 5 

# N-dimensions
y = [[1,2], [[3,4]], [5]]
print(y[0]) # [1,2]
print(y[1]) # [[3,4]]
#print(y[1][1]) # ERROR
print(y[1][0]) # [3,4]
print(y[1][0][1]) # 4

# Conceptual example:
'''
- Computer screens can be represented in a grid of pixels
    - Basic color screens can have color values (red, green, blue) to make
    different shades of colors
    - Monochrome screens (black and white), which are also represented as
    a grid of black / white pixels
'''

def new_screen(rows, columns):
    ''' Create and return an empty screen: a list of rows, with each row
        being a list of pixels going across that row. Initially, all pixels
        will be 0 (black)
    '''
    result = []
    for r in range(rows):
        result.append([0] * columns)
    return result

screen = new_screen(10,5)
#print(screen)

def print_screen(grid):
    ''' Print out the "screen" in a grid-like format'''
    for row in range(len(grid)):
        # Print one row
        for col in range(len(grid[0])):
            if grid[row][col] == 0:
                pixel = '*'
            else:
                pixel = ' '
            print(pixel, sep='', end='')
        print()
    return

#print_screen(screen)
#screen[2][3] = 1
#print()
#print_screen(screen)

def set_row(grid, row, value):
    ''' Change the screen so that the specified row has the specified
        value all the way across.
    '''
    for col in range(len(grid[row])):
        grid[row][col] = value
    return

'''
print()
print_screen(screen)
print()
set_row(screen, 7, 1)
print_screen(screen)
print(screen)
print()
'''

def set_column(grid, col, value):
    ''' Change the screen in place so the specified column
        has the specified value all the way down '''
    for row in range(len(grid)):
        grid[row][col] = value
    return

'''
screen2 = new_screen(20,30)
#print_screen(screen2)
print()
set_column(screen2, 17, 1)
set_column(screen2, 27, 1)
set_row(screen2, 15, 1)
print_screen(screen2)
print(screen2)
'''

'''
Other possible functions...
- def set_pixel(screen, row, col, value)
    - same as directly manipulating the object:
    screen[row][col] = value
- def draw_rectangle(screen, UL_row, UL_col, width, height)
'''

# More on String Formatting Tools

# String functions
# We've seen several of these: .split(), .strip()
# We'll talk about more...

s = "CS 8: Intro to Programming"
print("Where does the first 'mm' occur in s?")
print(s.find('mm'))
print(s.find("8:"))
print(s.find("fjksldfhkljas"))
```