# Collections

## Arrys



## Hashing

### set (Python's HashSet)
The Python set is an unordered collection of unique elements, similar to a HashSet in other languages. It is used to store unique elements and supports fast insertion, deletion, and search.

#### Features and Usage
- Unordered: Elements in a set are unordered and cannot be accessed by index.
- Unique elements: Elements must be unique; duplicates are ignored.
- Mutable: You can dynamically add or remove elements.
- Hash storage: Elements are hashed and stored in hash slots.
- Fast lookup: The average time complexity for insertion, deletion, and lookup is O(1)

### dict (Python's HashMap)
The Python dict is a key-value data structure, similar to a HashMap in other programming languages.It uses a hash table to store key-value pairs, allowing quick access to values using their keys.

#### Features and Usage
- Key-value structure: Each key maps to a specific value.
- Unique keys: Keys must be unique; duplicate keys will overwrite the existing value.
- Mutable: You can add, modify, or remove key-value pairs dynamically.
- Hash storage: Keys are hashed and stored in hash slots.
- Fast lookup: The average time complexity for lookup, insertion, and deletion is O(1)

```python
# Create a dictionary
my_dict = {
    'name': 'Alice',
    'age': 25,
    'city': 'New York'
}

# Access a value
print(my_dict['name'])  # Output: Alice

# Add or update a key-value pair
my_dict['age'] = 26  # Update age to 26
my_dict['profession'] = 'Engineer'  # Add a new key-value pair

# Delete a key-value pair
del my_dict['city']

# Check if a key exists
if 'age' in my_dict:
    print('Age is present')  # Output: Age is present

# Iterate over the dictionary
for key, value in my_dict.items():
    print(f"{key}: {value}")
```

#### dictionary-like
##### defaultdict()

```python
from collections import defaultdict

# Example list
words = ['apple', 'banana', 'apple', 'orange', 'banana', 'apple']

# Create a defaultdict with int as the factory function (default value 0)
word_count = defaultdict(int)

# Count the words
for word in words:
    word_count[word] += 1

print(word_count)
# Output: defaultdict(<class 'int'>, {'apple': 3, 'banana': 2, 'orange': 1})
```

```python
from collections import defaultdict

# Example list of tuples
pairs = [('fruit', 'apple'), ('fruit', 'banana'), ('vegetable', 'carrot'), ('fruit', 'orange')]

# Create a defaultdict with list as the factory function
grouped = defaultdict(list)

# Group items by their category
for category, item in pairs:
    grouped[category].append(item)

print(grouped)
# Output: defaultdict(<class 'list'>, {'fruit': ['apple', 'banana', 'orange'], 'vegetable': ['carrot']})
```

##### Counter()
```python
from collections import Counter

# 示例列表
nums = [1, 2, 2, 3, 3, 3, 4]

# 创建 Counter 对象
counter = Counter(nums)

# 输出：{3: 3, 2: 2, 1: 1, 4: 1}
print(counter)
```

- most_common([n])
```python
counter = Counter([1, 2, 2, 3, 3, 3, 4])

# 输出：[(3, 3), (2, 2), (1, 1), (4, 1)]
print(counter.most_common())

# 获取 2 个最常见的元素
# 输出：[(3, 3), (2, 2)]
print(counter.most_common(2))
```

- elements()
```python
counter = Counter(a=2, b=3)

# 输出：['a', 'a', 'b', 'b', 'b']
print(list(counter.elements()))
```