

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

