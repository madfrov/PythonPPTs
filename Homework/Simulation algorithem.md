```
### Z convert
def convert(s, numRows):
    if numRows == 1:
        return s

    size = len(s)
    d = 2 * numRows - 2
    ret = ""

    # 第一行
    for i in range(0, size, d):
        ret += s[i]

    # (1, numRows - 1)行
    for k in range(1, numRows - 1):
        for i, j in zip(range(k, size, d), range(d - k, size, d)):
            if i < size:
                ret += s[i]
            if j < size:
                ret += s[j]

    # 第numRows - 1行
    for i in range(numRows - 1, size, d):
        ret += s[i]

    return ret

s="PAYPALISHIRING"
print(convert(s, 3))
```

### Timo attacks

```
def findPoisonedDuration(timeSeries, duration):
    ret = 0
    for i in range(len(timeSeries) - 1):
        tmp = timeSeries[i + 1] - timeSeries[i]
        if tmp >= duration:
            ret += duration
        else:
            ret += tmp
    ret += duration
    return ret

timeSeries=[1,4,8]
duration=3
print(findPoisonedDuration(timeSeries, duration))
```

### Replace all question marks

```
def modifyString(s):
    size = len(s)
    s = list(s)  # 将字符串转换为可变列表
    for i in range(size):
        if s[i] == '?':
            for ch in range(ord('a'), ord('z')+1):
                ch = chr(ch)
                if (i == 0 or s[i-1] != ch) and (i == size-1 or s[i+1] != ch):
                    s[i] = ch
                    break
    return ''.join(s)  # 将列表转换回字符串

s="abc?za"
print(modifyString(s))
```

