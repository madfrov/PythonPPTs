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

print("times=?")
time = int(input())

print("sequence=?")
sequence = int(input())

sequence1 = 0
a = list("gbgkkdehh")
b = Counter(a)

result = None
for i in b:
    if b[i] == time:
        sequence1 += 1
        if sequence1 == sequence:
            result = i
            break

print("Result:", result)
print("Time:", time)
print("Sequence:", sequence1)   
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
n = int(input("Enter the number of rows: "))
total_sum = 0
total_count = 0

for _ in range(n):
    row = input("Enter the numbers in the row, separated by spaces: ").split()
    
    for j in range(len(row)):
        total_sum += int(row[j])
        total_count += 1

average = total_sum / total_count
print("Average:", average)
```

```
n = int(input("Enter the number of rows: "))
total_sum = 0
total_count = 0

for _ in range(n):
    row = input("Enter the numbers in the row, separated by spaces: ").split()
    
    for num in row:
        total_sum += int(num)
        total_count += 1

average = total_sum / total_count
print("Average:", average)
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

