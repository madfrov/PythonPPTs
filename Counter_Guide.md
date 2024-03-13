`Counter` is a class provided by the Python `collections` module. It is used for counting elements in an iterable and creating a dictionary-like object where the elements are stored as keys and their counts as values. Here are some common use cases and methods available in the `Counter` class:

1. Creating a Counter:
   ```python
   from collections import Counter
   
   # Creating a Counter from a list or string
   counter1 = Counter([1, 2, 3, 1, 2, 1])
   counter2 = Counter("hello")
   print(counter1)
   print(counter2)
   ```
   
2. Accessing Counts:
   ```python
   counter = Counter([1, 2, 3, 1, 2, 1])
   counter2=Counter([1,2,1,3,2,1,4,2,1])
   # Accessing the count of a specific element
   print(counter[1])  # Output: 3
   
   # Accessing the count of non-existing element returns 0
   print(counter[4])  # Output: 0
   
   print(counter2[1]) #Output:  4
   ```
   
3. Counting Elements:
   ```python
   counter = Counter([1, 2, 3, 1, 2, 1])
   
   # Counting elements in a list
   print(counter)  # Output: Counter({1: 3, 2: 2, 3: 1})
   
   # Counting elements in a string
   counter = Counter("hello")
   print(counter)  # Output: Counter({'l': 2, 'h': 1, 'e': 1, 'o': 1})
   ```

4. Common Operations:
   ```python
   counter1 = Counter([1, 2, 3, 1, 2, 1])
   counter2 = Counter([2, 3, 4])
   
   # Adding Counters
   counter_sum = counter1 + counter2
   print(counter_sum)  # Output: Counter({1: 3, 2: 3, 3: 2, 4: 1})
   
   # Subtracting Counters
   counter_diff = counter1 - counter2
   print(counter_diff)  # Output: Counter({1: 3})
   
   # Intersection of Counters
   counter_intersection = counter1 & counter2
   print(counter_intersection)  # Output: Counter({2: 1, 3: 1})
   ```

5. Other Methods:
   - `elements()`: Returns an iterator over the elements repeating each element as many times as its count.
   - `most_common([n])`: Returns a list of the `n` most common elements and their counts from the most common to the least.
   - `update()`: Updates the counter by adding elements from another iterable or from another counter.
   - `clear()`: Resets the counter, removing all elements and their counts.

```
from collections import Counter

# Example 1: Counting the frequency of elements in a list
a = [1, 1, 2, 3, 1, 2]
counter_obj = Counter(a)

print(counter_obj)
# Output: Counter({1: 3, 2: 2, 3: 1})

# Example 2: Getting the frequency of an element
print(counter_obj[1])
# Output: 3

# Example 3: Getting the most common elements and their frequencies
print(counter_obj.most_common(2))
# Output: [(1, 3), (2, 2)]

# Example 4: Updating the counts
counter_obj.update([1, 2, 3])  # Increase the frequencies of elements 1, 2, and 3
print(counter_obj)
# Output: Counter({1: 6, 2: 4, 3: 2})

# Example 5: Decreasing the counts
counter_obj.subtract([1, 2])  # Decrease the frequencies of elements 1 and 2
print(counter_obj)
# Output: Counter({1: 4, 2: 2, 3: 2})

# Example 6: Getting all elements
elements = list(counter_obj.elements())
print(elements)
# Output: [1, 1, 1, 1, 2, 2, 3, 3]

# Example 7: Clearing the counts
counter_obj.clear()
print(counter_obj)
# Output: Counter()
```



7.Counter wrapped in a function for easy calling

This is an example for last Exercise

```
from collections import Counter

a = [1, 1, 2, 3, 1, 2]
counter_list = Counter(a)

def counterl(x):
    return counter_list[x]

sorted_a = sorted(a, key=counterl, reverse=True)
a.sort(reverse=True, key=counterl)

print(sorted_a)
print(a)
```

```
output will be:
[1, 1, 1, 2, 2, 3]
[1, 1, 1, 2, 2, 3]
```