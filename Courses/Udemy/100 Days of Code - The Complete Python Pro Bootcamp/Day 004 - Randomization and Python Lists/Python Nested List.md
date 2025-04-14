# Python Nested Lists

In Python, a **nested list** is a list that appears as an element in another list. This allows you to create a two-dimensional structure, like a matrix, where each element of the outer list is a list itself. You can have multiple levels of nesting to create more complex data structures.

Here's an example of a simple nested list:

```python
nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

This creates a 3x3 matrix where each element is a list of three numbers.

You can access elements in a nested list using multiple indices. For example:

```python
print(nested_list[0])        # Output: [1, 2, 3]
print(nested_list[1][1])     # Output: 5
```

You can also iterate through a nested list using nested loops:

```python
for row in nested_list:
    for element in row:
        print(element, end=' ')
    print()
```

This would print each element of the nested list on a separate line.

You can modify elements in a nested list using indexing:

```python
nested_list[1][2] = 99
print(nested_list)
```

This would change the value at the second row, third column to 99.