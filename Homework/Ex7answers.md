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
#Selection sort
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
```
#Insertion Sort
def relativeSortArray(arr1, arr2):
    for i in range(1, len(arr1)):
        key = arr1[i]
        j = i - 1

        # 在arr2中找到key的索引，如果key不在arr2中，则返回len(arr2)
        index_key = arr2.index(key) if key in arr2 else len(arr2)

        while j >= 0 and (arr2.index(arr1[j]) if arr1[j] in arr2 else len(arr2)) > index_key:
            arr1[j+1] = arr1[j]
            j -= 1

        arr1[j+1] = key

    return arr1

arr1 = [3, 4, 2, 5, 4, 4, 6]
arr2 = [6, 3, 4, 2]
result = relativeSortArray(arr1, arr2)
print(result)
```
```
By G1-3 Andy Chen
import java.util.ArrayList;
import java.util.Arrays;
public class Main {
    public static void main(String[] args) {
//        ArrayList<Integer> arr1 = new ArrayList<Integer>();
//        for(int i = 0; i<10; i++){
//            arr1.add((int)(Math.random()*100));
//        }
//        System.out.println(arr1);
//        for(int i = 0; i<arr1.size()-1; i++){
//            int j=i;
//            while (j>0){
//                if (arr1.get(j-1)>arr1.get(j)){
//                    int a = arr1.get(j-1);
//                    int b = arr1.get(j);
//                    arr1.set(j,a);
//                    arr1.set(j-1,b);
//                    j--;
//                }
//                else {
//                    break;
//                }
//            }
//        }
//        System.out.println(arr1);


        ArrayList<Integer> arr1 = new ArrayList<Integer>(Arrays.asList(1,1,2,2,3,2));
        ArrayList<Integer> arr2 = new ArrayList<Integer>(Arrays.asList(3,2,1));
        int k = 0;
        for (int i = 0; i<arr2.size(); i++){
            for (int j = k; j<arr1.size(); j++){
                if (arr1.get(j)==arr2.get(i)){
                    int wala= arr1.get(j);
                    arr1.remove(j);
                    arr1.add(k,wala);
                    k++;
                }
            }
        }
        for (int i = 0; i<arr2.size()-k; i++){
            arr1.add(arr1.get(0));
            arr1.remove(0);
        }
        System.out.println(arr1);
    }
}
```
Q8

```
#by Selection sort
def maxFactorSort(nums):
    def get_max_factor(num):
        # 获取一个数的最大因数（非本身）
        if num < 2:
            return num
        for i in range(2, int(num/2) + 1):
            if num % i == 0:
                return num // i
        return num
    
    n = len(nums)
    
    # 选择排序
    for i in range(n):
        min_factor = nums[i]
        min_index = i
        
        # 在剩余的元素中找到最大因数最小的元素
        for j in range(i + 1, n):
            if get_max_factor(nums[j]) < get_max_factor(min_factor):
                min_factor = nums[j]
                min_index = j
            elif get_max_factor(nums[j]) == get_max_factor(min_factor):
                if nums[j] < min_factor:
                    min_factor = nums[j]
                    min_index = j
        
        # 交换当前位置和最大因数最小元素的位置
        nums[i], nums[min_index] = nums[min_index], nums[i]
    
    return nums


# 测试
nums = [5, 3, 15,21, 7]

# 根据最大因数进行选择排序（升序），当最大公约数相等时，根据本身大小排序
result = maxFactorSort(nums)
print(result)
```
```
#By Insertion Sort
def maxFactorSort(nums):
    def get_max_factor(num):
        # 获取一个数的最大因数（非本身）
        if num < 2:
            return num
        for i in range(2, int(num/2) + 1):
            if num % i == 0:
                return num // i
        return num
    
    n = len(nums)
    
    # 插入排序
    for i in range(1, n):
        key = nums[i]
        j = i - 1
        
        while j >= 0 and (get_max_factor(nums[j]) > get_max_factor(key) or (get_max_factor(nums[j]) == get_max_factor(key) and nums[j] > key)):
            nums[j+1] = nums[j]
            j -= 1
        
        nums[j+1] = key
    
    return nums


# 测试
nums = [5, 3,15, 21, 7]

# 根据最大因数进行插入排序（升序），当最大因数相等时，根据本身大小排序
result = maxFactorSort(nums)
print(result)
```
