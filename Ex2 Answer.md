1. Enter from the keyboard a list of positive integers ending in -1. Calculate the sum of the odd and even numbers in the list separately.
2. 10 students are known to have grades 68,75,32,99,78,45,88,72,83,78, please store the grades in a list, please count them and output the number of people with 4 grades of excellent (100-90), good (89-80), medium (79-60), poor (59-0)
3. Use the while loop to create a list of 10 odd numbers, if the input is not an odd number to give a message and can continue to enter, and then calculate the sum and average of the list
4. Input 5 integers into list list1, output the subscripts and values, then form a new list list2 from the elements of list list1 that are greater than the average value, output the average value and list list2. solve the problem using the list derivatives
5. Given the list [1, 9, 8, 7, 6, 5, 13, 3, 2, 1], delete all odd numbers in it before outputting it. Solve the problem using list derivatives.

 ```
 1:
 
 n = int(input("pls input a integer："))
 
 list3 = []
 
 while n != -1:
 
   list3.append(n)
 
   n = int(input("pls input a integer："))
 
 else:
 
   print("end of the input")
 
 print(list3)
 
 list1 = []
 
 list2 = []
 
 for i in list3:
 
   if i % 2 != 0 :
 
 ​    list1.append(i)
 
   else:
 
 ​    list2.append(i)
 
 print("sum of the odd",list1,sum(list1))
 
 print("sum of the even",list2,sum(list2))
 
  
 
 2:
 
 grade = int(input("pls input the score："))
 
 list_grade = []
 
 while grade > 0:
 
   list_grade.append(grade)
 
   grade = int(input("pls input the score："))
 
 else:
 
   print("input ending, now we count the score")
 
 print("total result list is：",list_grade)
 
 list1=[]
 
 list2=[]
 
 list3=[]
 
 list4=[]
 
 for i in list_grade:
 
   if i >=90:
 
 ​    list1.append(i)
 
   elif i>=80:
 
 ​    list2.append(i)
 
   elif i>=60:
 
 ​    list3.append(i)
 
   else:
 
 ​    list4.append(i)
 
 print("Excellent：",len(list1),  "Good：",len(list2),"Medium：",len(list3),"Poor：",len(list4))
 
  
 
 3.
 
 n = int(input("pls input the odd number："))
 
 list1=[]
 
 while len(list1) < 10:
 
   if n %2 != 0:
 
 ​    list1.append(n)
 
   else:
 
 ​    print("input error pls input again")
 
   n = int(input("pls input the odd number："))
 
 print("The sum of the list is ：",sum(list1),"The average of the list is：",sum(list1)/len(list1),list1)
 
  
 
 4.
 
 print("pls input 5 integers")
 
 list1 = []
 
 for i in range(5):
 
   n = int(input("pls input the"+str(i+1)+":"))
 
   list1.append(n)
 
 avg = sum(list1)/len(list1)
 
 list2 = [i for i in list1 if i > avg]
 
 print("Avg：",avg,"list2 is：",list2)
 
 5.
 
 a = [1,9,8,7,6,5,13,3,2,1]
 
 b = [i for i in a if i %2 == 0]
 
 print(b)
 ```



