# Python Dictionaries

In Python, a dictionary is a built-in data type that allows you to store and retrieve key-value pairs. Dictionaries are unordered collections of items, and each item in a dictionary has a key-value pair. The key is used to index and uniquely identify the item, and the associated value is the data that the key references.

Here's a basic example of a dictionary:

```python
# Creating a dictionary
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}

# Accessing values using keys
print("Name:", my_dict['name'])
print("Age:", my_dict['age'])
print("City:", my_dict['city'])
```

Output:

```
Name: John
Age: 30
City: New York
```

Key characteristics of dictionaries:

1. **Unordered:** Items in a dictionary are not ordered. The order in which you add items to a dictionary is not guaranteed to be maintained.

2. **Mutable:** You can add, remove, or modify items in a dictionary.

3. **Keys:** Must be unique within a dictionary. They are usually strings or numbers, but they can be of any immutable data type.

4. **Values:** Can be of any data type, including other dictionaries.

### Basic Operations on Dictionaries:

#### Adding and Updating Items:

```python
# Adding a new item
my_dict['gender'] = 'Male'

# Updating an existing item
my_dict['age'] = 31

print(my_dict)
```

#### Removing Items:

```python
# Removing a specific item
del my_dict['city']

# Removing all items
my_dict.clear()

# Deleting the entire dictionary
del my_dict
```

#### Methods:

```python
# Get all keys
keys = my_dict.keys()

# Get all values
values = my_dict.values()

# Get key-value pairs as tuples
items = my_dict.items()
```

#### Checking Existence:

```python
# Check if a key exists
if 'name' in my_dict:
    print("Name exists in the dictionary")

# Safe way to get a value with a default
age = my_dict.get('age', 0)
```

Dictionaries are commonly used for tasks such as storing configurations, representing JSON-like structures, or as a general-purpose mapping data structure in Python.

### Can Keys in Python dictionary be integers?

Yes, keys in a Python dictionary can be integers. In fact, keys can be of any immutable data type, including integers, strings, and tuples. This flexibility is one of the strengths of Python dictionaries. Here's an example with integer keys:

```python
# Dictionary with integer keys
my_dict = {1: 'one', 2: 'two', 3: 'three'}

# Accessing values using integer keys
print(my_dict[1])  # Output: one
print(my_dict[2])  # Output: two
print(my_dict[3])  # Output: three
```

In this example, the keys are integers (`1`, `2`, `3`), and the corresponding values are strings (`'one'`, `'two'`, `'three'`).

You can use a variety of data types as dictionary keys, and you can even mix different types within the same dictionary. However, it's important to note that keys must be immutable. This means that you can use numbers, strings, tuples, and other immutable types as keys, but you cannot use mutable types like lists as keys.

Here's an example with mixed key types:

```python
mixed_dict = {1: 'one', 'two': 2, (3, 4): 'three-four'}

print(mixed_dict[1])         # Output: one
print(mixed_dict['two'])     # Output: 2
print(mixed_dict[(3, 4)])     # Output: three-four
```

So, to summarize, integer keys are entirely valid and commonly used in Python dictionaries.