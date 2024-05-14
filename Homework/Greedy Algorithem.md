# Greedy Algorithem

Dijkstra

```

def dijkstra(graph, start):
    # 初始化距离字典，用于记录起始顶点到其他顶点的最短距离
    distances = {vertex: float('inf') for vertex in graph}
    distances[start] = 0  # 起始顶点到自身的距离为0

    # 初始化已访问顶点集合
    visited = set()

    while len(visited) < len(graph):
        # 在未访问顶点中选择距离最小的顶点
        min_distance = float('inf')
        min_vertex = None
        for vertex in graph:
            if vertex not in visited and distances[vertex] < min_distance:
                min_distance = distances[vertex]
                min_vertex = vertex

        visited.add(min_vertex)  # 将最小距离顶点标记为已访问

        # 更新与最小距离顶点相邻顶点的最短距离
        for neighbor, weight in graph[min_vertex].items():
            if neighbor not in visited:
                new_distance = distances[min_vertex] + weight
                if new_distance < distances[neighbor]:
                    distances[neighbor] = new_distance

    return distances

# 图的邻接表表示
graph = {
    'A': {'B': 5, 'C': 2},
    'B': {'A': 5, 'C': 1, 'D': 3},
    'C': {'A': 2, 'B': 1, 'D': 6},
    'D': {'B': 3, 'C': 6}
}

start_vertex = 'A'
shortest_distances = dijkstra(graph, start_vertex)

# 打印起始顶点到其他顶点的最短距离
for vertex, distance in shortest_distances.items():
    print(f"从顶点 {start_vertex} 到顶点 {vertex} 的最短距离为: {distance}")
```

Balance String

```
def balancedStringSplit(s):
    count = 0  # 计数器，记录平衡字符串的数量
    balance = 0  # 平衡因子，记录'L'和'R'的差值

    for char in s:
        if char == 'L':
            balance += 1
        else:
            balance -= 1

        if balance == 0:
            count += 1

    return count

# 示例测试
s = "RLRRRRLLRL"
result = balancedStringSplit(s)
print(result)  # 输出: 4
```

Shopping

```
def minimum_coins(amount):
    coins = [50, 20, 15, 5, 1]  # 硬币面额从大到小排序
    num_coins = 0

    for coin in coins:
        num_coins += amount // coin  # 计算当前面额的硬币个数
        amount %= coin  # 更新剩余金额

    return num_coins

# 测试
total_amount = 47
min_coins = minimum_coins(total_amount)
print("最少需要的硬币数量：", min_coins)
```

Jump

```
def canJump(self, nums):
        n = len(nums)
        rightmost = 0
        for i in range(n):
            if i <= rightmost:
                rightmost = max(rightmost, i + nums[i])
                if rightmost >= n - 1:
                    return True
        return False

self=[2,3,4,1,2]
print(canJump(self, nums))
```

