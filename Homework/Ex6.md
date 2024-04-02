# 1. 1. Given a string "hello_world_school", how do you get a list ["hello", "world" , "shool"]?

# 1.2 Given a string str, output the mth character that occurs only n times, e.g., in the string gbgkkdehh, find the 2nd character that occurs only 1 time, output the result: d

# 1.3 Given a number a, determine whether a number is odd or even.

# 1.4 Take the string s = "ajldjlajfdljfddd", de-duplicate it, and sort it from smallest to largest, and output "adfjl".

# 1.5 If you have a list a = [1,3,5,7,11], how do you invert it to [11,7,5,3,1] and get the odd number [1,5,11]?

# 1.5 Read n rows of numbers from the console window each row has different size of number calculate the average of all numbers using two different methods.
1. nested loop by indexing
2. nested loop by element

# 1.6 Given two positive integers m and n, m lines of n elements, giving an m×n× matrix A, followed by two non-negative integers i and j less than n, swap columns i and j of A and print the result.

## Write a function `swap_columns(a, i, j)` and call it to exchange the columns.

```
str= "hello_world_school"
print(str.split("_"))
```

```
def find_mth_character(str, m, n):
    frequency = {}
    for char in str:
        if char in frequency:
            frequency[char] += 1
        else:
            frequency[char] = 1

    count = 0
    for char in str:
        if frequency[char] == n:
            count += 1
            if count == m:
                return char

    return None  # Return None if no such character is found

# Example usage
string = "gbgkkdehh"
mth_character = find_mth_character(string,2,1)
print(mth_character)  # Output: d
```

```
#By G2 Justin
from collections import Counter

str = "gbgkkdehh"

print("times = ?")
times = int(input())

print("position = ?")
position = int(input())

counter = Counter(str)
result = None
count = 0

for char in counter:
    if counter[char] == times:
        count += 1
        if count ==position:
            result = char
            break

print("Result:", result) 
```



```
s = "ajldjlajfdljfddd"

# Step 1: Remove duplicates by converting to set
s1 = set(s)
print(s1)

# Step 2: Convert set back to list for sorting
s2 = list(unique_chars)

# Step 3: Sort the list in ascending order
s2.sort()

# Step 4: Convert the sorted list back to a string
s3 = ''.join(sorted_chars)

print(s3) 
```

```
# 使用空格作为分隔符，将列表中的元素连接在一起
words = ['Hello', 'World', 'Python']
result = ' '.join(words)
print(result)

# 使用逗号作为分隔符，将元组中的元素连接在一起
fruits = ('apple', 'banana', 'orange')
result = ','.join(fruits)
print(result)
```

```
s = "ajldjlajfdljfddd"
a=[]
for i in s:
    if i not in a:
        a.append(i)
print(sorted(a))
s3 = ''.join(a)
print(s3)
```

```
a = [1,3,5,7,11]
print(sorted(a,reverse=True))
b=[]
for i in range(1,len(a)+1):
    if i%2!=0:
        b.append(a[i-1])
print(b)
```

```
1.5.1  by G1 Andy
a=int(input())
average_overall=0
for i in range(a):
    average=0
    list1=input().split(" ")
    for j in range(len(list1)):
        average+=int(list1[j])
    average/=len(list1)
    average_overall+=average
print(average_overall)
1.5.2
a=int(input())
average_overall=0
for i in range(a):
    average=0
    list1=input().split(" ")
    for j in list1:
        average+=int(j)
    average/=len(list1)
    average_overall+=average
print(average_overall)
```

```
row=int(input('pls input row'))
col=int(input('pls input col'))
list1=[]
sum=0
for i in range(row):
    a=input().split()
    a2=map(int,a)
    a3=list(a2)
    list1.append(a3)

for i in range(row):
    for j in range(col):
        sum+=list1[i][j]
print(sum)
```

```
row = int(input('Please input the number of rows: '))
col = int(input('Please input the number of columns: '))

list1 = []
total_sum = 0
count=0
for i in range(row):
    a = input().split()
    a2 = map(int, a)
    a3 = list(a2)
    list1.append(a3)

for sublist in list1:
    for element in sublist:
        total_sum += element
        count+=1
print(total_sum/count)
```

```
def swap_columns(a, i, j):
    for row in a:
        row[i], row[j] = row[j], row[i]
    return a

# 读取矩阵的行数和列数
m = int(input("输入行数 (m): "))
n = int(input("输入列数 (n): "))

# 读取矩阵元素
print(f"输入 {m}x{n} 矩阵 A:")
A = []
for _ in range(m):
    row = list(map(int, input().split()))
    A.append(row)

# 读取要交换的列索引
i = int(input("输入要交换的第一列索引 (i): "))
j = int(input("输入要交换的第二列索引 (j): "))

# 调用 swap_columns() 函数交换列
result = swap_columns(A, i, j)

# 打印结果矩阵
print("结果:")
for row in result:
    print(*row)
```

