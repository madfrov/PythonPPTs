# Exercise 5

# List

#### Q0：Question: Write a program which can compute the factorial of a given numbers. 

####  Suppose the following input is supplied to the program: 8 Then, the output should be: 40320



#### Q1: Write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5, between 2000 and 3200 (both included). The numbers obtained should be printed in a comma-separated sequence on a single line.



#### Q2: Write a program that accepts a comma separated sequence of words as input and prints the words in a comma-separated sequence after sorting them alphabetically. 

#### Suppose the following input is supplied to the program: without,hello,bag,world 

#### Then, the output should be: bag,hello,without,world



#### Q3: Write a program that accepts sequence of lines as input and prints the lines after making all characters in the sentence capitalized.

#### Suppose the following input is supplied to the program: Hello world Practice makes perfect 

#### Then, the output should be: HELLO WORLD PRACTICE MAKES PERFECT



#### Q4: Write a program that calculates and prints the value according to the given 

#### formula: Q = Square root of [(2 * C * D)/H] 

#### Following are the fixed values of C and H: C is 50. H is 30. 

#### D is the variable whose values should be input to your program in a comma-separated sequence. 

#### Example Let us assume the following comma separated input sequence is given to 

#### the program: 100,150,180 

#### The output of the program should be: 18,22,24 (import math)



#### Q5: Write a program that accepts a sequence of whitespace separated words as input and prints the words after removing all duplicate words and sorting them alphanumerically. 

#### Suppose the following input is supplied to the program: 

#### hello world and practice makes perfect and hello world again

#### Then, the output should be: again and hello makes perfect practice world



#### Q6: Question: Write a program which accepts a sequence of comma separated 4 digit binary numbers as its input and then check whether they are divisible by 5 or not. The numbers that are divisible by 5 are to be printed in a comma separated sequence. 

#### Example: 0100,0011,1010,1001 Then the output should be: 1010 

# Tuple

#### Question7: Write a program which accepts a sequence of comma-separated numbers from console and generate a list and a tuple which contains every number. Suppose the following input is supplied to the program: 34,67,55,33,12,98 Then, the output should be: 

#### ['34', '67', '55', '33', '12', '98']

#### ('34', '67', '55', '33', '12', '98')



# 2D-Lists

#### Q8: Write a program which takes 2 digits, X,Y as input and generates a 2-dimensional array. The element value in the i-th row and j-th column of the array should be i*j. Note: i=0,1.., X-1; j=0,1,¡­Y-1. Example Suppose the following inputs are given to the program: 3,5 Then, the output of the program should be: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]



#### Q9: Create a function that takes a grid of # and -, where each hash (#) represents a mine and each dash (-) represents a mine-free spot.Return a grid, where each dash is replaced by a digit, indicating the number of mines immediately adjacent to the spot i.e. (horizontally, vertically, and diagonally).



# Dictionary

#### Q10: With a given integral number n, write a program to generate a dictionary that contains (i, i*i) such that is an integral number between 1 and n (both included). and then the program should print the dictionary. Suppose the following input is supplied to the program: 8 Then, the output should be: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64}



Answer1

```
l=[]
for i in range(2000, 3201):
    if (i%7==0) and (i%5!=0):
        l.append(str(i))

print(','.join(l))
```

```
items=[x for x in input().split(',')]
items.sort()
print(','.join(items))
```



```
values=input()
l=values.split(",")
t=tuple(l)
print(l)
print(t)
```

Answer2:

```
# Compulsory Task 1
# Create a file named minesweeper.py
# Create a function that takes a grid of # and -, where each hash (#) represents a
# mine and each dash (-) represents a mine-free spot.
# Return a grid, where each dash is replaced by a digit, indicating the number of
# mines immediately adjacent to the spot i.e. (horizontally, vertically, and diagonally).

# First define the minesweeper function
def minesweeper(grid):
    # Get the size of input grid
    rows = len(grid)
    cols = len(grid[0])
    # Use nested for loop to get the current position and value of the grid
    for r, row in enumerate(grid):
        for c, col in enumerate(row):
            if col == "-":
                count = 0
                # Let the variables i,j represent adjacent cells of current position r,c and iterate all to check if there is mine
                for i, j in [
                    (r-1, c-1), (r-1, c), (r-1, c+1),
                    (r, c-1),             (r, c+1),
                    (r+1, c-1), (r+1, c), (r+1, c+1),
                ]:
                    # If mines are found in adjacent cells count value will +1
                    if 0 <= i < rows and 0 <= j < cols and grid[i][j] == "#":
                        count += 1
                # Replace the cells which are not mine with the count value to give hints on the mine location
                grid[r][c] = str(count)


    return grid

# Create a grid and call out the minesweeper function to show the location of mines and all the hints
grid = [
["-", "-", "-", "#", "#"],
["-", "#", "-", "-", "-"],
["-", "-", "#", "-", "-"],
["-", "#", "#", "-", "-"],
["-", "-", "-", "-", "-"]
]

# Print out the input grid
print("This is the input grid.")
for input_row in grid:
    str_input__row = str(input_row)
    print(input_row)

# Print out the output of minesweeper
print("Here is the output of the minesweeper.")
result = minesweeper(grid)
for new_row in result:
    str_row = str(new_row)
    print(str_row)
```

```
input_str = input()
dimensions=[int(x) for x in input_str.split(',')]
rowNum=dimensions[0]
colNum=dimensions[1]
multilist = [[0 for col in range(colNum)] for row in range(rowNum)]

for row in range(rowNum):
    for col in range(colNum):
        multilist[row][col]= row*col

print(multilist)
```

```
value = []
items=[x for x in input().split(',')]
for p in items:
    intp = int(p, 2)
    if not intp%5:
        value.append(p)

print(','.join(value))
```

```
lines = []
while True:
    s = input()
    if s:
        lines.append(s.upper())
    else:
        break;

for sentence in lines:
    print(sentence)
```

```
import math
c=50
h=30
value = []
items=[x for x in input().split(',')]
for d in items:
    value.append(str(int(round(math.sqrt(2*c*float(d)/h)))))

print(','.join(value))
```

```
s = input()
words = [word for word in s.split(" ")]
print(" ".join(sorted(list(set(words)))))
```

```
def fact(x):
    if x == 0:
        return 1
    return x * fact(x - 1)

x=int(input())
print(fact(x))
```

```
n=int(input())
d=dict()
for i in range(1,n+1):
    d[i]=i*i

print(d)
```

```
def factorial(n):n=5   5* f(4)
    # 基本情况：阶乘的定义中规定 0! = 1
    if n == 0:
        return 1
    # 递归情况：计算 n!，其中 n 大于 0
    else:
        return n * factorial(n-1)
```

```
fruits = ['apple', 'banana', 'orange']

for index, fruit in enumerate(fruits):
    print(index, fruit)
```



