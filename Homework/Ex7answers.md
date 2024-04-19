Q1Answer:

```
def move_zeros_to_end(lst):
    nonzero_pos = 0
    for num in lst:
        if num != 0:
            # Move non-zero elements to the correct position
            lst[nonzero_pos] = num
            nonzero_pos += 1
    # Fill the remaining positions with zeros
    while nonzero_pos < len(lst):
        lst[nonzero_pos] = 0
        nonzero_pos += 1
    return lst
input_list = [0, 1, 0, 3, 12]
result = move_zeros_to_end(input_list)
print(result)
```

Q2 Answer:

```
def replaceWord(tup, word, target):
    tup=list(tup)
    for i in range(len(tup)):
         if tup[i]==word:
                tup[i]=target
    return tuple(tup)
tup = ('apple', 'banana', 'apple', 'cherry')
word = 'apple'
target = 'orange'
updated_tup = replaceWord(tup, word, target)
print(updated_tup)
```

Q3 Answer:

```
# Step 1: Input a 2D list of integers
m = int(input("Enter the number of rows: "))
n = int(input("Enter the number of columns: "))

matrix = []
for i in range(m):
    matrix.append(list(map(int, input().split())))

def swap_max_min(matrix):
    # Step 2: Find the index positions of the maximum and minimum elements
    max_value = matrix[0][0] ##记住用矩阵第一个数作为最大最小值
    min_value = matrix[0][0]
    max_index = (0,0)
    min_index = (0,0)

    for i in range(m):
        for j in range(n):
            if matrix[i][j] > max_value:
                max_value = matrix[i][j]
                max_index = (i, j)
            if matrix[i][j] < min_value:
                min_value = matrix[i][j]
                min_index = (i, j)

    # Step 3: Swap the positions of the maximum and minimum elements
    matrix[max_index[0]][max_index[1]], matrix[min_index[0]][min_index[1]] = matrix[min_index[0]][min_index[1]], matrix[max_index[0]][max_index[1]]

    return matrix

# Call the function to perform the required operations
swap_max_min(matrix)
```

Q4 Answer

```
def findMyself(students, name):
    for i in range(len(students)):
        if students[i] == name:
            return i + 1
    return -1

com3 = ["arraon", "andy", "sally","helen","david","james","ryan an","ryan wu"]
target = "arraon"
result = findMyself(com3, target)
if result == -1:
    print("We don't have this guy.")
else:
    print("The target is in number", result, "in our class.")
```

Q5 Answer

```
def find_peak(arr):
    left=0
    right=len(arr)-1
    while left<=right:
        mid=(left+right)//2
        if arr[mid]>arr[mid+1] and arr[mid]>arr[mid-1]:
            return mid
        elif arr[mid]<arr[mid+1]:
            left=mid+1
        elif arr[mid]>arr[mid+1]:
            right=mid-1
    return -1
arr=[2,3,5,8,4,3]
print(find_peak(arr))
```

Q6 Answer

```
def find_first(arr,target):
    left=0
    right=len(arr)-1
    position=-1
    while left<=right:
        mid=(left+right)//2
        if target==arr[mid]:
            position=mid
            right=mid-1
        elif target<arr[mid]:
            right=mid-1
        else:
            left=mid+1
    return position
arr=[1,1,2,2,2,3,3]
target=[3,1,2,5]
print([find_first(arr,x)for x in target])
```

Q7

```
def relativeSortArray(arr1, arr2):
    for i in range(len(arr1)):
        min_index = i
        for j in range(i+1, len(arr1)):
            # 在arr2中找到arr1[j]的索引，如果arr1[j]不在arr2中，则返回len(arr2)
            index_j = arr2.index(arr1[j]) if arr1[j] in arr2 else len(arr2)
            # 在arr2中找到arr1[min_index]的索引，如果arr1[min_index]不在arr2中，则返回len(arr2)
            index_min = arr2.index(arr1[min_index]) if arr1[min_index] in arr2 else len(arr2)
            if index_j < index_min:
                min_index = j
        arr1[i], arr1[min_index] = arr1[min_index], arr1[i]
    return arr1
arr1 = [3,4,2,5,4,4,6]
arr2 = [6,3,4,2]
result = relativeSortArray(arr1, arr2)
print(result)
```
