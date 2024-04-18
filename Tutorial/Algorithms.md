# Basic Algorithms

## Searching Algorithms

#### 1. Sequential Search

- Sequential search, also known as linear search, is a simple search algorithm that starts with the first element of a data structure and compares each element in turn until it finds the desired element, or traverses the entire data structure.

- The steps to implement a sequential search algorithm are as follows:

- Start the comparison from the first element of the data structure;
  If the desired element is found, the location of the element is returned;
  If the desired element is not found by traversing the entire data structure, the search fails.

### In the following example, find element 7 in the list [10,5,7,14,20].

First, element 7 is compared to the first element 10 in the list and found not to be.

![a](https://github.com/madfrov/PythonPPTs/blob/main/img/s1.png)

Element 7 continues to be compared with the second element 5 and is found to be also not our target

![b](https://github.com/madfrov/PythonPPTs/blob/main/img/s2.png)

Element 7 continues to move backward, comparing it to the third element in the list, and is found to be the element we are looking for.

![b](https://github.com/madfrov/PythonPPTs/blob/main/img/s3.png)

After finding, the logical position of the output element in the list is 3, because the array starts from 0, so the real position of 7 is 2, the logical position needs to be added 1.

From the above example, we can see that the time efficiency of the sequential search is O (n), that is, if in 10 million data lists, to find an element, his worst effect is to find all the elements once.

```
def sequential_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # find the target element and return the index 
    
    return -1  # no target element，return -1

# get the input list
arr = list(map(int, input("pls input the array").split()))

# get the target element
target = int(input("which number u want to search"))

# call the function
result = sequential_search(arr, target)

# output the result
if result != -1:
    print("target element is ", target, "index is", result)
else:
    print("target element is", target, "not exist")
```

#### The time complexity of the sequential search algorithm is O(n), where n is the length of the list. In the worst case, the entire list needs to be searched to determine the location of the target element.

# Here's a exercise, write a function that includes all the students in our class as well as your name, the names are arranged in a list according to your class number, find out where your name is in the list

```
def findMyself(students,name)

com3=
print()
```



```
import java.util.Scanner;

public class SequentialSearch {
    public static int sequentialSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i;  // Found the target element, return the index
            }
        }
        return -1;  // Target element not found, return -1
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get the input array
        System.out.print("Please input the array (separated by spaces): ");
        String[] inputArr = scanner.nextLine().split(" ");
        int[] arr = new int[inputArr.length];
        for (int i = 0; i < inputArr.length; i++) {
            arr[i] = Integer.parseInt(inputArr[i]);
        }

        // Get the target element
        System.out.print("Which number do you want to search? ");
        int target = scanner.nextInt();

        // Call the function
        int result = sequentialSearch(arr, target);

        // Output the result
        if (result != -1) {
            System.out.println("The target element " + target + " is found at index " + result);
        } else {
            System.out.println("The target element " + target + " does not exist");
        }
    }
}
```

```
def findMyself(students, name):
    for i in range(len(students)):
        if students[i] == name:
            return i + 1
    return -1

com3 = ["arraon", "andy", "sally"，"helen","david","james","ryan an","ryan wu"]
target = "arraon"
result = findMyself(com3, target)
if result == -1:
    print("We don't have this guy.")
else:
    print("The target is in number", result, "in our class.")
```

### What kinds of question are suitable for sequential search?

For sequential search, it is one of the simplest and least tricky ways to lookup. Sequential sorting is more suitable for unordered sets than ordered ones. Sequential sorting is suitable for small datasets, because for computers, the amount of computation in 1s is about 8 times 10, and due to various competitions, the time limit is usually within 1s, so for a one-dimensional sequential search, the amount of data is 8 times 10, that is, the amount of data is 100 million, and more than this amount of data can not be processed in a sequential search!

### 2. Binary Search

#### Binary Search is an efficient search algorithm that requires the list being searched to be ordered. The algorithm does this by comparing the target value to the middle element of the list, and depending on the result of the comparison, narrows the search range by half until either the target value is found or the search range is empty.

Example: Find element 27 in the list [10,25,26,27,55,87,123,150,160].

First, calculate the centroid based on the ordinal numbers of the ends, i.e., mid = (start + end) / 2 ; mid = (0+9) / 2 = 4, the element that is in the set and has ordinal number 4 is 55 (counting from 0), compare this with 27, which is 27 < 55, which means that 27 is only likely to be found to the left of 55 (since the set is ordered)

![b](https://github.com/madfrov/PythonPPTs/blob/main/img/b1.png)

According to mid = (start + end) / 2; at this point end becomes the original mid, mid = (0 + 4)/2 = 2. Taking out the element in the set with the ordinal number 2, i.e., 26, it is found that 27 > 26, which implies that the element could only be to the right of 26.

![b](https://github.com/madfrov/PythonPPTs/blob/main/img/b2.png)

start is updated to mid, at this time the start is 2, end is 4, according to mid = (start + end)/2; calculated that mid is 3, take out the collection of elements in the serial number of 3, is 27. is the element we want to find, exit the search.

![b](https://github.com/madfrov/PythonPPTs/blob/main/img/b3.png)

```
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1
    
    while left <= right:
        mid = (left + right) // 2
        
        if arr[mid] == target:
            return mid  # find the target element and return the index
        elif arr[mid] < target:
            left = mid + 1  # 目标元素在右侧，缩小搜索范围到右半部分
        else:
            right = mid - 1  # 目标元素在左侧，缩小搜索范围到左半部分
    
    return -1  # 没有找到目标元素，返回-1


arr = list(map(int, input().split()))
target = int(input())
result = binary_search(arr, target)

if result != -1:
    print("目标元素", target, "在列表中的索引位置为", result)
else:
    print("目标元素", target, "不存在于列表中")
```

```
import java.util.Scanner;

public class BinarySearch {
    public static int binarySearch(int[] arr, int target) {
        int low = 0;
        int high = arr.length - 1;
        
        while (low <= high) {
            int mid = (low + high) / 2;
            
            if (arr[mid] == target) {
                return mid;  // 找到目标元素，返回索引位置
            } else if (arr[mid] < target) {
                low = mid + 1;  // 目标元素在右侧，缩小搜索范围到右半部分
            } else {
                high = mid - 1;  // 目标元素在左侧，缩小搜索范围到左半部分
            }
        }
        
        return -1;  // 没有找到目标元素，返回 -1
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("请输入整数数组，以空格分隔: ");
        String[] inputArr = scanner.nextLine().split(" ");
        int[] arr = new int[inputArr.length];
        for (int i = 0; i < inputArr.length; i++) {
            arr[i] = Integer.parseInt(inputArr[i]);
        }

        System.out.print("请输入目标元素: ");
        int target = scanner.nextInt();

        int result = binarySearch(arr, target);

        if (result != -1) {
            System.out.println("目标元素 " + target + " 在数组中的索引位置为 " + result);
        } else {
            System.out.println("目标元素 " + target + " 不存在于数组中");
        }
    }
}
```



#### Note that the binary lookup algorithm requires that the list being searched must be ordered. If the list is unordered, you need to sort the list before applying the binary lookup algorithm.

#### The time complexity of binary search is O(log n), where n is the length of the list. Compared to sequential search, binary lookup is more efficient in large ordered lists.

### Q1:Suppose you are in a magical maze that is an ordered array of integers, but you don't know the exact contents of the array. Your task is to find the target value in the maze, and you can use binary search to find it as quickly as possible.Given an ordered integer array nums and a target value target, implement the function binary_search(nums, target) to return the index of the target value, or -1 if the target value does not exist in the array.

### Q2: Given an array of integers nums, find one of the peak elements and return its index. A peak element is an element whose value is strictly greater than the values of its left and right neighbors. There may be more than one peak in the array; simply return the index of any one peak. 

```
nums[i-1] < nums[i] > nums[i+1], the current position i is the value to look for
nums[i-1] < nums[i] < nums[i+1], the position is in the climbing zone, meaning there must be a maximum value to his right
nums[i-1] > nums[i] > nums[i+1], the position is in the downhill area, means there must be a maximum value in his left side

Since we can determine which of the two sides of the current element will have the maximum value, we can use dichotomization to solve for it:
We still take the middle value of mid, the two sides of the value of left and right

num[mid] is in a climbing state, update left.
num[mid] is going downhill, update right.
Until we reach the peak.
```



The time complexity of the binary search algorithm is calculated by the number of iterations. In each iteration, the search range is reduced by half until the target element is found or the search range is empty.

Suppose the length of the list is n. After the first iteration, the search range is reduced to n/2. After the second iteration, the search range is reduced again to n/4, and so on, with each iteration, the search range is reduced by half until the search range is empty or the target element is found.

Suppose it takes k iterations to find the target element or the search range is empty. Then the following equation holds:

```
n / (2^k) = 1
```

The value of k can be found by transforming the equation:

```
n = 2^k
```

Taking logarithms with base 2 on both sides of the above equation simultaneously gives:

```
log2(n) = log2(2^k)

k = log2(n)
```

Therefore, from the above calculations, it can be concluded that the number of iterations k is approximately equal to log2(n) in the bisection search algorithm.

Therefore, the time complexity of the bisection finding algorithm is O(log n), where n is the length of the list. This shows that the number of iterations required for bisection lookup grows logarithmically as the length of the list increases, making the algorithm highly efficient in large ordered lists.

```
def find_peak_element(nums):
    left = 0
    right = len(nums) - 1

    while left < right:
        mid = (left + right) // 2

        if nums[mid] > nums[mid + 1]:
            right = mid
        elif nums[mid] > nums[mid - 1]:
            left = mid
        else:
            # 当前元素无法确定峰值位置，需要进一步判断
            if nums[left] > nums[right]:
                right -= 1
            else:
                left += 1

    return left

# 示例数据
nums = [1, 2, 3, 3, 5, 6, 4]

# 执行查找峰值元素
peak_index = find_peak_element(nums)

# 输出结果
print("峰值元素的索引位置为:", peak_index)
print("峰值元素的值为:", nums[peak_index])
```

```
def findPeakElements(nums):
    peaks = []
    left = 0
    right = len(nums) - 1

    while left <= right:
        mid = left + (right - left) // 2

        if (mid == 0 or nums[mid] > nums[mid - 1]) and (mid == len(nums) - 1 or nums[mid] > nums[mid + 1]):
            # 当前位置是峰值元素
            peaks.append(mid)
            left = mid + 1
        elif mid < len(nums) - 1 and nums[mid] < nums[mid + 1]:
            # 峰值在右侧
            left = mid + 1
        else:
            # 峰值在左侧
            right = mid - 1

    return peaks

# 示例 2
nums2 = [1, 2, 1, 3, 1, 5, 4]
peaks2 = findPeakElements(nums2)
print("峰值元素的索引为:", peaks2)
```



### Summary

- From the above can be seen: halved search exit conditions are two, one is start than end, the second is to find the element you want to find.
- start and end of the update logic is, when now get the element a[mid] than to find the element temp hours, update start for mid, when now get the element a[mid] than temp, update end for mid;
- The time complexity of the half-fold lookup is O(log2n), compared to the sequential lookup, the speed of the half-fold lookup is greatly enhanced, but the half-fold lookup is only suitable for the ordered set.

Hw:

```
Please find the position of the 1st occurrence of the value x in an ordered non-decreasing array (with equal values in the array), using bisection search, and output -1 if x does not exist.

Please note: This question asks for q x's and the position of the first occurrence of each x in the array.

For example, if there are 6 numbers, which are: 1 2 2 2 2 3 3, then if you ask for 3 numbers: 3 2 5, the position of the first occurrence in the array, the answer is: 5 2 -1
```

```
def find_first_occurrence(nums, target):
    left = 0
    right = len(nums) - 1
    position = -1
    
    while left <= right:
        mid = (left + right) // 2
        
        if nums[mid] == target:
            position = mid
            right = mid - 1
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    
    return position

# Example data
nums = [1, 2, 2, 2, 2, 3, 3]
values = [3, 2, 5]

# Find the first occurrence of each value in the array
positions = [find_first_occurrence(nums, x) for x in values]

# Output results
for i, x in enumerate(values):
    print(f"The position of the first occurrence of {x} is: {positions[i]}")
```



## Sorting Algorithms

### 1. Selection Sort

#### Algorithm steps

- #### First find the smallest (large) element in the unsorted sequence and store it at the beginning of the sorted sequence.

- #### Then continue to find the smallest (large) element from the remaining unsorted elements and place it at the end of the sorted sequence.

- #### Repeat the second step until all elements are sorted.

![sss](https://github.com/madfrov/PythonPPTs/blob/main/img/Selection_sort.gif)

```\
def selection_sort(arr):
    n = len(arr)
    for i in range(n-1):
        min_idx = i
        # 找到未排序部分中的最小元素的索引
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

arr1=list(map(int,input().split()))
sorted=selection_sort(arr1)
print(sorted)
```

Using Recursion

```
def selection_sort(arr, n):
    if n == 1:
        return arr

    # 找到未排序部分的最大元素的索引
    max_index = 0
    for i in range(1, n):
        if arr[i] > arr[max_index]:
            max_index = i

    # 将最大元素交换到未排序部分的末尾
    arr[max_index], arr[n-1] = arr[n-1], arr[max_index]

    # 对剩余的 n-1 个元素进行递归排序
    selection_sort(arr, n-1)

    return arr


arr = list(map(int, input().split()))
n = len(arr)

sorted_arr = selection_sort(arr, n)
print("Sorted Array is:", sorted_arr)
```

- The time complexity of selection sort is O(n^2), where n is the length of the list. This is because in each iteration, selection sort needs to find the smallest element in the unsorted part and place it at the end of the sorted part. For each element of the list, a comparison operation is needed to find the smallest element, so n-1 comparisons are needed. After each comparison, a swap operation is also required to place the smallest element in the correct position.
- In selection sort, each iteration reduces the number of elements in the unsorted part by 1, so a total of n-1 iterations are required. In each iteration, n-1 comparisons and at most 1 swap operation are performed. Therefore, the total number of comparisons and swaps for selection sort is (n-1) + (n-2) + ... + 1 = n(n-1)/2, or O(n^2).
- Note that the time complexity of selection sort is always O(n^2), regardless of the initial order of the input list. Even if the list is already partially ordered, selection sort still requires the same number of compare and swap operations.
- The advantage of selection sort is that it is simple to implement and requires no extra space, but it has a high time complexity and is less efficient on large lists. For smaller lists or for educational purposes, selection sort is a simple and intuitive choice.

#### Question:You are given two arrays, arr1 and arr2, where the elements in arr2 are distinct and every element in arr2 appears in arr1.Sort the elements in arr1 so that the relative order of the items in arr1 is the same as the relative order in arr2. Elements that do not appear in arr2 are placed at the end of arr1 in ascending order.

#### Example 1:
Input: arr1 = [2,3,1,3,2,4,6,7,9,2,19], arr2 = [2,1,4,3,9,6]
Output: [2,2,2,1,4,3,3,9,6,7,19]    Can you do it with selection sort?



### 2. Insertion Sort

#### Algorithm steps

- #### Consider the first element of the first sequence to be sorted as an ordered sequence, and treat the second to the last element as an unsorted sequence.

- #### Scan the unsorted sequence from beginning to end, and insert each scanned element into an appropriate position in the ordered sequence. (If the element to be inserted is equal to an element in the ordered sequence, insert the element to be inserted after the equal element.)

![ii](https://github.com/madfrov/PythonPPTs/blob/main/img/Insertion_sort.gif)

```
def insertion_sort(arr):
    n = len(arr)
    for i in range(1, n):
        key = arr[i]  # 选择当前要插入的元素
        j = i - 1  # 从当前元素的前一个位置开始向前比较
        while j >= 0 and arr[j] > key:
            arr[j+1] = arr[j]  # 如果前一个元素大于当前元素，将前一个元素后移一位
            j -= 1  # 继续向前比较
        arr[j+1] = key  # 将当前元素插入到正确的位置
    return arr

arr = list(map(int, input().split()))
n = len(arr)

sorted_arr = insertion_sort(arr)
print("Sorted Array:", sorted_arr)
```

```
def insertion_sort_recursive(arr, n):
    # 基本情况：如果只有一个元素，无需排序
    if n <= 1:
        return

    # 对前 n-1 个元素进行排序
    insertion_sort_recursive(arr, n-1)

    # 将第 n 个元素插入到已排序的部分
    key = arr[n-1]
    j = n - 2
    while j >= 0 and arr[j] > key:
        arr[j+1] = arr[j]
        j -= 1
    arr[j+1] = key

# 获取输入的列表
arr = list(map(int, input().split()))

# 对列表进行插入排序
insertion_sort_recursive(arr, len(arr))

# 打印排序后的结果
print(arr)
```

- Insertion Sort has a time complexity of O(n^2), where n is the length of the list. In the worst case, i.e., when the list is sorted in reverse order, insertion sort requires a large number of compare and move operations.

- In insertion sort, initially the first element of the list is considered as the sorted part. Then, the iteration starts with the second element and inserts it into the correct position of the sorted part. For each element to be inserted, it is necessary to compare it with the elements of the sorted section and perform the corresponding move operation to free up the correct position for inserting that element.

- In the worst case, for the ith element to be inserted, it needs to be compared with i-1 elements of the sorted section and i-1 move operations may be required. Thus, in the worst case, the total number of comparisons and moves for insertion sort is 1 + 2 + 3 + ... + (n-1) = n(n-1)/2, which is O(n^2).

- Note that the time complexity of insertion sort is O(n) in the best case, i.e., when the list is already ordered, only n-1 comparisons need to be performed without any moves.

- The advantage of Insertion Sort is that it has better performance for small or largely ordered lists. It is simple to implement and does not require additional space in case of in-place sorting.

- Overall, insertion sort is a simple but high time complexity sorting algorithm. It can be a good choice when dealing with smaller lists or for certain situations.

### 3. Merge Sort

#### Algorithm steps

- #### Request space so that its size is the sum of the two already sorted sequences and this space is used to store the merged sequences;

- #### Set two pointers with initial positions at the start of each of the two already sorted sequences;

- #### Compare the elements pointed to by the two pointers, select the relatively small element to be placed in the merge space, and move the pointers to the next position;

- #### Repeat step 3 until one pointer reaches the end of the sequence;

![](C:\Users\89157\Desktop\merge_sorted.gif)

```
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    
    # 将列表分成两个子列表
    mid = len(arr) // 2
    left = arr[:mid]
    right = arr[mid:]
    
    # 递归对子列表进行排序
    left = merge_sort(left)
    right = merge_sort(right)
    
    # 合并两个有序子列表
    return merge(left, right)

def merge(left, right):
    result = []
    i = 0
    j = 0
    
    # 比较两个子列表的元素，将较小的元素依次加入结果列表
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    
    # 将剩余的元素加入结果列表
    while i < len(left):
        result.append(left[i])
        i += 1
    
    while j < len(right):
        result.append(right[j])
        j += 1
    
    return result

# 获取输入的列表
arr = list(map(int, input().split()))

# 对列表进行归并排序
sorted_arr = merge_sort(arr)

# 打印排序后的结果
print(sorted_arr)
```

- The time complexity of a subsumption sort is O(n log n), where n is the length of the list. The main operations of the subsumption sort are splitting and merging.

- In the splitting phase, the merge sort recursively splits the list into smaller sublists until each sublist contains only one element or is empty. The time complexity of this splitting process is O(log n) because the list is evenly split into smaller parts.

- In the merge phase, the subsumption sort combines the sorted sublists one by one until the entire list is sorted. In each merge operation, it is necessary to compare the elements of the two sublists and merge them in order into a new ordered list. The time complexity of this merge operation is O(n), where n is the total number of elements to be merged.

- Since the complexity of the split and merge operations are O(log n) and O(n), respectively, the overall time complexity of the subsumption sort is O(n log n).

- The advantages of subsumption sort are stability (the relative order of identical elements remains the same after sorting) and good performance, especially for large lists. Its disadvantage is that it requires extra space to store temporary sublists, hence the space complexity is O(n).

- Note that in practice, subsumption sort is usually used for external sorting or when stable sorting is required. For small lists, subsumption sort may not be the best choice due to its additional space requirement.
