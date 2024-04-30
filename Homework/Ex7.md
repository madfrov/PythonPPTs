# Exercise 7

#### Q1: Given a list, move all zeros to the end of the elements while maintaining the relative order of the non-zero elements. For example, input list: [0, 1, 0, 3, 12] the return data should be: [1, 3, 12, 0, 0]Complete the function below for the above intention.

#### def moveZeros(lst):



#### Q2: Complete the function below. Here are the input parameters: tup is a tuple of all strings. word and target are strings. If an element of the tub is same as word, replace it with target. Return the updated tuple. 

#### def replaceWord (tup, word, target) : 





#### Q3: Step1: Given two integers representing the rows and columns (m×n), input a 2d list of integers from your keyboard. Input can be read row by row or element by element. Step2: Then find the index positions of the maximum element and the minimum element, Step3: swap the positions for the maximum and the minimum. Step4: Print the result of the 2D list. You can assume every integer in the list is different. Requirement: swapping must be done within the original 2D list, which means the input 2D list will be changed after swapping



#### Q4: Write a function that includes all the students in our class as well as your name, the names are arranged in a list according to your class number, find out where your name is in the list

#### def findMyself(class,name):



#### Q5: Given an array of integers nums, find one of the peak elements and return its index. A peak element is an element whose value is strictly greater than the values of its left and right neighbors. There may be more than one peak in the array; simply return the index of any one peak.
for example I have a list [0,3,5,2,1] the peak number should be 5

#### Q6: Please find the position of the 1st occurrence of the value x in an ordered non-decreasing array (with equal values in the array), using bisection search, and output -1 if x does not exist. Please note: This question asks for q x's and the position of the first occurrence of each x in the array. For example, if there are 6 numbers, which are: 1 2 2 2 2 3 3, then if you ask for 3 numbers: 3 2 5, the position of the first occurrence in the array, the answer is: 5 2 -1

#### Q7:You are given two arrays, arr1 and arr2, where the elements in arr2 are distinct and every element in arr2 appears in arr1.Sort the elements in arr1 so that the relative order of the items in arr1 is the same as the relative order in arr2. Elements that do not appear in arr2 are placed at the end of arr1 in ascending order.
Remember return should be arr1 we can not draw a new list
Example 1:
Input: arr1 = [5,6,4,4,3,3,2,2,1,1], arr2 = [1,2,3,4] Output: [1,1,2,2,3,3,4,4,5,6] Can you do it with selection sort?

#### Q8：Given an array, the numbers in the array are sorted in ascending order based on the largest factor of the numbers in the array (excluding the numbers themselves) or the numbers themselves if they are prime. If the largest factors of the numbers are equal, the numbers themselves are sorted in comparative order according to their size.（selection sort）

Example:
Input: [3,15,5,21,25,7]
Output: [3,5,15,25,7,21]

#### Q9: Using Recursion to write the selection sort

####  Q10：Find the kth smallest integer in a list

#### Given a list of integers, write an algorithm to find the kth smallest integer in the list.Using Selection or Insertion sort

Input: a list of integers and the kth smallest integer to be found.
Output: kth smallest integer in the list.
Example:
Input: [5, 5，6，7，1，1，2，2, 9, 1, 7], k = 3
Output: The 3rd smallest integer is 5.
