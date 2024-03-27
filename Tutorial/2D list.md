

# 2 Dimensional List

## 2.1 How to create a simple 2D list?

```
a=[]
b=[1,2,3]
for j in range(3):
        a.append(b)
print(a)
```

## 2.2 How to input the numbers of row?

```
n=input()
b=[1,2,3]
a=[]
for i in range(int(n)):
    a.append(b)
print(a)
```

## 2.3 How can I input the content of each row?

```
row=input("pls input the rows:")
a=[]
for i in range(int(row)):
    col=list(map(int,input().split()))
    a.append(col)
print(a)
```

```
row = int(input()) 
a = []
for i in range(row):
    a.append([int(j) for j in input().split()])
print(a)
```

## 2.4 How can I specified the rows and cols for a 0 martrix

```
input_rowsandcols = input()
dimensions=[int(x) for x in input_str.split(',')]
rowNum=dimensions[0]
colNum=dimensions[1]
multilist = []
for row in range(rowNum):
    sublist = []
    for col in range(colNum):
        sublist.append(0)
    multilist.append(sublist)
print(multilist)
```

Q1:

```
def find_max_element_index(matrix):
    rows = len(matrix)
    cols = len(matrix[0])
    max_value = float('-inf')  # 初始化最大值为负无穷
    max_index = (0, 0)  # 初始化最大值的索引为 (0, 0)

    for i in range(rows):
        for j in range(cols):
            if matrix[i][j] > max_value:
                max_value = matrix[i][j]
                max_index = (i, j)

    return max_index
matrix = [
    [3, 2, 5],
    [1, 6, 4],
    [7, 8, 9]
]

max_index = find_max_element_index(matrix)
print("最大元素的索引位置：", max_index)
```

Q1. Answer by G2-5 Matthew

```
dx = 0
dy = 0
mp = []
mx = 0
n = int(input())
m = int(input())
for i in range(n) :
    row = input().split(" ")
    for j in range(m) :
        row[j] = int(row[j])
        
    mp.append(row)
for i in range(n) :
    for j in range(m) :
        if mp[i][j] > mx :
            mx = mp[i][j]
            dx = i
            dy = j
print(dx, " ",dy)
    
```



Q2:

```
n = int(input("Enter an odd number: "))

# Create the empty two-dimensional array
arr = [["." for _ in range(n)] for _ in range(n)]

# Fill the middle row with "*"
mid_row = n // 2
arr[mid_row] = ["*" for _ in range(n)]

# Fill the middle column with "*"
mid_col = n // 2
for row in range(n):
    arr[row][mid_col] = "*"

# Fill the diagonals with "*"
for i in range(n):
    arr[i][i] = "*"
    arr[i][n - i - 1] = "*"

# Print the array
for row in arr:
    print(" ".join(row))
```

Q3:

```
n = int(input("Enter the number of rows (n): "))
m = int(input("Enter the number of columns (m): "))

# Create the empty two-dimensional array
arr = []

for i in range(n):
    row = []
    for j in range(m):
        if (i + j) % 2 == 0:
            row.append(".")
        else:
            row.append("*")
    arr.append(row)

# Print the array
for row in arr:
    print(" ".join(row))
```

Q4

```
n = int(input("Enter an integer (n): "))

# Create the empty two-dimensional array
arr = [[0] * n for _ in range(n)]

# Fill the diagonals with the corresponding values
for i in range(n):
    for j in range(n):
        arr[i][j] = abs(i - j)

# Print the array
for row in arr:
    for element in row:
        print(element, end=" ")
    print()
```

