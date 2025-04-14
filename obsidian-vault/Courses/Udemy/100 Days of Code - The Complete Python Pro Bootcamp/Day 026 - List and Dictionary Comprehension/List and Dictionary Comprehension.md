# List and Dictionary Comprehension

## List Comprehension

List Comprehension is unique to Python.

Creating List Comprehension -
```python
new_list = [new_item for item in list]
```

Creating Conditional List Comprehension
```python
new_list = [new_item for item in list if test]
```

## Dictionary Comprehension

To create a new dictionary using Dictionary Comprehension -
```python
new_dict = {new_key:new_value for item in list}
```

To create a new dictionary using (key, value) from another dictionary -
```python
new_dict = {new_key:new_value for (key,value) in dict.items()}
```

Furthermore, you can even add a test -
```python
new_dict = {new_key:new_value for (key,value) in old_dict.items() if test}
```