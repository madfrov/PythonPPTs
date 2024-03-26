# 1. For the following set, given a list, for each element in the list, remove it if it is in the set, and add it if it is not in the set.

```
s = set([‘Adam’, ‘Lisa’, ‘Paul’])
L = [‘Adam’, ‘Lisa’, ‘Bart’, ‘Paul’]
print(s)
```



# 2. Mutual Friends Your frds A, B, C, his frds C, B, D, find the common frds
```
your_f = {'A', 'B', 'C'}
his_f ={'B', 'C', 'D'}

```



# 3. WeChat group reminder: stranger is not WeChat friends with anyone else in the group

```
John = {'A', 'B', 'C'}
Timothy ={'B', 'C', 'D'}
Caveman ={'B', 'C', 'D'}
Stranger = {"U"}
```



# 4.First, read all students’ scores into a list as numbers. Second, delete those scores from the list if they are below 60 points. Print out the list.

```
Examples: scores = [45, 60, 89, 30, 12, 59, 99, 80, 71, 66] 

After Delete: scores = [60, 89, 99, 80, 71, 66]
```

```
scores = [] (1p)
score = int(input("enter a score: ")) (2p)
while score != -99: (3p)
 scores.append(score). (3p)
 score = int(input("enter a score: ")) (2p)
''' alternatively
str = input("enter all scores seperated by space: ") (2p)
scores = str.split() (3p)
for i in range (len(scores)): (3p)
 scores[i] = int(scores[i]) (3p)
'''
i = 0 (1p)
while i<len(scores): (3p)
 if scores[i]<60: (3p)
 scores.remove(scores[i]) (4p)
 i -= 1 (2p)
 i+=1 (2p)
print(scores) (1p)
```



# 5. Given a list of strings with distinct length, swap the position of the longest string with the shortest string inside the same list and print the final list .

```
Example of input: [‘a’,’andrea’,’an’,’and’, ‘adherence’]

Example of output: [‘adherence’’,’andrea’,’an’,’and’, ‘a’]
```

```
def swap_longest_shortest(lst):
 longest = lst[0] (2p)
 index_l = 0 (2p)
 shortest = lst[0] (2p)
 index_s = 0 (1p)
 for i in range(1,len(lst)): (3p)
 if len(lst[i]) > len(longest): (3p)
 longest = lst[i] (2p)
 index_l = i (2p)
 if len(lst[i]) < len(shortest): (2p)
 shortest = lst[i] (2p)
 index_s = i (1p)
 lst[index_s] = longest (2p)
 lst[index_l] = shortest (2p)
```

