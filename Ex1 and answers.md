\#1.**Title: FizzBuzz**Write a program that prints numbers from 1 to 100. But for multiples of 3, print "Fizz" instead of numbers, for multiples of 5, print "Buzz" instead of numbers, and for numbers that are multiples of both 3 and 5, print "FizzBuzz".

 

\#**2.Title: Prime Number Determination**

Write a program that takes a positive integer input from the user and determines if the number is prime (divisible only by 1 and itself). If it is prime, print "is prime", otherwise print "is not prime".

 

\#3.**Title: Fibonacci series**

\#Write a program that accepts a positive integer n as input from the user and prints the first n numbers of the Fibonacci series. The Fibonacci sequence is defined as follows: the first and second digits are 1, and each digit from the third onward is the sum of the first two digits.

 

\#4.**Topic: Multiplication Tables**

 Write a program that prints out the multiplication table using a nested `for` loop.

 

\#5.Monkey Eating Peach Problem: The monkey picked a number of peaches on the first day, ate half of them instantly, and was not addicted to them, and ate one more. The next morning he ate half of the remaining peaches, and ate one more. Every morning after that, he ate half and one of the remaining peaches from the previous day. On the 10th morning, when you wanted to eat another peach, you saw that there was only one peach left. Find the total number of peaches picked on the first day.

 

Answers：

1. ```python

  for i in range(1, 101):

​    if i % 3 == 0 and i % 5 == 0:

​      print("FizzBuzz")

​    elif i % 3 == 0:

​      print("Fizz")

​    elif i % 5 == 0:

​      print("Buzz")

​    else:

​      print(i)

  \```

2.

num = int(input("pls input a positive integer: "))

is_prime = True

 

if num < 2:

  is_prime = False

else:

  for i in range(2, int(num**0.5) + 1):

​    if num % i == 0:

​      is_prime = False

​      break

 

if is_prime:

  print(num, "it is prime")

else:

print(num, "it is not a prime")

 

3.

\``` python

num = int(input("Please enter a positive integer: "))

fibonacci = [1, 1]

 

for i in range(2, num):

  next_num = fibonacci[i - 1] + fibonacci[i - 2]

  fibonacci.append(next_num)

 

print("Fibonacci series before", num, "The first number is:", fibonacci)

\```

 

4.

\``` python

for i in range(1, 10):

  for j in range(1, 10):

​    print(i * j, end="\t")

  print()

\```

5.

\```python

n = 1	#第10天桃子的数量为1

for i in range(9,0,-1):	#for循环，倒序,i表示第几天

  n = (n+1) * 2		#第一循环i取9，n=(1+1)*2=4;第二次循环i取8，n=(4+1)*2=10;......

print(n)

\```

 